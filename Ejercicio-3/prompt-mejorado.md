# NEXORA — Prompt completo del proyecto

**Cómo usarlo:** copia todo lo que está debajo de la línea en una conversación nueva. La IA ejecuta una fase a la vez y se detiene al terminar; para avanzar, escribe “Aprobada. Continúa con la Fase 2”.

---

## 1. Rol y objetivo

Actúa como Senior Product Designer y Front-end Engineer especializado en EdTech. Vas a construir NEXORA, una plataforma de aprendizaje adaptativo con IA para estudiantes de secundaria, universitarios, autodidactas y docentes. El proyecto completo se entrega en 4 fases, una por vez, y cada fase amplía la anterior.

**Identidad del producto:**

NEXORA combina un tutor IA que enseña en lugar de responder por el estudiante, un perfil de aprendizaje que se actualiza con cada actividad y entornos prácticos interactivos.

- Tagline: “Aprende a tu manera. Evoluciona a tu ritmo.”
- Idea central: “Cada mente aprende diferente. NEXORA aprende contigo.”
- Personalidad: innovadora, juvenil sin ser infantil, inteligente, cercana, confiable y enérgica.
- Debe sentirse como una startup EdTech premium: ni un sitio escolar tradicional ni un clon de chatbot genérico.

**Mapa de fases del proyecto:**

| Fase | Contenido | Resultado para el usuario |
|------|-----------|---------------------------|
| 1 | Landing, registro, onboarding, dashboard, tutor IA (4 modos) y una actividad interactiva | El estudiante completa su primer ciclo de aprendizaje |
| 2 | Perfil de aprendizaje, mapa de conocimiento y laboratorio de programación | El estudiante ve qué sabe y qué debe aprender después |
| 3 | Laboratorios de matemáticas y ciencias, y gamificación (misiones, logros, retos) | El estudiante practica y se motiva con propósito |
| 4 | Analíticas, Teacher Studio y pulido final | El docente entiende a su clase y el producto queda cohesionado |

Las secciones 2, 3, 4, 6, 7, 8 y 9 son la base común y aplican a todas las fases. Las secciones 5 y 10 son específicas de la Fase 1; las secciones 11, 12 y 13 definen las fases 2, 3 y 4, y la 14 fija los criterios finales.

## 2. Formato de entrega y stack

- Entrega un único archivo HTML autocontenido (o un artefacto React de un solo archivo si el entorno lo exige). Sin backend.
- React 18 y Tailwind por CDN con versiones fijas; gráficos y diagramas en SVG propio, sin librerías de gráficos pesadas.
- Navegación entre pantallas mediante estado de React (o hash simple tipo #tutor), sin recargas.
- Fuentes: Plus Jakarta Sans (títulos) e Inter (cuerpo), con alternativas system-ui por si no cargan.
- Todos los datos son simulados y deben estar rotulados como “Datos de demostración” donde se muestren cifras.
- Organiza el código en módulos separados por comentarios (`// ===== MÓDULO: tutor =====`): i18n, datos, ui, landing, auth, onboarding, dashboard, tutor, actividad y los que añada cada fase.
- Aísla la lógica del tutor en una sola función (`getTutorReply(modo, mensaje, perfil)`) para poder conectarla después a una API de IA real sin tocar la interfaz.

**Modo de trabajo por fases (obligatorio):**

1. Ejecuta solo la fase que te indique. Empieza por la Fase 1.
2. Cada fase amplía el archivo anterior: conserva todo lo ya aprobado y no rompas lo existente. Si el archivo completo no cabe en una respuesta, entrega solo los módulos nuevos o modificados e indica dónde se integran.
3. Si una fase no cabe en una sola respuesta, entrega la primera mitad, di qué falta y espera mi “Continúa”.
4. Antes de cerrar una fase, revisa sus criterios de aceptación y dime cuáles cumples y cuáles no.
5. Al terminar, entrega un resumen de máximo 8 líneas (qué incluye, decisiones tomadas, qué queda pendiente) y detente. No avances a la siguiente fase por tu cuenta.
6. Ante una duda menor, asume lo más razonable, decláralo en una línea y sigue; pregunta solo si no puedes avanzar.

## 3. Sistema de diseño

| Token | Valor | Uso |
|-------|-------|-----|
| Púrpura primario | #7255F7 | Marca, botones principales, enlaces |
| Azul eléctrico | #24B8E8 | Acentos, datos, íconos |
| Menta | #19C6A3 | Éxito, progreso, dominio alto |
| Naranja energía | #FFB547 | Rachas, XP, alertas suaves |
| Rosa creativo | #FF6B91 | Retos, énfasis puntual |
| Blanco nube | #F5F4FC | Fondo de la app |
| Azul marino | #202038 | Texto principal, modo oscuro |
| Blanco | #FFFFFF | Tarjetas |

**Reglas de uso (accesibilidad y consistencia):**

- Solo el púrpura (#7255F7) y el azul marino (#202038) pueden usarse como color de texto sobre fondos claros. Menta, naranja, azul eléctrico y rosa son únicamente para rellenos, íconos, gráficos y acentos; nunca para texto sobre blanco, porque no alcanzan contraste 4.5:1.
- Texto sobre fondos de color: blanco sobre púrpura; azul marino sobre menta, naranja, azul y rosa.
- Gradientes: máximo 3 usos por pantalla, reservados para el hero, el botón principal y la tarjeta “Tu siguiente paso”.
- Espaciado base de 8 px. Radios: 12 px (controles), 16 px (tarjetas), 24 px (paneles grandes). Sombras suaves de dos niveles.
- Escala tipográfica: 12 / 14 / 16 / 20 / 28 / 40 / 56 px. Métricas y títulos clave en Plus Jakarta Sans, peso 700–800.
- Todo componente interactivo tiene estados: normal, hover, foco visible, activo y deshabilitado.
- Ilustraciones: formas geométricas abstractas y objetos 3D estilizados creados con SVG/CSS (capas y sombras), sin personajes infantiles. Máximo un elemento decorativo grande por sección.
- Microinteracciones con propósito (feedback al completar, transiciones de 150–250 ms). Respeta `prefers-reduced-motion`.
- Evita: layouts genéricos tipo Bootstrap, paneles saturados, exceso de gradientes y de decoración.

**Modo oscuro:** claro por defecto y oscuro opcional desde los ajustes, implementado con variables CSS desde la Fase 1. En oscuro: fondo #202038, tarjetas un tono más claro, texto #F5F4FC y púrpura aclarado a #A18FFF para texto (contraste mayor a 4.5:1). Los acentos de color se conservan.

## 4. Idioma e internacionalización

- Español latinoamericano neutro por defecto (tuteo, sin regionalismos marcados). Idiomas disponibles: Español, English y Português.
- Selector de idioma visible en la barra de navegación y en los ajustes.
- Ningún texto visible escrito directamente en los componentes: usa un objeto `translations = { es: {...}, en: {...}, pt: {...} }` y una función `t('clave')`. Cambiar el idioma debe actualizar toda la interfaz, incluidos los mensajes del tutor, ejercicios, notificaciones, errores y estados vacíos.
- En cada fase, los tres idiomas deben estar completos en todas las pantallas entregadas hasta ese momento.

## 5. Fase 1 — Núcleo del estudiante

**Entrega de la Fase 1:** si no cabe en una sola respuesta, divídela en 1A (secciones 5.1 a 5.3: landing, autenticación y onboarding) y 1B (5.4, 5.5 y el tutor IA de la sección 6). Entrega 1A y espera mi “Continúa” antes de pasar a 1B.

### 5.1 Landing

- Hero: título “Aprender nunca fue tan personal.” Subtítulo: “Descubre una nueva forma de aprender. Tu inteligencia artificial personal entiende cómo aprendes y te ayuda a evolucionar a tu propio ritmo.” CTA primario “Comenzar gratis”; secundario “Descubrir NEXORA” (desplaza a “Cómo funciona”).
- Vista previa del producto (maqueta del tutor y del dashboard), tarjetas flotantes y estadísticas animadas rotuladas como demostración.
- Secciones: Cómo funciona (3 pasos), beneficios para estudiantes, beneficios para docentes, funciones destacadas, testimonios (rotulados “Testimonios de ejemplo”), precios (plan Gratis y plan Premium “Próximamente” con botón de lista de espera), preguntas frecuentes en acordeón (6 preguntas) y pie de página.

### 5.2 Autenticación

- Inicio de sesión, registro (nombre, correo, contraseña, edad), recuperación de contraseña (con estado de confirmación) y botón “Continuar con Google” (solo visual, simulado).
- Si la edad es menor de 18, mostrar una nota de consentimiento de madre, padre o tutor.
- Selección de rol: Estudiante o Docente. El rol Docente lleva a una pantalla “Teacher Studio llega pronto” con dos acciones: unirse a la lista de espera o probar la experiencia de estudiante. Sin callejones sin salida.

### 5.3 Onboarding del estudiante (5 pasos)

Barra de progreso, botón “Atrás” y posibilidad de omitir: (1) intereses, (2) nivel educativo, (3) estilo de aprendizaje preferido (visual, práctico, lectura y escritura, conversacional), (4) objetivos, (5) materias de interés. Al finalizar, muestra “Tu perfil de aprendizaje inicial” con un resumen y la primera recomendación, y entra al dashboard ya personalizado con esas respuestas.

### 5.4 Dashboard del estudiante

Saludo personalizado y avatar, nivel y barra de XP, racha, meta diaria, progreso semanal (gráfico SVG), tarjeta destacada “Tu siguiente paso”, actividades recomendadas, sesiones recientes, próximos retos y recomendaciones de la IA. Incluye campana de notificaciones (panel con 3 notificaciones), menú de usuario con ajustes (idioma, tamaño de texto, reducir movimiento) y un botón flotante del tutor accesible en todas las pantallas.

Navegación principal: Inicio, Tutor IA, Mi perfil, Laboratorios, Retos y Progreso. En la Fase 1 solo Inicio y Tutor IA son completos; las demás abren una pantalla “Pronto” con una vista previa de lo que traerá y dos acciones: “Volver al inicio” y “Avísame cuando esté listo” (muestra confirmación).

### 5.5 Actividad interactiva: “Parábola interactiva”

Ejercicio sobre funciones cuadráticas: el estudiante ajusta con controles deslizantes los coeficientes de y = x² + bx + c, ve la gráfica en SVG actualizarse en tiempo real y debe encontrar los puntos donde la curva corta el eje x. Incluye 3 pistas graduales, validación de la respuesta y retroalimentación específica para acierto y error.

Al completarla: +40 XP, la meta diaria avanza, el dominio de “Funciones cuadráticas” sube de 42 % a 48 %, aparece una celebración sobria y el dashboard refleja los cambios (incluida una actualización de “Tu siguiente paso”).

## 6. Tutor IA de NEXORA (función principal)

**Identidad:** asistente con nombre propio (“Nexo”), avatar abstracto animado y tono cercano, claro y alentador. No debe parecer un chat genérico: tiene estructura educativa visible.

**Diseño:**

- Escritorio: conversación a la izquierda y panel contextual a la derecha (concepto actual, progreso del concepto, recursos sugeridos). Móvil: pantalla completa, con el panel contextual en una hoja inferior.
- Selector de 4 modos con ícono y descripción breve: Explícame, Ponme un reto, Analiza mi error y Comprueba mi nivel.
- Mensajes con componentes ricos: pasos numerados, diagramas SVG, ejemplos interactivos, tarjetas de “Comprueba si lo entendiste” y botones de respuesta rápida.
- Entrada de texto con adjuntar imagen, documento o código (simulado: muestra una etiqueta con el nombre del archivo) y 3 mensajes sugeridos por modo.
- Estado de “pensando” elegante: orbe animado con 3 etapas de texto (“Leyendo tu pregunta…”, “Buscando tu punto de partida…”, “Preparando una explicación para ti…”).

**Comportamiento por modo:**

- **Explícame:** analogía + explicación por pasos + visual SVG + pregunta de comprensión.
- **Ponme un reto:** ejercicio adaptado al nivel del estudiante, hasta 3 pistas progresivas, validación y retroalimentación.
- **Analiza mi error:** recibe una solución, señala el paso exacto donde falla, nombra el posible malentendido conceptual y hace una pregunta guía en lugar de entregar la solución corregida.
- **Comprueba mi nivel:** 5 preguntas cortas, sin revelar respuestas hasta el final; resultado con nivel estimado y siguiente recomendación.

**Reglas pedagógicas (obligatorias):**

1. Nunca entregar la respuesta final de inmediato en los ejercicios; guiar con preguntas y pistas graduales.
2. Cada respuesta termina con una pregunta de seguimiento o una microactividad.
3. En “Comprueba mi nivel” no se dan pistas ni respuestas antes de terminar.
4. Si el tema es sensible (salud emocional, seguridad), responder con empatía y sugerir hablar con una persona de confianza o un docente.

**Simulación:** el tutor funciona con guiones predefinidos por modo, con efecto de escritura animada. El mensaje libre se asocia al guion del modo activo por palabras clave; si no hay coincidencia, responde con una pregunta aclaratoria amable.

**Ejemplo de referencia (modo “Analiza mi error”):**

> **Valentina:** Resolví x² − 5x + 6 = 0. Factoricé (x − 2)(x − 3) = 0 y me dio x = −2 y x = −3.
>
> **Nexo:** ¡Tu factorización es correcta! El error aparece en el paso siguiente. Dime: si x = −2, ¿cuánto vale el factor (x − 2)?
>
> *[Mini visual: recta numérica que muestra qué valor de x anula cada factor]*
>
> Lo que veo: parece que se toma el número del paréntesis tal cual, sin cambiarle el signo. Es un error muy común y tiene arreglo.
>
> **Comprueba si lo entendiste:** ¿qué valor de x hace que (x + 4) sea cero? A) 4  B) −4  C) 0

**Ejemplos de referencia para los otros tres modos:**

*Modo Explícame:*

> **Valentina:** Explícame qué es una función cuadrática.
>
> **Nexo:** Piensa en el recorrido de un balón al patearlo: sube, alcanza su punto más alto y baja. Esa curva es una parábola, y la función cuadrática es la regla que la describe.
>
> *[Visual: parábola con el vértice señalado]*
>
> Paso 1: en y = x², ¿cuánto vale y cuando x = 3? ¿Y cuando x = −3? ¿Qué notas?

*Modo Ponme un reto:*

> **Valentina:** Ponme un reto de factorización.
>
> **Nexo:** Ya dominas las ecuaciones lineales, así que subimos un nivel. Reto (nivel 2 de 5): factoriza x² + 7x + 12. Tienes 3 pistas disponibles; ¿quieres intentarlo primero sin ellas?

*Modo Comprueba mi nivel:*

> **Valentina:** Comprueba mi nivel en funciones cuadráticas.
>
> **Nexo:** Serán 5 preguntas cortas, sin pistas y con los resultados al final. Pregunta 1 de 5: ¿cuál de estas expresiones es una función cuadrática? A) y = 2x + 1  B) y = x² − 4  C) y = 1/x

## 7. Datos de demostración

Usa este perfil en todo el prototipo, siempre rotulado como demostración:

- Valentina Restrepo, 16 años, Medellín, 11.º grado. Objetivo: ingresar a Ingeniería.
- Nivel 7 “Explorador”, 1.240 / 1.500 XP, racha de 12 días, meta diaria de 30 min (18 completados).
- Fortalezas: ecuaciones lineales y porcentajes. A reforzar: funciones cuadráticas (42 %) y factorización (51 %).
- Error frecuente: cambio de signo al despejar y al hallar raíces.
- Sesiones recientes y próximos retos coherentes con ese perfil.

## 8. Accesibilidad, seguridad y privacidad

- Contraste mínimo 4.5:1 en texto, objetivos táctiles de al menos 44 px, navegación completa por teclado, foco visible, `aria-label` en íconos y roles semánticos en pestañas, modales y paneles.
- No pidas datos personales innecesarios (nada de dirección ni teléfono). Incluye un aviso breve de privacidad en el registro.
- No presentes cifras ni logros simulados como reales; todo lo simulado va rotulado.

## 9. Diseño responsivo

Puntos de quiebre: 640 y 1024 px. El escritorio es la referencia principal. En móvil: barra de navegación inferior de 5 elementos, tutor a pantalla completa, tarjetas apiladas, gráficos reducidos a lo esencial y hojas inferiores en lugar de paneles laterales. No es una versión comprimida del escritorio.

## 10. Criterios de aceptación de la Fase 1

La Fase 1 está lista cuando:

- El recorrido completo funciona sin errores: landing → registro → onboarding → dashboard → tutor → actividad → dashboard actualizado.
- Los cuatro modos del tutor responden con su comportamiento propio.
- Cambiar el idioma actualiza el 100 % de las pantallas incluidas.
- Todos los botones visibles hacen algo coherente; ninguna pantalla es un callejón sin salida.
- Los colores de texto cumplen contraste 4.5:1 y hay foco visible en todo elemento interactivo.
- Se ve bien en 375, 768 y 1280 px de ancho.
- No hay errores en la consola.

## 11. Fase 2 — Perfil de aprendizaje y laboratorio de programación

**Objetivo:** que el estudiante vea con claridad qué sabe, qué le falta y qué debe aprender después, y que practique programación con retroalimentación inmediata. Requiere la Fase 1 aprobada.

**Qué se activa en la navegación:** “Mi perfil” y “Laboratorios” (solo el laboratorio de programación; matemáticas y ciencias siguen como “Pronto”).

### 11.1 Mi perfil de aprendizaje

- Resumen superior: nivel, fortalezas, conceptos a reforzar y 3 recomendaciones personalizadas de Nexo.
- Dominio por concepto (0–100 %), historial de aprendizaje (últimas 10 sesiones) y errores frecuentes, cada uno con la acción “Practicar con Nexo”.
- Mapa de conocimiento en SVG con 14 a 18 nodos conectados en dos ramas: Matemáticas (ecuaciones lineales → factorización → funciones cuadráticas → …) y Programación (variables → condicionales → bucles → funciones → …).
- Estados visuales del nodo: dominado (menta), en progreso (azul), por reforzar (naranja) y bloqueado (gris con candado). Nunca uses solo el color: añade ícono o etiqueta.
- Al tocar un nodo se abre un panel con su dominio, prerrequisitos, errores frecuentes y el botón “Practicar con Nexo”, que abre el tutor ya contextualizado con ese concepto y el modo más adecuado.
- Todo se alimenta del estado de la Fase 1 y se actualiza al completar actividades (por ejemplo, “Funciones cuadráticas” en 48 %).

### 11.2 Laboratorio de programación

- Editor con numeración de líneas y resaltado de sintaxis hecho a mano (sin librerías externas) para JavaScript y Python.
- Botón “Ejecutar” y consola de salida. JavaScript se ejecuta de verdad en un iframe aislado (atributo `sandbox` con solo `allow-scripts`) que captura `console.log` y errores; Python usa salidas predefinidas por reto.
- 3 retos progresivos (por ejemplo: sumar números pares, contar vocales, invertir un texto) con casos de prueba visibles (✓ / ✗ y un mensaje de qué falló).
- Botón “Analizar con Nexo”: devuelve retroalimentación sobre el código (claridad, casos límite olvidados, posibles mejoras) aplicando las reglas pedagógicas: primero una pregunta guía, nunca la solución completa.
- Completar un reto otorga XP y actualiza el nodo correspondiente del mapa de conocimiento.

**Criterios de aceptación de la Fase 2**

- Todos los nodos del mapa se pueden recorrer con teclado y abren su panel.
- “Practicar con Nexo” abre el tutor con el concepto precargado.
- El código JavaScript se ejecuta y muestra su salida real; un error de sintaxis se muestra de forma comprensible, sin romper la página.
- Completar un reto actualiza XP, mapa y dashboard.
- La Fase 1 sigue funcionando sin cambios ni errores de consola.

## 12. Fase 3 — Laboratorios de matemáticas y ciencias, y gamificación

**Objetivo:** ampliar la práctica con laboratorios interactivos y motivar con un sistema de progreso que premie la comprensión, no el tiempo frente a la pantalla. Requiere la Fase 2 aprobada.

**Qué se activa:** “Laboratorios” (matemáticas y ciencias) y “Retos”.

### 12.1 Laboratorio de matemáticas

- Ecuaciones interactivas (lineales y cuadráticas) con controles deslizantes para las variables y una gráfica en SVG que cambia en tiempo real.
- Modo de resolución guiada: cada paso se revela solo después de responder una micropregunta; Nexo comenta el razonamiento, no solo el resultado.
- Botón “Llevar esto al tutor” que envía el problema actual a Nexo en el modo “Analiza mi error”.

### 12.2 Laboratorio de ciencias

- Simulación de proyectil: el estudiante ajusta ángulo y velocidad inicial, ve la trayectoria (una parábola) y la conecta con las funciones cuadráticas del laboratorio de matemáticas.
- Diagrama interactivo de la célula: cada parte se explica al tocarla, seguido de un minicuestionario de 4 preguntas.
- Ambos siguen el ciclo predecir → simular → comparar → explicar: antes de ejecutar, el estudiante anota qué cree que pasará.

### 12.3 Gamificación con propósito

- Pantalla “Retos” con 3 misiones diarias, 1 reto semanal, 12 logros (bloqueados y desbloqueados), hitos de progreso y contenido desbloqueable (laboratorios avanzados, personalización sobria del avatar).
- Curva de niveles clara (qué XP necesita cada nivel) y animaciones sobrias al subir de nivel.
- El XP premia aprendizaje real: corregir un error, explicar con palabras propias, completar un reto o avanzar un nodo del mapa. No premia clics ni minutos de uso.
- Sin cuentas regresivas agresivas ni castigos por perder una racha: si se rompe, Nexo propone retomar con una actividad corta.
- Debe sentirse como una herramienta de aprendizaje, no como un videojuego infantil.

**Criterios de aceptación de la Fase 3**

- Ambos laboratorios funcionan y reflejan los cambios de las variables en tiempo real.
- Completar misiones y laboratorios suma XP y desbloquea logros visibles en el dashboard.
- Los tres idiomas cubren todo lo nuevo.
- Las fases 1 y 2 siguen funcionando sin cambios ni errores de consola.

## 13. Fase 4 — Analíticas, Teacher Studio y pulido final

**Objetivo:** cerrar el ecosistema: que el estudiante entienda su evolución, que el docente entienda a su clase y que todo el producto se sienta cohesionado. Requiere la Fase 3 aprobada.

### 13.1 Progreso y analíticas del estudiante

- Pantalla “Progreso” con actividad semanal, dominio por tema, tiempo de estudio, habilidades adquiridas, mejoras respecto al mes anterior, historial de desempeño y áreas que requieren atención.
- Gráficos en SVG (líneas, barras y anillos de progreso) con título, leyenda y valores disponibles también como texto. Todos los datos rotulados como “Datos de demostración”.

### 13.2 Teacher Studio

Se accede desde la opción “Cambiar a vista docente” del menú de usuario y desde la selección de rol del registro. Usa el mismo sistema de diseño, con navegación propia.

Datos demo del docente: Prof. Camila Ortiz, “Colegio Demo”, aula “11-B Matemáticas” con 28 estudiantes ficticios. Ningún nombre ni dato debe parecer real.

- **Resumen docente:** indicadores de la clase, alertas y actividad reciente.
- **Aulas:** ver y crear aulas, con un código de acceso para que los estudiantes se unan.
- **Lista de estudiantes:** búsqueda, filtros por estado (al día, en riesgo, sin actividad) y acceso al perfil individual.
- **Perfil individual:** dominio por concepto, errores frecuentes y actividad reciente, con sugerencias de intervención.
- **Rendimiento de la clase:** distribución de niveles, dominio promedio por tema y un mapa de calor de estudiantes por concepto.
- **Detección de dificultades:** alertas con sentido pedagógico (por ejemplo, “9 de 28 estudiantes cambian el signo al hallar raíces”) y una actividad sugerida con el botón “Asignar a la clase”.
- **Generador de evaluaciones con IA:** formulario (tema, nivel, número de preguntas, tipo) que produce una vista previa editable de la evaluación (simulada).
- **Creación de tareas:** título, instrucciones, fecha de entrega y asignación a un aula.
- **Retos interactivos:** asignar a la clase actividades existentes, como la “Parábola interactiva”.
- **Reportes de progreso:** informe imprimible por clase o por estudiante, con botón “Exportar” (simulado, con confirmación).
- **Privacidad:** el docente solo ve a los estudiantes de sus propias aulas.

### 13.3 Pulido final

- Auditoría de internacionalización: ninguna cadena visible fuera de `translations`, en los tres idiomas.
- Auditoría de accesibilidad: contraste, teclado, foco, `aria-label` y `prefers-reduced-motion`.
- Consistencia visual: mismos tokens, radios, sombras y componentes en todas las pantallas; máximo 6 o 7 bloques principales por pantalla.
- Estados vacíos, de carga y de error redactados en los tres idiomas para cada pantalla.
- Revisión responsiva a 375, 768 y 1280 px de ancho.

**Criterios de aceptación de la Fase 4**

- El docente puede crear una tarea, asignarla y ver el rendimiento de la clase.
- El cambio entre vista estudiante y vista docente funciona sin perder el estado.
- Las fases 1, 2 y 3 siguen funcionando sin errores de consola.
- Al cerrar, entrega una guía de 10 líneas: cómo recorrer la demo y qué debe conectarse a servicios reales para producción (IA, autenticación, base de datos, moderación de contenido).

## 14. Criterios finales del proyecto completo

El proyecto está terminado cuando:

- Un estudiante nuevo completa el recorrido: crea su cuenta, hace el onboarding, recibe su perfil inicial, abre el tutor, completa una actividad, recibe retroalimentación personalizada y ve su progreso reflejado en el dashboard y en el mapa de conocimiento.
- La experiencia docente funciona de punta a punta: crear un aula, asignar una tarea y revisar el rendimiento.
- Español, English y Português cubren el 100 % de la interfaz, incluidos tutor, ejercicios y mensajes de error.
- Todos los botones visibles hacen algo coherente; ninguna pantalla es un callejón sin salida.
- Todo el texto cumple contraste 4.5:1 y toda la aplicación se maneja con teclado.
- Todos los datos simulados están rotulados como demostración.
- No hay errores en la consola y la primera carga tarda menos de 3 segundos.
- Visualmente: identidad consistente, jerarquía clara y ninguna pantalla saturada.

**Idea que debe comunicar todo el producto:** “Cada mente aprende diferente. NEXORA aprende contigo.”
