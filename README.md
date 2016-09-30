![](./img/meteor.jpg) 
#Trabalho Final da disciplina Produtividade no Desenvolvimento de Software - Bernardo Guedes Vieira.
# 
##Meteor
[Meteor](https://www.meteor.com/) é um *framework* para desenvolvimento de aplicações Web JavaScript *full-stack*, com um grande foco em produtividade e Tempo real. 

Isso significa que, na pilha arquitetural, cliente, servidor e banco de dados usam respectivamente JavaScript, Node.js e MongoDB nativamente. Está no *roadmap* o acesso nativo ao Mysql. Entretanto, quando necessário, existem pacotes [*3rd-party* que fornecem suporte para acessar os SGBDS MySql](https://github.com/numtel/meteor-mysql)  e [PostgreSQL](https://github.com/numtel/meteor-pg). 

Por *default*, toda aplicação desenvolvida utilizando o framework em questão é do formato *Single Page Application* (SPA) e tem como estilo arquitetural predominante Model-View-ViewModel (MVVM).

Como já foi dito anteriormente, o back-end de uma aplicação Meteor é suportado pelo Node.js. Assim como o NPM no Node executa a tarefa de gerenciamento de pacotes, no Meteor esta tarefa fica a cargo do Atmosphere. 

### Princípios do Meteor
Meteor foi construído com 7 princípios que estão listados a seguir: 
   - **One Language:** como já foi citado, o JavaScript é utilizado Verticalmente, sendo a linguagem utilizada tanto no cliente quanto no servidor (incluíndo banco de dados). Horizontalmente, o mesmo código escrito para aplicações web tradicionais é utilizado para aplicações *mobile*. 
    - **Database anywhere:** o acesso ao banco de dados ocorrer através de uma API única e tranparente, permitindo que operações sejam executadas da mesma forma tanto a partir do cleinte quanto do servidor.
    - **Latency Compensation:** No cliente é usado prefetching e model simulation na API do banco de dados para atingir latência zero no acesso de seus recursos.
    - **Full-Stack Reactivity:** Todas as camadas da aplicação são orientadas à eventos. Característica herdada do Node.js que dá às aplicações desenvolvidas a condição de Tempo Real. Isto significa que eventos que ocorrem no contexto da apliação são percebidos pelos usuários de forma quase instantânea. Exemplo é um comentário é adicionado a uma foto. Não é necessário que o uma a tela seja refrescada para que as pessoas que estão visualizando a foto tomem conhecimento desse comentário. Ele simplismente é adicionado na visão do usuário.
    - **Data on the wire:** HTML não é enviado pela rede. Somente dados trafegam e o cliente decide como e quando irá tratar e apresentar tal informação.
    - **Embrace the ecosystem:** Totalmente *open-source*, possui convenções pelas quais agrega valores, em vez de ser uma ferramenta que irá substituir outros *frameworks*.
    - **Simplicity equals Productivity:** 

###Características importantes 
####Publish/Subscribe

Em aplicações web, a forma mais comum de comunicação entre cliente e servidor é do tipo *Request-Response*, onde uma url é acessada pelo cliente, solicitando algum recurso provido pelo servidor. Esta requisição é processada uma resposta contendo as informações desejadas são retornadas, tipicamente nos formatos HTML, JSon ou XML. O Servidor nunca coloca diretamente informações no cliente quando algum evento altera o conteúdo no back-end. 

No Meteor, o fluxo de informação é bi-direcional, não sendo necessário por exemplo que *endpoints* REST sejam acessados para que a percepção do usuário seja modificada. São criados *endpoints* do tipo ***Publication***. 