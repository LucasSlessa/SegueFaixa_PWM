#include <Arduino.h>

const int sensorEsquerdoPin = 17;  // Pino do sensor esquerdo
const int sensorDireitoPin = 16;   // Pino do sensor direito
const int motorEsquerdoPino1 = 22; // Pino IN1 do motor esquerdo
const int motorEsquerdoPino2 = 21; // Pino IN2 do motor esquerdo
const int motorDireitoPino1 = 19;  // Pino IN3 do motor direito
const int motorDireitoPino2 = 18;  // Pino IN4 do motor direito

const int velocidadeMaxima = 255; // Valor máximo de PWM para velocidade máxima

void girarRobo(int graus);

void setup() {
  pinMode(sensorEsquerdoPin, INPUT);
  pinMode(sensorDireitoPin, INPUT);
  pinMode(motorEsquerdoPino1, OUTPUT);
  pinMode(motorEsquerdoPino2, OUTPUT);
  pinMode(motorDireitoPino1, OUTPUT);
  pinMode(motorDireitoPino2, OUTPUT);

  girarRobo(720);
}

void loop() {
  int leituraSensorEsquerdo = digitalRead(sensorEsquerdoPin);
  int leituraSensorDireito = digitalRead(sensorDireitoPin);

  // Calcula o valor de PWM com base na leitura do sensor
  int pwmEsquerdo = map(leituraSensorEsquerdo, LOW, HIGH, 0, velocidadeMaxima);
  int pwmDireito = map(leituraSensorDireito, LOW, HIGH, 0, velocidadeMaxima);

  // Define a velocidade dos motores com PWM
  analogWrite(motorEsquerdoPino1, pwmEsquerdo);
  analogWrite(motorEsquerdoPino2, LOW);
  analogWrite(motorDireitoPino1, pwmDireito);
  analogWrite(motorDireitoPino2, LOW);
}

void girarRobo(int graus) {
  // Define a direção de rotação dos motores para girar o robô
  digitalWrite(motorEsquerdoPino1, LOW);
  digitalWrite(motorEsquerdoPino2, HIGH);
  digitalWrite(motorDireitoPino1, LOW);
  digitalWrite(motorDireitoPino2, HIGH);

  // Calcula a duração em milissegundos para girar os graus desejados
  int duracao = (graus * 1000) / 360;

  // Aguarda a duração calculada
  delay(duracao);

  // Para os motores após o tempo de giro ter passado
  digitalWrite(motorEsquerdoPino1, LOW);
  digitalWrite(motorEsquerdoPino2, LOW);
  digitalWrite(motorDireitoPino1, LOW);
  digitalWrite(motorDireitoPino2, LOW);
}
