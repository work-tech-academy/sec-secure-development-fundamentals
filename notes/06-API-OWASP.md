[<< Sesión Anterior](./05-Movil-OWASP.md) | [Volver al Índice Principal](../README.md) | **Sesión Siguiente >>** [07-DevSecOps.md](./07-DevSecOps.md)

---

## Sesión 6: Desarrollo Seguro de APIs (OWASP API Security Top 10)

### Resumen del Tópico

Este tópico explora la seguridad de las Interfaces de Programación de Aplicaciones (APIs), que son la columna vertebral de las arquitecturas de software modernas. Utiliza el OWASP API Security Top 10 de 2023 para explicar riesgos únicos como la Autorización Rota a Nivel de Objeto (BOLA), la Autenticación Rota y el Consumo No Restringido de Recursos.

---

### Diálogo de Estudio: Alex y Sofía

**(Intro - Sonido de la videollamada, Alex sonríe)**

**Alex:** Muy bien, Sofía, entramos en mi terreno favorito: las APIs. El **Capítulo 6: Desarrollo Seguro de APIs**. Si las aplicaciones web y móviles son la cara visible, las APIs son el sistema nervioso central que lo conecta todo. Por eso, asegurarlas es absolutamente crítico.

**Sofía:** Y veo que el manual se basa en el **OWASP API Security Top 10**, específicamente en la versión de 2023, que incluye nuevos riesgos como SSRF y otros. Estoy lista. Empecemos por la cima: **API1:2023 - Broken Object Level Authorization (BOLA)**.

**Alex:** BOLA. Grábate este nombre. Es el riesgo número uno por una razón: es extremadamente común y fácil de explotar. Se trata de un fallo en validar correctamente si un usuario tiene permiso para acceder o manipular un objeto específico al que normalmente hace referencia a través de su ID.
* **¿Cómo ocurre?** La API expone un endpoint como `GET /api/orders/{orderId}`. Un atacante, que es un usuario legítimo, solicita su propio pedido para ver cómo funciona. Luego, simplemente cambia el `orderId` en la solicitud por otro que adivina o encuentra. Si la API no verifica que ese pedido pertenece al usuario que hace la llamada, se produce BOLA.
* **Prevención:** Es crucial implementar chequeos de autorización a nivel de objeto en cada función de la API que acceda a datos usando un ID del cliente. Además, usar identificadores de objeto aleatorios y largos (como UUIDs) en lugar de enteros secuenciales dificulta que se puedan adivinar los IDs de otros objetos.

---
**Sofía:** Entendido. El siguiente es **API2:2023 - Broken Authentication (Autenticación Rota)**.

**Alex:** Si BOLA es sobre "qué puedes hacer", la autenticación rota es sobre "quién eres". Ocurre cuando los mecanismos para verificar la identidad de un usuario están mal implementados.
* **Vectores Específicos de API:** Esto incluye desde políticas de contraseña débiles hasta un manejo inseguro de tokens, como los JWTs. Por ejemplo, un JWT sin fecha de expiración, o uno que usa un algoritmo débil como `alg:none`. También incluye API keys hardcodeadas en el código de una app móvil o la no invalidación de tokens de sesión en el servidor después de un logout.
* **Prevención:** Implementar mecanismos de autenticación fuertes como OAuth 2.0. Exigir MFA si es posible. Asegurar la gestión de tokens: usar JWTs firmados con algoritmos fuertes (ej. RS256), con una expiración corta, y transmitirlos siempre por HTTPS. Y, por supuesto, aplicar *rate limiting* a los endpoints de autenticación para prevenir ataques de fuerza bruta.

---
**Sofía:** De acuerdo, ahora **API3:2023 - Broken Object Property Level Authorization (Autorización Rota a Nivel de Propiedad de Objeto)**. Esto suena muy parecido a BOLA. ¿Cuál es la diferencia?

**Alex:** ¡Excelente pregunta! Es una distinción sutil pero vital. BOLA (API1) es sobre si puedes acceder al **objeto entero**. API3 es sobre si puedes acceder o modificar **propiedades específicas *dentro* de ese objeto**. Esta categoría engloba dos problemas muy comunes:
1.  **Exposición Excesiva de Datos:** La API devuelve más propiedades de un objeto de las que el usuario debería ver. Por ejemplo, una llamada a `/api/users/me` devuelve tu objeto de usuario, pero también incluye campos como `passwordHash` o `internalAdminNotes`.
2.  **Asignación Masiva (Mass Assignment):** Es el inverso. Permites que un usuario modifique propiedades que no debería. El ejemplo clásico es un usuario que actualiza su perfil enviando un JSON con `{"email": "new@example.com", "isAdmin": true}`. Si tu API procesa ciegamente la propiedad `isAdmin`, el usuario acaba de escalarse a sí mismo a administrador.
* **Prevención:** Para la exposición, define esquemas de respuesta específicos y nunca uses funciones genéricas como `toJson()` que vuelcan todo el objeto. Para la asignación masiva, usa siempre **listas blancas** de las propiedades que un cliente tiene permitido modificar en un endpoint específico.

---
**Sofía:** Siguiente: **API4:2023 - Unrestricted Resource Consumption (Consumo No Restringido de Recursos)**.

**Alex:** Esto es básicamente abrir la puerta a ataques de Denegación de Servicio (DoS), ya sea por malicia o por accidente. Ocurre cuando las APIs no imponen límites al consumo de recursos como CPU, memoria o número de solicitudes.
* **Vectores Específicos de API:** La falta de *rate limiting* o *throttling*. No validar el tamaño de los payloads (imagina que alguien sube un archivo de 10 GB a un endpoint de procesamiento de imágenes). O permitir consultas a la base de datos muy complejas que consumen toda la CPU.
* **Prevención:** Implementar *rate limiting* y *throttling* para limitar el número de solicitudes por cliente. Validar y limitar el tamaño de todas las entradas. Y establecer *timeouts* para las solicitudes de larga duración.

---
**Sofía:** Ahora **API5:2023 - Broken Function Level Authorization (BFLA)**. Diferénciamelo de BOLA otra vez, por favor.

**Alex:** Claro. **BOLA (API1) es sobre DATOS**. ¿Puedes ver el pedido de otro usuario? **BFLA (API5) es sobre ACCIONES**. ¿Puedes invocar una función de administrador? Ocurre cuando no se aplican chequeos de autorización a nivel de función o endpoint.
* **Ejemplo:** Un usuario normal descubre la URL de un endpoint administrativo como `POST /api/invites/new` y logra crear una invitación con privilegios de administrador.
* **Prevención:** Denegar por defecto. Implementar chequeos de autorización explícitos basados en roles en cada endpoint, especialmente los sensibles. No confíes en que el cliente ocultará la función; la seguridad debe estar en el servidor.

---
**Sofía:** Vamos con los nuevos y brillantes riesgos. **API6:2023 - Unrestricted Access to Sensitive Business Flows**.

**Alex:** Este es sobre el abuso de la lógica de negocio a escala, algo que las APIs automatizan muy bien para los atacantes.
* **Ejemplo:** El *scalping* de entradas para conciertos o zapatillas de edición limitada. Los bots bombardean la API de compra para acaparar todo el stock en segundos para la reventa. Otro ejemplo es la creación masiva de cuentas falsas para abusar de una promoción.
* **Prevención:** Esto requiere más que autenticación. Necesitas **detección de bots**, CAPTCHAs, *device fingerprinting* y un monitoreo de la lógica de negocio para detectar patrones anómalos.

---
**Sofía:** **API7:2023 - Server-Side Request Forgery (SSRF)**. ¡Aquí está de nuevo!

**Alex:** Sí, y es tan crítico en el mundo de las APIs que ha entrado en su propio Top 10. Una API vulnerable a SSRF obtiene un recurso de una URL proporcionada por el usuario sin validarla.
* **Ejemplo en APIs:** Una API de webhook que intenta conectarse a una URL proporcionada por el usuario. El atacante le da una serie de IPs internas para escanear la red interna del servidor desde dentro.
* **Prevención:** Igual que en la web: usar una **lista blanca** estricta de dominios, protocolos y puertos permitidos. Y deshabilitar las redirecciones HTTP o validarlas contra la misma lista.

---
**Sofía:** Ya casi. **API8:2023 - Security Misconfiguration**.

**Alex:** Este es el cajón de sastre de los errores de configuración en cualquier nivel de la pila de la API.
* **Vectores Específicos de API:** Políticas de **CORS (Cross-Origin Resource Sharing)** demasiado permisivas como `Access-Control-Allow-Origin: *`. Falta de cabeceras de seguridad HTTP. Mensajes de error detallados que revelan información del sistema.
* **Prevención:** Implementar un proceso de hardening automatizado y configurar las políticas de CORS de forma restrictiva, definiendo explícitamente los orígenes permitidos.

---
**Sofía:** **API9:2023 - Improper Inventory Management**. El problema de las APIs olvidadas.

**Alex:** Exacto. "No puedes proteger lo que no sabes que tienes". Este riesgo cubre las **"Shadow APIs"** (desplegadas sin aprobación) y las **"Zombie APIs"** (versiones antiguas no retiradas). Estas APIs a menudo carecen de parches y monitoreo, convirtiéndolas en puntos de entrada fáciles para atacantes.
* **Prevención:** Mantener un inventario actualizado y preciso de todas las APIs. Monitorear el tráfico para descubrir "Shadow APIs". Y tener un proceso formal para desmantelar versiones antiguas.

---
**Sofía:** Y el último: **API10:2023 - Unsafe Consumption of APIs**.

**Alex:** Este es interesante porque se enfoca en el **cliente** de la API. Ocurre cuando los desarrolladores confían implícitamente en los datos recibidos de APIs de terceros sin validarlos.
* **Ejemplo:** Tu aplicación de e-commerce usa una API de un tercero para obtener el precio de un producto. La API es comprometida y devuelve un precio de "$0.01". Si tu aplicación procesa ese precio sin cuestionarlo, acabas de regalar tu inventario.
* **Prevención:** La responsabilidad recae en el desarrollador de la aplicación consumidora. Debe tratar los datos de cualquier API externa como entrada no confiable, validándola y sanitizándola siempre.

---
**Sofía:** Vaya, es todo un ecosistema. ¿Cerramos con las preguntas de examen?

**Alex:** ¡Claro! **P: ¿Cuál es la diferencia fundamental entre BOLA (API1) y BFLA (API5)?**

**Sofía:** BOLA (Broken Object Level Authorization) es sobre acceder a un *objeto de datos* específico que no te pertenece. BFLA (Broken Function Level Authorization) es sobre invocar una *función o endpoint completo* al que tu rol no te da acceso.

**Alex:** ¡Perfecto! **P: Describa un ejemplo de Asignación Masiva (Mass Assignment) en el contexto de API3 y cómo se puede prevenir.**

**Sofía:** Ejemplo: un usuario actualiza su perfil con `PUT /api/users/me` y añade `"isAdmin": true` al JSON. Si la API lo procesa ciegamente, el usuario escala privilegios. Se previene usando una lista blanca en el servidor para permitir explícitamente solo las propiedades que el usuario puede modificar.

**Alex:** ¡Muy bien! **P: ¿Por qué API9: Improper Inventory Management es un riesgo de seguridad significativo?**

**Sofía:** Porque las "Zombie APIs" y "Shadow APIs" a menudo carecen de monitoreo, parches y controles de seguridad modernos, convirtiéndolas en puntos de entrada fáciles para los atacantes que buscan vulnerabilidades conocidas.

**Alex:** ¡Exacto! Y la última: **P: ¿Qué es el riesgo API10: Unsafe Consumption of APIs y quién es el principal responsable de mitigarlo?**

**Sofía:** Es el riesgo de que una aplicación cliente confíe implícitamente en los datos de una API externa sin validarlos. El principal responsable de mitigarlo es el desarrollador de la aplicación cliente (la consumidora), que debe tratar todos los datos externos como no confiables.

**Alex:** ¡Lo has clavado, Sofía! Has navegado por las complejidades de la seguridad de las APIs como una profesional. El siguiente capítulo nos llevará a cómo orquestar todo esto en un pipeline moderno. Hablemos de DevSecOps.

**Sofía:** ¡Estoy preparada!

---
[<< Sesión Anterior](./05-Movil-OWASP.md) | [Volver al Índice Principal](../README.md) | **Sesión Siguiente >>** [07-DevSecOps.md](./07-DevSecOps.md)