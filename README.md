# SIMULACION-ARDUINO
ESTE CODIGO HA SIDO DISEÑADO PARA UTILIZAR SENSORES MEDIDORES DE GAS 



Connections:

MQ-135: A0

MQ-7: A1

MQ-4: A2


// Definition of pins for the sensors

const int mq135Pin = A0; // Pin analógico para MQ-135

const int mq7Pin = A1;    // Pin analógico para MQ-7

const int mq4Pin = A2;    // Pin analógico para MQ-4


void setup() {

  Serial.begin(9600); // Inicializa la comunicación serie
  
}

void loop() {

  // Leer valores de los sensores
  
  float mq135Value = analogRead(mq135Pin);
  
  float mq7Value = analogRead(mq7Pin);
  
  float mq4Value = analogRead(mq4Pin);
  

  // Convertir las lecturas a voltaje (0 - 5V)
  
  float voltageMQ135 = mq135Value * (5.0 / 1023.0);
  
  float voltageMQ7 = mq7Value * (5.0 / 1023.0);
  
  float voltageMQ4 = mq4Value * (5.0 / 1023.0);
  

  // Imprimir resultados en el monitor serie
  
  Serial.print("MQ-135 (CO2) Voltage: ");
  
  Serial.print(voltageMQ135);
  
  Serial.println(" V");



  Serial.print("MQ-7 (CO) Voltage: ");
  
  Serial.print(voltageMQ7);
  
  Serial.println(" V");



  Serial.print("MQ-4 (Metano) Voltage: ");
  
  Serial.print(voltageMQ4);
  
  Serial.println(" V");

  

  // Esperar un segundo antes de la siguiente lectura
  delay(1000);
  
}
