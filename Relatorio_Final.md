## INTRODUÇÃO
Hoje em dia, as pessoas prezam por um bem-estar e estarem seguras seja qual espaço que estejam requerendo o bom tratamento ou estando em um lugar que elas se sintam à vontade, diante disso, elas podem contar com o apoio da Internet das Coisas, que segundo Bertoncello (2020), são dispositivos conectados à internet que enviam dados para serem manipulados, visando sempre que possível trazer melhores retornos para os usuários.

Considerando a busca de saber teórico e prático, torna-se importante entender o desenvolvimento e a manipulação dos objetos físicos incorporados a sensores, que estes serão responsáveis por capturar as informações que os usuários não conseguiria obter por exatidão através dos sentidos, trabalhando conjuntamente com software, fazendo a conexão e trocar dados com outro dispositivo e conjuntamente com a interface gráfica, para trazer o resultado esperado a qual tem com o único propósito de auxiliar o bem estar humano.

Em atendimento ao objetivo, vamos trabalhar na elaboração do projeto com construção do projeto prático que será capaz de capturar a temperatura e umidade para fornecer informações de alerta sobre o clima para garantir uma boa hidratação e bem estar em climas mais amenos.

## DESENVOLVIMENTO
### ESTUDO DO CASO DO PROJETO DA DISCIPLINA
O objetivo é capturar a umidade e temperatura do ambiente, foram trabalhados vários métodos, a princípio foi com  teste com arduino, led, sensor DHT11 (Temperatura e umidade), evoluindo para o projeto o Node e ESP8266, substituindo a placa arduino e adotando dispositivo de conexão web, para serem visualizados os dados da captura da temperatura e umidade pelo navegador, considerando exposto, vamos abordar quais elementos foram utilizados ao longo dos projetos, em seguida iremos relembrar como foi com o projeto arduino e em seguida suas modificações para ser visualizado em interface gráfica.

### ELEMENTOS UTILIZADOS
1. Arduino: <br/>
Segundo Canaltech (2015), “arduíno é uma placa de prototipagem eletrônica de código aberto”, que possibilita o desenvolvimento dos mais diversos projetos robóticos, atuando como um tipo de cérebro eletrônico programável de simplificada utilização, com diversas portas para conexões com módulos e sensores. Dispositivo utilizado em um protótipo.

1. LED:<br/>
Como um dos principais de retornar o comportamento ao usuário, o led, segundo Mundodaeletrica (2022), trata-se de um diodo emissor de luz que conduz corrente elétrica em uma polarização, que são conhecidos como ânodo  positivo e cátodo negativo.  Quando integrado aos projetos práticos, servem como sinalizadores de aviso. Dispositivo utilizado nos dois protótipos.

1. Resistores:<br/>
Como medida de proteção contra queima de dispositivos, utilizam os resistores, que segundo Mundodaeletrica (2022), “[...] componente elétrico passivo que tem a função primária de limitar o fluxo da corrente elétrica em um circuito”. Dispositivo utilizado nos dois protótipos.

1. Protoboard:<br/>
Muito utilizado em projeto de prototipagem, o protoboard, segundo a Casadarobotica (2022), “permite que os componentes eletrônicos possam ser interligados em um número quase infinito de maneiras para produzir circuitos eletrônicos em trabalhos de prototipagem”. Dispositivo utilizado nos dois protótipos.

1. ESP8266 WIFI:<br/>
Utilizando para fazer conexão com o node-red e suporte para obter informações, o ESP8266, segundo Usinainf (2022), “[...] é um pequeno chip microcontrolador com WiFi que conta com um pequeno processador a bordo, para que possa funcionar com total autonomia, sem a necessidade de uma placa Arduino”, que pode ser conectado ao computador,e utilizar o IDE do arduino para configurar o seu uso, ressaltando que para o uso, torna-se necessário resistores com tensão 3.3V DC.

1. DHT11:<br/>
Um dos componentes bases para essa prototipação, DHT11, segundo Blogdarobotica (2020), [...] é um sensor capaz de medir a temperatura e a umidade do ambiente”. Blogdarobotica afirma que é formado por duas partes principais: “[...] um sensor de umidade capacitivo e um sensor de temperatura termistor NTC, isto é um resistor sensível à variação de temperatura”.
No DHT11, tem o pino VCC que significa Corrente de tensão contínua, que normalmente está ligada à alimentação. O Dados, segundo Blogdarobotica (2022) “[...] é o pino de comunicação de dados, será através dele que o valor da temperatura e umidade serão comunicados a placa microcontroladora”. O N.C é um pino vazio, que não será utilizado e o GND se refere ao terminal terra.

1. MQTT:<br/>
Considerando o MQTT um dos protocolos bastante utilizado na Internet das coisas, segundo Imasters (2022). Ele diz que o MQTT faz uso de “[...] um modelo leve de publicação/assinatura de mensagens, o que é ideal para a conectividade máquina-máquina (M2M)”, utilizando sensores de baixa potência e como faz a comunicação com dispositivos móveis para ver as mensagens advindos dos pacotes transitados.Este protocolo utiliza o broker, que segundo Kalatec (2022), ele é como intermediário e “[...] tem o papel de filtrar todas as mensagens, recebendo-as, enfileirando-as e distribuindo-as para cada assinante, que irá receber somente as mensagens de seu interesse”.

### PROJETO ARDUINO 

Para o protótipo  com arduino, tivemos como base o exemplo dado pelo blog filipeflop, configuramos o que tínhamos com o que era necessário, como o sistema de luzes, mas tivemos o primeiro problema, precisávamos de uma biblioteca para o arduino saber como interpretar o componente DHT11. Para conseguir essa biblioteca, no próprio site que tinha o link para o repositório do “DHT-sensor-library”, baixamos, o descompactamos, renomeamos para DHT (isto é uma ação necessária para o funcionamento) e colocamos na pasta libraries do arquivo do arduino.

Continuando a configuração, nos deparamos com o segundo problema, as permissões do computador.  Para resolver,  tivemos que baixar uma nova versão do arduino.
Após o download, conseguimos permissão para realizar alterações, com a biblioteca instalada e o código pronto, rodamos novamente o teste, porém ele falhou, a biblioteca DHT11 precisava de uma dependência a mais, a “Adafruit_Sensor”.

Na busca, conseguimos encontrar o link para essa dependência no próprio link onde encontramos o DHT11, fizemos downloads, anexando a dependência do Adafruit as bibliotecas do arduino. 
Após o processo, rodamos o código novamente, finalmente obtivemos sucesso. O nosso dispositivo estava funcional e operante, agora só precisaremos ajustar o modelo de cálculo de temperatura.

Neste protótipo,  sensor funcionará continuamente, analisando a temperatura e umidade do ar, onde será feito o cálculo do Índice de Temperatura e Umidade (ITU), então liga-se um Led correspondente às condições climáticas atuais.
Quando as condições forem favoráveis o led acesso será verde, condições de desconforto moderado acenderá o led amarelo, e situações com grandes desconfortos será acesso o led vermelho juntamente com um alerta sonoro.

### PROJETO NODE-RED

O NODE-RED trata-se de uma ferramenta que possibilita ao usuário fazer programação com fins de conectar dispositivos de APIs, hardware e serviços online. (NODERED, 2022)
O NODE-RED trabalha com nós de paletas, que tem variadas habilidades que quando estão em conexão, possibilita construir um ambiente que conseguimos visualizar os dados que aquele conjunto de aplicações e hardware traz do ambiente externo, ou seja, conseguindo trabalhar com a Internet das Coisas.
Com a prototipagem inicial do projeto de sensor de temperatura, o objetivo é visualizar por meio de interface gráfica como os dados irão ser capturados e visualizados pelos usuários, sendo assim, considerando fundamental o uso do Node-RED para construir a interface gráfica e comunicação com o dispositivo através de ESP8266 WIFI,que este terá a função de conectar a internet e por meio de protocolo MQTT, irá interligar com o sensor DHT11, leds e protoboard.
No Node-Red foram utilizados 15 nodes para construção do ambiente gráfico, considerando que todos apresentam relação de dependência. 

#### Mqtt in
- Sensor_Temperatura: Nó que vai receber dados do sensor referente a temperatura.
- Índice de Temperatura/Umidade (ITU): Nó que recebe dados do índice ITU, que segundo UFPR (2022) “é um avaliador de conforto humano para o verão, baseado em condições de temperatura e umidade”.    
- Sensor_Umidade: Nó que vai receber dados do sensor referente a umidade.   

#### Text node
- Temperatura Valor: Label com o nome Temperatura
- Umidade Valor: Label com o nome Umidade
- ITU: Label Índice de Temperatura e Umidade        

#### Switch node                                 
- alerta_temperatura:  Envio de alerta para temperatura maior ou igual a 85, maior ou igual a 65 ou menor ou igual a 65.
- alerta_umidade: Envio de alerta para umidade, maior ou igual a 40, ou maior ou igual 30 e menor que 30     

#### Gauge node
- Temperatura: Medidor, onde será exibida a leitura do sensor do sensor
- Umidade: Medidor, onde será exibida a leitura do sensor do sensor

##### Notification Node
- Alerta Temp Max: Mensagem de notificação “Temperaturas Alarmantes! Se hidrate!”
- Alerta Temp: Mensagem de notificação “Temperaturas altas, lembre-se de se hidratar!"
- Alerta Umid: Mensagem de notificação "Umidade baixa, lembre-se de se hidratar!"   
- Alerta Umid Min: Mensagem de notificação "Umidade baixíssima! Se hidrate!”

### Chart Node
- Índice de Calor: Exibirá a leitura do sensor

Sobre a codificação para fazer conexão com ESP8266, bem como o LED e sensor DHT11, presente no Arduino IDE, segue a seguir suas principais pontos:
Os quadros de 1 a 7 servem como declarações constantes a serem utilizados no desenvolvimento: 
O quadro 1 demonstra as bibliotecas que precisavam ser utilizadas como ESP8266, PubSubCliente que permite que ESP8266 faça a comunicação com o Node-RED e o sensor de temperatura e umidade, o DHT.
```C

```


