[<< Sesión Anterior](./04-Web-OWASP.md) | [Volver al Índice Principal](../README.md) | **Sesión Siguiente >>** [06-API-OWASP.md](./06-API-OWASP.md)

---

## Sesión 5: Desarrollo Seguro de Aplicaciones Móviles

### Resumen del Tópico

Este tópico aborda los desafíos y riesgos de seguridad específicos de las plataformas móviles (Android e iOS). Se basa en el OWASP Mobile Top 10 para describir vulnerabilidades como el uso inadecuado de credenciales, el almacenamiento inseguro de datos en el dispositivo, la comunicación insegura y la falta de protecciones del binario de la app contra la ingeniería inversa.

---

### Diálogo de Estudio: Alex y Sofía

**(Intro - Sonido de la videollamada)**

**Alex:** Muy bien, Sofía, entramos al **Capítulo 5: Desarrollo Seguro de Aplicaciones Móviles**. El manual deja claro que, aunque muchos principios son los mismos que en la web, el contexto cambia por completo. El atacante puede tener acceso físico a tu dispositivo, las plataformas (Android e iOS) son ecosistemas cerrados con sus propias reglas, y dependemos de tiendas de aplicaciones.

**Sofía:** Sí, y el manual se basa en el **OWASP Mobile Top 10**, en su versión más reciente de 2024. Estoy lista para desglosarlo. Empecemos con **M1: Improper Credential Usage (Uso Inadecuado de Credenciales)**.

**Alex:** Perfecto. Este es el pan de cada día en las auditorías móviles. Se refiere al manejo, almacenamiento o transmisión incorrectos de credenciales.
* **Vectores Específicos para Móviles:** El error más común es el "hardcoding" de secretos, como claves de API, directamente en el código fuente o en archivos de recursos como `strings.xml` en Android o `Info.plist` en iOS. También es común el almacenamiento inseguro en `SharedPreferences` (Android) o `UserDefaults` (iOS) sin cifrar, o la fuga accidental de secretos a través de logs de depuración que no se eliminan en las versiones de producción.
* **Estrategias de Prevención:** La regla número uno es: **no hardcodear credenciales**. Para almacenar secretos de forma segura en el dispositivo, se deben usar los mecanismos de la plataforma: el **Android Keystore System** y el **iOS Keychain**. Estos sistemas son como cajas fuertes protegidas por hardware para guardar pequeños bloques de datos sensibles.

---
**Sofía:** El siguiente, **M2: Inadequate Supply Chain Security (Seguridad Inadecuada de la Cadena de Suministro)**, suena muy parecido al riesgo web.

**Alex:** Lo es, pero en el móvil el impacto es más directo. Las apps modernas son un Frankenstein de SDKs de terceros: para publicidad, análisis, notificaciones push, etc..
* **Vectores Específicos para Móviles:** El riesgo es incluir un SDK malicioso o vulnerable que recopila datos excesivos, o el compromiso de las herramientas de desarrollo o de las claves de firma de aplicaciones, permitiendo distribuir versiones troyanizadas de tu app.
* **Estrategias de Prevención:** Hay que "investigar" a los componentes de terceros antes de integrarlos. Usa herramientas de SCA para analizar sus vulnerabilidades, revisa los permisos que solicitan y utiliza solo SDKs de fuentes confiables. Además, protege rigurosamente tus claves de firma de la app.

---
**Sofía:** **M3: Insecure Authentication/Authorization (Autenticación/Autorización Insegura)**. ¿Cuál es el giro móvil aquí?

**Alex:** El giro es la falsa sensación de seguridad que da el cliente. Muchos desarrolladores cometen el error de poner lógica de autorización en la app.
* **Vectores Específicos para Móviles:** El principal error es depender de chequeos del lado del cliente, que pueden ser fácilmente eludidos con herramientas como Frida o Burp Suite. Un atacante puede manipular la app para que crea que es un usuario premium o un administrador.
* **Estrategias de Prevención:** La regla es inquebrantable: **toda la lógica de autenticación y autorización crítica debe residir y ser validada en el servidor backend en cada solicitud**. La app móvil es solo una interfaz; la autoridad es el backend.

---
**Sofía:** Entendido. **M4: Insufficient Input/Output Validation (Validación Insuficiente de Entradas/Salidas)**.

**Alex:** De nuevo, un concepto conocido, pero con nuevas fuentes de entrada.
* **Vectores Específicos para Móviles:** En el móvil, las entradas no son solo campos de texto. Pueden ser parámetros de **deeplinks** (`myapp://...`), datos de **comunicación entre procesos (IPC)** de otras apps, payloads de notificaciones push, o datos de NFC y Bluetooth. Una falta de validación aquí puede llevar a inyección SQL en la base de datos local o a XSS en `WebViews`.
* **Estrategias de Prevención:** Validar estrictamente todas estas fuentes de entrada. Usar consultas parametrizadas para las bases de datos locales (SQLite). Y configurar las `WebViews` de forma segura, por ejemplo, deshabilitando JavaScript si no es estrictamente necesario.

---
**Sofía:** Ok, pasemos a **M5: Insecure Communication (Comunicación Insegura)**.

**Alex:** Un clásico. Transmitir datos sensibles sin el cifrado adecuado.
* **Vectores Específicos para Móviles:** El uso de HTTP en lugar de HTTPS es el pecado capital. Pero también lo es una implementación incorrecta de SSL/TLS, como aceptar certificados inválidos, autofirmados o expirados.
* **Estrategias de Prevención:** Usa TLS 1.2 o superior para todas las comunicaciones. Y para aplicaciones de alta seguridad, considera implementar **Certificate Pinning**, que "clava" el certificado del servidor en la app para evitar ataques de Man-in-the-Middle. En Android, es crucial usar la **Network Security Configuration** para forzar políticas de comunicación segura y deshabilitar el tráfico en texto claro.

---
**Sofía:** La privacidad es un tema candente. **M6: Inadequate Privacy Controls (Controles de Privacidad Inadecuados)**.

**Alex:** Exacto. Esto va más allá de un bug técnico; es sobre el manejo respetuoso de los datos del usuario.
* **Vectores Específicos para Móviles:** El principal problema es la solicitud de **permisos excesivos**. La clásica app de linterna que pide acceso a tus contactos y tu ubicación. También incluye el registro de Información Personalmente Identificable (PII) en los logs de la app o las fugas de datos a través de SDKs de terceros.
* **Estrategias de Prevención:** El principio de **minimización de datos**: recolectar y procesar solo la PII estrictamente necesaria para la funcionalidad de la app. Y el principio de **mínimo privilegio para permisos**: solicitar solo los permisos del dispositivo que sean absolutamente necesarios y explicar claramente al usuario por qué se necesitan.

---
**Sofía:** Ahora uno muy específico del móvil: **M7: Insufficient Binary Protections (Protecciones Binarias Insuficientes)**.

**Alex:** Este riesgo trata de proteger la propiedad intelectual y la integridad de tu app.
* **Vectores Específicos para Móviles:** Sin protección, un atacante puede descompilar el binario de tu app para entender su lógica, extraer secretos que hayas hardcodeado, o modificarla (tampering) para saltarse verificaciones de licencia o para inyectar malware.
* **Estrategias de Prevención:** Se usa una combinación de técnicas: **ofuscación de código** para dificultarlo, **detección de root/jailbreak**, y mecanismos **anti-tampering** para verificar la integridad del código en tiempo de ejecución. Herramientas de **RASP (Runtime Application Self-Protection)** pueden automatizar mucho de esto.

---
**Sofía:** Los tres últimos parecen muy interconectados: **M8, M9 y M10**.

**Alex:** Lo están. Son como tres mosqueteros de la inseguridad local en el dispositivo.
* **M8: Security Misconfiguration (Configuración de Seguridad Incorrecta):** Son los errores de configuración específicos del móvil. Por ejemplo, dejar un componente de Android (como una Activity o un Service) "exportado" sin protegerlo con permisos, permitiendo que otra app maliciosa lo invoque. O dejar `android:debuggable="true"` en una build de producción, lo que permite a cualquiera depurar la app. Otro clásico es dejar `android:allowBackup="true"`, permitiendo que datos sensibles de la app se extraigan a través del sistema de backup de Android.
* **M9: Insecure Data Storage (Almacenamiento Inseguro de Datos):** Como ya dijimos, es el almacenamiento de datos sensibles en el dispositivo sin cifrar. Esto puede ser en bases de datos SQLite, archivos de preferencias, o en el almacenamiento externo.
* **M10: Insufficient Cryptography (Criptografía Insuficiente):** Este es el "porqué" del fallo de M9. Ocurre si *intentas* cifrar los datos, pero lo haces mal. Por ejemplo, usando un algoritmo débil como DES, una clave hardcodeada, o un vector de inicialización (IV) estático o predecible.

**Sofía:** Entonces, para proteger los datos en el dispositivo, necesito un buen cifrado (evitar M10) para el almacenamiento (evitar M9), y las claves de ese cifrado deben gestionarse de forma segura con el Keystore/Keychain (evitar M1).

**Alex:** ¡Exactamente! Has conectado los puntos a la perfección.

---
**Sofía:** Cerremos el capítulo con las preguntas del examen.

**Alex:** Adelante. **P: ¿Qué es M1: Improper Credential Usage en el contexto móvil y cómo se puede mitigar el riesgo de credenciales hardcodeadas en una app Android?**

**Sofía:** M1 es el manejo incorrecto de credenciales. Para evitar el hardcoding, una opción es almacenar la clave en `gradle.properties` (excluyéndolo del control de versiones) y acceder a ella a través de `BuildConfig`. Pero idealmente, las claves más sensibles deben gestionarse a través del Android Keystore.

**Alex:** ¡Correcto! Siguiente: **P: Explique el riesgo M5: Insecure Communication y mencione dos prácticas específicas de Android para prevenirlo, además del uso de HTTPS.**

**Sofía:** M5 es la transmisión de datos sin cifrado adecuado. En Android, además de HTTPS, se puede usar la **Network Security Configuration** para definir políticas de comunicación segura (ej. forzar TLS, deshabilitar cleartext traffic). También es crucial remover código de desarrollo que acepte todos los certificados y asegurar que la validación de certificados sea correcta.

**Alex:** Muy bien. **P: ¿Por qué M7: Insufficient Binary Protections es un riesgo importante para las apps móviles y qué técnicas se pueden usar para mitigarlo?**

**Sofía:** Es importante porque los binarios (APK/IPA) pueden ser fácilmente obtenidos y descompilados para robar secretos o modificados para insertar malware. Las técnicas de mitigación incluyen ofuscación de código, detección de root/jailbreak, mecanismos anti-tampering y RASP.

**Alex:** ¡Perfecto! Y la última: **P: Describa un ejemplo de M9: Insecure Data Storage en una app iOS y cómo se podría haber prevenido.**

**Sofía:** Un ejemplo sería almacenar un token de API sensible en `UserDefaults` sin ningún tipo de cifrado. Esto es inseguro porque `UserDefaults` es un archivo plist no cifrado accesible si el dispositivo está jailbroken. La prevención sería almacenar ese token en el **iOS Keychain**, que proporciona almacenamiento cifrado y protegido por hardware.

**Alex:** ¡Excelente, Sofía! Dominado el campo móvil. Ahora que sabemos cómo proteger a los clientes web y móviles, el siguiente paso lógico es proteger la columna vertebral que los conecta a ambos: las APIs. ¿Lista para el Capítulo 6?

**Sofía:** ¡Vamos a por ello!

---
[<< Sesión Anterior](./04-Web-OWASP.md) | [Volver al Índice Principal](../README.md) | **Sesión Siguiente >>** [06-API-OWASP.md](./06-API-OWASP.md)
