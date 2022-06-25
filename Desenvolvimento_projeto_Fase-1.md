
## INTRODUÇÃO    

Hoje em dia, as pessoas prezam por um bem-estar e estarem seguras seja qual espaço que estejam requerendo o bom tratamento ou estando em um lugar que elas se sintam à vontade, diante disso, elas podem contar com o apoio da Internet das Coisas, que segundo Bertoncello (2020), são dispositivos conectados à internet que enviam dados para serem manipulados, visando sempre que possível trazer melhores retornos para os usuários.

Considerando que a Internet das coisas tem como o foco a captação de dados para futuras manipulações, umas dessas captações acontecem por meio de sensores, que segundo Abreu (2022) eles “[...]coletam informações do ambiente e se comunicam permitindo que os diversos componentes que compõe esse sistema troquem dados entre si [...]”, diante disso, estes sensores podem ser aplicados por diversas partes, seja na área da saúde, na captação de presença ou sinais virtuais, seja na segurança, como forma de detectar objetos ou acessos a certos lugares, outras aplicações que fazem do uso com objetivo de assegurar o exercício regular das atividades variadas.

Sobre os sensores na Internet das Coisas, há aqueles que são classificados como IoT, que segundo Abreu (2022), eles são “[...] responsáveis por “ler” o ambiente, gerar informações e transmitir sinais entre outros sensores e entre eles e o controlador [...]”, considerando que se objetivam a captar variações do objeto ou ambiente, eles podem ser trabalhados na perspectiva de trazer situações que aos olhos não conseguem captar e isso dar opção do indivíduo saber julgar conforme a percepção racional, não mais como modelo antigo que é o julgamento irracional, ou seja, subjetiva.

Diante disso, os sensores já estão trazendo bons resultados, possibilitando ao usuário ter ótimos retornos sobre o passado, em questão da avaliação da presença em determinado tempo específico, do fato corrente, que acontecem eventos que são importantes serem captadas e tratadas (se possível).

## Justificativa

Manter-se hidratado é tão importante quanto respirar, principalmente em dias com altas temperaturas e baixa umidade. Porém, muitas pessoas esquecem de se hidratar durante o dia, considerando usar meios físicos para auxiliar e manipular o nosso dia a dia, para que possamos ser mais flexíveis em questão de lembrar dos atos simples como beber água, sendo assim entra a internet das coisas para dar suporte a essa rotina.

Nos últimos anos, a Internet das Coisas vem se tornando cada vez mais popular e importante. Podendo conectar objetos do dia a dia à internet, permitindo uma comunicação perfeita entre pessoas e processos. Os sistemas digitais podem registrar, monitorar e ajustar cada interação entre os itens conectados, assim o mundo físico encontra o mundo digital e eles trabalham juntos.

### Objetivo Geral:

Entender o desenvolvimento e a construção de  objetos físicos incorporados a sensores, software e outras tecnologias, para o auxílio no cotidiano a partir da conexão e trocar dados com outro dispositivo, a fim de auxiliar o bem estar humano.

### Objetivo Específico:

Analisar a temperatura e umidade para fornecer informações de alerta sobre o clima para garantir uma boa hidratação e bem estar em climas mais amenos.

### Componentes:

- **Arduino** - O Arduino é uma plataforma de prototipagem eletrônica de hardware livre e de placa única, que possibilita o desenvolvimento dos mais diversos projetos robóticos, atuando como um tipo de cérebro eletrônico programável de simplificada utilização, com diversas portas para conexões com módulos e sensores.

- **LED** - LED ou diodo emissor de luz, é um componente eletrônico usado para a emissão de luz. Especialmente utilizado em produtos de microeletrônica como sinalizador de avisos.

- **Sensor DHT11 (Temperatura e umidade)** - O DHT11 possui um controlador de 8 bits que converte o sinal de temperatura e umidade dos sensores e um sinal serial e envia ao Arduino através do pino de dados (Data). O sensor DHT11 pode medir temperaturas entre 0 a 50º Celsius com uma precisão de 2 graus, e umidade entre 20 a 90 % com uma precisão de 5%.

- **Buzzer** - O buzzer é um componente eletrônico que funciona a partir de uma diferença de potencial aplicada que gera uma deformação mecânica variável, produzindo assim uma onda sonora.

## Metodologia 

Após montarmos a parte física das coisas, começamos o desenvolvimento do sistema, utilizando o exemplo dado pelo site: [filipeflop](https://www.filipeflop.com/blog/monitorando-temperatura-e-umidade-com-o-sensor-dht11/), configuramos o que tínhamos com o que era necessário, como o sistema de luzes, mas tivemos o primeiro problema, precisávamos de uma biblioteca para o arduino saber como interpretar o componente DHT11, no próprio site onde estávamos pegando as informações tinha um link para o repositório Github do “DHT-sensor-library”, descompactamos, renomeamos para DHT (isto é uma ação necessária para o funcionamento) e colocamos na pasta libraries do arquivo do arduino, mas isso gerou o segundo problema, tivemos problema na parte de permissões do computador, para resolver isso tivemos que baixar uma nova versão do arduino, onde tínhamos permissão para realizar alterações, com a biblioteca instalada e o código pronto, rodamos novamente o teste, porém ele falhou, a biblioteca DHT11 precisava de uma dependência a mais, a “Adafruit_Sensor”, nós conseguimos encontrar o link para essa dependência no próprio link onde encontramos o DHT11, baixamos e anexamos a dependência do Adafruit as bibliotecas do arduino e rodamos o código novamente, finalmente obtivemos sucesso. O nosso dispositivo estava funcional e operante, agora só precisaremos ajustar o modelo de cálculo de temperatura.

### Funcionamento:

O sensor funcionará continuamente, analisando a temperatura e umidade do ar, onde será feito o cálculo do Índice de Temperatura e Umidade (ITU), então liga-se um Led correspondente às condições climáticas atuais.

Onde quando as condições forem favoráveis o led acesso será verde, condições de desconforto moderado acenderá o led amarelo, e situações com grandes desconfortos será acesso o led vermelho juntamente com um alerta sonoro.

## Conclusões



## Trabalhos Futuros

A montagem do Dispositivo de medição foi a parte mais fácil, o sistema de medição em si foi onde encontramos mais dificuldades, principalmente no desenvolvimento do cálculo de medição do Índice de Temperatura-Umidade (ITU).

Futuramente depois da correção de erros planejamos atualizar algumas funções do dispositivo, como: Integração com outros dispositivos e Integração para um aplicativo mobile onde terão informações mais detalhadas.

## Referências
