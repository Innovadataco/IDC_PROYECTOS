# INSTRUCCION-ODIN-002-CORRECCION.md
**Proyecto:** PROYECTO-005: Semáforo de Confianza (Protección Infantil)  
**Módulo:** 002 — Consulta Semáforo (Corrección Post-Validación)  
**Actividad:** ACT-002-CORRECCION — Corrección de Hallazgos  
**Auditoría base:** ACTA-VALIDACION-ODIN-002-v2.md  
**Asignado:** ODIN (CEO IA Dev)  
**Aprobador:** Jelkin Zair Carrillo Franco (CEO)  
**Fecha instrucción:** 2026-06-14 11:46 CST (Shanghai) / 10:46 (Bogotá)  
**Estado:** APROBADA ✅

---

## 1. CONTEXTO

**ACT-002 fue VALIDADO CON HALLAZGOS.**

22/22 tasks implementados. 2 hallazgos menores detectados por ZEUS.

Jelkin ordena: **ODIN corrige los 2 hallazgos antes de iniciar Módulo 003.**

**No hay merge a main hasta que los hallazgos estén corregidos y validados.**

---

## 2. HALLAZGOS A CORREGIR

### HALLAZGO 1: TI-002.3 — Nginx cache no configurado

**Severidad:** 🟡 MEDIA  
**Task:** TI-002.3 — Nginx cache de respuestas 200 (5 min)  
**Archivo:** `nginx/nginx.conf`  
**Commit original:** 28dc349 (mensaje dice cache, pero código no lo tiene)

**Problema:**
El commit dice "infra(nginx): TI-002.3 cache 5 min para respuestas 200 de /api/v1/validate/" pero el archivo `nginx/nginx.conf` NO tiene la configuración de `proxy_cache`.

**Código actual (incorrecto):**
```nginx
location /api/ {
    proxy_pass http://backend;
    proxy_set_header Host $host;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_set_header X-Forwarded-Proto $scheme;
}
```

**Código esperado (correcto):**
```nginx
# Cache zone para validaciones
proxy_cache_path /var/cache/nginx/validate levels=1:2 keys_zone=validate_cache:10m max_size=100m inactive=60m;

server {
    listen 80;
    server_name localhost;

    # Cache de 5 min para respuestas 200 de /api/v1/validate/
    location /api/v1/validate/ {
        proxy_pass http://backend;
        proxy_cache validate_cache;
        proxy_cache_valid 200 5m;
        proxy_cache_use_stale error timeout updating;
        proxy_cache_key "$scheme$request_method$host$request_uri";
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }

    location /api/ {
        proxy_pass http://backend;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }

    location / {
        proxy_pass http://frontend;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```

**Notas de implementación:**
- `proxy_cache_path` debe ir en el bloque `http` (arriba de `server`)
- `proxy_cache` debe ir en el bloque `location /api/v1/validate/` (no en `/api/` genérico)
- Solo cachear respuestas 200 (no errores 4xx/5xx)
- TTL: 5 minutos (300 segundos)
- Tamaño de cache: 10m (10 megabytes)

**Commit esperado:**
```
fix(infra): TI-002.3 agrega nginx cache para /api/v1/validate/

- Agrega proxy_cache_path en bloque http
- Agrega location /api/v1/validate/ con proxy_cache
- Cache de 5 min para respuestas 200
- Hallazgo de ACTA-VALIDACION-ODIN-002-v2.md corregido

Refs: TI-002.3, ACT-002-CORRECCION
```

---

### HALLAZGO 2: Tests — No ejecutados por limitación de entorno

**Severidad:** 🟡 MEDIA  
**Categoría:** CAT-06 — Control de calidad y tests  
**Nota:** Este hallazgo NO requiere corrección de código de ODIN. Es una mejora de proceso.

**Problema:** ZEUS no pudo ejecutar tests localmente porque no tiene Python. ODIN reportó 90% cobertura pero ZEUS no pudo confirmar.

**Solución (por ZEUS, no por ODIN):**
- Implementar GitHub Actions para ejecutar tests automáticamente en cada push a `feature/v2-fullstack`
- Esto permitirá a ZEUS verificar tests sin necesidad de entorno local

**ODIN debe hacer:**
1. Asegurar que tests pasan en su entorno local: `pytest --cov=app --cov-report=term-missing`
2. Confirmar cobertura ≥ 80%
3. Reportar resultado a ZEUS

**No requiere commit de código.** Solo reporte de ejecución.

---

## 3. REGLAS DE CORRECCIÓN

### R-001: 1 commit por hallazgo
Cada hallazgo debe corregirse en un commit individual.

### R-002: Mensaje de commit claro
Formato: `fix(<scope>): <task> — <descripción breve>`

### R-003: Push inmediato
Después de cada commit: `git push origin feature/v2-fullstack`

### R-004: No tocar IDC_PROYECTOS
ODIN solo trabaja en el repo `Desarrollos`. ZEUS maneja `IDC_PROYECTOS`.

### R-005: Timestamp obligatorio
ODIN registra fecha/hora de fin de corrección en `INSTRUCCION-ODIN-002-CORRECCION.md`.

### R-006: No declarar "completado"
ODIN declara "LISTO PARA VALIDACIÓN DE CORRECCIONES". ZEUS decide si VALIDA o RECHAZA.

---

## 4. DEFINICIÓN DE TERMINADO (DoD)

- [ ] Hallazgo 1 (TI-002.3) corregido con commit individual
- [ ] nginx.conf tiene `proxy_cache_path` y `location /api/v1/validate/` con cache
- [ ] Hallazgo 2 (Tests) confirmado por ODIN: tests pasan localmente
- [ ] ODIN reporta cobertura ≥ 80% (screenshot o texto)
- [ ] Push a `origin/feature/v2-fullstack` completado
- [ ] ODIN declara "LISTO PARA VALIDACIÓN DE CORRECCIONES" con timestamp

---

## 5. EJEMPLO DE FLUJO

```bash
# 1. Asegurarse de estar en rama correcta
git checkout feature/v2-fullstack

# 2. Corregir Hallazgo 1: TI-002.3
# Editar nginx/nginx.conf
# Agregar proxy_cache_path y location /api/v1/validate/
git add nginx/nginx.conf
git commit -m "fix(infra): TI-002.3 agrega nginx cache para /api/v1/validate/"

# 3. Verificar tests pasan
pytest --cov=app --cov-report=term-missing
# Capturar resultado (screenshot o copiar texto)

# 4. Push
git push origin feature/v2-fullstack

# 5. Registrar FIN con timestamp
```

---

## 6. CONSECUENCIAS

**Si ODIN corrige ambos hallazgos:**
→ ZEUS valida → ACTA-VALIDACION-ODIN-002-CORRECCION.md → Merge a main → Módulo 003

**Si ODIN no corrige o introduce nuevos errores:**
→ ZEUS rechaza → ACTA-CORRECCION-ODIN-002-CORRECCION.md → ODIN re-corrige

**Sin validación, no hay merge. Sin merge, no hay Módulo 003.**

---

## 7. FORMATO DE DECLARACIÓN DE FIN

Cuando ODIN termine, debe escribir EXACTAMENTE:

```
ACT-002-CORRECCION — LISTO PARA VALIDACIÓN

Fecha/hora fin: [YYYY-MM-DD HH:MM] [Zona horaria]
Hallazgos corregidos:
1. TI-002.3: [Sí/No] — Commit: [hash]
2. Tests: [Sí/No] — Cobertura: [X%]

Commits de corrección:
- [hash] — [mensaje]

Tests ejecutados:
- Backend: [X] tests, [X%] cobertura
- Frontend: [X] tests
- E2E: [X] tests

Notas: [cualquier nota relevante]
```

---

## 8. FIRMA

| Rol | Nombre | Firma | Fecha |
|-----|--------|-------|-------|
| CEO | Jelkin Zair Carrillo Franco | ✅ Aprobado | 2026-06-14 |
| PMO | ZEUS | ✅ Generado | 2026-06-14 |
| Dev | ODIN | [Pendiente] | — |

---

> **"Corregir un hallazgo es más rápido que explicar por qué no lo corregiste."**
> **Jelkin Zair Carrillo Franco — CEO**

---

**Instrucción generada:** 2026-06-14 11:46 CST (Shanghai) / 10:46 (Bogotá)  
**Próxima acción:** ODIN lee instrucción → corrige → declara listo → ZEUS valida  
**Estado:** APROBADA — Esperando ejecución por ODIN
