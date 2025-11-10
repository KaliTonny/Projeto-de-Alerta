# Projeto Alerta — Etony Guedes e Geovanna Almeida

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
O Projeto é um sistema de alerta de segurança desenvolvido para o velário do Santuário de Nossa Senhora das Candeias.
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
- `/codigo` — código-fonte (explicar arquivos principais)
- `/docs` — documentação e imagens
- `/figma` — link externo para a interface (não é pasta; ver seção Figma)

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
**Link Figma:** COLE_AQUI_O_LINK_DE_COMPARTILHAMENTO_DO_FIGMA  
> Observação: certifique-se de que o link de compartilhamento está em modo de visualização pública (ou 'anyone with the link').

---

## Screenshots
(Incluir imagens do circuito, do código rodando e telas do Figma)
- `docs/screenshot-circuito.png`<img width="1904" height="814" alt="image" src="https://github.com/user-attachments/assets/e7d7323e-dba2-4c5a-8549-fa5d6656ff1d" />

- `docs/screenshot-figma-1.png`

---

## Autor(es)
- Etony Guedes do Nascimento - 2°Ano Informatica Turma - 92232
- Geovanna Almeida França - - 2°Ano Informatica Turma - 92232


---

## Licença
MIT
