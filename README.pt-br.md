**Atenção usuários MacOS, Windows e Linux através de AppImage**

- A funcionalidade de atualização automática estava quebrada nas versões anteriores a 1.7.5. Por favor, faça atualização de forma manual a partir da seção de [release](https://github.com/beekeeper-studio/beekeeper-studio/releases).

# Beekeeper Studio

Beekeeper Studio é um editor e gerenciador SQL de banco de dados multiplataforma, disponível para Linux, MacOS e Windows.

Beekeeper Studio usa a licença MIT, portanto é livre e grátis.

Baixe agora [do nosso site](https://beekeeperstudio.io).

Curtiu o Beekeeper Studio e quer contribuir, mas não com código? [Temos algumas ideias pra você!](https://github.com/beekeeper-studio/beekeeper-studio/issues/287)

# Funcionalidades

Principais funcionalidades: é leve 🍫, rápido 🏎 e você realmente vai gostar de usa-lo 🥰

- Editor de queries SQL com autocomplemento e realce de sintaxe.
- Interface com abas, então você pode fazer multitarefas.
- Ordenação e filtros dos dados na tabela, para facilitar encontrar o que você precisa.
- Atalhos sensíveis no teclado.
- Opção de salvar as consultas.
- Histórico de consultas executadas, permitindo saber as consultas que você executou anteiormente.
- Tema escuro como padrão.

Uma de nossas frustrações com outros editores e gerenciadores SQL de código aberto é que eles usam uma abordagem de "pia na cozinha" para suas funcionalidades, adicionando tantas funcionalidades que tornam a interface desordenada e difícil de navegar. Nós queremos um visual legal, uma ferramenta SQL de código aberto que seja poderosa, mas fácil de usar. Não encontramos uma que atendesse esses requisitos, então resolvemos criar uma.

![Beekeeper Studio Screenshot](https://app.duckdocs.com/sites/2/pages/introduction/images/1)

Beekeeper Studio suporta conexão com os seguintes bancos de dados:

- PostgreSQL
- SQLite
- MySQL
- MariaDB
- SQL Server
- Amazon Redshift
- CockroachDB
- Oracle Database
- Google BigQuery
- Apache Cassandra

## Instalação

Baixe a última release na nossa [página de releases](https://github.com/beekeeper-studio/beekeeper-studio/releases), ou do nosso [site](https://beekeeperstudio.io).

## Documentação

Acesse o site [docs.beekeeperstudio.io](https://docs.beekeeperstudio.io) para acessar o guia de usuário, FAQs, dicas de soluções de problemas, e mais.

## Contribuindo com Beekeeper Studio

Nós amamos _qualquer_ engajamento da comunidade, mesmo que seja uma crítica de algo que você não goste na aplicação.

Construir uma comunidade inclusiva e acolhedora é importante pra gente, então por favor, siga o nosso código de conduta ao se envolver no projeto.

### Contribuições sem código

Nós queremos a sua contribuição, leia nosso [guia de contribuição de 10 minutos sem códificação](https://github.com/beekeeper-studio/beekeeper-studio/issues/287).

### Inicializando o Beekeeper Studio na versão de Desenvolvimento

Quer melhorar o Beekeeper Studio codificando ou melhorando a documentação? Execute o projeto de forma fácil no Mac, Linux ou Windows.

```bash
# Primeiro: Instale NodeJS 12+ ou 14, NPM e Yarn
# ...

# 1. Crie um fork do repositório do Beekeeper Studio (clique no botão de fork no topo a direita dessa tela)
# 2. Checkout o seu fork:
git clone git@github.com:<your-username>/beekeeper-studio.git beekeeper-studio
cd beekeeper-studio/
yarn install # instala dependencias

# Se estiver usando NodeJS 16.17+:
export NODE_OPTIONS=--openssl-legacy-provider

# Agora você pode iniciar a aplicação:
yarn run electron:serve ## a aplicação será iniciada
```

### Onde fazer modificações?

Beekeeper Studio tem dois pontos de entrada:

- `background.js`: essa é a parte electron, código que controla as partes nativas como mostrar as janelas.
- `main.js`: esse é o ponto de entrada para a aplicação Vue.js. Você pode seguir os _breadcrumbs_ dos componentes a partir de `App.vue` para encontrar a tela que você precisa.

**No geral nós temos duas telas:**

- ConnectionInterface: Conectando com um Banco de dados
- CoreInterface - Interação com o Banco de Dados

### Como submeter um alteração?

- Suba as alterações para o seu repositório (seu fork) e abra um Pull Request para o nosso repositório (essa página).
- Certifique-se de escrever alguma descrição sobre o que suas alterações fazem.

## Notas para os mantenedores (leitores casuais podem ignorar)

### Processo de release

1. Incremente a versão no package.json
2. Substitua `build/release-notes.md` com as últimas notas da release. Siga o formato que está aqui.
   - execute `git log <last-tag>..HEAD --oneline | grep 'Merge pull'` para encontrar os Pull Requests mergeados.
3. Commit
4. Push para master
5. Crie uma tag `git tag v<version>`. Precisa começar com a letra 'v'
6. `git push origin <tagname>`
   - Agora espere pela ação de _build/publish_ completar no GitHub.
7. Subir a nova release

- Vá para o "rascunho" da nova release na aba de releases do GitHub, edite as notas e publique
- Faça Login em snapcraft.io, arraste a versão enviada para o canal 'estável' de cada arquitetura.

## Agradecimentos

Beekeeper Studio não existiria sem [Sqlectron-core](https://github.com/sqlectron/sqlectron-core), a biblioteca principal de Banco de Dados (agora não mais mantida) Sqlectron project. O Beekeeper Studio começou como um fork experimental desse repositório. Um grande obrigado ao @maxcnunes e os outros membros da comunidade Sqlectron.
