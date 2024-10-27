# (EEN251) Projeto 2 e 3 - Hub de temperatura e umidade
Documentação e códigos desenvolvidos para o segundo projeto da disciplina EEN251 - Microcontroladores e Sistemas Embarcados

## Grupo
Izabel Sampaio Goes P. Lapa - RA: 21.00098-0

Júlia Galhardi Cerqueira - RA: 21.01997-5

## Descrição do Projeto
O tema escolhido para o projeto será a criação e implmentação de um hub usando mini computador e periféricos. A motivação para o projeto foi manter o ambiente com temperatura e umidade em faixas de valores determinados em valores ideais de vivência de ratos twister.

As faixas ideais para eles são de 18°C a 26°C e de 50% a 70% de umidade do ar.

Com isso em mente, o projeto aqui apresentado visa ser um hub que possa ser instalado no ambiente dos ratos e que monitore esses dois parâmetros, tanto interna quanto externamente para via de comparação.
As medições internas são feitas através de um sensor de umidade e temperatura (DTH11) e as externas tem como fonte a API da Open Weather.

Os valores de temperatura e umidade são exibidos em formato numérico e atualizados, para via de teste, a cada 10 segundos. Além disso, é feito um gráfico em tempo real com os valores de temperatura e umidade captados internamente e recebidos externamente.

Caso os valores internos saiam da faixa ideal, é exibida mensagem avisando que a temperatura ou umidade estão abaixo ou acima dos valores ideais.

Em uma segunda iteração e continuação deste projeto, foi feito a integração deste hub com um dashboard online no Ubidots, sobra a qual serão dados mais detalhes abaixo.

## Requisitos do Sistema
![Tabela de Requisitos](/imagens/Tabela_Requisitos.png "Tabela de Requisitos do Sistema Proposto")

## Diagrama de Blocos do Sistema
Tem-se a seguir o Diagrama de Blocos, com o mini computador e os periféricos utilizados. As setas indicam se o fluxo de dados é de *input* ou *output*.

![Diagrama de Blocos](/imagens/Diagrama_de_Blocos.png "Primeira versão do Diagrama de Blocos do Sistema")

## Conexões
Essa seção irá abordar em mais detalhes as conexões de cada componente e os pinos do microcontrolador Raspberry Pi Pico que estão sendo utilizados em cada uma delas.

> ### Alimentação
> - Uma linha de GND (Pino 6)
> - Uma linha de VCC 5V (Pino 2)
> - Alimentar a entrada C com carregador (atrvés da placa do display)

> ### Display OLED
> - Alimentação - entrada C e conectando a fonte à tomada

> ### Sensor DTH11
> - VCC 3,3 V (Pino 1)
> - GND (Pino 9)
> - GPIO15 (Pino 10)

## Desenvolvimento do projeto 2
O desenvolvimento do software foi feito através do Node Red, utilizando as bibliotecas específicas para conexão com o periférico DTH11 e a API do wheathermap.

## Imagens do projeto 2
Aqui serão apresentadas imagens do sistema no quesito desenvolvimento e do produto final.

![Programação no Node Red](/imagens/Programa_Node_Red.png "Visão geral da progreamação no Nore Red")

![Tela Medições](/imagens/Tela_Medicoes.png "Tela de Medições")

![Tela Medições - Warning](/imagens/Tela_Medicoes_warning.png "Tela de Medições com warning")

## Vídeos de apresentação
Segue link do vídeo de apresentação do projeto: [Apresentação T2](https://youtu.be/OLLFZQJT4Pk)

