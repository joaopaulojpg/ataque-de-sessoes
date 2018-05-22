Sequestro de sessões

As variáveis de sessão podem ser "sequestradas". Isso é chamado de session hijacking: 
https://en.wikipedia.org/wiki/Session_hijacking

Como isso é possível?

É muito fácil. Se uma pessoa tiver acesso ao computador de uma pessoa, poderá facilmente usar a sessão aberta.
Mesmo as variáveis de sessão serem gravadas no servidor, elas são guardadas no cookie client-side.
Se você conseguir recuperar o id da sessão, poderá acessar as informações da sessão em qualquer outro computador, e assim logar com sua conta.

PHP Cabuete?!

No PHP, há uma diretiva de configuração do ambiente chamada session.use-trans-sid.
Serve para transportar o ID da sessão de forma transparente em requisições $_GET e $_POST de forma automática.
Desative essa opção, pois é mais fácil que um hacker obtenha o session id do usuário, mesmo sem estar de frente com o computador físicamente do usuário.


Como evitar hacker de sessão?

Evitar guardar ids por usuário e gerar períodicament. É recomendado em 5 em 5 minutos.
No PHP você poderá usar a função session_regenerate_id(), que será usada para gerar novos IDs de sessão.
