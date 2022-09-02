# PROJETO SENSOR DE TEMPERATURA E UMIDADE
**INSTITUTO FEDERAL DE EDUCAÇÃO, CIÊNCIA E TECNOLOGIA DO RIO GRANDE DO NORTE**

Alunos: ***ALAN ALVES DA SILVA*** e ***HETRISLEY DA SILVA GOMES***

Discente: ***Prof. Dr. Valerio Gutemberg de Medeiros Junior***

Parnamirim – RN / 2022

**SÚMARIO:**

- [Introdução](#introdução)
- [Desenvolvimento](#desenvolvimento)
- [Metodologia](#metodologia)
- [Conclusões](#conclusões)
- [Considerações Finais](#considerações-finais)
- [Referências](#referências)
- [Anexos](#anexo)

---
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

#### Chart Node
- Índice de Calor: Exibirá a leitura do sensor

### CODIFICAÇÃO DO PROJETO

Sobre a codificação para fazer conexão com ESP8266, bem como o LED e sensor DHT11, presente no Arduino IDE, segue a seguir suas principais pontos:
Os quadros de 1 a 7 servem como declarações constantes a serem utilizados no desenvolvimento: 

Nesse quadro demonstra as bibliotecas que precisavam ser utilizadas como ESP8266, PubSubCliente que permite que ESP8266 faça a comunicação com o Node-RED e o sensor de temperatura e umidade, o DHT.
```C
#include <ESP8266WiFi.h>          //Biblioteca para funcionamento do WiFi do ESP8266
#include <PubSubClient.h>
#include "DHT.h"
```

Nesse quadro são demonstradas as constantes utilizadas para fazer conexão com o ESP8266, tais como o DHTPIN que está conectado à pinagem 2 e DHTTYPE que está conectado ao DHT11.
```C
#define INTERVALO_ENVIO 1000
#define DHTPIN 2                       // pino que estamos conectado o sensor
#define DHTTYPE DHT11          // DHT 11
```

Nesse quadro demonstramos o uso dos sensores DHT como parâmetro, para serem utilizados na função de leitura do sensor, principalmente no quadro 13.
```C
DHT dht(DHTPIN, DHTTYPE);
```

Nesse quadro Foram utilizados conexão Wifi, fornecidos pelo docente em sala, para fazer a ligação com a placa ESP8266, como demonstrado o login e senha
```C
const char* ssid = "v2g";                           // Rede WiFi
const char* password = "qwertyuiop";
```

Para utilizar o servidor em nuvem, foi feito a conexão com mosquitto, para preparar as informações de conexão a ele, deixamos variáveis prontas
```C
const char* mqttServer = "test.mosquitto.org";              //servidor
const char* mqtt_username = NULL;                           //usuário
const char* mqtt_password = NULL;                           //senha
const int mqttPort = 1883;                                  //porta
const char* mqttTopicSub ="htrsly/sensor/temperatura";      //tópico que sera assinado
int ultimoEnvioMQTT = 0;                                    // inicializa com zero  

WiFiClient espClient;
PubSubClient client(espClient);
```

Criamos variáveis também para cada pino de LED de alerta, que fica no dispositivo físico:
```C
// Define o pino 8 para o alerta de temperatura baixa
int AlertaVerde=5;
// Define o pino 12 para o alerta de temperatura média
int AlertaAmarelo=4;
// Define o pino 13 para o alerta de temperatura alta
int AlertaVermelho=0;
```
#### Pré Configuração


Para início da configuração, os pinos foram classificados como verde, amarelo e verde, conforme as cores do leds disponíveis no laboratório, eles estão sendo acionados para funcionar como modo de saída. Nessa ocasião, faz a inicialização do serial e o sensor de temperatura
```C
void setup() {
  pinMode(AlertaVerde, OUTPUT);
  pinMode(AlertaAmarelo, OUTPUT);
  pinMode(AlertaVermelho, OUTPUT);
  Serial.begin(115200);
  dht.begin();

```

Fazemos a inicialização da internet, usando como parâmetro o login e senha
Após a inicialização do wifi, torna-se necessário que faça o teste de conexão, conforme o quadro 4, onde o usuário pode saber se foi sucedido ou não. Verificando se o wi-fi conectado está diferente do status do wi-fi, considerando isso, enquanto estiver tentando fazer conexão, ele irá está imprimindo o ponto. Se estiver conectado, deve fazer impressão no serial do IP, o cliente utilizará os parâmetros de servidor, conectando com o servidor MQTT e também estará setando o callback, que tem como propósito fazer uso de outras funções. 
Ainda nesse quadro, verificamos a conexão com ESP8266, se for sucesso, deve dizer que fez a conexão ao broker mqtt público, caso contrário, continuará tentando estabelecer a conexão.
```C
WiFi.begin(ssid, password); 
 while (WiFi.status() != WL_CONNECTED) { //Enquanto estiver aguardando status da conexão
    delay(1000);
    Serial.print(".");                                     //Imprime pontos
  }
  Serial.println("");
  Serial.println("WiFi Conectado");
  Serial.print("IP: ");
  Serial.println(WiFi.localIP());              //Função para exibir o IP da ESP8266  
  client.setServer(mqttServer, mqttPort);
  client.setCallback(callback);

   while (!client.connected()) {
      String client_id = "esp8266-client-";
      client_id += String(WiFi.macAddress());
      Serial.printf("The client %s connects to the public mqtt broker\n", client_id.c_str());
      if (client.connect(client_id.c_str(), mqtt_username, mqtt_password)) {
      } else {
          Serial.print("failed with state ");
          Serial.print(client.state());
          delay(2000);
      }
  }
}
```
#### Loop

O Loop ficará executando o comando de fazer leitura do sensor continuamente, com um intervalo de 2 segundos.
```C
void loop() {
  enviaDHT();
  delay(2000); 
  client.loop();
}
```

Uma função callback é uma função passada a outra função como argumento, que é então invocado dentro da função externa para completar algum tipo de rotina ou ação, no nosso caso, verifica a integridade da conexão com o protocolo MQTT.
```C
void callback(char *topic, byte *payload, unsigned int length) {
    Serial.print("Message arrived in topic: ");
    Serial.println(topic);
    Serial.print("Message:");
    for (int i = 0; i < length; i++) {
        Serial.print((char) payload[i]);
    }
    Serial.println();
    Serial.println("-----------------------");
}
```

Aqui estamos fazendo leitura dos dados de temperatura, umidade e o índice de calor, os LEDs também acenderão de acordo com o valor recebido, se estiver com algum problema na leitura, todos os LEDs acenderão, caso contrário, acenderá o LED de acordo com o grau de Calor do índice de temperatura, o qual nós colocamos o nome de “ITU”.
```C
void enviaDHT(){
 
  char MsgUmidadeMQTT[10];
  char MsgTemperaturaMQTT[10];
  char MsgITU[10];
  float h = dht.readHumidity();
  float t = dht.readTemperature();

  float itu = dht.computeHeatIndex(t, h, false); 
 
  if (isnan(t) || isnan(h)) 
  {
    digitalWrite(AlertaVerde, HIGH);
    digitalWrite(AlertaAmarelo, HIGH);
    digitalWrite(AlertaVermelho, HIGH);
    Serial.println(F("Failed to read from DHT sensor!"));
  } else {

   if (itu > 90){
      digitalWrite(AlertaVerde, LOW);
      digitalWrite(AlertaAmarelo, LOW);
      digitalWrite(AlertaVermelho, HIGH);
  
    
    } else if (itu > 75){
      digitalWrite(AlertaVerde, LOW);
      digitalWrite(AlertaAmarelo, HIGH);
      digitalWrite(AlertaVermelho, LOW);
    } else {
      digitalWrite(AlertaVerde, HIGH);
      digitalWrite(AlertaAmarelo, LOW);
      digitalWrite(AlertaVermelho, LOW);
    }
    //
      Serial.print("Umidade: ");
      Serial.print(h);
      Serial.print(" %t\n");
      Serial.print("Temperatura: ");
      Serial.print(t);
      Serial.println(" *C");
      Serial.println(itu);
    //
    sprintf(MsgUmidadeMQTT,"%f",h);
    client.publish("htrsly/sensor/umidade", MsgUmidadeMQTT);
    sprintf(MsgTemperaturaMQTT,"%f",t);
    client.publish("htrsly/sensor/temperatura", MsgTemperaturaMQTT);
    sprintf(MsgITU,"%f",itu);
    client.publish("htrsly/sensor/itu", MsgITU);
  }
}
```

### Os Dados:
Após a configuração elaborada anteriormente, caso sucedido, podemos observar o comportamento no serial do arduino, conforme a figura 06, onde está sendo visualizado a umidade em termos percentuais, a temperatura em Celsius e o índice de temperatura e umidade (ITU). 

Com os dados lidos pelo sensor, e enviados pelo MQTT até o Node Red, fomos capaz de criar um Dashboard com os dados recebidos

Figura 01: Leitura em ambiente gráfico

<img src="/images/Dashboard_node.PNG" style="width: 500px"/>

Fonte: Autoria própria (2022)

O protótipo físico funcionando conectado ao computador do laboratório com o ESP8266, como segue a figura 02:

<img src="/images/Aparelho.PNG" style="width: 500px"/>

Fonte: Autoria própria (2022)

## CONSIDERAÇÕES FINAIS

Considerando o objetivo inicial do projeto de elaborar a construção de protótipo que possa retornar a temperatura e umidade para servir de alerta para manter a hidratação, acreditamos que fomos bem sucedidos.

Não foi considerado uma tarefa fácil, tivemos que obter conhecimentos teóricos a respeito da Internet das Coisas e estudar sobre o funcionamento sobre sensores, especificamente a respeito da temperatura e umidade, capturados por meio do DHT11, além disso, passando por várias falhas e ajustes para fazer a entrega básica com a conexão com internet e uso do MQTT e Node-Red.

Como de costume, ainda falta alguns ajustes e implementações, que ficam como projetos futuros como o uso do botão e o acionamento de alarme,  o primeiro seria útil para quando for acionado o alerta vermelho, acionaria o alarme e o usuário tivesse capacidade de desligar o alarme por meio do botão.

## REFERÊNCIA
BERTONCELLO, Soraya Damasio. IoT: sensores que facilitam a vida. 2020. Disponível em: https://www.novus.com.br/blog/artigo-iot-sensores-que-facilitam-a-vida/. Acesso em: 24 jun. 2022.

BLOGDAROBOTICA (org.). Medindo temperatura e umidade usando o sensor DHT11. 2020. Disponível em: https://www.blogdarobotica.com/2020/10/29/medindo-temperatura-e-umidade-usando-o-sensor-dht11/. Acesso em: 01 set. 2022.

CANALTECH (org.). O que é Arduíno? 2015. Disponível em: https://canaltech.com.br/hardware/o-que-e-arduino/. Acesso em: 01 set. 2022.

CASADAROBOTICA (org.). Protoboard 830 Furos. Disponível em: https://www.casadarobotica.com/prototipagem-e-ferramentas/prototipagem/protoboard/protoboard-830-furos-pontos. Acesso em: 01 set. 2022.

FILIPEFLOP (org.). Sensor de Umidade e Temperatura DHT11. Disponível em: https://www.filipeflop.com/produto/sensor-de-umidade-e-temperatura-dht11/. Acesso em: 01 set. 2022.

IMASTERS (org.). Servidor Eclipse Mosquitto MQTT na Nuvem: como criar uma rede iot pessoal. Como Criar uma Rede IoT Pessoal. Disponível em: https://imasters.com.br/cloud/servidor-eclipse-mosquitto-mqtt-na-nuvem-como-criar-uma-rede-iot-pessoal. Acesso em: 01 set. 2022.

KALATEC (org.). Como o Protocolo MQTT funciona e quais são as suas vantagens? Disponível em: https://blog.kalatec.com.br/protocolo-mqtt/. Acesso em: 01 set. 2022.

MUNDODELÉTRICA (org.). O que é um LED? Disponível em: https://www.mundodaeletrica.com.br/o-que-e-um-led/. Acesso em: 01 set. 2022.

MUNDODAELETRICA (org.). O que é um resistor? Disponível em: https://www.mundodaeletrica.com.br/o-que-e-um-resistor/. Acesso em: 01 set. 2022.

NODERED (org.). Node-RED: low-code programming for event-driven applications. Low-code programming for event-driven applications. Disponível em: https://nodered.org/. Acesso em: 01 set. 2022.

UFPR. ÍNDICES DE DESCONFORTO HUMANO. Disponível em: https://fisica.ufpr.br/grimm/aposmeteo/cap3/cap3-4.html. Acesso em: 02 set. 2022.
USINAINFO (org.). ESP8266. Disponível em: https://www.usinainfo.com.br/esp8266-610#. Acesso em: 01 set. 2022.


























## Anexos

**Código Completo do Arduino (ESP8266)**
```C
// Importando as bibliotecas
#include<ESP8266WiFi.h> //Biblioteca para funcionamento do WiFi do ESP
#include <PubSubClient.h>

#include "DHT.h"

//definindo o sensor
#define DHTPIN 2 // pino que estamos conectado
#define DHTTYPE DHT11 // DHT 11

DHT dht(DHTPIN, DHTTYPE);

// conectando ao wifi
const char* ssid = "v2g";  // Rede WiFi
const char* password = "qwertyuiop";

//informações do broker MQTT - Verifique as informações geradas pelo CloudMQTT
const char* mqttServer = "test.mosquitto.org";   //server
const char* mqtt_username = NULL;              //user
const char* mqtt_password = NULL;      //password
const int mqttPort = 1883;                     //port
const char* mqttTopicSub ="htrsly/sensor/temperatura";            //tópico que sera assinado
int ultimoEnvioMQTT = 0;

WiFiClient espClient;
PubSubClient client(espClient);

// Define o pino 8 para o alerta de temperatura baixa
int AlertaVerde=5;
// Define o pino 12 para o alerta de temperatura alta
int AlertaAmarelo=4;
// Define o pino 13 para o alerta de temperatura alta
int AlertaVermelho=0;





void setup() {
// put your setup code here, to run once:
  pinMode(AlertaVerde, OUTPUT);
  pinMode(AlertaAmarelo, OUTPUT);
  pinMode(AlertaVermelho, OUTPUT);
  Serial.begin(115200);
  //pinMode(Som, OUTPUT);
  //pinMode(4, INPUT);
  dht.begin();
  
  WiFi.begin(ssid, password); //Inicialização da comunicação Wi-Fi
  //Verificação da conexão
  while (WiFi.status() != WL_CONNECTED) { //Enquanto estiver aguardando status da conexão
    delay(1000);
    Serial.print("."); //Imprime pontos
  }
  Serial.println("");
  Serial.println("WiFi Conectado");
  Serial.print("IP: ");
  Serial.println(WiFi.localIP()); //Função para exibir o IP da ESP
  
  client.setServer(mqttServer, mqttPort);
  client.setCallback(callback);

   while (!client.connected()) {
      String client_id = "esp8266-client-";
      client_id += String(WiFi.macAddress());
      Serial.printf("The client %s connects to the public mqtt broker\n", client_id.c_str());
      if (client.connect(client_id.c_str(), mqtt_username, mqtt_password)) {
      } else {
          Serial.print("failed with state ");
          Serial.print(client.state());
          delay(2000);
      }
  }
}

void loop() {
  Serial.print("teste1");

  enviaDHT();
  delay(2000);
  
  client.loop();
}

void callback(char *topic, byte *payload, unsigned int length) {
    Serial.print("Message arrived in topic: ");
    Serial.println(topic);
    Serial.print("Message:");
    for (int i = 0; i < length; i++) {
        Serial.print((char) payload[i]);
    }
    Serial.println();
    Serial.println("-----------------------");
}

//função para leitura do DHT11
void enviaDHT(){
 
  char MsgUmidadeMQTT[10];
  char MsgTemperaturaMQTT[10];
  char MsgITU[10];
  float h = dht.readHumidity();
  float t = dht.readTemperature();


  float itu = dht.computeHeatIndex(t, h, false);
 
  
  if (isnan(t) || isnan(h)) 
  {
    digitalWrite(AlertaVerde, HIGH);
    digitalWrite(AlertaAmarelo, HIGH);
    digitalWrite(AlertaVermelho, HIGH);
    Serial.println(F("Failed to read from DHT sensor!"));
  } else {

   if (itu > 90){
      digitalWrite(AlertaVerde, LOW);
      digitalWrite(AlertaAmarelo, LOW);
      digitalWrite(AlertaVermelho, HIGH);
      
    } else if (itu > 75){
      digitalWrite(AlertaVerde, LOW);
      digitalWrite(AlertaAmarelo, HIGH);
      digitalWrite(AlertaVermelho, LOW);
    } else {
      digitalWrite(AlertaVerde, HIGH);
      digitalWrite(AlertaAmarelo, LOW);
      digitalWrite(AlertaVermelho, LOW);
    }
    //
      Serial.print("Umidade: ");
      Serial.print(h);
      Serial.print(" %t\n");
      Serial.print("Temperatura: ");
      Serial.print(t);
      Serial.println(" *C");
      Serial.println(itu);
    //
    sprintf(MsgUmidadeMQTT,"%f",h);
    client.publish("htrsly/sensor/umidade", MsgUmidadeMQTT);
    sprintf(MsgTemperaturaMQTT,"%f",t);
    client.publish("htrsly/sensor/temperatura", MsgTemperaturaMQTT);
    sprintf(MsgITU,"%f",itu);
    client.publish("htrsly/sensor/itu", MsgITU);
  }
}
```

** Código do dashboard do nodered **
```JSON
[
    {
        "id": "962e794ab22e0aa9",
        "type": "tab",
        "label": "IoT",
        "disabled": false,
        "info": "",
        "env": []
    },
    {
        "id": "eb2a9a4baf93b815",
        "type": "mqtt in",
        "z": "962e794ab22e0aa9",
        "name": "Sensor_Temperatura",
        "topic": "htrsly/sensor/temperatura",
        "qos": "2",
        "datatype": "auto-detect",
        "broker": "14245302f91be584",
        "nl": false,
        "rap": true,
        "rh": 0,
        "inputs": 0,
        "x": 280,
        "y": 200,
        "wires": [
            [
                "c5add9221b9ce4ef",
                "8e69c099627e0fc9",
                "3080777252909c1f"
            ]
        ]
    },
    {
        "id": "d278d9fa5ac004e7",
        "type": "mqtt in",
        "z": "962e794ab22e0aa9",
        "name": "Sensor_Umidade",
        "topic": "htrsly/sensor/umidade",
        "qos": "2",
        "datatype": "auto-detect",
        "broker": "14245302f91be584",
        "nl": false,
        "rap": true,
        "rh": 0,
        "inputs": 0,
        "x": 260,
        "y": 440,
        "wires": [
            [
                "cdbf1258c8e1a115",
                "99ab3d9a52a1d8f8",
                "ca6cec5d10a57e4d"
            ]
        ]
    },
    {
        "id": "3cf82d14b1654e09",
        "type": "mqtt in",
        "z": "962e794ab22e0aa9",
        "name": "Indice de Temperatura/Humidade",
        "topic": "htrsly/sensor/itu",
        "qos": "2",
        "datatype": "auto-detect",
        "broker": "14245302f91be584",
        "nl": false,
        "rap": true,
        "rh": 0,
        "inputs": 0,
        "x": 310,
        "y": 320,
        "wires": [
            [
                "3f4acb78c4cd5806",
                "53847adbc41d7faa"
            ]
        ]
    },
    {
        "id": "8e69c099627e0fc9",
        "type": "switch",
        "z": "962e794ab22e0aa9",
        "name": "alerta_temperatura",
        "property": "payload",
        "propertyType": "msg",
        "rules": [
            {
                "t": "gte",
                "v": "40",
                "vt": "str"
            },
            {
                "t": "gte",
                "v": "27",
                "vt": "str"
            },
            {
                "t": "lt",
                "v": "27",
                "vt": "str"
            }
        ],
        "checkall": "true",
        "repair": false,
        "outputs": 3,
        "x": 570,
        "y": 200,
        "wires": [
            [
                "6a4c7a20d9c094b8"
            ],
            [
                "d09fdcdda18fa9d2"
            ],
            []
        ]
    },
    {
        "id": "99ab3d9a52a1d8f8",
        "type": "switch",
        "z": "962e794ab22e0aa9",
        "name": "alerta_umidade",
        "property": "payload",
        "propertyType": "msg",
        "rules": [
            {
                "t": "gte",
                "v": "60",
                "vt": "str"
            },
            {
                "t": "gte",
                "v": "45",
                "vt": "str"
            },
            {
                "t": "lt",
                "v": "45",
                "vt": "str"
            }
        ],
        "checkall": "true",
        "repair": false,
        "outputs": 3,
        "x": 560,
        "y": 440,
        "wires": [
            [],
            [
                "a960b5facd2611c1"
            ],
            [
                "a09913529b42a396"
            ]
        ]
    },
    {
        "id": "c5add9221b9ce4ef",
        "type": "ui_gauge",
        "z": "962e794ab22e0aa9",
        "name": "Temperatura",
        "group": "72c6ed31ece54e57",
        "order": 1,
        "width": 6,
        "height": "4",
        "gtype": "gage",
        "title": "gauge",
        "label": "units",
        "format": "{{value}}",
        "min": 0,
        "max": "60",
        "colors": [
            "#00b500",
            "#e6e600",
            "#ca3838"
        ],
        "seg1": "",
        "seg2": "",
        "className": "",
        "x": 550,
        "y": 260,
        "wires": []
    },
    {
        "id": "cdbf1258c8e1a115",
        "type": "ui_gauge",
        "z": "962e794ab22e0aa9",
        "name": "Umidade",
        "group": "72c6ed31ece54e57",
        "order": 2,
        "width": 6,
        "height": "4",
        "gtype": "gage",
        "title": "gauge",
        "label": "units",
        "format": "{{value}}",
        "min": 0,
        "max": "100",
        "colors": [
            "#00b500",
            "#e6e600",
            "#ca3838"
        ],
        "seg1": "",
        "seg2": "",
        "className": "",
        "x": 540,
        "y": 380,
        "wires": []
    },
    {
        "id": "6a4c7a20d9c094b8",
        "type": "ui_toast",
        "z": "962e794ab22e0aa9",
        "position": "top left",
        "displayTime": "3",
        "highlight": "",
        "sendall": true,
        "outputs": 0,
        "ok": "OK",
        "cancel": "",
        "raw": false,
        "className": "",
        "topic": "Temperaturas Alarmantes! Se hidrate!",
        "name": "Alerta Temp Max",
        "x": 850,
        "y": 160,
        "wires": []
    },
    {
        "id": "d09fdcdda18fa9d2",
        "type": "ui_toast",
        "z": "962e794ab22e0aa9",
        "position": "top left",
        "displayTime": "3",
        "highlight": "",
        "sendall": true,
        "outputs": 0,
        "ok": "OK",
        "cancel": "",
        "raw": false,
        "className": "",
        "topic": "Temperaturas altas, lembre de se hiratar!",
        "name": "Alerta Temp",
        "x": 830,
        "y": 200,
        "wires": []
    },
    {
        "id": "a960b5facd2611c1",
        "type": "ui_toast",
        "z": "962e794ab22e0aa9",
        "position": "top right",
        "displayTime": "3",
        "highlight": "",
        "sendall": true,
        "outputs": 0,
        "ok": "OK",
        "cancel": "",
        "raw": false,
        "className": "",
        "topic": "Humidade Baixa, lembre de se hiratar!",
        "name": "Alerta Umid",
        "x": 830,
        "y": 440,
        "wires": []
    },
    {
        "id": "a09913529b42a396",
        "type": "ui_toast",
        "z": "962e794ab22e0aa9",
        "position": "top right",
        "displayTime": "3",
        "highlight": "",
        "sendall": true,
        "outputs": 0,
        "ok": "OK",
        "cancel": "",
        "raw": false,
        "className": "",
        "topic": "Humidade baixíssima! Se hidrate!",
        "name": "Alerta Umid Min",
        "x": 840,
        "y": 480,
        "wires": []
    },
    {
        "id": "3f4acb78c4cd5806",
        "type": "ui_chart",
        "z": "962e794ab22e0aa9",
        "name": "",
        "group": "72c6ed31ece54e57",
        "order": 6,
        "width": 12,
        "height": 6,
        "label": "Indice de Calor",
        "chartType": "line",
        "legend": "false",
        "xformat": "HH:mm:ss",
        "interpolate": "linear",
        "nodata": "",
        "dot": false,
        "ymin": "",
        "ymax": "",
        "removeOlder": 1,
        "removeOlderPoints": "",
        "removeOlderUnit": "3600",
        "cutout": 0,
        "useOneColor": false,
        "useUTC": false,
        "colors": [
            "#1f77b4",
            "#aec7e8",
            "#ff7f0e",
            "#2ca02c",
            "#98df8a",
            "#d62728",
            "#ff9896",
            "#9467bd",
            "#c5b0d5"
        ],
        "outputs": 1,
        "useDifferentColor": false,
        "className": "",
        "x": 900,
        "y": 300,
        "wires": [
            []
        ]
    },
    {
        "id": "53847adbc41d7faa",
        "type": "ui_text",
        "z": "962e794ab22e0aa9",
        "group": "72c6ed31ece54e57",
        "order": 5,
        "width": 12,
        "height": 1,
        "name": "ITU",
        "label": "Indice de Temperatura e Umidade",
        "format": "{{msg.payload}}",
        "layout": "row-spread",
        "className": "",
        "x": 870,
        "y": 340,
        "wires": []
    },
    {
        "id": "ca6cec5d10a57e4d",
        "type": "ui_text",
        "z": "962e794ab22e0aa9",
        "group": "72c6ed31ece54e57",
        "order": 4,
        "width": 6,
        "height": 1,
        "name": "Umidade Valor",
        "label": "Umidade",
        "format": "{{msg.payload}}",
        "layout": "row-spread",
        "className": "",
        "x": 560,
        "y": 500,
        "wires": []
    },                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          
    {
        "id": "3080777252909c1f",
        "type": "ui_text",
        "z": "962e794ab22e0aa9",
        "group": "72c6ed31ece54e57",
        "order": 3,
        "width": 6,
        "height": 1,
        "name": "Tempoeratura Valor",
        "label": "Temperatura:",
        "format": "{{msg.payload}}",
        "layout": "row-spread",
        "className": "",
        "x": 570,
        "y": 140,
        "wires": []
    },
    {
        "id": "14245302f91be584",
        "type": "mqtt-broker",
        "name": "",
        "broker": "https://test.mosquitto.org/",
        "port": "1883",
        "clientid": "",
        "autoConnect": true,
        "usetls": false,
        "protocolVersion": "4",
        "keepalive": "60",
        "cleansession": true,
        "birthTopic": "",
        "birthQos": "0",
        "birthPayload": "",
        "birthMsg": {},
        "closeTopic": "",
        "closeQos": "0",
        "closePayload": "",
        "closeMsg": {},
        "willTopic": "",
        "willQos": "0",
        "willPayload": "",
        "willMsg": {},
        "userProps": "",
        "sessionExpiry": ""
    },
    {
        "id": "72c6ed31ece54e57",
        "type": "ui_group",
        "name": "Default",
        "tab": "ed01f6537c153731",
        "order": 1,
        "disp": true,
        "width": 12,
        "collapse": false,
        "className": ""
    },
    {
        "id": "ed01f6537c153731",
        "type": "ui_tab",
        "name": "IOT",
        "icon": "dashboard",
        "disabled": false,
        "hidden": false
    }
]

```


