[<< Sesión Anterior](./02-Fundamentos.md) | [Volver al Índice Principal](../README.md) | **Sesión Siguiente >>** [04-Web-OWASP.md](./04-Web-OWASP.md)

---

## Sesión 3: Pruebas Estáticas, Dinámicas e Interactivas (SAST, DAST, IAST)

### Resumen del Tópico

Este tema detalla las metodologías de prueba de seguridad más comunes. Explica el Análisis Estático (SAST), que revisa el código fuente en busca de fallos ("caja blanca"), y el Análisis Dinámico (DAST), que prueba la aplicación en ejecución simulando ataques ("caja negra"). Se comparan sus ventajas, desventajas y su lugar en el SDLC.

---

### Diálogo de Estudio: Alex y Sofía

**(Intro - Sonido de la videollamada, Alex toma la palabra)**

**Alex:** Muy bien, Sofía, entramos en el **Capítulo 3: Pruebas Estáticas y Dinámicas de Aplicaciones Seguras**. Ya hemos hablado de la importancia de la fase de verificación, pero ahora vamos a ver las herramientas y metodologías específicas que usamos. Este capítulo es el corazón técnico de la detección de vulnerabilidades.

**Sofía:** Genial. El manual empieza con **SAST (Static Application Security Testing)**. Lo describiste antes como un "corrector gramatical para el código". ¿Podemos profundizar en cómo funciona y sus pros y contras?

**Alex:** Por supuesto. SAST es una metodología de "caja blanca". Esto significa que analiza el código fuente, el bytecode o los binarios de una aplicación sin ejecutarla.
* **¿Cómo funciona?** Las herramientas SAST examinan el código en busca de patrones que se sabe que son inseguros. Buscan fallos de seguridad conocidos o violaciones de las políticas de codificación segura que hemos definido. Pueden identificar cosas como posibles inyecciones SQL, desbordamientos de búfer o vulnerabilidades de entidad externa XML (XXE).

**Sofía:** Suena muy útil para la detección temprana. El manual lista varias ventajas.

**Alex:** Sí, y son muy importantes:
* **Detección Temprana:** Es su mayor fortaleza. Puede integrarse directamente en el IDE del desarrollador, permitiendo corregir vulnerabilidades cuando es mucho más barato y rápido hacerlo.
* **Cobertura del Código:** Tiene el potencial de analizar el 100% de la base de código a la que le das acceso.
* **No Requiere una Aplicación en Ejecución:** Puedes realizar las pruebas sin necesidad de tener un entorno de pruebas funcional, lo cual es una gran ventaja en las primeras etapas.
* **Mejora de la Calidad del Código:** Ayuda a los desarrolladores a aprender y aplicar prácticas de codificación segura al ver los errores que cometen.

**Sofía:** Pero también tiene desventajas, ¿verdad? Mencionaste los falsos positivos.

**Alex:** Exacto. Es su talón de Aquiles.
* **Falsos Positivos:** Tiende a generar un número significativo de falsos positivos porque no tiene el contexto de la ejecución. Puede marcar un código que parece vulnerable de forma aislada, pero que en la práctica no lo es debido a otros controles en la aplicación.
* **Dependencia del Lenguaje:** Las herramientas SAST son específicas para los lenguajes de programación y los frameworks que se utilizan.
* **No Detecta Vulnerabilidades en Tiempo de Ejecución:** Es ciego a los errores de configuración del entorno o a las vulnerabilidades que solo se manifiestan cuando la aplicación está en funcionamiento.

---
**Sofía:** De acuerdo, eso tiene sentido. Ahora, contrastémoslo con **DAST (Dynamic Application Security Testing)**.

**Alex:** DAST es el polo opuesto. Es una metodología de "caja negra". No necesita acceso al código fuente. En su lugar, examina la aplicación mientras está en su estado de ejecución, enviándole entradas maliciosas simuladas y observando su comportamiento y respuestas para identificar vulnerabilidades.
* **¿Cómo funciona?** Simula ataques externos. Busca vulnerabilidades como Cross-Site Scripting (XSS), inyección SQL, fallos de autenticación, problemas de cifrado y, muy importante, configuraciones incorrectas del servidor.

**Sofía:** Entonces, sus ventajas y desventajas deberían ser casi un espejo de las de SAST.

**Alex:** En gran medida, sí.
* **Ventajas de DAST:**
    * **Menos Falsos Positivos:** Generalmente produce menos falsos positivos porque prueba la aplicación en un estado operativo real. Si encuentra algo, es muy probable que sea una vulnerabilidad explotable.
    * **Independiente del Lenguaje:** No le importa si la aplicación está hecha en Java, .NET o Ruby, ya que la prueba desde fuera.
    * **Detecta Vulnerabilidades en Tiempo de Ejecución:** Su gran fortaleza. Puede encontrar problemas de configuración del servidor, problemas de sesión y vulnerabilidades que solo aparecen cuando la aplicación interactúa con otros componentes.
* **Desventajas de DAST:**
    * **Detección Tardía:** Se realiza más tarde en el SDLC, cuando ya hay una aplicación funcionando, lo que puede hacer que la remediación sea más costosa y compleja.
    * **No Cubre Todo el Código:** Solo puede probar las partes de la aplicación que son accesibles y ejecutables a través de sus interfaces externas.
    * **Puede ser Más Lento:** Las pruebas dinámicas, que navegan por la aplicación, pueden llevar más tiempo que un análisis estático.

**Sofía:** Y el manual menciona un tercer tipo, **IAST**. El híbrido.

**Alex:** Sí, **IAST (Interactive Application Security Testing)**. Combina elementos de SAST y DAST. Opera desde *dentro* de la aplicación en ejecución, normalmente a través de agentes instrumentados. Mientras los probadores (manuales o automatizados con DAST) usan la aplicación, el agente IAST monitorea el flujo de datos y el código que se ejecuta en tiempo real.
* **Ventaja Principal:** Al tener acceso tanto al código como al contexto de ejecución, puede ser mucho más preciso, con menos falsos positivos. Puede rastrear cómo una entrada maliciosa fluye a través de la aplicación hasta el punto exacto del código donde causa un problema.
* **Desventaja Principal:** La instrumentación puede afectar el rendimiento de la aplicación durante las pruebas y su implementación puede ser más costosa y compleja.

---
**Sofía:** La tabla comparativa de la sección 3.4 es muy útil para resumir. Repasémosla rápidamente.

**Alex:** Buena idea.
* **Qué escanea:** SAST escanea el código fuente o binarios; DAST escanea la aplicación en ejecución.
* **Cuándo escanea:** SAST lo hace temprano en el SDLC (codificación); DAST lo hace tarde (pruebas, post-despliegue).
* **Acceso al código:** SAST lo requiere; DAST no lo requiere.
* **Falsos positivos:** SAST es más propenso; DAST es menos propenso.
* **Vulnerabilidades típicas:** SAST encuentra errores de codificación; DAST encuentra problemas de configuración y vulnerabilidades explotables en tiempo real.

---
**Sofía:** Y para terminar el capítulo, el manual menciona algunas herramientas. Es bueno ponerles nombre.

**Alex:** Totalmente. Es importante saber que hay opciones tanto de código abierto como comerciales.
* **Herramientas SAST Open Source:** El manual menciona varias, como **Bandit** para Python, **Brakeman** para Ruby on Rails, y la plataforma **SonarQube**.
* **Herramientas DAST Open Source:** La más famosa y un estándar de la industria es **OWASP ZAP (Zed Attack Proxy)**. Es una herramienta increíblemente potente y gratuita.
* **Herramientas Comerciales:** Hay muchas suites que ofrecen SAST, DAST, IAST y SCA en un solo paquete. El manual menciona a **Veracode, Checkmarx, Invicti (Netsparker), Snyk** y la funcionalidad incluida en **GitLab Ultimate**.

La conclusión del manual es que una estrategia madura no elige una, sino que emplea una **combinación** de estas técnicas en diferentes etapas del SDLC para lograr una defensa en profundidad.

---
**Sofía:** Perfecto. Vamos con las preguntas de examen para cerrar el capítulo.

**Alex:** ¡Dispara! **P: ¿Cuál es la principal diferencia entre SAST y DAST en términos de cómo analizan una aplicación?**

**Sofía:** SAST analiza el código fuente o binario sin ejecutar la aplicación (caja blanca), mientras que DAST prueba la aplicación mientras está en ejecución, interactuando con ella desde fuera (caja negra).

**Alex:** Correcto. **P: Mencione una ventaja y una desventaja de SAST.**

**Sofía:** Ventaja: Detección temprana de vulnerabilidades en el SDLC. Desventaja: Mayor propensión a falsos positivos por la falta de contexto de ejecución.

**Alex:** ¡Muy bien! **P: ¿En qué fase del SDLC se suele utilizar DAST y por qué?**

**Sofía:** Se utiliza típicamente en la fase de pruebas o incluso en producción, porque requiere que la aplicación esté en un estado de ejecución para poder simular ataques reales y observar su comportamiento.

**Alex:** Exacto. Última: **P: ¿Qué tipo de vulnerabilidades es más probable que detecte DAST que SAST no pueda encontrar?**

**Sofía:** DAST es más probable que detecte vulnerabilidades relacionadas con el entorno de ejecución, como errores de configuración del servidor, problemas de gestión de sesión y vulnerabilidades que solo se manifiestan cuando la aplicación interactúa con otros sistemas en tiempo real.

**Alex:** ¡Excelente, Sofía! Has dominado completamente el arsenal de pruebas de seguridad. Ahora que sabemos cómo encontrar las vulnerabilidades, en el próximo capítulo veremos en detalle las más comunes en aplicaciones web: el famoso OWASP Top 10.

**Sofía:** ¡Perfecto! Estoy lista para entrar en materia.

---
[<< Sesión Anterior](./02-Fundamentos.md) | [Volver al Índice Principal](../README.md) | **Sesión Siguiente >>** [04-Web-OWASP.md](./04-Web-OWASP.md)