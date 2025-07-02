[<< Sesión Anterior](./07-DevSecOps.md) | [Volver al Índice Principal](../README.md) | **Sesión Siguiente >>** [09-Estrategia-Examen.md](./09-Estrategia-Examen.md)

---

## Sesión 8: Seguridad en Inteligencia Artificial

### Resumen del Tópico

Este tópico introduce el nuevo y complejo panorama de riesgos de seguridad en sistemas de Inteligencia Artificial y Machine Learning. Se describen ataques específicos a estos sistemas, como el envenenamiento de datos (Data Poisoning) y la inyección de prompts (Prompt Injection), y se presentan marcos como el OWASP Top 10 para LLMs.

---

### Diálogo de Estudio: Alex y Sofía

**(Intro - Sonido de la videollamada, Alex tiene una mirada de interés)**

**Alex:** Y llegamos al **Capítulo 8: Seguridad de la IA**. Si los capítulos anteriores eran sobre proteger el software que programamos, este es sobre proteger el software que aprende por sí mismo. La Inteligencia Artificial y el Machine Learning (ML) no solo introducen capacidades increíbles, sino también un panorama de riesgos completamente nuevo y complejo.

**Sofía:** Este tema me intimida un poco, parece muy diferente a todo lo demás. El manual menciona dos marcos para empezar a entender este nuevo mundo: **MITRE ATLAS** y el **OWASP Top 10 para LLMs**.

**Alex:** Exacto. Son nuestros mapas para este nuevo territorio.
* **MITRE ATLAS** es como el famoso framework ATT&CK, pero para IA. Es una base de conocimientos que cataloga las tácticas y técnicas que los adversarios usan para atacar sistemas de IA. Es el lenguaje común que permite a los científicos de datos y a los equipos de seguridad colaborar.
* El **OWASP Top 10 para LLMs** es una respuesta directa al boom de los Modelos de Lenguaje Grandes como ChatGPT. Se enfoca en las vulnerabilidades únicas de estas tecnologías, que son muy distintas a las de las aplicaciones web tradicionales.

---
**Sofía:** De acuerdo. El manual divide los ataques comunes en dos fases: entrenamiento e inferencia. Empecemos por el **entrenamiento**.

**Alex:** La fase de entrenamiento es cuando el modelo está aprendiendo de un conjunto de datos. El ataque principal aquí es el **Envenenamiento de Datos (Data Poisoning)**. Un atacante manipula los datos de entrenamiento para corromper el modelo, introducir sesgos o incluso crear "puertas traseras" secretas.
* **Ejemplo:** Imagina que estás entrenando un clasificador de imágenes. Un atacante podría introducir miles de imágenes de gatos etiquetadas como "perro" para sabotear el clasificador. Es un ataque a la integridad del proceso de aprendizaje.
* **Prevención:** La mitigación clave es tener una cadena de suministro de datos muy rigurosa y validada.

**Sofía:** ¿Y en la fase de **inferencia**, cuando el modelo ya está en uso?

**Alex:** Aquí los ataques son más directos. El manual destaca varios:
* **Ataques Adversariales de Evasión:** El atacante realiza modificaciones muy pequeñas, a menudo imperceptibles para un humano, en una entrada para engañar al modelo y que produzca una salida incorrecta. El ejemplo clásico es una pegatina en una señal de "STOP" que hace que un coche autónomo la interprete como un límite de velocidad.
* **Ataques de Inferencia de Privacidad:** El objetivo aquí es robar información sobre el modelo o sus datos. Hay dos tipos principales:
    1.  **Inferencia de Membresía:** El atacante intenta determinar si un dato específico (como el registro médico de una persona) formó parte del conjunto de entrenamiento del modelo.
    2.  **Inversión de Modelo:** Es más ambicioso. Intenta reconstruir los datos de entrenamiento originales (como una imagen facial) a partir de las predicciones que da el modelo.
* **Robo de Modelo:** Es literalmente lo que suena. El atacante intenta robar un modelo de ML propietario, ya sea exfiltrando sus archivos o creando una copia funcional interactuando con él a través de su API.

---
**Sofía:** Vaya, es un mundo completamente nuevo de problemas. Profundicemos en el **OWASP Top 10 para LLMs**. El manual selecciona algunos riesgos clave. ¿Cuál es el primero?

**Alex:** **LLM01: Inyección de Prompts (Prompt Injection)**. Este es el ataque número uno contra los LLMs. Es muy parecido a la inyección SQL, pero en lugar de inyectar código SQL, se inyectan instrucciones en el prompt del usuario para manipular al LLM. El objetivo es eludir sus filtros de seguridad o hacer que realice acciones no deseadas.

**Sofía:** El siguiente es **LLM02: Manejo Inseguro de Salidas (Insecure Output Handling)**.

**Alex:** Sí, y es crucial. Ocurre cuando la salida de un LLM se pasa a otro sistema sin una sanitización adecuada. Imagina que le pides a un LLM que genere código HTML y JavaScript. Si ese código se renderiza directamente en una página web sin validación, un atacante podría haber engañado al LLM para que genere un script malicioso, causando un ataque de XSS.

**Sofía:** Entiendo. ¿Y la **Denegación de Servicio del Modelo (LLM04)**?

**Alex:** Los LLMs consumen muchos recursos. Un atacante puede enviar prompts que sean particularmente largos o complejos, obligando al modelo a consumir una cantidad desproporcionada de recursos. Esto degrada el servicio para otros usuarios y, muy importante, puede inflar enormemente los costos operativos de la API del LLM.

**Sofía:** Tiene sentido. ¿Qué hay de la **Fuga de Información Sensible (LLM06)**?

**Alex:** Los LLMs se entrenan con cantidades masivas de datos, a veces incluyendo información propietaria o sensible. Existe el riesgo de que, en respuesta a un prompt, el LLM revele accidentalmente parte de esa información confidencial que "memorizó" durante su entrenamiento.

---
**Alex:** Los dos últimos que destaca el manual son muy interesantes porque se centran en cómo *usamos* los LLMs.
* **LLM08: Agencia Excesiva (Excessive Agency):** El peligro aumenta cuando un LLM no solo genera texto, sino que tiene "agencia", es decir, la capacidad de interactuar con otros sistemas (ejecutar código, enviar correos, usar APIs). Si a un LLM se le otorgan demasiados permisos, un prompt malicioso podría hacer que abuse de ellos, como borrar archivos o enviar correos de phishing.
* **LLM09: Confianza Excesiva (Overreliance):** Este es un riesgo 100% humano. Ocurre cuando los desarrolladores o usuarios confían ciegamente en la salida del LLM sin una revisión adecuada. El ejemplo perfecto es un desarrollador que copia y pega código generado por un LLM sin entenderlo ni validarlo, introduciendo así código inseguro en la aplicación.

---
**Sofía:** Es fascinante y aterrador a la vez. Cerremos con las preguntas de examen de este último capítulo.

**Alex:** ¡Adelante! **P: ¿Qué es un ataque de envenenamiento de datos en el contexto de ML?**

**Sofía:** Es un ataque a la integridad de un modelo de ML donde un atacante manipula los datos de entrenamiento para corromper el aprendizaje del modelo o crear puertas traseras.

**Alex:** ¡Correcto! **P: Describa la diferencia entre un ataque de "inversión de modelo" y un ataque de "inferencia de membresía".**

**Sofía:** La inversión de modelo intenta reconstruir los datos de entrenamiento originales a partir de las predicciones del modelo. La inferencia de membresía tiene un objetivo más simple: solo busca determinar si un dato específico estuvo o no en el conjunto de entrenamiento.

**Alex:** ¡Perfecto! **P: ¿Qué es una inyección de prompt (LLM01)?**

**Sofía:** Es un ataque en el que un atacante crea un prompt cuidadosamente diseñado para engañar a un LLM y hacer que ignore sus instrucciones de seguridad y realice una acción no deseada por sus desarrolladores.

**Alex:** ¡Excelente! Y la última: **P: Un desarrollador utiliza un LLM para generar código de validación de contraseñas y lo implementa sin revisarlo. El código resulta ser vulnerable. ¿Qué riesgo del OWASP Top 10 para LLMs se ha materializado?**

**Sofía:** Ese es claramente **LLM09: Confianza Excesiva (Overreliance)**, porque el desarrollador confió en la salida del LLM sin la supervisión y validación humana adecuadas.

---
**(Outro - Sonido de la videollamada, Alex y Sofía parecen satisfechos)**

**Alex:** Y con eso, Sofía, hemos cubierto todo el manual, de principio a fin. Desde los cimientos del Secure SDLC hasta la nueva frontera de la IA. ¿Cómo te sientes?

**Sofía:** Siento que las piezas finalmente han encajado. Una cosa es leer los conceptos y otra muy distinta es discutirlos, ver cómo se conectan y entenderlos con ejemplos reales. Esta maratón ha sido increíblemente valiosa. Muchísimas gracias, Alex.

**Alex:** El placer ha sido mío. Has hecho las preguntas correctas y has demostrado que entiendes la mentalidad que hay detrás, que es lo más importante. La seguridad es un viaje de aprendizaje continuo.

**Sofía:** Me siento mucho más preparada para el examen, y lo que es más importante, para aplicar todo esto en mi trabajo diario.

**Alex:** Ese es el verdadero éxito. ¡Mucha suerte en el examen! Aunque, sinceramente, no creo que la necesites.

**Sofía:** (Risas) ¡Gracias, Alex! Hablamos pronto.

---
[<< Sesión Anterior](./07-DevSecOps.md) | [Volver al Índice Principal](../README.md) | **Sesión Siguiente >>** [09-Estrategia-Examen.md](./09-Estrategia-Examen.md)