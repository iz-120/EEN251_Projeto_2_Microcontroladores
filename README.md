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

Para a continuação do projeto, agora devemos considerar a interação entre o sistema anterior e o Ubidots. Através de requisições HTTP POST e GET, existe comunicação bidirecional, como pode ser visto no novo diagrama.

![Novo Diagrama de Blocos](/imagens/Diagrama_de_Blocos_2.png "Segunda versão do Diagrama de Blocos do Sistema")

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

Na segunda iteração, foi utilizada a mesma aplicação desenvolvida anteriormente no Node Red, apenas fazendo as adições necessárias para atender ao comportamento desejado com o Ubidots. Foram utilizados nós de requisição HTTP para a comunicação com o Dashboard online. Agora, ao invés de apresentar *warnings* na tela (naquela na qual está conectado o Raspberry Pi) quando a temperatura ou umidade saem da faixa ideal, o Dashboard exibe a temperatura com faixas de cores indicativas do status:
- Vermelho: temperatura acima do ideal;
- Verde: temperatura na faixa ideal;
- Azul: temperatura abaixo do ideal.

Para a umidade, os limites ideais são mostrados como linhas tracejadas no gráfico.

Além disso, caso o usuário do Dashboard perceba que a temperatura ou umidade estão fora da faixa, ele pode solicitar o ajuste delas através de botões, um para pedir o ajuste da temperatura e outro, para umidade. Ao pressionar o botão, uma mensagem é exibida na tela pedindo que o ajuste seja feito. Enquanto a pessoa do outro lado não confirma que o ajuste foi feito, o botão de solicitar ajuste fica desabilitado no Dashboard. Ao tocar em "Ajuste feito", o pop-up some e o botão do Dashboard volta a ficar habilitado.


## Imagens
Aqui serão apresentadas imagens do sistema no quesito desenvolvimento e do produto final.
### Estrutura
![Programação no Node Red](/imagens/Programa_Node_Red.png "Visão geral da programação no Nore Red")

### Tela
![Tela Medições](/imagens/Tela_Medicoes.png "Tela de Medições")

### Tela com warning
![Tela Medições - Warning](/imagens/Tela_Medicoes_warning.png "Tela de Medições com warning")

## Vídeos de apresentação
### Projeto 2 - T2
Segue link do vídeo de apresentação do projeto: [Apresentação T2](https://youtu.be/OLLFZQJT4Pk)

### Projeto 3 - T3
Segue link do vídeo de apresentação do projeto:

