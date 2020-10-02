# resumo-http
Resumo baseado no curso Alura "HTTP: Entendendo a web por baixo dos panos"

Itens tratados no curso:

- A Web Segura (HTTP e HTTPs)
- Endereços, Domínios e Portas
- Sessões, Cookies e Servidores
- Parâmetros de Requisição e Resposta
- Serviços REST (verbos usados pelo HTTP)
- Última versão do HTTP

# Sumário
○ [Introdução](#Introdução)
○ [HTTP e HTTPS](#HTTP-e-HTTPS)

# Introdução
> Curso da Alura </br>*HTTP - Entendendo a Internet Por Baixo dos Panos: Aula 01*

**HTTP** (**Hypertext Transfer Protocol**) é um canal de comunicação que une o **cliente** - quem recebe o conteúdo - e o **servidor** - quem envia o conteúdo. 

Ou seja: o HTTP funciona no **Modelo Cliente-Servidor**, baseando-se em um conjunto de regras.

HTTP é independente da plataforma de desenvolvimento, sendo aplicável em .Net, PHP, Java, entre outros.

Os detalhes das regras de comunicação HTTP estão disponíveis num RFC (ou *Request For Comments* - documento técnico) mantido pela *The Internet Society* e pela *Internet Engineering Task Force*: [RFC HTTP](https://tools.ietf.org/html/rfc2616).

Numa arquitetura completa, funciona assim: 
1. O cliente faz uma requisição via HTTP;
2. A requisição vai para o servidor;
3. O servidor solicita ao banco de dados o conteúdo pedido;
4. O banco de dados responde ao servidor;
5. O servidor devolve uma resposta ao cliente.

 Exemplo da Alura:

```js
Cliente  <-- HTTP --> Servidor Java  <---- SQL ----> Banco de dados
          protocolo de              linguagem para se 
          comunicação             conectar com o banco
                                        de dados
```

✎ Existem outros modelos de comunicação além do "cliente-servidor", como o P2P, ou Peer-To-Peer. 

✎ E existem outros protocolos de comunicação também, como o BitTorrent, FTP, SMTP...

# HTTP e HTTPS
> Curso da Alura </br>*HTTP - Entendendo a Internet Por Baixo dos Panos: Aula 02*

`ALERTA!` O HTTP transporta as requisições do usuário como um texto puro! Se o site acessado pelo usuário for apenas "http" e houver uma solicitação de login e senha, por exemplo, esses dados pessoais trafegarão até o servidor como um texto. 

⚠️ Isso pode ser perigoso, pois invasores podem roubar as informações confidenciais nos intervalos por onde elas passam: modem, roteador, provedor...

Como solução, foi criado o HTTPS - *Hypertext Transfer Protocol Secure*, que usa recursos de criptografia para conectar cliente e servidor.

O protocolo *HTTPS nada mais é do que o protocolo HTTP com uma camada adicional de segurança*, a camada TLS(Transport Layer Security) ou seu antecessor SSL (Secure Sockets Layer). Ambos são protocolos também, mas de segurança.

Porém para o navegador realmente confiar nesse site, ele precisa ter uma identidade confirmada: o **certificado digital**, cedido por uma **autoridade certificadora**. Esse certificado tem uma chave pública que vai criptografar todos os dados que o cliente envia para o servidor. Lá do outro lado, no servidor, existe uma outra chave, agora uma chave privada, para descriptografar as informações. 

obs.: Na verdade quem possui a chave privada é uma aplicação Web que, no exemplo anterior, é a aplicação da Alura. 

Chamamos essa forma de criptografia de **criptografia assimétrica**. Mas ela tem um problema sério: é lenta.

Já na segunda forma de criptografia, a **criptografia simétrica**, o cliente e servidor têm a mesma chave. Ela é mais rápida, ok. Mas menos segura.

Então, olha só, o HTTPS usa as duas formas para fazer a comunicação! Assim:

- Cliente recebe a chave pública via certificado digital;
- Servidor continua com sua chave privada;
- O cliente gera duas chaves simétricas;
- E envia uma dessas chaves para o servidor, usando a chave assimétrica (já que a chave do servidor ainda é a primeira);
- Essas duas chaves simétricas serão usadas para todas as requisições seguintes, com os dados criptografados normalmente.

✎ É possível ver o certificado dos sites em `Inspecionar > Security`. Dá pra ver a data de emissão e expiração do certificado, além da autoridade certificadora.



