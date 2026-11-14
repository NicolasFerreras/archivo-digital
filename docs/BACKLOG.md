# Backlog detallado — Archivo Digital

Vista de lectura del [Project Archivo Digital — Backlog](https://github.com/users/NicolasFerreras/projects/13).

**10 épicas · 2 historias · 88 tareas · 17 sprints.**

> Las tareas son draft items del Project. El sprint indicado es una propuesta inicial.

## Épica 1 — Infraestructura y arquitectura

**Prioridad:** P0 · **Sprint:** S1–S2 · **Estimación:** 21 puntos · **Área:** infrastructure

**Issue:** [#1](https://github.com/NicolasFerreras/archivo-digital/issues/1)

Dejar la base técnica del sistema: arquitectura, modelo de dominio, repositorios, entornos, Docker Compose, CI/CD y contratos OpenAPI.

### Tareas

- [ ] Definir arquitectura y límites de los módulos. — **S1**
- [ ] Definir modelo de dominio y entidades principales. — **S1**
- [ ] Configurar repositorios y estrategia de ramas. — **S1**
- [ ] Configurar ambientes de desarrollo y pruebas. — **S1**
- [ ] Configurar Docker Compose para el entorno local. — **S2**
- [ ] Configurar pipeline CI/CD con GitHub Actions. — **S2**
- [ ] Definir contratos iniciales de API con OpenAPI. — **S2**
- [ ] Definir política de secretos y variables de entorno. — **S2**

### Criterios de aceptación

- La arquitectura, el modelo de dominio y los contratos iniciales quedan documentados.
- El pipeline de CI/CD corre en cada Pull Request y el entorno local se levanta con Docker Compose.

## Épica 2 — Inventario Digital

**Prioridad:** P0 · **Sprint:** S2–S5 · **Estimación:** 21 puntos · **Área:** database

**Issue:** [#2](https://github.com/NicolasFerreras/archivo-digital/issues/2)

Construir el registro central de piezas y archivos digitales, con estados, checksum, historial y respaldos.

### Tareas

- [ ] Diseñar modelo de datos del inventario. — **S2**
- [ ] Implementar registro de piezas. — **S2**
- [ ] Implementar registro de archivos digitales. — **S3**
- [ ] Asociar archivos digitales con piezas. — **S3**
- [ ] Registrar checksum, formato, tamaño y ubicación. — **S4**
- [ ] Implementar estados de digitalización. — **S4**
- [ ] Registrar historial de cambios y operador responsable. — **S4**
- [ ] Implementar consulta del estado del inventario. — **S5**
- [ ] Implementar mecanismos de respaldo y recuperación. — **S5**

### Historias

- [ ] Historia: consulta del estado de digitalización — **S2** · [#11](https://github.com/NicolasFerreras/archivo-digital/issues/11)

### Criterios de aceptación

- Una pieza y sus archivos digitales se registran y consultan desde el inventario.
- Cada cambio de estado registra fecha, operador y queda auditado.

## Épica 3 — Integración con catálogos legacy

**Prioridad:** P0 · **Sprint:** S3–S7 · **Estimación:** 34 puntos · **Área:** integration

**Issue:** [#3](https://github.com/NicolasFerreras/archivo-digital/issues/3)

Integrar los tres catálogos legacy mediante adaptadores de solo lectura y una interfaz común normalizada.

### Tareas

- [ ] Relevar estructura y disponibilidad de Sistema A. — **S3**
- [ ] Relevar contratos de las APIs de Sistemas B y C. — **S3**
- [ ] Diseñar interfaz común de registros de catálogo. — **S4**
- [ ] Implementar adaptador de Sistema A con acceso de solo lectura. — **S4**
- [ ] Implementar adaptador de Sistema B. — **S5**
- [ ] Implementar adaptador de Sistema C. — **S5**
- [ ] Normalizar metadatos de los tres catálogos. — **S5**
- [ ] Vincular registros mediante sistema de origen e identificador externo. — **S6**
- [ ] Implementar sincronización incremental o por lotes. — **S6**
- [ ] Registrar errores, última sincronización y reintentos. — **S7**
- [ ] Implementar caché para consultas de integración. — **S7**

### Criterios de aceptación

- Los sistemas A, B y C se consultan sin escritura y a través de un contrato único.
- Los errores de sincronización, la última ejecución y los reintentos quedan registrados.

## Épica 4 — Digitalización y procesamiento

**Prioridad:** P1 · **Sprint:** S3–S7 · **Estimación:** 21 puntos · **Área:** backend

**Issue:** [#4](https://github.com/NicolasFerreras/archivo-digital/issues/4)

Implementar la ingesta, el procesamiento asíncrono y la generación de derivados de los archivos digitales.

### Tareas

- [ ] Implementar carga de archivos originales. — **S3**
- [ ] Validar formatos y tamaño de archivos. — **S3**
- [ ] Registrar archivos en el inventario. — **S4**
- [ ] Implementar cola de trabajos. — **S5**
- [ ] Implementar worker de procesamiento. — **S5**
- [ ] Generar derivados de imágenes y documentos. — **S5**
- [ ] Implementar transcodificación de video. — **S6**
- [ ] Aplicar marca de agua a los derivados. — **S7**
- [ ] Gestionar errores y reintentos de procesamiento. — **S7**

### Criterios de aceptación

- Un archivo original se procesa y genera sus derivados sin bloquear la plataforma.
- Los errores de procesamiento se reintentan y quedan visibles.

## Épica 5 — Buscador e indexación

**Prioridad:** P1 · **Sprint:** S6–S9 · **Estimación:** 21 puntos · **Área:** backend

**Issue:** [#5](https://github.com/NicolasFerreras/archivo-digital/issues/5)

Construir el índice de búsqueda desacoplado y las consultas por título, tipo, fecha y filtros.

### Tareas

- [ ] Seleccionar y configurar motor de búsqueda. — **S6**
- [ ] Diseñar estructura del índice. — **S6**
- [ ] Implementar worker de indexación. — **S7**
- [ ] Indexar metadatos normalizados. — **S7**
- [ ] Implementar búsqueda por título, tipo y fecha. — **S8**
- [ ] Implementar filtros de búsqueda. — **S8**
- [ ] Implementar actualización del índice ante cambios. — **S9**
- [ ] Medir y validar tiempos de respuesta inferiores a 2 segundos. — **S9**

### Historias

- [ ] Historia: búsqueda pública de piezas — **S6** · [#12](https://github.com/NicolasFerreras/archivo-digital/issues/12)

### Criterios de aceptación

- Una búsqueda por título, tipo y fecha responde en menos de 2 segundos bajo carga nominal.
- El índice se actualiza ante cambios sin reconstruirse completo.

## Épica 6 — Disponibilización y CDN

**Prioridad:** P1 · **Sprint:** S7–S10 · **Estimación:** 13 puntos · **Área:** infrastructure

**Issue:** [#6](https://github.com/NicolasFerreras/archivo-digital/issues/6)

Publicar los derivados en la CDN, con URLs firmadas, control de acceso y streaming adaptativo.

### Tareas

- [ ] Diseñar flujo de publicación de archivos. — **S7**
- [ ] Implementar publicación de archivos derivados. — **S7**
- [ ] Integrar almacenamiento de objetos con CDN. — **S8**
- [ ] Generar URLs firmadas y temporales. — **S9**
- [ ] Implementar control de acceso a contenido. — **S9**
- [ ] Implementar streaming adaptativo. — **S9**
- [ ] Validar distribución de contenido durante picos de demanda. — **S10**

### Criterios de aceptación

- Un derivado se publica y se reproduce desde la CDN con URL firmada y temporal.
- La distribución resiste los picos de demanda previstos.

## Épica 7 — Frontend y visualización

**Prioridad:** P1 · **Sprint:** S6–S12 · **Estimación:** 21 puntos · **Área:** frontend

**Issue:** [#7](https://github.com/NicolasFerreras/archivo-digital/issues/7)

Desarrollar la interfaz pública y la de operador, incluyendo búsqueda, detalle, reproducción y recorridos.

### Tareas

- [ ] Diseñar navegación principal de la plataforma. — **S6**
- [ ] Implementar interfaz pública. — **S7**
- [ ] Implementar resultados de búsqueda. — **S7**
- [ ] Implementar detalle de una pieza. — **S8**
- [ ] Implementar visualización de imágenes y documentos. — **S9**
- [ ] Implementar reproducción de contenido audiovisual. — **S9**
- [ ] Implementar interfaz de operador. — **S10**
- [ ] Implementar consulta del inventario. — **S11**
- [ ] Implementar interfaz de muestras virtuales. — **S11**
- [ ] Implementar recorridos virtuales. — **S12**

### Criterios de aceptación

- Un visitante busca, abre y reproduce una pieza desde la interfaz pública.
- Un operador consulta el inventario y el estado de digitalización.

## Épica 8 — Autenticación y autorización

**Prioridad:** P0 · **Sprint:** S3–S5 · **Estimación:** 21 puntos · **Área:** backend

**Issue:** [#8](https://github.com/NicolasFerreras/archivo-digital/issues/8)

Implementar autenticación interna y externa, autorización por roles y protección de endpoints.

### Tareas

- [ ] Diseñar roles y permisos. — **S3**
- [ ] Integrar autenticación interna con directorio corporativo. — **S3**
- [ ] Implementar autenticación de usuarios externos mediante OIDC. — **S4**
- [ ] Implementar registro e inicio de sesión propio, si corresponde. — **S4**
- [ ] Implementar autorización por roles. — **S4**
- [ ] Proteger endpoints internos. — **S4**
- [ ] Implementar sesiones y cierre de sesión. — **S5**
- [ ] Probar acceso de invitados y usuarios registrados. — **S5**

### Criterios de aceptación

- Un operador entra con el directorio corporativo y un visitante con OIDC.
- Los permisos por rol se respetan en los endpoints internos y públicos.

## Épica 9 — Estadísticas

**Prioridad:** P1 · **Sprint:** S1–S17 · **Estimación:** 13 puntos · **Área:** backend

**Issue:** [#9](https://github.com/NicolasFerreras/archivo-digital/issues/9)

Registrar eventos de uso y exponer métricas de actividad, contenido consultado y tiempos de respuesta.

### Tareas

- [ ] Definir eventos de actividad que se van a registrar. — **S1**
- [ ] Implementar captura de eventos desde el inicio del proyecto. — **S4**
- [ ] Registrar búsquedas realizadas. — **S6**
- [ ] Registrar contenido más consultado. — **S9**
- [ ] Registrar tiempos de respuesta. — **S12**
- [ ] Integrar el servicio de estadísticas. — **S14**
- [ ] Implementar visualización de métricas. — **S17**

### Criterios de aceptación

- Los eventos se capturan desde el inicio del proyecto.
- Las métricas de actividad y contenido consultado se visualizan.

## Épica 10 — Testing, seguridad y despliegue

**Prioridad:** P1 · **Sprint:** S2–S17 · **Estimación:** 21 puntos · **Área:** testing

**Issue:** [#10](https://github.com/NicolasFerreras/archivo-digital/issues/10)

Asegurar la calidad, la seguridad y el despliegue: pruebas, mocks, RPO/RTO y estabilización.

### Tareas

- [ ] Implementar pruebas unitarias. — **S2**
- [ ] Implementar pruebas de integración. — **S4**
- [ ] Crear mocks o copias controladas de los sistemas legacy. — **S5**
- [ ] Implementar pruebas de contrato OpenAPI. — **S6**
- [ ] Ejecutar pruebas de carga. — **S8**
- [ ] Ejecutar pruebas de seguridad. — **S10**
- [ ] Validar restauración de backups. — **S11**
- [ ] Definir y probar objetivos RPO/RTO. — **S12**
- [ ] Preparar entorno de producción. — **S14**
- [ ] Ejecutar despliegue. — **S16**
- [ ] Realizar estabilización posterior al despliegue. — **S17**

### Criterios de aceptación

- Las pruebas unitarias, de integración, carga y seguridad pasan antes del despliegue.
- La restauración de backups y los objetivos RPO/RTO se validan.

