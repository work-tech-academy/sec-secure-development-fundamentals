[<< Sesión Anterior](./03-SAST-DAST.md) | [Volver al Índice Principal](../README.md) | **Sesión Siguiente >>** [05-Movil-OWASP.md](./05-Movil-OWASP.md)

---

## Sesión 4: Seguridad en Aplicaciones Web (OWASP Top 10 2021)

### Resumen del Tópico

Este tópico se enfoca en los riesgos de seguridad más críticos para las aplicaciones web, utilizando como guía el proyecto OWASP Top 10. Se analizan en detalle las principales vulnerabilidades de la lista de 2021, como el Control de Acceso Roto (A01), la Inyección (A03), la Configuración de Seguridad Incorrecta (A05) y el Server-Side Request Forgery (SSRF) (A10).

---

### Diálogo de Estudio: Alex y Sofía

**(Intro - Sonido de la videollamada)**

**Alex:** Muy bien, Sofía, entramos en el **Capítulo 4: Seguridad en Aplicaciones Web**. Y eso significa que vamos a hablar del **OWASP Top 10**. Si trabajas en seguridad de aplicaciones, esta es tu biblia.

**Sofía:** He oído hablar de él constantemente. El manual dice que es un "documento de concienciación estándar" y un "excelente punto de partida". Entiendo que representa un consenso sobre los riesgos más críticos.

**Alex:** Exactamente. Y se actualiza cada pocos años para reflejar cómo cambian las amenazas. La versión que vamos a ver es la de 2021. Vamos a analizarlos uno por uno, porque cada uno es un mundo. ¿Lista?

**Sofía:** Lista. Empecemos por el número uno: **A01:2021 - Broken Access Control (Control de Acceso Roto)**.

**Alex:** Este es el rey de las vulnerabilidades. Según los datos de 2021, es la categoría con el riesgo de seguridad más grave. Ocurre cuando las restricciones sobre lo que un usuario *autenticado* puede hacer no se aplican correctamente.
* **¿Cómo ocurre?** Por fallos en la validación de permisos, manipulación de parámetros en la URL o, el más famoso, **IDOR (Insecure Direct Object References)**.
* **Ejemplo:** Imagina que accedes a tu cuenta en `https://example.com/app/accountInfo?acct=123`. Un atacante simplemente cambia el parámetro `acct` a `124` y, si no hay una comprobación de permisos adecuada, ve la información de la cuenta de otro usuario.
* **Prevención:** La clave es implementar los controles de acceso en el lado del servidor y hacerlos cumplir en cada solicitud. Deben denegar por defecto y verificar que el usuario logueado tiene permiso para acceder al objeto específico que está pidiendo.

---
**Sofía:** Entendido. El siguiente es **A02:2021 - Cryptographic Failures (Fallos Criptográficos)**.

**Alex:** Antes se llamaba "Exposición de Datos Sensibles". Ahora se enfoca en la causa raíz: la criptografía débil o ausente.
* **¿Cómo ocurre?** De muchas formas: transmitir datos sensibles en texto claro (HTTP). Usar algoritmos de cifrado débiles u obsoletos como DES o MD5. Una gestión de claves deficiente, como claves hardcodeadas en el código. Y, muy importante, no cifrar los datos sensibles cuando están almacenados en la base de datos.
* **Ejemplo:** Almacenar contraseñas en texto plano, o incluso "hasheadas" con un algoritmo rápido como SHA-1 sin "sal". Un atacante que obtiene la base de datos puede usar "rainbow tables" para descifrarlas en segundos.
* **Prevención:** Primero, clasifica tus datos y no almacenes datos sensibles que no necesites. Cifra todos los datos sensibles en tránsito (usando TLS 1.2 o superior) y en reposo (usando AES-256). Y para contraseñas, usa siempre hashes fuertes, lentos y con "sal", como **Argon2, scrypt o bcrypt**.

---
**Sofía:** **A03:2021 - Injection (Inyección)**. Este es un clásico.

**Alex:** El más clásico. En la edición de 2021, esta categoría absorbió también a Cross-Site Scripting (XSS). Una inyección ocurre cuando datos no confiables se envían a un intérprete (como un intérprete de SQL, del sistema operativo, etc.) como parte de un comando.
* **¿Cómo ocurre?** Porque los datos del usuario no se validan o sanitizan y se concatenan directamente en una consulta dinámica.
* **Ejemplo de SQLi:** En un login, un atacante introduce en el campo de usuario `' OR '1'='1' --`. Si la consulta se construye como `"SELECT * FROM users WHERE username = '" + userInput + "'"`... ¡boom! El atacante se ha autenticado como el primer usuario de la tabla sin saber la contraseña.
* **Prevención:** La opción preferida es usar APIs seguras que eviten el intérprete por completo, como las **consultas parametrizadas (prepared statements)** o los ORMs. Esto separa el comando de los datos, haciendo la inyección imposible.

---
**Sofía:** La siguiente, **A04:2021 - Insecure Design (Diseño Inseguro)**, es nueva y parece más abstracta.

**Alex:** Es abstracta, pero fundamental. Se enfoca en fallos relacionados con el diseño y la arquitectura. Un diseño inseguro no puede ser corregido por una implementación perfecta.
* **¿Cómo ocurre?** Por no realizar un modelado de amenazas adecuado o por no pensar en cómo se podría abusar de la lógica de negocio.
* **Ejemplo:** El manual da un gran ejemplo: un sistema de reservas de cine que no tiene un límite en la cantidad de asientos que un solo usuario puede reservar. Un competidor podría crear un bot para reservar todos los asientos de todas las películas, sin intención de pagar, causando una denegación de servicio y pérdida de ingresos. No es un bug de código, es un fallo de diseño.
* **Prevención:** Establecer un ciclo de vida de desarrollo seguro. Usar modelado de amenazas para flujos críticos y aplicar patrones de diseño seguro.

---
**Sofía:** **A05:2021 - Security Misconfiguration (Configuración de Seguridad Incorrecta)**. Supongo que esto va de errores de sysadmin.

**Alex:** No solo, pero sí en gran parte. Esta categoría ahora también incluye la antigua **XXE (XML External Entities)**.
* **¿Cómo ocurre?** Dejar características o puertos innecesarios habilitados. Dejar cuentas por defecto y contraseñas sin cambiar. Mensajes de error que revelan información interna. Y no aplicar parches de seguridad de manera oportuna.
* **Ejemplo:** Un servidor de aplicaciones que tiene su consola de administración habilitada en producción con la contraseña por defecto. O una explotación de XXE que permite a un atacante leer archivos locales del servidor como `/etc/passwd`.
* **Prevención:** Implementar un proceso de "hardening" repetible y automatizado para los entornos. Construir una plataforma mínima, deshabilitando todo lo que no sea necesario. Y tener un proceso de gestión de parches robusto.

---
**Sofía:** Vamos con **A06:2021 - Vulnerable and Outdated Components (Componentes Vulnerables y Desactualizados)**.

**Alex:** Este es el riesgo de la cadena de suministro de software. Usas librerías, frameworks y otros módulos que tienen vulnerabilidades de seguridad conocidas.
* **¿Cómo ocurre?** Por no saber qué componentes de terceros estás usando o en qué versión. Por no escanearlos en busca de vulnerabilidades conocidas (CVEs).
* **Ejemplo:** La famosa brecha de **Equifax** en 2017. Los atacantes explotaron una vulnerabilidad conocida en el framework Apache Struts, para la cual ya existía un parche, pero Equifax no lo había aplicado.
* **Prevención:** Mantener un inventario de todos los componentes. Escanear regularmente con herramientas **SCA (Software Composition Analysis)**. Y, de nuevo, tener un proceso ágil para aplicar parches.

---
**Sofía:** **A07:2021 - Identification and Authentication Failures (Fallos de Identificación y Autenticación)**. ¿No es esto lo mismo que Control de Acceso Roto?

**Alex:** ¡No! Y es una distinción crucial. **Autenticación** es verificar *quién eres*. **Control de Acceso (Autorización)** es verificar *qué puedes hacer* una vez que sabemos quién eres.
* **¿Cómo ocurre?** Permitiendo ataques automatizados como *credential stuffing* o fuerza bruta por no limitar los intentos de login. Permitiendo contraseñas débiles o por defecto. Teniendo procesos de recuperación de contraseña débiles. O no invalidando los tokens de sesión en el servidor después del logout.
* **Prevención:** Implementar **Autenticación Multifactor (MFA)** siempre que sea posible. Imponer políticas de contraseñas fuertes alineadas con las guías de NIST 800-63b. Y usar un gestor de sesiones seguro del lado del servidor que invalide los tokens correctamente.

---
**Sofía:** **A08:2021 - Software and Data Integrity Failures (Fallos de Integridad de Software y Datos)**. Otra categoría nueva.

**Alex:** Sí, y muy relevante. Se enfoca en hacer suposiciones sobre la integridad de las actualizaciones de software, los datos críticos y los pipelines de CI/CD. El ejemplo más conocido aquí es la **deserialización insegura**.
* **¿Cómo ocurre?** Por ejemplo, una funcionalidad de auto-actualización que descarga e instala un paquete sin verificar su firma digital. O una aplicación que deserializa un objeto enviado por un cliente sin verificar que no ha sido manipulado, lo que puede llevar a Ejecución Remota de Código (RCE).
* **Ejemplo:** El ataque a **SolarWinds**, donde los atacantes comprometieron el mecanismo de actualización para distribuir una versión maliciosa del software a miles de organizaciones.
* **Prevención:** Usar firmas digitales para verificar que el software y los datos provienen de la fuente esperada. Asegurar el pipeline de CI/CD para que no se pueda inyectar código malicioso. Y no deserializar datos no firmados provenientes de clientes no confiables.

---
**Sofía:** Ya casi terminamos. **A09:2021 - Security Logging and Monitoring Failures (Fallos de Registro y Monitoreo de Seguridad)**.

**Alex:** Este es el riesgo de ser un "guardia de seguridad ciego". Puedes tener las mejores cerraduras del mundo, pero si no tienes cámaras ni alarmas, un ladrón podría pasar días dentro de tu casa sin que te enteres.
* **¿Cómo ocurre?** Cuando eventos auditables como logins, logins fallidos o transacciones de alto valor no se registran. Cuando los logs no se monitorean en busca de actividad sospechosa. O cuando no hay un plan de respuesta a incidentes.
* **Ejemplo:** El manual menciona el caso de un proveedor de salud que no pudo detectar durante mucho tiempo una brecha en la que se accedió y modificó los datos de 3.5 millones de niños, simplemente por falta de monitoreo.
* **Prevención:** Asegurar que todos los fallos de login, control de acceso y validación de entrada se registren con suficiente contexto. Enviar los logs a un sistema centralizado y seguro (como un SIEM) que pueda correlacionar eventos y generar alertas. Y tener un plan de respuesta a incidentes bien definido, como el del NIST 800-61r2.

---
**Sofía:** Y el último, **A10:2021 - Server-Side Request Forgery (SSRF)**. Ya lo mencionamos.

**Alex:** Sí, pero es tan importante que tiene su propia categoría. Ocurre cuando un atacante coacciona a la aplicación del lado del servidor para que envíe una solicitud manipulada a un destino inesperado.
* **¿Cómo ocurre?** Cuando una aplicación obtiene un recurso remoto (importa un archivo, genera una vista previa de un enlace) sin validar la URL suministrada por el usuario.
* **Ejemplo:** El ataque a los metadatos de servicios en la nube. Un atacante le pide a tu aplicación que acceda a la URL `http://169.254.169.254/` (una dirección interna en muchos proveedores de cloud) y la API del proveedor de la nube le devuelve credenciales de acceso temporales con las que el atacante puede comprometer tu infraestructura.
* **Prevención:** La mitigación no es usar una lista negra, que es fácil de eludir. La solución es usar una **lista blanca positiva (allow list)**, haciendo cumplir estrictamente el esquema de URL, el puerto y el destino permitidos.

---
**Alex:** Y con eso, completamos el Top 10. Lo importante, como dice el manual al final, es ver que todos estos riesgos están interconectados. Un ataque exitoso raramente explota una sola categoría. Es una cadena. Por eso se necesita una estrategia integral y una defensa en profundidad.

**Sofía:** Vaya, ha sido un maratón, pero ahora cada categoría tiene mucho más sentido. ¿Revisamos las preguntas del examen para este capítulo?

**Alex:** ¡Por supuesto! Es la mejor forma de consolidar. **P: ¿Qué tipo de vulnerabilidad es A01:2021-Broken Access Control y cómo se diferencia de A07:2021-Identification and Authentication Failures?**

**Sofía:** A01:Broken Access Control es sobre autorización, lo que un usuario *ya autenticado* tiene permitido hacer. A07:Identification and Authentication Failures es sobre autenticación, el proceso de *verificar la identidad* del usuario.

**Alex:** ¡Perfecto! **P: Describa un ejemplo de ataque de Inyección SQL (A03) y una medida de prevención primaria.**

**Sofía:** Ejemplo: un atacante ingresa `' OR '1'='1' --` en un campo de nombre de usuario para saltarse un login. La prevención primaria es usar consultas parametrizadas.

**Alex:** ¡Muy bien! **P: ¿Por qué el "Diseño Inseguro" (A04) es una categoría importante y difícil de solucionar posteriormente en el ciclo de vida del software?**

**Sofía:** Porque si los controles de seguridad no se integran desde el diseño, la implementación no puede compensarlo. Corregir fallos de diseño en etapas tardías implica rediseños arquitectónicos costosos y complejos.

**Alex:** ¡Exacto! **P: ¿Cuál es el riesgo principal asociado con A06:2021-Vulnerable and Outdated Components y cómo se puede mitigar eficazmente?**

**Sofía:** El riesgo es que los componentes de terceros tengan vulnerabilidades conocidas que puedan ser explotadas. Se mitiga manteniendo un inventario, escaneándolos con herramientas SCA, y aplicando parches de manera oportuna.

**Alex:** Y la última: **P: Explique qué es un ataque de Server-Side Request Forgery (SSRF) (A10) y mencione dos formas de prevenirlo a nivel de aplicación.**

**Sofía:** SSRF es cuando un atacante engaña al servidor para que realice solicitudes a un destino no deseado. Se previene validando la URL de entrada con una lista blanca estricta y deshabilitando o validando las redirecciones HTTP.

**Alex:** ¡Felicidades, Sofía! Has sobrevivido al OWASP Top 10. Ahora estás lista para llevar este conocimiento al mundo móvil.

---
[<< Sesión Anterior](./03-SAST-DAST.md) | [Volver al Índice Principal](../README.md) | **Sesión Siguiente >>** [05-Movil-OWASP.md](./05-Movil-OWASP.md)