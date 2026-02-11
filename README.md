# IOT-Aulas
### Aula 1 - 10/02 
Para começar, montamos o arduino com um led, 2 jumpers, fizemos um sistema simples e relembramos que:
- Negativo, perna menor, perna torta
- Positivo, perna maior, perna reta
- Preferencialmente colocar o resistor no negativo e o jumper

- Código primeira aula C++
#define ledR 8
#define ledG 12

void setup() {
  // put your setup code here, to run once:
  pinMode(ledR, OUTPUT); // O led é output
  Serial.begin(9600); // Velocidade de comunicação do Arduino
}

void loop() {
  // put your main code here, to run repeatedly:
  // digitalWrite(ledR, HIGH); // Ligando o arduino
  if(Serial.available() > 0){ // Se a serial está disponível e se alguém digitar qualquer valor vai cair no if pois será maior que zero
    char comando = Serial.read(); // O que a pessoa digitou vai ser armazenado na variável comando
    if(comando == '1'){
      digitalWrite(ledR, HIGH); 
    }else if(comando == '0'){
      digitalWrite(ledR, LOW);
    }else if(comando == '5'){
      digitalWrite(ledG, HIGH);
    }
  }
}

