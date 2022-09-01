## Gerenciamento de projetos

- Boirlerplate: starter
- VSCODE: extensões + link cheetacheat
- Docker: Link installer
- Git: Link installer + commands and configurations + link cheetacheat
- Github CLI: cheetcheat, porqwue usar, e installer
 https://github.com/alexeymezenin/laravel-best-practices
 https://buttercms.com/blog/laravel-best-practices/
 https://phptherightway.com/
 
 https://www.w3.org/wiki/JavaScript_best_practices
 https://developer.wordpress.org/coding-standards/wordpress-coding-standards/javascript/
 https://medium.com/before-semicolon/50-javascript-best-practice-rules-to-write-better-code-86ce731311d7
 
 
- [Configuração ambiente de desenvolvimento](#headers)  
  - [Ferramentas](#emphasis)
  - [Boilerplates](#emphasis)
- [Gerenciamento de projetos](#emphasis)
  - [Criando novo projeto](#emphasis)
    - [Histórias de usuário](#emphasis)
    - [BDD com Gherkin](#emphasis)
    - [Planejamento e versionamento](#)
    - [TDD](#emphasis)
    - [Desenvolvimento](#)
    - [Refatoração](#)
    - [??QA](#)
    - [CI/CD](#)
    - [Changelogs](#)
  - [Iniciando em projeto existente](#emphasis)
- [Regras e padrões de desenvolvimento](#emphasis)
  - [Nomenclatura](#)
  - [Estilo de código](#)
    - [JS](#)
    - [PHP](#) 
  - [Segurança](#)
  - [Acessibilidade](#)
  
   
- [Configuração CI/CD](#emphasis)  
  - [Configurando ambiente CI](#)
  - [Configurando ambiente CD](#)
  - [Gerenciando servidores](#)
  - [Gerenciando Backups](#)



# Configuração ambiente de desenvolvimento
## Ferramentas
## Boirlerplates
# Gerenciamento de projetos
O gerenciamento dos projetos são feitos com base na técnica de desenvolvimento [Extreme Programming](http://www.extremeprogramming.org/).
## Criando um novo projeto
Antes de iniciar um projeto, avalie se a melhor alternativa é realmente criar algo do zero, sempre que for possível valide a ideia de forma rápida e simples, e apartir da validação prática naturalmente os problemas reais a serem resolvidos irão aparecer.

Ao iniciar um novo projeto dentro dos padrões do XP, devemos sempre ter em mente os dois termos **MVP** e **Entrega Contínua**.

**MVP**: MVP significa Minimum Viable Product ou Produto Mínimo Viável. Ao iniciar a reunião para definir os requisitos e funcionalidades do novo projeto, devemos buscar a versão mínima do produto, para que possamos lançar da forma mais rápida e simples possível, por que geralmente ao longo do lançamento as necessidades que aparecerem irão definir os próximos passos do projeto.

**Entrega Contínua**: Entrega contínua é uma abordagem na qual os times de desenvolvimento lançam produtos de qualidade de forma frequente, previsível e automatizada. Em vez de fazer grandes entregas de uma vez, fazem várias pequenas e rápidas — reduzindo as chances de erros e conquistando maior controle de qualidade.

### Histórias de usuário
Após alguns rabiscos e horas de reunião, vamos organizar as funcionalidades em descrições curtas e simples que são contadas da perspectiva da pessoa que está desempenhando a interação, essas histórias vão fazer parte de um contexto maior que descreve o problema real a ser resolvido e por que você está resolvendo.

As histórias de usuário, tem foco no usuário, não no produto.

Uma história de usuário geralmente se concentra em três áreas:

- Como/Sendo um ( quem )
- Eu quero/Gostaria/Devo/Posso ( o que )
- Para que/De/Para ( por que )

Critérios de aceite:
- [Mensagens de erro e validações padrão](#), não deve ser adicionadas nos critérios de aceite, validação só é adicionada caso seja exclusiva da regra de negócio.
- Não use a palavra "não", exemplo:

    ❌ Como usuário, não quero ter que digitar minha senha toda vez que acessar minha conta.

    ✅ Como usuário, quero que minha senha seja lembrada e preenchida automaticamente para que eu possa acessar minha conta sem redigitar minha senha.

Sendo um Comprador
Eu quero me cadastrar na plataforma
Para ter acesso ao questionário


_Críterios de aceite_
    
    -> Os compradores só podem enviar o formulário caso preencham todos os campos obrigatórios [`Email`, `Senha`, `Selecionar empresa`]
    -> Após o registro o comprador é redirecionado para o questionário.
Sendo um Comprador
Eu quero Responder o questionário
Para Receber a Ánalise da Minha personalidade

Sendo um Administrador
Eu quero Adicionar as perguntas do questionário
Para que o comprador tenha acesso ao questionário

Isso tudo geralmente é seguido por critérios de aceitação, que definem como você sabe se a interação foi bem-sucedida.

Independente = fazer com que ela possa ser resolvida sem depender de outras histórias.

Negociável = pode ser alterada

Valiosa = elas devem gerar valor para o usuário final, não colocar nada que seja técnico.

Estimável = tem que ser possível estimar a funcionalidade que a história conta, por isso ela deve ser clara e pequena.

Small = deve ser concisa e objetiva.

Testável = deve ser possível testar se a história foi realizada.


### BDD com Gherkin

