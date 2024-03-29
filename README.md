#*Respuesta Automatica*

Descripción del Proyecto:

Este proyecto tiene como objetivo desarrollar un sistema de respuesta automática para llamadas entrantes en WhatsApp. Cuando un usuario recibe una llamada y está ocupado, el sistema enviará automáticamente un mensaje predeterminado, por ejemplo, "Estoy ocupado, te llamaré más tarde". La implementación permitirá una personalización fácil del mensaje y proporcionará opciones avanzadas para adaptar las respuestas según diferentes situaciones.

Cómo se utiliza la programación en tiempo real:

La programación en tiempo real se utilizará para monitorear el estado de disponibilidad del usuario y activar automáticamente la respuesta automática cuando se reciba una llamada. Esto implica un monitoreo constante de la disponibilidad del usuario y una respuesta instantánea al evento de llamada entrante. Además, se utilizarán algoritmos de tiempo real para garantizar que las respuestas automáticas se envíen de manera eficiente y sin demoras perceptibles.


Problemas que Busca Resolver:

1. Interrupciones no Deseadas:
   - Aborda el problema de las interrupciones no deseadas al proporcionar una manera automática y educada de informar a los contactos que el usuario está ocupado.

2. Gestión Eficiente del Tiempo:
   - Resuelve el desafío de la gestión del tiempo al permitir que el usuario establezca automáticamente su disponibilidad y gestione las llamadas de manera más eficiente.

Cómo Mejora la Experiencia del Usuario:

1. Autonomía y Control:
   - Proporciona a los usuarios un mayor control sobre su disponibilidad y les permite establecer límites de manera automática, contribuyendo a una sensación de autonomía.

2. Personalización:
   - La personalización de respuestas permite a los usuarios adaptar el sistema a su estilo de comunicación, mejorando así la experiencia personalizada.

3. Reducción del Estrés:
   - Al automatizar la gestión de llamadas en momentos ocupados, el sistema contribuye a reducir el estrés asociado con la necesidad de responder manualmente en situaciones inconvenientes.


Semaforo:

Se usó un semáforo con un contador inicial de 1 en la clase SistemaRespuestaAutomatica. Luego, dentro del método monitorear_estado, el semáforo se adquiere (acquire) antes de acceder a la sección crítica del código, donde se verifica y actualiza el estado del usuario y se envía el mensaje de WhatsApp. Esto garantiza que solo una parte del código se ejecute a la vez, evitando problemas de concurrencia. Una vez que se completa la sección crítica, el semáforo se libera (release) para permitir que otros hilos accedan a la sección crítica.

Se creó un objeto threading. Condition llamado condicion en la clase SistemaRespuestaAutomatica. Este objeto se utiliza para implementar un semáforo utilizando los métodos wait y notify (equivalentes a signal en otros lenguajes). Se adquiere el semáforo utilizando el método with self.condicion, y se libera automáticamente al salir del bloque with.

Con esta implementación, se garantiza que la sección crítica del código (donde se verifica y actualiza el estado del usuario) sea ejecutada de manera segura por un único hilo a la vez.

