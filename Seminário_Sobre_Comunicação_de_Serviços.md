# Seminário sobre comunicação de serviços web para IoT

## Introdução

### O que é a solução?

**Conexão MQTT**

O MQTT (do inglês Message Queue Telemetry Transport) é um protocolo de comunicação entre máquinas.

O MQTT está se tornando um dos principais protocolos para implementações de Internet das Coisas (IoT), uma tendência de aplicação na indústria ou mesmo no dia a dia das pessoas. 

***O que é o MQTT e como ele funciona?***

Basicamente, o protocolo permite o envio de mensagens e comandos entre os dispositivos que falam MQTT por meio de TCP/IP.

Sendo projetado para passar apenas os dados solicitados, há a melhora da performance com baixa largura de banda, não sobrecarregando internet e dispositivo e, assim, melhora a comunicação entre vários dispositivos.

Outra vantagem é a simples codificação, o que facilita que o MQTT funcione em sistemas não tão modernos ou com problemas de armazenamento.

***Broker***

Um dispositivo pode ser “inscrito= subscribed” ou uma “publicação=publish”. 

- Quando tal dispositivo é um Publish, ele publica informações pré-estabelecidas. 

- Já o dispositivo Subscribe recebe todas essas informações que estão sendo publicadas.

O Broker é um servidor que gere as informações aos inscritos e vice-versa, funcionando, então, como um intermediário entre Subscribers e Publishers, podendo ser tanto um servidor local, como uma estrutura em nuvem. 

Além de armazenar, o Broker também filtra as informações. Os dados deste servidor estão armazenados em tópicos e, os Subscribers escolhem quais os tópicos querem se inscrever e receber apenas os que os convém. *O Broker recebe todas as mensagens, filtra e decide quem está interessado e inscrito nela ou não.*


### Quais as aplicações e relações com IoT?

***Conexões q podem ser realizadas com o mqtt e sua conexão***

## Aplicação do serviço

### Como usar?

***como usar o mqtt***

- Quais requisitos para utilização?

- Quais passos técnicos para utilizar? Descreva claramente o(s) exemplo(s).


### Estudo de caso do projeto da disciplina
- Como pode ser empregado no seu projeto? Como poder ser a comunicação com o dispositivo programado (arduino/Esp8266/Raspberry/...)?

***Como usar o MQTT no nosso projeto***

## Considerações finais
### Quais os principais resultados obtidos no uso do serviço?
### Existem outros serviços de concorrentes? Comente sobre eles.
