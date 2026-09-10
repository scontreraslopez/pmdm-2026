# T01 · Propuestas de cambio

> Documento de trabajo. Revisión completa de `T01.md` (238 líneas) para la edición 2026 del módulo.
> Fecha de revisión: **9 de septiembre de 2026**. Las referencias `L###` son líneas del `T01.md` actual.

**Leyenda:** ✅ correcto, no tocar · ✏️ retoque de redacción · ➕ ampliación de contenido · ⚠️ problema de fondo (error, duplicado o afirmación floja)

---

## 0. Resumen: qué haría sí o sí para mañana

Si solo hay tiempo para una pasada corta, estos son los ocho puntos:

| # | Dónde | Qué | Tipo |
| :-- | :-- | :-- | :-- |
| 1 | `L231` | `### Conclusión` → `## Conclusión` (el índice la lista como sección de primer nivel) | ⚠️ |
| 2 | `L26` + `L28` | Dos párrafos que dicen lo mismo, con el mismo arranque literal | ⚠️ |
| 3 | `L211` | "Los **desarrolles** multiplataforma…" → typo | ⚠️ |
| 4 | `L140` | "…del entorno móvil.**Sin** embargo" → falta el espacio | ⚠️ |
| 5 | `L221` / `L224` | El **mismo vídeo** (`Wib6pjJoFzc`) enlazado dos veces a tres líneas de distancia | ⚠️ |
| 6 | `L220` | El párrafo "Actualización 2025" ha caducado (ver §5.2, texto listo para pegar) | ⚠️ |
| 7 | `L123-128` | En "desarrollo nativo" **no aparece Jetpack Compose**, siendo la base de todo el curso | ➕ |
| 8 | `L83` | El párrafo de "código limpio ⇒ se alinea con RISC" no se sostiene (ver §3.2) | ⚠️ |

---

## 1. Cabecera e índice

**`L1` · Título** ✏️ [DONE]
`# T01-Tecnologías para aplicaciones en dispositivos móviles` no casa con el README nuevo, que usa `T01 · Tecnologías para dispositivos móviles`. Unificaría el separador `·` de un tirón en los 14 ficheros para que el índice del README y los títulos coincidan.

**`L3-22` · Índice** ✅ [DONE]
Las anclas están todas bien: GitHub se come los `**` de los encabezados en negrita y las comillas de "Scrummerfall", así que los enlaces funcionan. El único fallo es el de Conclusión, por el nivel de encabezado (punto 1 del resumen).

---

## 2. Metodologías de desarrollo

### 2.1 Entradilla · `L26` + `L28` ⚠️

**Son el mismo párrafo dos veces.** Los dos empiezan literalmente igual ("El desarrollo de aplicaciones móviles, como…") y los dos concluyen lo mismo: mismas etapas que cualquier software, lo que cambia es la metodología. Fusionar en uno.

Además: dices "sigue una serie de etapas bien definidas" pero no las enumeras hasta `L32`, ya dentro de Cascada, donde parecen propias de Waterfall. Sacaría la enumeración a la entradilla —análisis → diseño → desarrollo → pruebas → despliegue → mantenimiento— dejando claro que **esas etapas existen siempre; lo que cambia es el orden y el tamaño del lote**. Es la idea que sostiene toda la sección.

### 2.2 Modelo en Cascada · `L30-39` ✅➕

El texto está bien. Dos añadidos que dan mucho juego en clase:

- **El origen del modelo.** Royce (1970) describió el modelo secuencial puro *como ejemplo de lo que sale mal*, y la industria se quedó con el diagrama e ignoró el aviso. Es una anécdota que se les queda pegada.
- **Dónde sigue vivo.** "Hoy es poco práctico" vale para producto, pero Cascada **sigue siendo el modelo de la contratación pública y de los sectores regulados** (sanidad, aeronáutica, banca): alguien tiene que firmar un alcance cerrado antes de que el software exista. Ojo, que esto responde directamente a tu propia pregunta de `L39` — quizá te interese guardarlo como pista para la puesta en común y **no** escribirlo en el material.

**`L36-39` reflexión** ✅ — Buenas preguntas, la segunda especialmente.

### 2.3 Metodologías Ágiles · `L41-52` ✏️➕

**`L43`** ✏️ — El epígrafe es "Metodologías Ágiles (Scrum)" y solo se explica Scrum. Falta la línea que separa el paraguas de la implementación: **Agile son valores y principios (Manifiesto, 2001); Scrum, Kanban y XP son marcos concretos que los implementan.** Sin eso, salen creyendo que ágil *es* Scrum, y luego en `L58` aparece Kanban sin haberlo presentado nunca.

**`L45`** ➕ — El texto alternativo de la imagen promete "Sprints, roles y eventos", pero el texto no nombra ni un rol ni un evento. O bien añades la lista mínima (PO / Scrum Master / equipo · planning, daily, review, retro) o bien cambias el alt de la imagen. *Duda para ti: si esto ya lo dan en Proyecto o en Entornos de Desarrollo, lo dejaría en repaso de cinco minutos y no lo engordaría.*

**`L47-52` reflexión** ✏️ — Cuatro preguntas es mucho, y **la 1 y la 2 son la misma** vista del derecho y del revés (presupuesto cerrado ↔ "cheque en blanco"). Fusionaría esas dos y dejaría tres. La cuarta es la más rica y la que menos pista tiene: apunta a métricas de valor entregado, *Definition of Done* y demos por sprint.

### 2.4 Scrummerfall · `L54-65` ✅➕

Mi apartado favorito del tema: es honesto y es exactamente lo que se van a encontrar. Dos ampliaciones:

- **SAFe** merece una mención como el híbrido "oficial" de las grandes corporaciones (y como el más discutido del sector). Es el nombre que van a ver en ofertas de empleo.
- El patrón concreto que más van a sufrir es el **mini-waterfall dentro del sprint**: análisis el lunes, código hasta el jueves, pruebas el viernes a las 18:00. Nombrarlo les da un vocabulario para detectarlo.

El registro de "es harto probable que lo acabéis viviendo" es tu voz y funciona; lo dejaría.

### 2.5 Lo que falta en toda la sección ➕

**El ciclo de vida específicamente móvil.** Ahora mismo esta sección serviría igual para un módulo de web o de escritorio, y hay un puñado de restricciones que son propias de móvil y que cambian cómo se planifica:

- No puedes desplegar quince veces al día: hay **revisión de la store** (App Store sobre todo) entre tú y el usuario.
- **El usuario decide cuándo actualiza**, así que conviven versiones antiguas de tu app en producción durante meses.
- De ahí las herramientas del oficio: *release trains*, **canales de testing** (Play Internal/Closed testing, TestFlight), **despliegue por fases** (*staged rollout*) y **feature flags** para activar funcionalidad sin publicar una versión nueva.

Es la ampliación con más valor de toda la sección y enlaza directamente con **T12 (publicación)**. Con un párrafo corto y una lista basta.

---

## 3. Limitaciones de la ejecución en dispositivos móviles

**`L69` entradilla** ✅ — "No son meras limitaciones, sino las reglas del juego que definen una aplicación de calidad" es una buena frase de arranque.

### 3.1 Gestión de recursos · `L71-77` ✅➕

Correcto. Dices "usar las APIs correctas para tareas en segundo plano" sin nombrar ninguna, y son precisamente las que dan la cara en T10. Añadiría los nombres para que suenen: **Doze y App Standby**, los *buckets*, **WorkManager** para trabajo diferible y las restricciones a los *foreground services*. Sin desarrollarlo — solo para que cuando lleguen a T10 les suene de aquí.

### 3.2 Arquitectura del procesador · `L79-83` ⚠️

**Es el apartado más flojo del tema, por dos motivos.**

**a) El marco ya no es cierto.** "El escritorio es x86/CISC y el móvil es ARM/RISC" se rompió hace años: los Mac son ARM desde 2020 (Apple Silicon) y Windows tiene portátiles ARM desde 2024 (Snapdragon X). La frontera hoy no es escritorio/móvil.

**b) La conclusión de `L83` no se sostiene.** "Un código limpio, que descompone las tareas en pasos sencillos, se alineará mejor con la filosofía del hardware" — entre tu Kotlin y el ARM hay un compilador y **ART** (bytecode + JIT/AOT) tomando todas esas decisiones. Escribir sentencias cortas no te acerca a RISC. Si un alumno espabilado lo pregunta, no hay forma de defenderlo.

**Lo que sí es verdad y sí les sirve** es que la arquitectura les va a aparecer en sitios muy concretos:

- **ABIs**: `arm64-v8a` es lo que llevan los móviles reales; `x86_64` es lo que suele necesitar el emulador. Si una librería nativa no trae la ABI que toca, la app peta en un dispositivo y funciona en otro.
- El **Android App Bundle** entrega a cada dispositivo solo el `.so` de su arquitectura, y por eso el APK universal pesa más.
- **El emulador va mucho mejor si su arquitectura coincide con la de tu máquina** (en Mac con Apple Silicon, imagen ARM64; en PC Intel/AMD, imagen x86_64). Esto es puro consejo práctico de T00 y lo van a agradecer.
- Solo bajas a la arquitectura de verdad si usas el **NDK** (C/C++), y eso queda fuera del módulo.

**Texto propuesto para sustituir `L79-83`:**

> ### 2. La Arquitectura del Procesador: Un Mundo Diferente
>
> Los dispositivos móviles utilizan mayoritariamente procesadores con arquitectura **ARM**, basada en un juego de instrucciones reducido (**RISC**) y diseñada desde el principio para exprimir cada milivatio. Frente a ella, el escritorio ha sido tradicionalmente territorio de **x86/x64** (**CISC**). Esa frontera, eso sí, se está borrando: los Mac con Apple Silicon y los portátiles Windows con Snapdragon también son ARM.
>
> Como desarrolladores de aplicaciones no escribimos ensamblador —entre nuestro Kotlin y el procesador están el compilador y la máquina virtual **ART**, que se encargan de traducir y optimizar—, pero la arquitectura nos aparecerá en tres sitios muy concretos:
>
> * **Las ABIs.** Los dispositivos reales son `arm64-v8a`; los emuladores suelen ser `x86_64`. Una librería con código nativo que no incluya la ABI adecuada hará que la app falle en un dispositivo y funcione en otro.
> * **El tamaño de la descarga.** El **Android App Bundle** entrega a cada dispositivo únicamente el código nativo de su arquitectura, en lugar de un APK universal con todas dentro.
> * **El rendimiento del emulador.** Elige siempre una imagen del sistema de la misma arquitectura que tu ordenador (ARM64 en Mac con Apple Silicon, x86_64 en PC Intel/AMD); si no coinciden hay emulación por software y la diferencia de velocidad es brutal.

### 3.3 Conectividad intermitente · `L85-89` ✅➕

Muy bien planteado. Ampliaría en dos direcciones:

- **No es solo "hay red o no hay red".** También hay latencia alta, ancho de banda ridículo y **datos móviles que el usuario paga** (modo ahorro de datos). Diseñar para "conectado o desconectado" deja fuera el caso más frecuente: conectado pero mal.
- **Enlaza el *offline-first* con el curso**: es literalmente lo que van a construir en **T10** (Room como caché local) y **T11** (Retrofit como origen remoto). Decirlo aquí le da sentido a los dos temas.

### 3.4 Entorno de alta vulnerabilidad · `L91-95` ✅➕

Correcto. Le añadiría el punto que más falta les va a hacer este curso:

> **El cliente no es de fiar.** Un APK se puede descargar y descompilar. R8/ProGuard ofusca el código, pero **no lo protege**: cualquier clave de API, contraseña o secreto que escribas en la app se puede extraer. Todo lo que deba permanecer secreto vive en el servidor, nunca en el dispositivo.

Se lo van a saltar en T11/T12 con las claves de Firebase y de las APIs, así que cuanto antes lo oigan, mejor. Y de paso mencionaría el **sandbox por aplicación** y los **permisos en tiempo de ejecución** como las dos defensas que Android pone de serie.

### 3.5 Fragmentación · `L97-101` ➕ (la ampliación más urgente del tema)

El apartado sigue redactado como "hay muchos tamaños de pantalla", que era el discurso de hace diez años. **En 2026 la fragmentación tiene una noticia concreta y es muy buena para clase:**

> **Android 17** (API 37, publicado el 16 de junio de 2026) **ignora las restricciones de orientación, redimensionado y relación de aspecto** en pantallas de más de 600dp de ancho. Deja de tener efecto el atributo `screenOrientation` del manifiesto, las llamadas a `setRequestedOrientation()`, `resizeableActivity="false"` y los límites de *aspect ratio*. **No hay forma de desactivarlo** para apps que apunten a API 37, y Google Play exigirá ese nivel de API en agosto de 2027.
>
> Traducción: diseñar interfaces adaptables ha dejado de ser una buena práctica para convertirse en un requisito. Tu app se va a redimensionar y a rotar, la hayas preparado o no.

Con eso el apartado deja de ser abstracto. Y encaja el resto del panorama actual: plegables, tablets, ChromeOS, Android XR.

Un segundo eje que no aparece y que es muy real: **la fragmentación no es solo de versiones, es de fabricantes**. Las capas de personalización con gestión agresiva de batería matan servicios en segundo plano de forma distinta en cada marca. La web `dontkillmyapp.com` existe precisamente por eso y es una anécdota estupenda para cerrar el apartado.

### 3.6 La batalla por la relevancia · `L103-105` ✅➕

Buen apartado y buen cierre de la sección. Ampliaciones opcionales:

- El **tamaño de la app** como factor de conversión, y cómo el App Bundle ayuda.
- El **cambio regulatorio europeo (DMA)**: tiendas alternativas y navegadores de terceros en iOS/Android en la UE. Es el mayor cambio del panorama de distribución en años, aunque quizá encaje mejor en T12; aquí bastaría una frase.

---

## 4. Tecnologías disponibles

**`L109-111` entradilla** ✅

**`L113-114` vídeo** ✏️ — El enlace está puesto como URL desnuda `[url](url)`. Le pondría título descriptivo, y comprobaría antes de clase que el vídeo sigue vigente (los resúmenes de "opciones actuales" envejecen fatal).

### 4.1 Desarrollo nativo · `L120-137` ➕⚠️

**`L123-128`** ➕ — **Falta el toolkit de UI, que es lo más importante de la ficha.** Pones lenguaje e IDE, pero no cómo se construye la interfaz — y el curso entero (T03 a T09) va de eso. Debería aparecer el par:

- **Android:** Vistas XML (clásico) → **Jetpack Compose** (declarativo, el recomendado y el que usaremos).
- **iOS:** UIKit (clásico) → **SwiftUI** (declarativo).

Y con ello la idea de fondo: **el cambio de paradigma de imperativo a declarativo** (describes cómo debe verse la UI para un estado dado, en lugar de manipular la vista paso a paso). Es el concepto que les va a costar en T03-T04, y presentarlo aquí, cuando aún no hay código de por medio, es gratis. Nota didáctica: que ambas plataformas hayan hecho el mismo viaje a la vez es el mejor argumento de que no es una moda de Google.

**`L124` "Java (legacy)"** ✏️ — Matizaría. Java no está muerto: hay muchísimo código Java en producción y el SDK de Android sigue siendo interoperable. "Legacy" en el sentido de *no es donde empieza un proyecto nuevo desde 2019*, no en el de *ya no existe*.

**`L132-137` ventajas** ⚠️ — Cuatro ventajas con ✅ y **ningún inconveniente**. El coste (dos equipos, dos bases de código, dos ciclos de publicación) aparece de pasada en `L130` y en la tabla, pero visualmente esto queda como publicidad. Añadiría dos o tres ❌ para equilibrar; si no, la elección de "nativo" para el curso parece una conclusión ya escrita.

### 4.2 Estrategias multiplataforma · `L139-152`

**`L140`** ⚠️ — Falta el espacio en "entorno móvil.Sin embargo". El paralelismo con el WORA de Java está muy bien traído y la imagen de `L142` lo remata.

**`L144-146` híbrido / WebView** ✏️➕

- "un motor de navegador **sin chrome**" es un juego de palabras que en un tema de Android va a leerse como "sin Google Chrome". Cambiaría a "sin la interfaz del navegador (barra de direcciones, pestañas, botones)".
- **Actualizar los ejemplos.** Apache Cordova no está archivado formalmente, pero está en mantenimiento y su ecosistema se ha ido apagando (App Center cerró en marzo de 2025; Ionic dejó de vender sus servicios comerciales en febrero de 2025 y Appflow cierra a finales de 2027). **Ionic ya no usa Cordova: usa Capacitor desde 2019.** Dejaría Cordova como referencia histórica y pondría **Capacitor** como el ejemplo vivo.

**`L148-150` compilado / renderizado nativo** ⚠️ — Bien explicado, pero los dos ejemplos técnicos han caducado:

- **React Native ya no tiene "puente".** La *New Architecture* (Fabric + JSI + TurboModules) es la de por defecto desde la 0.76 (2024), el *bridge* clásico se eliminó en la 0.82 y desde la 0.86 (junio de 2026) los proyectos nuevos nacen *bridgeless*. Comunicación directa JS↔C++, sin serializar JSON entre hilos.
- **Flutter ya no renderiza con Skia**, sino con **Impeller** (por defecto en iOS y Android; en Android 10+ Skia ya ni siquiera está disponible como alternativa). Esto afecta también a `L200`, donde vuelves a describir Skia como el motor de Flutter.

### 4.3 Web móvil y PWA · `L154-160` ✅

El apartado está muy bien matizado, y el párrafo sobre **descubribilidad** —que el "añadir a pantalla de inicio" nadie lo entiende— es de lo mejor del tema. Como actualización menor: Safari admite notificaciones push web desde iOS 16.4 (2023), así que "las PWA no tienen push en iPhone" ya no vale como argumento.

### 4.4 Tabla comparativa · `L162-175` ✏️

La tabla funciona muy bien como resumen visual. Tres matices:

- **"Multiplataforma" mete en el mismo saco a Flutter, React Native y KMP**, y sus perfiles son muy distintos: una app con UI 100% nativa vía KMP no tiene el mismo techo de rendimiento ni los mismos problemas de UX que una WebView. Una nota al pie lo resuelve sin partir la tabla.
- **PWA · Rendimiento "⭐⭐ Bajo"** es duro para 2026, con WebAssembly y WebGPU por medio. Yo lo subiría a medio con matices.
- **PWA · Acceso a novedades del SO "N/A (no depende del SO)"** no es exacto: depende del navegador *y* del SO (justo el caso de iOS es el ejemplo canónico). Y **"Escalabilidad ⚠️ Cuidado"** es ambiguo — ¿escala mal el producto, el equipo o el código? Concretaría o quitaría la fila.

---

## 5. Qué estudiaremos en este módulo

**`L179-181`** ✅

### 5.1 ¿Por qué nativo con Kotlin? · `L183-189` ✏️➕

Los puntos 1 y 2 están bien. **El 3 se queda a medias**: "Kotlin es el lenguaje preferido para Android y la base de KMP" — y ahí termina, sin cerrar el argumento. El cierre es: *aprender Kotlin y Compose ahora te deja la puerta abierta a KMP y Compose Multiplatform después, sin cambiar de lenguaje ni de toolkit de UI.* Nativo aquí no es la alternativa a multiplataforma: es el camino de entrada.

Añadiría un cuarto punto: **el conocimiento nativo es transferible**. Cualquier framework multiplataforma acaba obligándote a tocar el proyecto Android o iOS —permisos, manifiesto, firma, publicación, un plugin que falta—, y ahí quien sabe nativo no se bloquea. Es el mismo argumento que ya haces en `L211`, así que quedaría reforzado.

### 5.2 Flutter y KMP · `L191-227`

**`L199` Dart / Hot Reload** ✏️ — El *Hot Reload* no es exactamente "una ventaja del lenguaje Dart", es una capacidad del framework y su toolchain. Matiz menor, pero si alguien pregunta por qué Kotlin no lo tiene, la respuesta se enreda. Y de hecho Compose tiene **previews y Live Edit**, así que conviene no vender el hot reload como exclusivo.

**`L200` Skia** ⚠️ — Sustituir por **Impeller** (ver §4.2).

**`L203-209` cuándo usar Flutter** ✅ — Nada que objetar.

**`L211`** ⚠️ — Typo: "Los **desarrolles** multiplataforma con la experiencia y en particular los buenos, son aquellos que…". La frase además va muy trabada. Propuesta:

> **La experiencia importa:** los buenos desarrolladores multiplataforma son, casi siempre, los que además **entienden cómo funcionan los sistemas nativos por debajo**. Conocer las bases de Android e iOS es una ventaja enorme incluso si acabas especializándote en Flutter.

**`L213-221` estado de KMP** ⚠️ — El párrafo "Actualización 2025" ha caducado: anunciaba que la web llegaría a beta "durante este año", y en 2026 hay que dar el resultado. **Texto propuesto para sustituir `L220-221`:**

> **Actualización 2026:** KMP y Compose Multiplatform han seguido consolidándose. Al nivel 1 —compartir la lógica de negocio— se le ha sumado el nivel 2 —compartir también la interfaz— con **Compose Multiplatform**, ya **estable en Android, iOS y escritorio**. El objetivo web (Kotlin/Wasm) sigue en **Beta**: utilizable, pero aún no al nivel de las demás plataformas. Las versiones de referencia a día de hoy son Kotlin 2.4.20 y Compose Multiplatform 1.12.0.
>
> El caso de adopción más llamativo del último año: **Sony rehízo su aplicación Sound Connect con Compose Multiplatform, sustituyendo a React Native.** Que una migración vaya en esa dirección dice bastante del momento del ecosistema.

**`L217` empresas** ➕ — "Netflix, VMWare y Forbes" sigue siendo válido; añadir Sony le da un ejemplo de 2026.

**`L221` + `L224`** ⚠️ — **El mismo vídeo enlazado dos veces** (`Wib6pjJoFzc`, keynote de KotlinConf) con dos textos distintos y tres líneas de separación. Dejaría uno solo, y actualizaría al keynote de 2026 si te sirve mejor.

**`L226-227` artículo de devexperto** ✏️ — Comprobar la fecha antes de clase: un "Flutter vs Kotlin" de hace cuatro o cinco años hoy despista más que ayuda, sobre todo en la parte de KMP.

---

## 6. Conclusión · `L231-237`

**`L231`** ⚠️ — `### Conclusión` debe ser `##`. Ahora cuelga jerárquicamente de "¿Qué Estudiaremos en Este Módulo?" mientras que el índice la presenta como sección propia.

**`L233-237`** ✅➕ — Cerrar con los resultados de aprendizaje del 0489 está muy bien. Le añadiría dos líneas de transición hacia lo siguiente ("en T02 empezamos con Kotlin, y en T03 con el primer proyecto en Android Studio"), que es lo que van a preguntar al salir de clase.

---

## 7. Cuestiones transversales

### 7.1 Formato inconsistente de las reflexiones ✏️

Conviven dos formatos distintos:

- En Metodologías: `**Reflexión:**` seguido de lista de preguntas (`L36`, `L47`, `L62`).
- En Limitaciones: `*Pregunta de reflexión: …*` en cursiva, suelta dentro del texto (`L75`, `L89`, `L95`).

Unificaría a uno solo. Si usas *callouts* de GitHub (`> [!NOTE]`, `> [!TIP]`) como ya haces en el README, quedarían destacadas visualmente y serían fáciles de localizar mientras das clase.

### 7.2 Reflexiones que faltan ➕

Las limitaciones **2 (arquitectura), 5 (fragmentación) y 6 (relevancia)** no tienen pregunta, mientras que 1, 3 y 4 sí. Tres propuestas:

- **(2) Arquitectura:** *¿Por qué creéis que el emulador de Android va lento en unos ordenadores y fluido en otros, si la app es exactamente la misma?*
- **(5) Fragmentación:** *¿Cuántos móviles Android distintos hay entre los que estáis en esta clase? ¿Y cuántas versiones de Android? Probemos a contarlo ahora mismo.* (Sale un histograma real en dos minutos y el concepto queda clavado.)
- **(6) Relevancia:** *¿Cuál fue la última app que instalasteis y por qué? ¿Cuántas de las que tenéis instaladas habéis abierto esta semana?*

### 7.3 No hay actividad evaluable ⚠️

Todos los temas con carga práctica cierran con ejercicios y entrega (T02, T03, T04, T05, T07, T11, T12). **T01 no tiene ninguna**: solo preguntas de reflexión para debate oral, que no dejan evidencia.

Y resulta que el primer resultado de aprendizaje del módulo es literalmente **"evaluar las tecnologías disponibles"** (lo citas tú en `L235`). Propuesta de actividad corta y muy alineada con ese RA:

> **Ejercicio T01.** Se presentan tres encargos ficticios: (a) una app de fichaje para los 40 empleados de una empresa, con lectura de NFC; (b) el MVP de una startup que necesita estar en iOS y Android en tres meses; (c) el catálogo online de una tienda de barrio. Para cada uno, elige una estrategia de desarrollo (nativa, multiplataforma, PWA o web *responsive*) y **justifica la decisión en 5-10 líneas** apoyándote en la tabla comparativa del tema. Se valora el razonamiento, no la respuesta: hay más de una defendible.

Se corrige rápido, obliga a releer el tema y les hace usar la tabla en lugar de mirarla.

### 7.4 Falta la IA en el panorama tecnológico ➕

El README de 2026 le dedica media página al uso de IA, pero en "Tecnologías disponibles" no aparece por ningún lado. Dos ángulos, y el segundo es el que aporta contenido de verdad:

1. **La IA como herramienta de desarrollo** (Gemini en Android Studio, asistentes de código). Se puede resolver con un enlace al README y no repetir el discurso.
2. **La IA *dentro* del dispositivo** — y aquí sí hay tema: modelos ejecutándose en local (Gemini Nano, ML Kit GenAI) sin enviar datos a ningún servidor. Es un ejemplo perfecto de **capacidad que solo tienes desde código nativo**, y refuerza justo el argumento del punto 6 sobre el "valor añadido innegable" frente a una web móvil.

### 7.5 Repaso de enlaces antes de clase ✏️

Cuatro enlaces externos conviene abrirlos antes de mañana: el vídeo resumen de `L114`, los dos recursos de `L146` y `L160`, y el artículo de devexperto de `L227`. Los enlaces desnudos (`L114`, `L224`, `L227`) los pondría con título descriptivo, por accesibilidad y porque el PDF exportado queda mejor.

---

## 8. Datos verificados el 9/9/2026 (para copiar sin miedo)

| Dato | Estado |
| :-- | :-- |
| Compose Multiplatform | Estable en Android, iOS y escritorio; **web en Beta** |
| Versiones actuales | Kotlin **2.4.20** · Compose Multiplatform **1.12.0** (agosto 2026) |
| Android 17 | API **37**, publicado el **16 de junio de 2026** |
| Restricciones de orientación/redimensionado | Ignoradas en pantallas >600dp, **sin opt-out**; Play exigirá API 37 en **agosto de 2027** |
| React Native | *New Architecture* por defecto desde 0.76; *bridge* eliminado en 0.82; *bridgeless* total en 0.86 (junio 2026) |
| Flutter | **Impeller** por defecto en iOS y Android; Skia ya no disponible en Android 10+ |
| Cordova / Ionic | Cordova en mantenimiento; **Ionic usa Capacitor** desde 2019; App Center cerró en marzo de 2025 |
| Sony | Migró Sound Connect de React Native a **Compose Multiplatform** |

**Por verificar antes de citarlo:** se ha comentado que Google usa KMP en apps de Workspace (Docs), pero no lo he confirmado con fuente primaria — no lo metería en el material sin comprobarlo.

**Fuentes:**

- [Compose Multiplatform · kotlinlang.org](https://kotlinlang.org/compose-multiplatform/)
- [Compose Multiplatform 1.12.0 · JetBrains Blog](https://blog.jetbrains.com/kotlin/2026/08/compose-multiplatform-1-12-0/)
- [Restrictions on orientation and resizability are ignored · Android Developers](https://developer.android.com/about/versions/17/changes/ff-restrictions-ignored)
- [Prepare your app for the resizability and orientation changes in Android 17](https://developer.android.com/blog/posts/prepare-your-app-for-the-resizability-and-orientation-changes-in-android-17)
- [Impeller rendering engine · Flutter docs](https://docs.flutter.dev/perf/impeller)
- [Ionic isn't Cordova Anymore · Ionic Blog](https://ionic.io/blog/ionic-isnt-cordova-anymore)

---

## 9. Checklist de aplicación

**Correcciones (5 minutos):**

- [x] `L1` · Título con separador `·`, igual que el README (aplicado también a T00-T13)
- [ ] `L26`/`L28` · Fusionar los dos párrafos duplicados
- [ ] `L140` · Espacio en "móvil.Sin embargo"
- [ ] `L211` · Typo "desarrolles" y reescritura de la frase
- [ ] `L221`/`L224` · Eliminar el vídeo duplicado
- [x] `L231` · `### Conclusión` → `##`

**Actualización 2026 (30 minutos):**

- [ ] `L220-221` · Párrafo de KMP/CMP (texto propuesto en §5.2)
- [ ] `L79-83` · Apartado de arquitectura (texto propuesto en §3.2)
- [ ] `L97-101` · Fragmentación con Android 17 (§3.5)
- [ ] `L123-128` · Jetpack Compose y SwiftUI en la ficha de nativo (§4.1)
- [ ] `L144-150` · Capacitor, Impeller, React Native sin bridge (§4.2)
- [ ] `L200` · Skia → Impeller

**Mejoras (cuando haya hueco):**

- [ ] Ciclo de vida móvil: stores, rollout por fases, feature flags (§2.5)
- [ ] Agile ≠ Scrum; roles y eventos (§2.3)
- [ ] "El cliente no es de fiar": secretos fuera del APK (§3.4)
- [ ] Unificar el formato de las reflexiones (§7.1)
- [ ] Añadir reflexión a las limitaciones 2, 5 y 6 (§7.2)
- [ ] Ejercicio evaluable de elección de tecnología (§7.3)
- [ ] IA en el dispositivo como capacidad nativa (§7.4)
- [ ] Inconvenientes del desarrollo nativo, para equilibrar (§4.1)
- [ ] Matices de la tabla comparativa (§4.4)
- [ ] Revisar los cuatro enlaces externos (§7.5)
