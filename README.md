# desafio-juliano
desafio-hotmart juliano césar
 Implementar um codigo do github que  lista os  repositórios, além disso, implementar um container docker para subir  o projeto via container. 
 atividades:
 1. instalei o módulo requests em python: pip install requests
 ao acessar a url: api.github.com, vemos o seguinte:
 {
  "current_user_url": "https://api.github.com/user",
  "current_user_authorizations_html_url": "https://github.com/settings/connections/applications{/client_id}",
  "authorizations_url": "https://api.github.com/authorizations",
  "code_search_url": "https://api.github.com/search/code?q={query}{&page,per_page,sort,order}",
  "commit_search_url": "https://api.github.com/search/commits?q={query}{&page,per_page,sort,order}",
  "emails_url": "https://api.github.com/user/emails",
  "emojis_url": "https://api.github.com/emojis",
  "events_url": "https://api.github.com/events",
  "feeds_url": "https://api.github.com/feeds",
  "followers_url": "https://api.github.com/user/followers",
  "following_url": "https://api.github.com/user/following{/target}",
  "gists_url": "https://api.github.com/gists{/gist_id}",
  "hub_url": "https://api.github.com/hub",
  "issue_search_url": "https://api.github.com/search/issues?q={query}{&page,per_page,sort,order}",
  "issues_url": "https://api.github.com/issues",
  "keys_url": "https://api.github.com/user/keys",
  "label_search_url": "https://api.github.com/search/labels?q={query}&repository_id={repository_id}{&page,per_page}",
  "notifications_url": "https://api.github.com/notifications",
  "organization_url": "https://api.github.com/orgs/{org}",
  "organization_repositories_url": "https://api.github.com/orgs/{org}/repos{?type,page,per_page,sort}",
  "organization_teams_url": "https://api.github.com/orgs/{org}/teams",
  "public_gists_url": "https://api.github.com/gists/public",
  "rate_limit_url": "https://api.github.com/rate_limit",
  "repository_url": "https://api.github.com/repos/{owner}/{repo}",
  "repository_search_url": "https://api.github.com/search/repositories?q={query}{&page,per_page,sort,order}",
  "current_user_repositories_url": "https://api.github.com/user/repos{?type,page,per_page,sort}",
  "starred_url": "https://api.github.com/user/starred{/owner}{/repo}",
  "starred_gists_url": "https://api.github.com/gists/starred",
  "topic_search_url": "https://api.github.com/search/topics?q={query}{&page,per_page}",
  "user_url": "https://api.github.com/users/{user}",
  "user_organizations_url": "https://api.github.com/user/orgs",
  "user_repositories_url": "https://api.github.com/users/{user}/repos{?type,page,per_page,sort}",
  "user_search_url": "https://api.github.com/search/users?q={query}{&page,per_page,sort,order}"
}
https://api.github.com/users/{user}
Então, se substituirmos o parâmetro user no link acima, excluindo também as chaves por um nome de usuário válido, por exemplo:
https://api.github.com/users/julianotrovao
teremos como resultado a mesma estrutura já vista antes, porém, com os dados do usuário julianotrovao.
a nossa api será apresentada assim:
{
  "login": "julianotrovao",
  "id": 2048163,
  "node_id": "MDQ6VXNlcjIwNDgxNjM=",
  "avatar_url": "https://avatars.githubusercontent.com/u/2048163?v=4",
  "gravatar_id": "",
  "url": "https://api.github.com/users/julianotrovao",
  "html_url": "https://github.com/julianotrovao",
  "followers_url": "https://api.github.com/users/julianotrovao/followers",
  "following_url": "https://api.github.com/users/julianotrovao/following{/other_user}",
  "gists_url": "https://api.github.com/users/julianotrovao/gists{/gist_id}",
  "starred_url": "https://api.github.com/users/julianotrovao/starred{/owner}{/repo}",
  "subscriptions_url": "https://api.github.com/users/julianotrovao/subscriptions",
  "organizations_url": "https://api.github.com/users/julianotrovao/orgs",
  "repos_url": "https://api.github.com/users/julianotrovao/repos",
  "events_url": "https://api.github.com/users/julianotrovao/events{/privacy}",
  "received_events_url": "https://api.github.com/users/julianotrovao/received_events",
  "tipo": "Usuário",
  "site_admin": falso,
  "nome": null,
  "empresa": null,
  "blogue": "",
  "local": null,
  "e-mail": null,
  "aluguel": null,
  "bio": null,
  "twitter_username": null,
  "public_repos": 15,
  "public_gists": 0,
  "seguidores": 1,
  "seguindo": 2,
  "created_at": "2012-07-26T19:08:20Z",
  "updated_at": "2022-03-22T02:17:26Z"
}

###implementando em   python

Para implementar em   python, usaremos a instrução import requests e   import json:
A instrução import é usada para importar pacotes, módulos e bibliotecas em Python. 
 usaremos import requests e  import json(JavaScript Object Notation)  um formato de representação de dados muito utilizado em API's,  Para uma melhor organização do nosso código.)
 
 #queremos que a  resposta seja o código 200 em nossa aplicação.
 
 #vamos criar a classe listarepositorio
 e a função dev init:
 Métodos em Classes: __init__
A regra para se criar uma classe é simples e você já conhece, se cria do mesmo jeito que se cria uma função em Python: instrução def, nome da função, parêntesis (com parâmetros ou não), dois pontos e o código que vai ser executado.
teremos condicionais em nosso código, onde caso retorne a  resposta 200, irá efetuar uma ação, caso negativo, irá  executar outra ação.
• Python/Django
• solicitações de
• Pipeline
• NodeJS
• Bower
Essa é toda a tecnologia de que precisaremos. Python e Django fornecerão a estrutura para o aplicativo. As solicitações serão usadas para fazer uma solicitação simples à API do Github. NodeJS e Bower serão usados ​​para gerenciamento de dependências de front-end e o Pipeline fará a compactação de ativos.
Vamos tentar subir isso tudo via docker.
