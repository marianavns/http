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