# Seminário sobre comunicação de serviços web para IoT

## Introdução

### O que é a solução?

**Conexão MQTT**

O MQTT (do inglês *Message Queue Telemetry Transport*) é um protocolo de comunicação entre máquinas. Está se tornando um dos principais protocolos para implementações de Internet das Coisas (IoT), uma tendência de aplicação na indústria ou mesmo no dia a dia das pessoas. 

**O que é o MQTT e como ele funciona?**

Basicamente, o protocolo permite o envio de mensagens e comandos entre os dispositivos que falam MQTT por meio de TCP/IP.

Sendo projetado para passar apenas os dados solicitados, usando uma performance de baixa largura de banda, não sobrecarregando internet e, assim, melhora a comunicação entre vários dispositivos.

Outra vantagem é a simples codificação, o que facilita que o MQTT funcione em sistemas não tão modernos ou com problemas de armazenamento.

***Broker***

Um dispositivo pode ser “inscrito=*subscribed*” ou uma “publicação=*publish*”. 

- Quando tal dispositivo é um *Publish*, ele publica informações pré-estabelecidas. 

- Já o dispositivo *Subscribe* recebe todas essas informações que estão sendo publicadas.

O Broker é um servidor que gere as informações aos inscritos e vice-versa, funcionando como um intermediário entre *Subscribers* e *Publishers*, podendo ser tanto um servidor local, como uma estrutura em nuvem. 

Além de armazenar, o Broker também filtra as informações. Os dados deste servidor estão armazenados em tópicos e, os Subscribers escolhem quais os tópicos querem se inscrever e receber apenas os que os convém, ou seja, recebendo todas as mensagens, e decidindo quem está interessado e inscrito nela ou não.




### Quais as aplicações e relações com IoT?

[comment]: <> (Conexões q podem ser realizadas com o mqtt e sua conexão)

**MQTT e Internet das Coisas**

Cada vez mais dispositivos ganham a capacidade de se conectarem à internet. Mas para que estes dispositivos e máquinas conversem entre si, é necessário um protocolo de comunicação. O MQTT, de forma simples, leve e segura, possibilita toda essa dinâmica.

Esta era uma tendência que está se tornando realidade. Manufaturas começam a se adaptar para se enquadrarem na Indústria 4.0 com as tecnologias de IIoT (Industry Internet of Things). Tal recurso permite que as manufaturas obtenham dados de e para dispositivos de uma rede, independente do lugar do mundo que estejam situados.


**MQTT na prática**

O protocolo MQTT tem grande valia na manufatura. Imagina que você tem uma linha de produção de caixas de leite. No seu processo você necessita armazenar a produção em um local com temperatura monitorada. Sem a integração destas informações, você necessitará de um profissional para periodicamente verificar a temperatura do armazenamento do produto e tomar medidas caso necessário.  

Com um protocolo MQTT, as informações de temperatura são coletadas e armazenadas no Broker no tópico “temperatura”, por exemplo. A partir do momento que você escolher os Subscriber, eles vão receber apenas as informações relativas a este tópico nos dispositivos cadastrados, facilitando o acesso aos dados de temperatura para as análises necessárias. Isto deixará sua equipe mais produtiva e você economiza recursos.


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

https://www.hitecnologia.com.br/blog/o-que-e-protocolo-mqtt/


https://www.gta.ufrj.br/ensino/eel878/redes1-2019-1/vf/mqtt/#:~:text=As%20vantagens%20s%C3%A3o%3A%20baixo%20consumo,o%20baixo%20consumo%20de%20banda.
