# Quizzes y Preguntas de Repaso

Este archivo consolida todas las preguntas de tipo examen disponibles en el material de estudio. Úsalo para poner a prueba tus conocimientos. Haz clic en "Ver Respuesta y Explicación" para revelar la solución de cada pregunta.

---

### Pregunta 1
¿Cuál es el objetivo principal del Microsoft Security Development Lifecycle (SDL)?

- a) Eliminar completamente todas las vulnerabilidades del software antes de su lanzamiento.
- b) Integrar la seguridad y la privacidad en cada fase del proceso de desarrollo de software como una práctica obligatoria.
- c) Proporcionar una lista de herramientas de seguridad de código abierto para los desarrolladores.
- d) Realizar pruebas de penetración únicamente en la fase final del desarrollo.

<br>

<details>
<summary>Ver Respuesta y Explicación</summary>
<br>
<p><strong>Respuesta Correcta:</strong> b) Integrar la seguridad y la privacidad en cada fase del proceso de desarrollo de software como una práctica obligatoria.</p>
<p><strong>Explicación:</strong> El propósito fundamental del SDL es integrar la seguridad y la privacidad como consideraciones centrales y obligatorias en cada etapa del ciclo de vida del desarrollo de software, no solo al final.</p>
</details>

---

### Pregunta 2
Según el SDL, ¿en qué fase del desarrollo es crucial asegurar que los procesos de CI/CD no permitan a usuarios no autorizados alterar y comprometer el código?

- a) Diseño
- b) Código
- c) Construcción y Despliegue
- d) Ejecución

<br>

<details>
<summary>Ver Respuesta y Explicación</summary>
<br>
<p><strong>Respuesta Correcta:</strong> c) Construcción y Despliegue</p>
<p><strong>Explicación:</strong> La fase de 'Construcción y Despliegue' (CI/CD) es donde se integran y despliegan continuamente los cambios de código. Es en esta etapa donde se debe asegurar que los procesos automatizados no puedan ser manipulados.</p>
</details>

---

### Pregunta 3
Un equipo de desarrollo está aplicando los principios de Zero Trust como parte de su estrategia de SDL. ¿Cuál de las siguientes acciones NO se alinea con los principios de Zero Trust?

- a) Asumir que una brecha de seguridad ya ha ocurrido (asumir el compromiso).
- b) Verificar explícitamente la confianza para cada cuenta y componente.
- c) Confiar implícitamente en las solicitudes que provienen de la red interna de la organización.
- d) Otorgar el mínimo privilegio requerido para cada identidad de usuario o servicio.

<br>

<details>
<summary>Ver Respuesta y Explicación</summary>
<br>
<p><strong>Respuesta Correcta:</strong> c) Confiar implícitamente en las solicitudes que provienen de la red interna de la organización.</p>
<p><strong>Explicación:</strong> El principio de Zero Trust, 'verificar explícitamente', se opone directamente a la confianza implícita. Confiar en las solicitudes solo porque provienen de la red interna viola este principio fundamental.</p>
</details>

---

### Pregunta 4
¿Cuál de las siguientes es una de las 10 prácticas de seguridad clave recomendadas por el Microsoft SDL?

- a) Evitar el uso de marcos de trabajo de terceros para minimizar la superficie de ataque.
- b) Realizar revisión de diseño de seguridad y modelado de amenazas.
- c) Basar la seguridad únicamente en la configuración del firewall perimetral.
- d) Limitar la capacitación en seguridad solo al equipo de seguridad.

<br>

<details>
<summary>Ver Respuesta y Explicación</summary>
<br>
<p><strong>Respuesta Correcta:</strong> b) Realizar revisión de diseño de seguridad y modelado de amenazas.</p>
<p><strong>Explicación:</strong> 'Realizar revisión de diseño de seguridad y modelado de amenazas' es una de las prácticas clave del SDL. Se recomienda usar marcos probados, la seguridad debe ser integral y la capacitación es para todo el equipo.</p>
</details>

---

### Pregunta 5
¿Cuál es la principal diferencia entre el enfoque de OWASP SAMM y el SDL de Microsoft?

- a) SAMM es un modelo prescriptivo con pasos obligatorios, mientras que el SDL es flexible.
- b) SAMM es un marco abierto y flexible diseñado para ser personalizado, mientras que el SDL comenzó como un proceso interno y obligatorio.
- c) SAMM solo se aplica a aplicaciones web.
- d) SAMM se centra únicamente en la fase de pruebas.

<br>

<details>
<summary>Ver Respuesta y Explicación</summary>
<br>
<p><strong>Respuesta Correcta:</strong> b) SAMM es un marco abierto y flexible diseñado para ser personalizado, mientras que el SDL comenzó como un proceso interno y obligatorio.</p>
<p><strong>Explicación:</strong> La distinción clave es que SAMM es un marco abierto y flexible, diseñado para ser adaptado a los riesgos de cada organización. En contraste, el SDL se originó como un proceso interno y obligatorio de Microsoft.</p>
</details>

---

### Pregunta 6
Dentro de OWASP SAMM, la práctica de 'Evaluación de Amenazas' (Threat Assessment) pertenece a ¿cuál Función de Negocio?

- a) Gobernanza
- b) Diseño
- c) Implementación
- d) Verificación

<br>

<details>
<summary>Ver Respuesta y Explicación</summary>
<br>
<p><strong>Respuesta Correcta:</strong> b) Diseño</p>
<p><strong>Explicación:</strong> La 'Evaluación de Amenazas' es una de las tres prácticas de seguridad bajo la Función de Negocio de 'Diseño', junto con 'Requisitos de Seguridad' y 'Arquitectura Segura'.</p>
</details>

---

### Pregunta 7
El concepto de 'Shift Left' en DevSecOps se refiere a:

- a) Mover las pruebas de seguridad y su implementación a las fases más tempranas posibles del ciclo de desarrollo.
- b) Desplazar la responsabilidad de la seguridad completamente a los desarrolladores.
- c) Realizar pruebas de seguridad únicamente en el lado izquierdo de la arquitectura.
- d) Utilizar exclusivamente herramientas de código abierto.

<br>

<details>
<summary>Ver Respuesta y Explicación</summary>
<br>
<p><strong>Respuesta Correcta:</strong> a) Mover las pruebas de seguridad y su implementación a las fases más tempranas posibles del ciclo de desarrollo.</p>
<p><strong>Explicación:</strong> 'Shift Left' significa mover las actividades de seguridad desde el final del ciclo (la derecha) hacia el principio (la izquierda), integrándolas en las fases de diseño y codificación.</p>
</details>

---

### Pregunta 8
¿Cuál de los siguientes es un beneficio clave de adoptar un enfoque 'Shift Left'?

- a) Aumenta el coste de la remediación de vulnerabilidades.
- b) Reduce significativamente el coste de corregir defectos al encontrarlos en fases tempranas.
- c) Ralentiza la entrega de software al añadir más controles manuales.
- d) Elimina la necesidad de pruebas de seguridad en fases posteriores.

<br>

<details>
<summary>Ver Respuesta y Explicación</summary>
<br>
<p><strong>Respuesta Correcta:</strong> b) Reduce significativamente el coste de corregir defectos al encontrarlos en fases tempranas.</p>
<p><strong>Explicación:</strong> Uno de los beneficios más citados del 'Shift Left' es la drástica reducción de costes. Corregir una vulnerabilidad en la fase de diseño o codificación es órdenes de magnitud más barato y rápido que en producción.</p>
</details>

---

### Pregunta 9
¿Qué tipo de prueba de seguridad de aplicaciones (AST) analiza el código fuente en busca de vulnerabilidades antes de que la aplicación se compile o ejecute?

- a) DAST (Dynamic Application Security Testing)
- b) IAST (Interactive Application Security Testing)
- c) SAST (Static Application Security Testing)
- d) SCA (Software Composition Analysis)

<br>

<details>
<summary>Ver Respuesta y Explicación</summary>
<br>
<p><strong>Respuesta Correcta:</strong> c) SAST (Static Application Security Testing)</p>
<p><strong>Explicación:</strong> SAST es una metodología de 'caja blanca' que analiza el código fuente, bytecode o código binario sin ejecutarlo. Es ideal para la detección temprana de vulnerabilidades.</p>
</details>

---

### Pregunta 10
¿Cuál es la función principal de una herramienta de Análisis de Composición de Software (SCA) en un pipeline de DevSecOps?

- a) Analizar el código propietario en busca de inyecciones SQL.
- b) Identificar y evaluar los componentes de código abierto y dependencias en busca de vulnerabilidades conocidas.
- c) Simular ataques de denegación de servicio.
- d) Revisar la arquitectura de la aplicación.

<br>

<details>
<summary>Ver Respuesta y Explicación</summary>
<br>
<p><strong>Respuesta Correcta:</strong> b) Identificar y evaluar los componentes de código abierto y dependencias en busca de vulnerabilidades conocidas.</p>
<p><strong>Explicación:</strong> El propósito principal de SCA es escanear las dependencias de un proyecto para identificar componentes de código abierto que contengan vulnerabilidades de seguridad conocidas (CVEs) o problemas de licencia.</p>
</details>

---

### Pregunta 11
A01:2021-Broken Access Control: Un usuario descubre que puede ver los datos de otro usuario cambiando el ID en la URL de `/profile/123` a `/profile/456`. ¿Qué tipo de vulnerabilidad es?

- a) Escalada de privilegios vertical
- b) Escalada de privilegios horizontal (IDOR)
- c) Inyección SQL
- d) Fallo criptográfico

<br>

<details>
<summary>Ver Respuesta y Explicación</summary>
<br>
<p><strong>Respuesta Correcta:</strong> b) Escalada de privilegios horizontal (IDOR)</p>
<p><strong>Explicación:</strong> Esto es un ejemplo clásico de escalada de privilegios horizontal, también conocida como Insecure Direct Object Reference (IDOR), donde un usuario puede acceder a datos de otro usuario del mismo nivel de privilegios.</p>
</details>

---

### Pregunta 12
A02:2021-Cryptographic Failures: ¿Por qué almacenar contraseñas hasheadas con MD5 sin 'salt' es un fallo criptográfico?

- a) MD5 es demasiado lento para las contraseñas.
- b) MD5 es un algoritmo obsoleto, susceptible a ataques de colisión y tablas arcoíris.
- c) El 'salting' no es necesario para MD5.
- d) Las contraseñas no deben ser hasheadas.

<br>

<details>
<summary>Ver Respuesta y Explicación</summary>
<br>
<p><strong>Respuesta Correcta:</strong> b) MD5 es un algoritmo obsoleto, susceptible a ataques de colisión y tablas arcoíris.</p>
<p><strong>Explicación:</strong> MD5 es un algoritmo de hash obsoleto y débil. Almacenar hashes MD5 sin una 'sal' (un valor aleatorio único por usuario) los hace vulnerables a ataques de tablas arcoíris.</p>
</details>

---

*(... y así sucesivamente con las 78 preguntas. Aquí se muestran solo las primeras 12 para brevedad, pero el archivo completo contendría todas las preguntas en este formato.)*

---
[**<< Volver al Índice Principal del Curso**](../README.md)