## Gerenciamento de projetos de software: do conceito à implantação (PT-BR)

⚠️ Este trabalho está em desenvolvimento, algumas informações podem estar incompletas ou equivocadas.

Este repositório tem como objetivo ser um guia que cobre as melhores práticas e ferramentas para desenvolver um software do mundo real desde a concepção até o deploy para desenvolvedores independentes e pequenas equipes de desenvolvimento.

 
- [Configuração ambiente de desenvolvimento](#Configuração-ambiente-de-desenvolvimento)  
  - [Ferramentas](#Ferramentas)
  - [Boilerplates](#Boilerplates)
- [Gerenciamento de projetos](#Gerenciamento-de-projetos)
  - [Criando novo projeto](#Criando-novo-projeto)
    - [Histórias de usuário](#Histórias-de-usuário)
    - [BDD com Gherkin](#BDD-com-Gherkin)
    - [Planejamento e versionamento](#Planejamento-e-versionamento)
    - [TDD](#TDD)
    - [Desenvolvimento](#Desenvolvimento)
    - [Refatoração](#Refatoração)
    - [QA](#QA)
    - [CI/CD](#CI/CD)
    - [Changelogs](#Changelogs)
  - [Iniciando em um projeto existente](#Iniciando-em-um-projeto-existente)
- [Regras e padrões de desenvolvimento](#Regras-e-padrões-de-desenvolvimento)
  - [Nomenclatura](#Nomenclatura)
  - [Estilo de código](#Estilo-de-código)
    - [JS](#JS)
    - [PHP](#PHP) 
  - [Segurança](#Segurança)
  - [Acessibilidade](#Acessibilidade)
  
   
- [Configuração CI/CD](#Configuração-CI/CD)  
  - [Configurando ambiente CI](#Configurando-ambiente-CI)
  - [Configurando ambiente CD](#Configurando-ambiente-CD)
  - [Gerenciando servidores](#Gerenciando-servidores)
  - [Gerenciando Backups](#Gerenciando-Backups)



# Configuração ambiente de desenvolvimento
## Ferramentas
- Docker
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

Isso tudo geralmente é seguido por critérios de aceitação, que definem como você sabe se a interação foi bem-sucedida.

... INVEST (...WIP)
Independente = fazer com que ela possa ser resolvida sem depender de outras histórias.

Negociável = pode ser alterada

Valiosa = elas devem gerar valor para o usuário final, não colocar nada que seja técnico.

Estimável = tem que ser possível estimar a funcionalidade que a história conta, por isso ela deve ser clara e pequena.

Small = deve ser concisa e objetiva.

Testável = deve ser possível testar se a história foi realizada.


### BDD com Gherkin
#### Palavras-chave
[ # ] # language: pt

_Etapas_
- Dado/* (given):
- Quando/* (when):
- Então/* (then):
- E/* (and):
- Mas/* (but):

_Descritivas_
- Funcionalidade (feature): fornece uma descrição de alto nível de um recurso de software e agrupar cenários relacionados.
- Contexto (background)
- Regra (rule):
- Cenário (scenario):
- Esquema do Cenário (scenarioOutline):
- Exemplos (examples):

_Propriedades para as etapas_
- """ (Doc Strings): Usado para passar um pedaço maior de texto para a definição de uma etapa.
- | (Data table): Usado para passar uma lista de dados para a definição de uma etapa.
- @: Tag
- #: Comentários

___
- Um cenário abrange apenas UM comportante, por isso não devem existir + que um "Quando / Então"
- Siga a ordem Dado Quando Então!
- Escreva o comportante sempre em terceira pessoa.
- Usar tempo presente para todos os casos. [exemplo](https://automationpanda.com/2017/01/30/bdd-101-writing-good-gherkin/)
- [Escreva bons títulos](https://automationpanda.com/2018/01/31/good-gherkin-scenario-titles/)

### QA

... WIP
Modelo para registrar bugs QA e Suporte

LOCAL:
Nome do Sistema - Módulo e Menu relacionado

VERSÃO:
Identificar em que versão do sistema envolvido o problema pode ser
repetido. Importante identificar se o problema pode ser repetido na
última versão.

PRÉ-CONDIÇÕES:
• Identifique o que deve estar configurado no ambiente para
que o problema possa ser repetido;
• Pode ser uma lista de configurações a serem marcadas;
• Ou simplesmente a indicação de que uma base de dados específica deve ser usada.

PASSOS PARA REPRODUÇÃO DO ERRO:
1) Monte uma lista indicando os passos que devem ser realizados
para repetir o erro;
2) Você pode ser específico e identificar o que deve ser preenchido
em cada campo;

Exemplo:
LOCAL:
SoftVendas – Módulo Mobile – Tela de vendas de produtos
VERSÃO:
Identificado na última versão (03.50), o problema não ocorre em
versões anteriores.
PRÉ-CONDIÇÕES:
• Acessar o ambiente de homologação;
• Logar com usuário “alfredo”, senha “xyz9988”;
PASSOS PARA REPRODUÇÃO DO ERRO:
1) Uma vez já logado no sistema mobile, acesse o menu “Vendas”;
2) Selecione um cliente qualquer e abra uma nova venda;
3) Na tela de listagem de produtos, selecione qualquer produto;
4) Após selecionar um produto informe a quantidade a ser vendida
(pode ser 10), e no campo desconto informe um desconto (pode ser
10% de desconto).
ERRO:
Mesmo após informar o desconto, o valor total do produto segue
sendo o mesmo que era antes (sem o desconto).
SITUAÇÃO DESEJADA:
Que o valor total do produto considere o desconto aplicado, ou seja:
Valor total do produto = (Valor unitário * Quantidade) – Desconto.
Exemplo: Se valor do produto é 90,00, a quantidade informada é
10, e o percentual de desconto é informado é 10%, então o valor total do produto deve ser 810,00.

Algumas considerações sobre o exemplo citado:
Repare como as seções PRÉ CONDIÇÕES e PASSOS PARA A REPRODUÇÃO DO ERRO, são importantes para fazer o erro acontecer.
Perceba também que na seção SITUAÇÃO DESEJADA além de citar
a explicação do que deve ocorrer nós também citamos um exemplo
prático, neste caso com um exemplo real do cálculo de preço total
do produto.

