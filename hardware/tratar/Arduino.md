
## código

```

int eixo_X = A0; // PINO REFERENTE A LIGACAO DO EIXO X
int eixo_Y = A1; // PINO REFERENTE A LIGACAO DO EIXO Y
int botao = 2;   // PINO REFERENTE A LIGACAO NO PINO KEY (EIXO Z)

// Definir limiares para detectar movimentos
const int centro_min = 400;  // Valor minimo para considerar que o joystick esta no centro
const int centro_max = 600;  // Valor maximo para considerar que o joystick esta no centro

void setup() {
  //pinMode(botao, INPUT_PULLUP); 
  Serial.begin(9600);           // Inicializa o monitor serial
}

void loop() {
  int leituraX = analogRead(eixo_X);
  int leituraY = analogRead(eixo_Y);
  int estadoBotao = digitalRead(botao);

  // Verifica direções individuais e diagonais
  if (leituraX < centro_min && leituraY > centro_max) {
    Serial.println("PARA CIMA E ESQUERDO");
  } else if (leituraX < centro_min && leituraY < centro_min) {
    Serial.println("PARA CIMA E DIREITA");
  } else if (leituraX > centro_max && leituraY > centro_max) {
    Serial.println("PARA BAIXO E ESQUERDO");
  } else if (leituraX > centro_max && leituraY < centro_min) {
    Serial.println("PARA BAIXO E DIRETIA");
  } else if (leituraX < centro_min) {
    Serial.println("PARA CIMA");
  } else if (leituraX > centro_max) {
    Serial.println("PARA BAIXO");
  } else if (leituraY < centro_min) {
    Serial.println("DIRETO");
  } else if (leituraY > centro_max) {
    Serial.println("ESQUERDO");
  } else {
    Serial.println("CENTRO");
  }

  // Verifica se o botão foi pressionado
  if (estadoBotao == LOW) {
    Serial.println("BOTAO PRESSIONADO");
  }

  delay(500); // Pequeno atraso para evitar flooding no monitor serial
}

```

## funções e
- Serial
	objeto responsável pela comunicação com o computador
	Arduino e computador precisam concordar no "bod", 9600.
- ``Serial.begin(9600)
	estabelece a comunicação serial (protocolo serial)
	 
	para gerar output na tela
	tool -> serial monitor
	
	9600 - board rate
	frequência de comunicação
	
	Nota : USB - Universal Serial Bus
- ``analogRead()
- setup()
	roda uma vez
