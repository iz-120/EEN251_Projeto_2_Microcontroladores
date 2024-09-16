# (EEN251) Projeto 2 - Hub de temperatuara e umidade
Documentação e códigos desenvolvidos para o segundo projeto da disciplina EEN251 - Microcontroladores e Sistemas Embarcados

## Grupo
Izabel Sampaio Goes P. Lapa - RA: 21.00098-0

Júlia Galhardi Cerqueira - RA: 21.01997-5

## Descrição do Projeto
O tema escolhido para o projeto será a criação e implmentação de um hub usando microcontrolador e prefidéricos.

## Requisitos do Sistema
![Tabela de Requisitos](/imagens/Tabela_Requisitos.png "Tabela de Requisitos do Sistema Proposto")

## Diagrama de Blocos do Sistema
Tem-se a seguir o Diagrama de Blocos, com o microcontrolador e os periféricos utilizados. As setas indiram se o fluxo de dados é de *input* ou *output*.

![Diagrama de Blocos](/imagens/Diagrama_Blocos.png "Primeira versão do Diagrama de Blocos do Sistema")

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

## Desenvolvimento
O desenvolvimento do software foi feito através do Node Red, utilizando as bibliotecas específicas para conexão com o periférico DTH11 e a API do wheathermap.

## Imagens
Aqui serão apresentadas imagens do sistema no quesito desenvolvimento e do produto final.

![Programação no Node Red](/imagens/Programa_Node_Red.png "Visão geral da progreamação no Nore Red")

![Tela Medições](/imagens/Tela_Medicoes.png "Tela de Medições")

![Tela Medições - Warning](/imagens/Tela_Medicoes_warning.png "Tela de Medições com warning")

