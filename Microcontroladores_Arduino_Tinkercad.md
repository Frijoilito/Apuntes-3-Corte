# **Apuntes: Microcontroladores y Arduino**
## **¿Qué son los microcontroladores y cómo funcionan?**
Un microcontrolador es un pequeño cerebro electrónico diseñado para ejecutar tareas específicas dentro de un sistema. Es como un miniordenador empaquetado en un solo chip que incluye:
1\. Unidad de procesamiento (CPU): La parte que interpreta y ejecuta instrucciones.
2\. Memoria: Para almacenar datos temporales (RAM) y permanentes (ROM o Flash).
3\. Entradas y salidas (I/O): Los “sentidos” que le permiten interactuar con el mundo, como botones, sensores o motores.

Los microcontroladores trabajan en un ciclo simple:
1\. Reciben información: Por ejemplo, una señal de un sensor que mide la temperatura.
2\. Procesan datos: Según las instrucciones programadas, deciden qué hacer con esa información.
3\. Envían resultados: Activan una salida, como encender un ventilador si la temperatura supera un límite.
## **Arduino: Un microcontrolador amigable para todos**
Arduino es una plataforma de hardware y software que hace que trabajar con microcontroladores sea accesible, incluso si no eres un experto. Está formada por:
\- Placas físicas (como Arduino Uno) que incluyen un microcontrolador y puertos de entrada/salida.
\- Un entorno de desarrollo (IDE): Donde escribes y cargas el código que controla la placa.

Por ejemplo, para encender un LED conectado al pin 13, el código sería:
\```c
void setup() {
`  `pinMode(13, OUTPUT);
}
void loop() {
`  `digitalWrite(13, HIGH);
`  `delay(1000);
`  `digitalWrite(13, LOW);
`  `delay(1000);
}
\```
## **Uso de Tinkercad**
Tinkercad es una herramienta en línea gratuita que te permite diseñar circuitos electrónicos y simular proyectos con Arduino sin necesidad de tener una placa física. Puedes experimentar, cometer errores y aprender sin dañar componentes físicos. Para usar Tinkercad:
1\. Crea una cuenta en tinkercad.com.
2\. Ve a la sección 'Circuitos' y selecciona 'Crear nuevo circuito'.
3\. Arrastra una placa Arduino y componentes al área de trabajo.
4\. Escribe el código y ejecuta la simulación para probarlo.
## **Temporizadores con Arduino para controladores numéricos**
Un temporizador en Arduino permite medir el tiempo con precisión, lo que es fundamental en sistemas donde se necesitan cálculos exactos para controlar procesos. Por ejemplo, para mover un motor cada segundo, el código sería:
\```c
unsigned long tiempoAnterior = 0;
const int intervalo = 1000;

void setup() {
`  `pinMode(9, OUTPUT);
}
void loop() {
`  `unsigned long tiempoActual = millis();
`  `if (tiempoActual - tiempoAnterior >= intervalo) {
`    `digitalWrite(9, !digitalRead(9));
`    `tiempoAnterior = tiempoActual;
`  `}
}
\```
Usar temporizadores permite dividir procesos en partes pequeñas, logrando precisión en tareas repetitivas o secuenciales.
## **Conclusión**
Los microcontroladores son herramientas fundamentales en la tecnología moderna. Arduino, al simplificar su uso, los hace accesibles para aprender, experimentar y crear proyectos innovadores. Usar Tinkercad permite practicar sin riesgos, y los temporizadores en Arduino abren la puerta a sistemas de control precisos. ¡El único límite es tu imaginación!
