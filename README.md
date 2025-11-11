# TempGuard — Etony Guedes e Geovanna Almeida

## Sumário
- Descrição
- Requisitos
- Estrutura do repositório
- Como testar no Tinkercad
- Link do Tinkercad
- Link da interface mobile no Figma
- Screenshots
- Autor(es)
- Licença

---

## Descrição
O Projeto tempguard é um sistema de alerta de segurança desenvolvido para o velário do Santuário de Nossa Senhora das Candeias.
Seu objetivo é monitorar a temperatura ambiente e acionar alertas visuais e sonoros quando o calor ultrapassar limites seguros, prevenindo riscos de superaquecimento e incêndio.
O sistema simula o funcionamento real utilizando o Tinkercad e a plataforma Arduino Uno.
---

## Requisitos
1 Arduino Uno R3
1 Sensor de Temperatura (TMP36)
1 LED Verde
1 LED Amarelo
1 LED Vermelho
4 Resistores de 220 Ω
1 Piezo
- Versão do ambiente (se aplicável)
Plataforma: Tinkercad
Linguagem: C++ 
---

## Estrutura do repositório
- `/codigo` — /*
  Projeto Velário de Candeias
  Monitor de Temperatura
  Feito por: Adalberto Santana
*/

void setup() {
  // Define os pinos dos LEDs e do alarme como SAÍDA
  pinMode(2, OUTPUT); // LED Verde
  pinMode(3, OUTPUT); // LED Amarelo
  pinMode(4, OUTPUT); // LED Vermelho
  pinMode(5, OUTPUT); // Buzzer (Alarme)

  // Define o pino do sensor como ENTRADA
  pinMode(A0, INPUT);
  
  // Inicia o monitor serial (para ver a temp no PC)
  Serial.begin(9600);
}

void loop() {
  // 1. LER O SENSOR
  int leituraDoSensor = analogRead(A0);

  // 2. CONVERTER A LEITURA PARA GRAUS CELSIUS
  // Primeiro, converte a leitura (0-1023) para voltagem (0-5V)
  float voltagem = leituraDoSensor * (5.0 / 1023.0);
  // Agora, converte a voltagem para temperatura
  float temperatura = (voltagem - 0.5) * 100;

  // 3. MOSTRAR O VALOR NO MONITOR
  Serial.print("Temperatura atual: ");
  Serial.print(temperatura);
  Serial.println(" C");

  // 4. LÓGICA DE DECISÃO (IF / ELSE)
  
  if (temperatura < 40) {
    // TUDO NORMAL (abaixo de 40 graus)
    digitalWrite(2, HIGH); // Liga o verde
    digitalWrite(3, LOW);  // Desliga o amarelo
    digitalWrite(4, LOW);  // Desliga o vermelho
    noTone(5);             // Desliga o alarme

  } else if (temperatura < 60) {
    // ATENÇÃO (entre 40 e 60 graus)
    digitalWrite(2, LOW);
    digitalWrite(3, HIGH); // Liga o amarelo
    digitalWrite(4, LOW);
    noTone(5);

  } else {
    // PERIGO! (acima de 60 graus)
    digitalWrite(2, LOW);
    digitalWrite(3, LOW);
    digitalWrite(4, HIGH); // Liga o vermelho
    tone(5, 1000);         // Toca o alarme
  }
  // Espera 1 segundo antes de medir de novo
  delay(1000);
}
- `/docs` — <img width="662" height="610" alt="image" src="https://github.com/user-attachments/assets/65d14766-50a9-43f4-bffd-43578815a71b" />

- `/figma` — https://www.figma.com/design/oArSTwikzTKxZZDqsHb0Ay/TempGuard?node-id=0-1&t=RB5rl17NIjoG9QiY-1

---

## Como testar no Tinkercad
Acesse o link do projeto (abaixo).
Clique em “Iniciar simulação”.
Observe o comportamento:
Abaixo de 40 °C → LED Verde aceso (normal).
Entre 40 °C e 60 °C → LED Amarelo aceso (atenção).
Acima de 60 °C → LED Vermelho acende e o buzzer é acionado.
Você pode alterar a temperatura simulando a variação do sensor TMP36 para verificar as respostas do sistema.
---

## Link do Tinkercad
(https://www.tinkercad.com/things/bOZpuzeN5D8-sensor-de-temp?sharecode=81q7CrpV6zBq5xmCJg8Gqxt9uVBhiqRJ7xXiILSDwac)

---

## Interface mobile (Figma)
Criei uma interface mobile para controle do sistema. Acesse a visualização pública aqui:  
**Link Figma:** https://www.figma.com/design/oArSTwikzTKxZZDqsHb0Ay/TempGuard?node-id=0-1&t=RB5rl17NIjoG9QiY-1

---

## Screenshots
(Incluir imagens do circuito, do código rodando e telas do Figma)
<img width="1904" height="814" alt="image" src="https://github.com/user-attachments/assets/e7d7323e-dba2-4c5a-8549-fa5d6656ff1d" />

<img width="1395" height="826" alt="image" src="https://github.com/user-attachments/assets/c508169c-12ef-4b6c-9946-68e40c9491eb" />


---

## Autor(es)
- Etony Guedes do Nascimento - 2°Ano Informatica Turma - 92232
- Geovanna Almeida França - - 2°Ano Informatica Turma - 92232


---

## Licença
MIT
