# SOA - Service-Oriented Architecture

<img src="https://github.com/shnonomura/diarioProgramacao/blob/master/SOAP/2020-04-10/soap.png">

**SOAP (Simple Object Access Protocol, em português Protocolo Simples de Acesso a Objetos)** _é um protocolo_ para troca de informações estruturadas em uma _plataforma descentralizada e distribuída_. É um dos padrões para o desenvolvimento de web services ( há tanmbém, o REST ou RESTFull).

Para seu formato de mensagem utiliza-se do XML (Extensible Markup Language).

Na camada de aplicação do modelo OSI, utiliza-se dos protocolos RPC e HTTP para negociação e transmissão de mensagens, respectivamente.
<img src="https://github.com/shnonomura/diarioProgramacao/blob/master/SOAP/2020-04-10/web_service_soap.JPG">

_Web Services SOAP em Java - 2ª Edição: Guia prático para o desenvolvimento - Autor : Daniel Adorno Gomes_

O protocolo para negociação de _chamadas de procedimento remoto (RPC -Remote Procedure Calls)_ consiste em chamar um procedimento em outro programa por uma rede (ex.: a internet). Normalmente, estes protocolos são independentes da linguagem permitindo que um programa cliente escrito em C++ chame um servidor de banco de dados remoto escrito em Java sem que qualquer um dos lados saibam a linguagem empregada pelas partes.

O protocolo de transmissão de mensagens _HTTP - Hipertext Transfer Protocol_ é o protocolo empregado na internet. Para toda transação web realizada o protocolo HTTP é invocado. HTTP está por trás de qualquer requisição para qualquer documento web ou gráfico, cada clique de hipertexto e para toda requisição de um formulário. Ele é útil porque fornece um modo padronizado para os computadores se comunicarem entre si.

**Referências**
_1.Web Services SOAP em Java - 2ª Edição: Guia prático para o desenvolvimento - Autor : Daniel Adorno Gomes_