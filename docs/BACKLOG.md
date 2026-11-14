# Backlog detallado — Archivo Digital

Vista de lectura del [Project Archivo Digital — Backlog](https://github.com/users/NicolasFerreras/projects/13).

**10 épicas · 2 historias · 88 tareas · 17 sprints.**

> Las tareas son sub-issues de cada épica y también items del Project. El sprint indicado es una propuesta inicial.

## Épica 1 — Infraestructura y arquitectura

**Prioridad:** P0 · **Sprint:** S1–S2 · **Estimación:** 21 puntos · **Área:** infrastructure

**Issue:** [#1](https://github.com/NicolasFerreras/archivo-digital/issues/1)

Dejar la base técnica del sistema: arquitectura, modelo de dominio, repositorios, entornos, Docker Compose, CI/CD y contratos OpenAPI.

### Tareas

- [ ] Definir arquitectura y límites de los módulos. — **S1** · [#13](https://github.com/NicolasFerreras/archivo-digital/issues/13)
- [ ] Definir modelo de dominio y entidades principales. — **S1** · [#14](https://github.com/NicolasFerreras/archivo-digital/issues/14)
- [ ] Configurar repositorios y estrategia de ramas. — **S1** · [#15](https://github.com/NicolasFerreras/archivo-digital/issues/15)
- [ ] Configurar ambientes de desarrollo y pruebas. — **S1** · [#16](https://github.com/NicolasFerreras/archivo-digital/issues/16)
- [ ] Configurar Docker Compose para el entorno local. — **S2** · [#17](https://github.com/NicolasFerreras/archivo-digital/issues/17)
- [ ] Configurar pipeline CI/CD con GitHub Actions. — **S2** · [#18](https://github.com/NicolasFerreras/archivo-digital/issues/18)
- [ ] Definir contratos iniciales de API con OpenAPI. — **S2** · [#19](https://github.com/NicolasFerreras/archivo-digital/issues/19)
- [ ] Definir política de secretos y variables de entorno. — **S2** · [#20](https://github.com/NicolasFerreras/archivo-digital/issues/20)

### Criterios de aceptación

- La arquitectura, el modelo de dominio y los contratos iniciales quedan documentados.
- El pipeline de CI/CD corre en cada Pull Request y el entorno local se levanta con Docker Compose.

## Épica 2 — Inventario Digital

**Prioridad:** P0 · **Sprint:** S2–S5 · **Estimación:** 21 puntos · **Área:** database

**Issue:** [#2](https://github.com/NicolasFerreras/archivo-digital/issues/2)

Construir el registro central de piezas y archivos digitales, con estados, checksum, historial y respaldos.

### Tareas

- [ ] Diseñar modelo de datos del inventario. — **S2** · [#21](https://github.com/NicolasFerreras/archivo-digital/issues/21)
- [ ] Implementar registro de piezas. — **S2** · [#22](https://github.com/NicolasFerreras/archivo-digital/issues/22)
- [ ] Implementar registro de archivos digitales. — **S3** · [#23](https://github.com/NicolasFerreras/archivo-digital/issues/23)
- [ ] Asociar archivos digitales con piezas. — **S3** · [#24](https://github.com/NicolasFerreras/archivo-digital/issues/24)
- [ ] Registrar checksum, formato, tamaño y ubicación. — **S4** · [#25](https://github.com/NicolasFerreras/archivo-digital/issues/25)
- [ ] Implementar estados de digitalización. — **S4** · [#26](https://github.com/NicolasFerreras/archivo-digital/issues/26)
- [ ] Registrar historial de cambios y operador responsable. — **S4** · [#27](https://github.com/NicolasFerreras/archivo-digital/issues/27)
- [ ] Implementar consulta del estado del inventario. — **S5** · [#28](https://github.com/NicolasFerreras/archivo-digital/issues/28)
- [ ] Implementar mecanismos de respaldo y recuperación. — **S5** · [#29](https://github.com/NicolasFerreras/archivo-digital/issues/29)

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

- [ ] Relevar estructura y disponibilidad de Sistema A. — **S3** · [#30](https://github.com/NicolasFerreras/archivo-digital/issues/30)
- [ ] Relevar contratos de las APIs de Sistemas B y C. — **S3** · [#31](https://github.com/NicolasFerreras/archivo-digital/issues/31)
- [ ] Diseñar interfaz común de registros de catálogo. — **S4** · [#32](https://github.com/NicolasFerreras/archivo-digital/issues/32)
- [ ] Implementar adaptador de Sistema A con acceso de solo lectura. — **S4** · [#33](https://github.com/NicolasFerreras/archivo-digital/issues/33)
- [ ] Implementar adaptador de Sistema B. — **S5** · [#34](https://github.com/NicolasFerreras/archivo-digital/issues/34)
- [ ] Implementar adaptador de Sistema C. — **S5** · [#35](https://github.com/NicolasFerreras/archivo-digital/issues/35)
- [ ] Normalizar metadatos de los tres catálogos. — **S5** · [#36](https://github.com/NicolasFerreras/archivo-digital/issues/36)
- [ ] Vincular registros mediante sistema de origen e identificador externo. — **S6** · [#37](https://github.com/NicolasFerreras/archivo-digital/issues/37)
- [ ] Implementar sincronización incremental o por lotes. — **S6** · [#38](https://github.com/NicolasFerreras/archivo-digital/issues/38)
- [ ] Registrar errores, última sincronización y reintentos. — **S7** · [#39](https://github.com/NicolasFerreras/archivo-digital/issues/39)
- [ ] Implementar caché para consultas de integración. — **S7** · [#40](https://github.com/NicolasFerreras/archivo-digital/issues/40)

### Criterios de aceptación

- Los sistemas A, B y C se consultan sin escritura y a través de un contrato único.
- Los errores de sincronización, la última ejecución y los reintentos quedan registrados.

## Épica 4 — Digitalización y procesamiento

**Prioridad:** P1 · **Sprint:** S3–S7 · **Estimación:** 21 puntos · **Área:** backend

**Issue:** [#4](https://github.com/NicolasFerreras/archivo-digital/issues/4)

Implementar la ingesta, el procesamiento asíncrono y la generación de derivados de los archivos digitales.

### Tareas

- [ ] Implementar carga de archivos originales. — **S3** · [#41](https://github.com/NicolasFerreras/archivo-digital/issues/41)
- [ ] Validar formatos y tamaño de archivos. — **S3** · [#42](https://github.com/NicolasFerreras/archivo-digital/issues/42)
- [ ] Registrar archivos en el inventario. — **S4** · [#43](https://github.com/NicolasFerreras/archivo-digital/issues/43)
- [ ] Implementar cola de trabajos. — **S5** · [#44](https://github.com/NicolasFerreras/archivo-digital/issues/44)
- [ ] Implementar worker de procesamiento. — **S5** · [#45](https://github.com/NicolasFerreras/archivo-digital/issues/45)
- [ ] Generar derivados de imágenes y documentos. — **S5** · [#46](https://github.com/NicolasFerreras/archivo-digital/issues/46)
- [ ] Implementar transcodificación de video. — **S6** · [#47](https://github.com/NicolasFerreras/archivo-digital/issues/47)
- [ ] Aplicar marca de agua a los derivados. — **S7** · [#48](https://github.com/NicolasFerreras/archivo-digital/issues/48)
- [ ] Gestionar errores y reintentos de procesamiento. — **S7** · [#49](https://github.com/NicolasFerreras/archivo-digital/issues/49)

### Criterios de aceptación

- Un archivo original se procesa y genera sus derivados sin bloquear la plataforma.
- Los errores de procesamiento se reintentan y quedan visibles.

## Épica 5 — Buscador e indexación

**Prioridad:** P1 · **Sprint:** S6–S9 · **Estimación:** 21 puntos · **Área:** backend

**Issue:** [#5](https://github.com/NicolasFerreras/archivo-digital/issues/5)

Construir el índice de búsqueda desacoplado y las consultas por título, tipo, fecha y filtros.

### Tareas

- [ ] Seleccionar y configurar motor de búsqueda. — **S6** · [#50](https://github.com/NicolasFerreras/archivo-digital/issues/50)
- [ ] Diseñar estructura del índice. — **S6** · [#51](https://github.com/NicolasFerreras/archivo-digital/issues/51)
- [ ] Implementar worker de indexación. — **S7** · [#52](https://github.com/NicolasFerreras/archivo-digital/issues/52)
- [ ] Indexar metadatos normalizados. — **S7** · [#53](https://github.com/NicolasFerreras/archivo-digital/issues/53)
- [ ] Implementar búsqueda por título, tipo y fecha. — **S8** · [#54](https://github.com/NicolasFerreras/archivo-digital/issues/54)
- [ ] Implementar filtros de búsqueda. — **S8** · [#55](https://github.com/NicolasFerreras/archivo-digital/issues/55)
- [ ] Implementar actualización del índice ante cambios. — **S9** · [#56](https://github.com/NicolasFerreras/archivo-digital/issues/56)
- [ ] Medir y validar tiempos de respuesta inferiores a 2 segundos. — **S9** · [#57](https://github.com/NicolasFerreras/archivo-digital/issues/57)

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

- [ ] Diseñar flujo de publicación de archivos. — **S7** · [#58](https://github.com/NicolasFerreras/archivo-digital/issues/58)
- [ ] Implementar publicación de archivos derivados. — **S7** · [#59](https://github.com/NicolasFerreras/archivo-digital/issues/59)
- [ ] Integrar almacenamiento de objetos con CDN. — **S8** · [#60](https://github.com/NicolasFerreras/archivo-digital/issues/60)
- [ ] Generar URLs firmadas y temporales. — **S9** · [#61](https://github.com/NicolasFerreras/archivo-digital/issues/61)
- [ ] Implementar control de acceso a contenido. — **S9** · [#62](https://github.com/NicolasFerreras/archivo-digital/issues/62)
- [ ] Implementar streaming adaptativo. — **S9** · [#63](https://github.com/NicolasFerreras/archivo-digital/issues/63)
- [ ] Validar distribución de contenido durante picos de demanda. — **S10** · [#64](https://github.com/NicolasFerreras/archivo-digital/issues/64)

### Criterios de aceptación

- Un derivado se publica y se reproduce desde la CDN con URL firmada y temporal.
- La distribución resiste los picos de demanda previstos.

## Épica 7 — Frontend y visualización

**Prioridad:** P1 · **Sprint:** S6–S12 · **Estimación:** 21 puntos · **Área:** frontend

**Issue:** [#7](https://github.com/NicolasFerreras/archivo-digital/issues/7)

Desarrollar la interfaz pública y la de operador, incluyendo búsqueda, detalle, reproducción y recorridos.

### Tareas

- [ ] Diseñar navegación principal de la plataforma. — **S6** · [#65](https://github.com/NicolasFerreras/archivo-digital/issues/65)
- [ ] Implementar interfaz pública. — **S7** · [#66](https://github.com/NicolasFerreras/archivo-digital/issues/66)
- [ ] Implementar resultados de búsqueda. — **S7** · [#67](https://github.com/NicolasFerreras/archivo-digital/issues/67)
- [ ] Implementar detalle de una pieza. — **S8** · [#68](https://github.com/NicolasFerreras/archivo-digital/issues/68)
- [ ] Implementar visualización de imágenes y documentos. — **S9** · [#69](https://github.com/NicolasFerreras/archivo-digital/issues/69)
- [ ] Implementar reproducción de contenido audiovisual. — **S9** · [#70](https://github.com/NicolasFerreras/archivo-digital/issues/70)
- [ ] Implementar interfaz de operador. — **S10** · [#71](https://github.com/NicolasFerreras/archivo-digital/issues/71)
- [ ] Implementar consulta del inventario. — **S11** · [#72](https://github.com/NicolasFerreras/archivo-digital/issues/72)
- [ ] Implementar interfaz de muestras virtuales. — **S11** · [#73](https://github.com/NicolasFerreras/archivo-digital/issues/73)
- [ ] Implementar recorridos virtuales. — **S12** · [#74](https://github.com/NicolasFerreras/archivo-digital/issues/74)

### Criterios de aceptación

- Un visitante busca, abre y reproduce una pieza desde la interfaz pública.
- Un operador consulta el inventario y el estado de digitalización.

## Épica 8 — Autenticación y autorización

**Prioridad:** P0 · **Sprint:** S3–S5 · **Estimación:** 21 puntos · **Área:** backend

**Issue:** [#8](https://github.com/NicolasFerreras/archivo-digital/issues/8)

Implementar autenticación interna y externa, autorización por roles y protección de endpoints.

### Tareas

- [ ] Diseñar roles y permisos. — **S3** · [#75](https://github.com/NicolasFerreras/archivo-digital/issues/75)
- [ ] Integrar autenticación interna con directorio corporativo. — **S3** · [#76](https://github.com/NicolasFerreras/archivo-digital/issues/76)
- [ ] Implementar autenticación de usuarios externos mediante OIDC. — **S4** · [#77](https://github.com/NicolasFerreras/archivo-digital/issues/77)
- [ ] Implementar registro e inicio de sesión propio, si corresponde. — **S4** · [#78](https://github.com/NicolasFerreras/archivo-digital/issues/78)
- [ ] Implementar autorización por roles. — **S4** · [#79](https://github.com/NicolasFerreras/archivo-digital/issues/79)
- [ ] Proteger endpoints internos. — **S4** · [#80](https://github.com/NicolasFerreras/archivo-digital/issues/80)
- [ ] Implementar sesiones y cierre de sesión. — **S5** · [#81](https://github.com/NicolasFerreras/archivo-digital/issues/81)
- [ ] Probar acceso de invitados y usuarios registrados. — **S5** · [#82](https://github.com/NicolasFerreras/archivo-digital/issues/82)

### Criterios de aceptación

- Un operador entra con el directorio corporativo y un visitante con OIDC.
- Los permisos por rol se respetan en los endpoints internos y públicos.

## Épica 9 — Estadísticas

**Prioridad:** P1 · **Sprint:** S1–S17 · **Estimación:** 13 puntos · **Área:** backend

**Issue:** [#9](https://github.com/NicolasFerreras/archivo-digital/issues/9)

Registrar eventos de uso y exponer métricas de actividad, contenido consultado y tiempos de respuesta.

### Tareas

- [ ] Definir eventos de actividad que se van a registrar. — **S1** · [#83](https://github.com/NicolasFerreras/archivo-digital/issues/83)
- [ ] Implementar captura de eventos desde el inicio del proyecto. — **S4** · [#84](https://github.com/NicolasFerreras/archivo-digital/issues/84)
- [ ] Registrar búsquedas realizadas. — **S6** · [#85](https://github.com/NicolasFerreras/archivo-digital/issues/85)
- [ ] Registrar contenido más consultado. — **S9** · [#86](https://github.com/NicolasFerreras/archivo-digital/issues/86)
- [ ] Registrar tiempos de respuesta. — **S12** · [#87](https://github.com/NicolasFerreras/archivo-digital/issues/87)
- [ ] Integrar el servicio de estadísticas. — **S14** · [#88](https://github.com/NicolasFerreras/archivo-digital/issues/88)
- [ ] Implementar visualización de métricas. — **S17** · [#89](https://github.com/NicolasFerreras/archivo-digital/issues/89)

### Criterios de aceptación

- Los eventos se capturan desde el inicio del proyecto.
- Las métricas de actividad y contenido consultado se visualizan.

## Épica 10 — Testing, seguridad y despliegue

**Prioridad:** P1 · **Sprint:** S2–S17 · **Estimación:** 21 puntos · **Área:** testing

**Issue:** [#10](https://github.com/NicolasFerreras/archivo-digital/issues/10)

Asegurar la calidad, la seguridad y el despliegue: pruebas, mocks, RPO/RTO y estabilización.

### Tareas

- [ ] Implementar pruebas unitarias. — **S2** · [#90](https://github.com/NicolasFerreras/archivo-digital/issues/90)
- [ ] Implementar pruebas de integración. — **S4** · [#91](https://github.com/NicolasFerreras/archivo-digital/issues/91)
- [ ] Crear mocks o copias controladas de los sistemas legacy. — **S5** · [#92](https://github.com/NicolasFerreras/archivo-digital/issues/92)
- [ ] Implementar pruebas de contrato OpenAPI. — **S6** · [#93](https://github.com/NicolasFerreras/archivo-digital/issues/93)
- [ ] Ejecutar pruebas de carga. — **S8** · [#94](https://github.com/NicolasFerreras/archivo-digital/issues/94)
- [ ] Ejecutar pruebas de seguridad. — **S10** · [#95](https://github.com/NicolasFerreras/archivo-digital/issues/95)
- [ ] Validar restauración de backups. — **S11** · [#96](https://github.com/NicolasFerreras/archivo-digital/issues/96)
- [ ] Definir y probar objetivos RPO/RTO. — **S12** · [#97](https://github.com/NicolasFerreras/archivo-digital/issues/97)
- [ ] Preparar entorno de producción. — **S14** · [#98](https://github.com/NicolasFerreras/archivo-digital/issues/98)
- [ ] Ejecutar despliegue. — **S16** · [#99](https://github.com/NicolasFerreras/archivo-digital/issues/99)
- [ ] Realizar estabilización posterior al despliegue. — **S17** · [#100](https://github.com/NicolasFerreras/archivo-digital/issues/100)

### Criterios de aceptación

- Las pruebas unitarias, de integración, carga y seguridad pasan antes del despliegue.
- La restauración de backups y los objetivos RPO/RTO se validan.

