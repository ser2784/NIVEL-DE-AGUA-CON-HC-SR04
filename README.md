# Practica Nivel de agua
Este repositorio muestra como podemos programar una ESP32 con el sensor HC-SR04.

## Introducción

### Descripción

La ```Esp32``` la utilizamos en un entorno de adquision de datos, lo cual en esta practica ocuparemos un sensor (```HC-SR04```) para adquirir temperatura y humedad del entorno; Cabe aclarar que esta practica se usara un simulador llamado [WOKWI](https://https://wokwi.com/).


## Material Necesario

Para realizar esta practica necesitas lo siguiente

- [WOKWI](https://https://wokwi.com/)
- Tarjeta ESP 32
- HC-SR04
- 4 Resistencias
- 4 led 
- GND
- VCC



## Instrucciones

### Requisitos previos

Para poder usar este repositorio necesitas entrar a la plataforma [WOKWI](https://https://wokwi.com/).


### Instrucciones de preparación de entorno 

1. Abrir la terminal de programación y colocar la siguente programación:

```
// defines pins numbers
const int trigPin = 4;
const int echoPin = 15;
const int led1 = 22;
const int led2 = 21;
const int led3 = 19;
const int led4 = 18;

// defines variables
long duration;
int distance;
int safetyDistance;


void setup() {
pinMode(trigPin, OUTPUT); // Sets the trigPin as an Output
pinMode(echoPin, INPUT); // Sets the echoPin as an Input
pinMode(led1, OUTPUT);
pinMode(led2, OUTPUT);
pinMode(led3, OUTPUT);
pinMode(led4, OUTPUT);
Serial.begin(9600); // Starts the serial communication
}


void loop() {
// Clears the trigPin
digitalWrite(trigPin, LOW);
delayMicroseconds(2);

// Sets the trigPin on HIGH state for 10 micro seconds
digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);

// Reads the echoPin, returns the sound wave travel time in microseconds
duration = pulseIn(echoPin, HIGH);

// Calculating the distance
distance= duration*0.034/2;

safetyDistance = distance;
if (safetyDistance>=2 && safetyDistance<=10)
{
  digitalWrite(led1, HIGH);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
}
else if(safetyDistance>=10 && safetyDistance<=20) 
{
  digitalWrite(led1, HIGH);
  digitalWrite(led2, HIGH);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
}
else if(safetyDistance>=20 && safetyDistance<=30) 
{
  digitalWrite(led1, HIGH);
  digitalWrite(led2, HIGH);
  digitalWrite(led3, HIGH);
  digitalWrite(led4, LOW);
}
else if(safetyDistance>=30 && safetyDistance<=40) 
{
  digitalWrite(led1, HIGH);
  digitalWrite(led2, HIGH);
  digitalWrite(led3, HIGH);
  digitalWrite(led4, HIGH);
}
else
{
 digitalWrite(led1,  LOW);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
}

// Prints the distance on the Serial Monitor
Serial.print("Distance: ");
Serial.println(distance);
delay (2000);
}

```


2. Hacer la conexion de **HC-SR04** con la **ESP32** como se muestra en la siguente imagen.

![](https://github.com/ser2784/NIVEL-DE-AGUA-CON-HC-SR04/blob/main/NIVEL%20DE%20AGUA%20NINGUN%20LED%20PRENDIDO.png)

### Instrucciónes de operación

1. Iniciar simulador.
2. Visualizar los datos en el HC-SR04.
3. Colocar la distancia en el **HC-SR04**  *doble click* al sensor **HC-SR04** 
4. Segun sea la distancia penden los led del 2 al 40 .

## Resultados

Cuando haya funcionado, verás los valores como se muestra en la siguente imagen.

![](https://github.com/ser2784/NIVEL-DE-AGUA-CON-HC-SR04/blob/main/NIVEL%20DE%20AGUA%201LED.png)
![](https://github.com/ser2784/NIVEL-DE-AGUA-CON-HC-SR04/blob/main/NIVEL%20DE%20AGUA%202LED.png)
![](https://github.com/ser2784/NIVEL-DE-AGUA-CON-HC-SR04/blob/main/NIVEL%20DE%20AGUA%203LED.png)
![](https://github.com/ser2784/NIVEL-DE-AGUA-CON-HC-SR04/blob/main/NIVEL%20DE%20AGUA%20LED4.png)
![](https://github.com/ser2784/NIVEL-DE-AGUA-CON-HC-SR04/blob/main/NIVEL%20DE%20AGUA%20NINGUN%20LED%20PRENDIDO.png)
## Evidencias

[por El momento no contamos con el video ]


# Créditos

Desarrollado por Ing. Sergio Rivera 

- [GitHub](https://github.com/ser2784)