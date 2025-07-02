[<< Sesión Anterior](./01-SDLC.md) | [Volver al Índice Principal](../README.md) | **Sesión Siguiente >>** [03-SAST-DAST.md](./03-SAST-DAST.md)

---

## Sesión 2: Fundamentos de la Programación Segura

### Resumen del Tópico

Este tópico cubre los principios y prácticas esenciales para prevenir la introducción de vulnerabilidades en el código. Cubre conceptos clave como la tríada CIA (Confidencialidad, Integridad, Disponibilidad), el principio de mínimo privilegio, y la defensa en profundidad. Se enfoca en la importancia crítica de la validación de todas las entradas de usuario y la codificación de las salidas para prevenir ataques de inyección.

---

### Diálogo de Estudio: Alex y Sofía

**(Intro - Sonido de la videollamada, Sofía toma un sorbo de café)**

**Alex:** Muy bien, Sofía, entremos al **Capítulo 2: Fundamentos de la Programación Segura**. Si el capítulo anterior fue el "dónde" y el "cuándo" de la seguridad, este es el "qué" y el "porqué". Son los principios básicos que, si los interiorizas, te pondrán por delante del 90% de los problemas.

**Sofía:** Genial. El manual arranca con dos tríadas: CIA y AAA. Siempre las veo juntas, pero a veces las confundo.

**Alex:** Es una confusión común. Piénsalo así: la **Tríada CIA** son los *objetivos* de la seguridad, el resultado que queremos lograr.
* **Confidencialidad:** Es la protección de los datos contra la divulgación no autorizada. En simple, que solo la gente autorizada pueda ver la información, tanto si está guardada en un disco como si viaja por la red.
* **Integridad:** Es asegurar que los datos no sean alterados de manera indebida. Queremos garantizar que la información sea exacta y completa.
* **Disponibilidad:** Es garantizar que los usuarios autorizados tengan acceso a la información y a los servicios cuando lo necesiten. De nada sirve tener los datos más seguros del mundo si el sistema está caído y nadie puede usarlos.

**Sofía:** Ok, objetivos: confidencialidad, integridad, disponibilidad. ¿Y la Tríada AAA?

**Alex:** La **Tríada AAA** son los *mecanismos* para alcanzar esos objetivos.
* **Autenticación:** Es el proceso de verificar la identidad de un usuario, proceso o dispositivo. Es el "¿Quién eres?".
* **Autorización:** Una vez que sabemos quién eres, este es el proceso para determinar si tienes permiso para acceder a un recurso o realizar una acción. Es el "¿Qué puedes hacer?".
* **Auditoría (Accounting):** Es el registro de las acciones que realizas para poder rastrear la actividad y asignar responsabilidades. Es el "¿Qué hiciste?".

**Sofía:** Eso lo deja mucho más claro. El manual luego lista una serie de principios clave. ¿Cuáles son los más importantes en la práctica?

**Alex:** Yo me centraría en estos, que son los que te salvan el día a día:
1.  **Principio de Mínimo Privilegio:** Lo mencionamos en el capítulo anterior, pero vale la pena repetirlo. Otorga solo los privilegios mínimos necesarios para realizar una función. Esto limita enormemente el daño potencial si un componente es vulnerado.
2.  **Defensa en Profundidad:** No dependas de una sola capa de seguridad. Implementa múltiples controles, de modo que si uno falla, otros puedan seguir protegiendo tus activos.
3.  **No Confiar en la Entrada del Usuario (Zero Trust Input):** Considera toda entrada de fuentes externas como no confiable y valídala rigurosamente antes de procesarla.
4.  **Seguridad por Defecto (Fail-Safe):** Diseña los sistemas para que, en caso de un fallo, caigan en un estado seguro. El ejemplo clásico es un control de acceso: si falla, debe denegar el acceso por defecto, no permitirlo.
5.  **Simplicidad (Keep it Simple):** Los diseños complejos son más difíciles de implementar y verificar, y más propensos a errores.

**Sofía:** El manual también menciona algo que *no* es un principio válido: la Seguridad a Través de la Oscuridad.

**Alex:** ¡Exacto! Y es un punto crucial. Confiar en que tu diseño o algoritmo es secreto como principal método de seguridad es una pésima práctica. Los mecanismos de seguridad deben ser robustos incluso si un atacante conoce perfectamente cómo funcionan por dentro.

---
**Sofía:** Ok, el principio de "No Confiar en la Entrada del Usuario" parece el más accionable a nivel de código y conecta directamente con la siguiente sección: **Validación de Entradas y Salidas.**

**Alex:** Totalmente. La validación de entradas es una de las defensas más críticas. ¿Por qué? Porque previene ataques de inyección (SQL, XSS, Command Injection), desbordamientos de búfer y otros problemas causados por datos maliciosos o malformados.
* **¿Qué validar?** Todo: el tipo de dato, la longitud, el formato, el rango y los caracteres permitidos.
* **¿Cómo hacerlo?** Aquí el manual da varias claves. La más importante es usar **Listas Blancas (Allow Lists)**. Es decir, especificar exactamente qué entradas son permitidas y rechazar todo lo demás. Es mucho más seguro que las listas negras, que intentan prohibir patrones de ataque conocidos, porque es imposible predecir todos los patrones nuevos que inventarán los atacantes.
* Y como dijimos antes, **siempre validar en el lado del servidor**. La validación en el lado del cliente es fácilmente eludible por un atacante.

**Sofía:** Y después de validar la entrada, tenemos que preocuparnos por la salida. ¿Qué es la **Codificación de Salidas**?

**Alex:** La codificación de salidas (o sanitización) previene principalmente los ataques de Cross-Site Scripting (XSS). Su objetivo es asegurar que los datos que se muestran en un navegador sean interpretados como texto plano y no como código ejecutable. Por ejemplo, si un usuario introduce el texto `<script>`, antes de mostrarlo en la página, lo codificas a `&lt;script&gt;`. El navegador mostrará el texto `<script>`, pero no lo ejecutará. Es crucial que esta codificación sea sensible al contexto: la forma de codificar para HTML es diferente que para un atributo de URL o para código JavaScript.

---
**Sofía:** Entendido. La sección 2.3 habla de **Prácticas de Codificación Segura** de OWASP y SANS. ¿Qué destaca el manual aquí?

**Alex:** Básicamente, agrupa todo lo que hemos hablado en una lista de buenas prácticas. Menciona los **Controles Proactivos de OWASP**. Algunos puntos clave que resalta el manual son:
* **Aprovechar Frameworks y Librerías de Seguridad:** No intentes reinventar la rueda para cosas como la protección contra CSRF o la gestión de sesiones.
* **Asegurar el Acceso a la Base de Datos:** Usa consultas parametrizadas para prevenir Inyección SQL y aplica el principio de mínimo privilegio a las cuentas de la base de datos.
* **Proteger los Datos en Todas Partes:** Esto significa usar cifrado tanto en tránsito (cuando viajan por la red) como en reposo (cuando están almacenados).
* **Manejar Todos los Errores y Excepciones:** Y hacerlo de forma segura, sin revelar información sensible, como trazas de la pila (stack traces), en los mensajes de error.

**Sofía:** ¿Y el CWE/SANS Top 25?

**Alex:** El **CWE/SANS Top 25** es una lista de los errores de software más peligrosos y extendidos. Es más granular que el OWASP Top 10. Se enfoca en debilidades específicas como Desbordamiento de Búfer (CWE-120) o el Uso de Credenciales Hardcodeadas (CWE-798). La recomendación general del manual es conocer estas listas y enfocarse en eliminar o mitigar las amenazas que identifican.

---
**Sofía:** Perfecto. Creo que estoy lista para las preguntas de examen del capítulo.

**Alex:** ¡Vamos a ello! Primera: **P: Describa la Tríada CIA y su importancia en la seguridad del software.**

**Sofía:** La Tríada CIA consiste en Confidencialidad (proteger datos de divulgación no autorizada), Integridad (asegurar que los datos no sean alterados indebidamente) y Disponibilidad (garantizar el acceso a datos y servicios para usuarios autorizados). Es fundamental porque define los objetivos básicos de seguridad que cualquier software debe alcanzar.

**Alex:** ¡Correcto! Siguiente: **P: ¿Qué es el principio de mínimo privilegio y por qué es importante para la programación segura?**

**Sofía:** El principio de mínimo privilegio establece que a un componente o usuario solo se le deben otorgar los permisos estrictamente necesarios para realizar su tarea. Es importante porque si ese componente es comprometido, el daño potencial se limita a los permisos que tenía.

**Alex:** ¡Excelente! Tercera: **P: Explique la diferencia entre listas blancas y listas negras en la validación de entradas y cuál es preferible.**

**Sofía:** Las listas blancas especifican explícitamente qué entradas son permitidas, rechazando todo lo demás. Las listas negras especifican qué está prohibido, permitiendo el resto. Las listas blancas son preferibles porque son más restrictivas y es menos probable que omitan patrones de ataque nuevos o desconocidos.

**Alex:** ¡Muy bien explicado! Última pregunta: **P: ¿Por qué la validación de entradas debe realizarse principalmente en el lado del servidor?**

**Sofía:** Porque la validación en el lado del cliente puede ser eludida fácilmente por un atacante, por ejemplo, desactivando JavaScript o manipulando la solicitud HTTP. La validación en el lado del servidor es la única forma confiable de asegurar que datos maliciosos no sean procesados por la aplicación.

**Alex:** ¡Fantástico, Sofía! Has clavado el capítulo 2. Estos fundamentos son la base sobre la que se construye todo lo demás. ¿Lista para hablar de cómo encontramos los errores que se nos escapan? Hablemos de SAST y DAST.

**Sofía:** ¡Adelante!

---
[<< Sesión Anterior](./01-SDLC.md) | [Volver al Índice Principal](../README.md) | **Sesión Siguiente >>** [03-SAST-DAST.md](./03-SAST-DAST.md)