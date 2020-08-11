![image](https://ik.imagekit.io/bot95am5zi/proffy_FPyDbOrWT.png "logo")

Proffy é uma aplicação desenvolvida na Next Level Week 2 da Rocketseat onde alunos e professores poderão se conectar para ter aulas online, foram desenvolvidas a aplicação web e a aplicação mobile.

A Rocketseat montou esse projeto tendo em vista o dia nacional do profissional da educação (6 de agosto).

- - -

## Índices

1. [ Funcionalidades ](#funcionalidades)\
1.1 [Aplicação Web](#aplicação-web)\
1.2 [Aplicação mobile](#aplicação-mobile)
2. [ Tecnologias utilizadas ](#tecnologias-utilizadas)
3. [ O que eu aprendi ](#o-que-eu-aprendi)\
3.1 [ Front-end web](#front-end-web)\
3.2 [ Back-end ](#back-end)\
3.3 [ Mobile ](#mobile)
4. [ Como usar ](#como-usar)

- - -

<a name="funcionalidades"></a>

## Funcionalidades

<a name="aplicação-web"></a>

### Aplicação web

  - Escolher entre estudar ou dar aulas.
  - Cadastrar o perfil para professores, como nome, biografia, informações sobre a aula e horários disponíveis.
  - Filtrar por matéria, dia da semana e horário.
  - Listar todos os professores que têm disponibilidade.
  - Entrar em contato com os professores.

<a name="aplicação-mobile"></a>

### Aplicação mobile

  - Possui as mesmas funcionalidades da aplicação web.
  - Favoritar alguns professores.
  - Visualizar os professores que foram marcados como favorito.

- - -

<a name="tecnologias-utilizadas"></a>

## Tecnologias utilizadas

  - Typescript
  - NodeJS
  - ReactJS

- - -

<a name="o-que-eu-aprendi"></a>

## O que eu aprendi

<a name="front-end-web"></a>

### Front-end web

ReactJS é uma biblioteca focada no desenvolvimento de interfaces.

Construção de **SPAs** (Single Page Applications).

**SPAs** são aplicações que não precisa ser recarregada do 0 toda vez que o usuário navega de uma tela para outra, somente os conteúdos diferentes entre as telas são recarregados. Isso nasceu de uma necessidade de melhorar a experiência do usuário final e para ter mais controle sobre a interface do projeto.

Construção de interfaces responsivas utilizando o conceito de **Mobile First**.

Esse conceito foca no desenvolvimento da interface mobile primeiro para depois adaptar para uma tela maior, como um tablet ou desktop.

Motivações: a maiorias das pessoas acessam um site principalmente pelo celular e não mais pelos computadores.

O react é uma biblioteca estritamente Frontend, assim que a aplicação é carregada, o React começa a montar a interface, ou seja ela é criada em tempo de execução.

Em ReactJS temos uma biblioteca chamada ReactDOM que faz com que o React consiga entender que a forma que ele precisa criar interfaces é com HTML.

**Componentes** são funções que retornam um HTML, na maioria das vezes criamos componentes para podermos reaproveitar código entre várias telas, mantendo o código mais simples.

**Propriedades** são atributos que são enviados para o componente.

**Estados**: Sempre que precisar manipular algum valor através de uma ação do usuário, manipular um valor de dentro do componente, nós vamos criar um estado.<br>
**Por que criar um estado?** Com o React, quando criamos uma interface, nós estamos criando uma interface de maneira declarativa, ou seja, a nossa interface é montada a partir do JavaScript (a partir das informações que ela recebe).<br>
Quando usamos estado no React, nós não podemos manipular diretamente as variáveis do estado (imutabilidade), as variáveis não são modificáveis depois de criadas.<br>
Para alterar alguma informação dentro do estado, usamos um [Hook do React](https://pt-br.reactjs.org/docs/hooks-state.html) chamado **useState**.<br>
O useState retorna dois valores, a variável (que não pode ser alterada diretamente) e uma função que altera o valor dessa variável, e é com essa função que manipulamos as informações dentro do estado.

**Importante**: 
- Nome do componente deve iniciar com letra maiúscula, caso contrário o react entenderá que é uma tag html.
- Toda vez que for trabalhar com HTML dentro do TSX/JSX é obrigatório importar o React dentro do código.
- TSX/JSX: Typescript/Javascript com XML.
- Sempre que for importar algum arquivo, se não for do node_modules, precisa passar o caminho inteiro do arquivo.

A unidade _rem_ funciona da mesma forma que porcentagem, rem significa **root** + a unidade **em**, são adaptáveis ao tamanho da tela.
Por exemplo, se o tamanho da fonte no root for 60% de 16px (tamanho padrão), estamos transformando esse valor em 9,6px, isso quer dizer que toda vez que escrevemos 1rem é a mesma coisa que 9,6px.
Trabalhar com essa unidade de medida permite alterar o tamanho de qualquer fonte, box e containers modificando apenas o valor no root.
Isso também é importante para trabalhar com acessibilidade, principalmente quando o usuário tem controle sobre o tamanho da fonte.

E por fim, utilizamos o **axios**, que é uma biblioteca que serve para consumirmos APIs externas, basicamente conseguir fazer requisições para a API.

<a name="back-end"></a>

### Back-end

Como funciona o back-end?

O Front-end envia uma requisição HTTP para o Back-end, dentro dessa mensagem terá algumas informações, geralmente essa requisição é formada por um cabeçalho e um corpo da mensagem.
No **cabeçalho** há informações que definem o tipo da mensagem, como por exemplo: Criar alguma coisa, listar, editar ou excluir.

O **corpo** da mensagem é o conteúdo da requisição, por exemplo o envio dos dados de um formulário de cadastro de usuário (nome, email, senha, avatar).

O Back-end recebe essa mensagem e pode fazer algumas operações, por exemplo se ele está recebendo os dados de cadastro de um usuário, ele pode salvar o usuário no banco de dados, enviar um e-mail ao usuário, criptografar a senha do usuário, validar se o e-mail já está cadastrado.

Essas são ações que acontencem no back-end porque são operações que precisam de credenciais do banco de dados, de acesso ao servidor, algoritmos de criptografia (HASH), ou seja são coisas que não podem estar no front-end (que é a parte visual, que aprece para o usuário, ele tem acesso a tudo que está no front-end).

Depois de finalizar todas as operações, o back-end devolve uma resposta, e novamente uma resposta tem um cabeçalho e um corpo.

Toda mensagem enviada entre front-end e back-end tem cabeçalho e corpo.

**Construção de uma API RESTFUL**

Ao invés do back-end retornar um HTML completo para o front-end (modelo Full MVC - Back-end com responsabilidade pela parte das entidades, controllers e visual da aplicação), o back-end retorna somente os dados necessários, por exemplo: se for feita uma requisição da lista de usuários, o back-end retornará um JSON (**J**ava**S**cript **O**bject **N**otation), dentro desse JSON há informações dos dados do usuário.

Dessa forma, qualquer front-end pode entender a resposta do back-end, seja ele mobile ou web, e as próprias tecnologias (ReactJS, React Native, Kotlin, Swift, Flutter) farão a construção da parte visual, diferente do modelo Full MVC, em que somente aplicações web podem mandar requisições, pois nesse modelo é retornado dados HTML.

**Por que Node.js?**

Com o Node.JS é possível usar a mesma linguagem (JavaScript/Typescript) no Back-end que é utilizada no Front-end (ReactJS e React Native). 

Além de ser uma tecnologia altamente performática, um dos pontos mais peculiares da arquitetura do Node é o Non-Blocking I/O.

Non-Blocking I/O: Controle sobre assincronismo, ou seja é possível executar funcionalidades ao mesmo tempo, sem precisar esperar uma ação finalizar para realizar a próxima ação. 

Streams: permite consumir dados aos poucos, é possível trabalhar com um dado antes de estar completo.

Worker Threads: permite trabalhar com todos os cors da CPU de um processador para realizar ações diferentes dentro de um servidor Node.

**Rotas e Recursos**

Cada rota é um endereço da aplicação.

Exemplo:

Rota que lista usuários: http://localhost:3333/users

Rota que lista contatos: http://localhost:3333/contacts

Recurso é tudo o que fica depois do endereço principal (http://localhost:3333), ou seja no exemplo seria o "users" e "contacts".

**Métodos HTTP**

**GET**: Buscar uma ou mais informações do back-end.<br>
**POST**: Criar uma nova informação no back-end.<br>
**PUT**: Atualizar uma informação existente no back-end.<br>
**DELETE**: Remover uma informação do back-end.

**Parâmetros**

**Request Body**: Parâmetros para criação/atualização de informações.<br>
**Route Params**: Parâmetros que vem na própria rota que identificam um recurso.<br>
**Query Params**: Parâmetros que vêm na própria rota para filtros, paginação, geralmente são opcionais.

**Knex**

Knex é um query builder, ele permite escrever SQL usando Javascript.

**Migrations**: 

Controlam a versão do banco de dados.

Dentro das migrations é descrito o que será feito no banco (Criar uma tabela nova, criar um campo novo, excluir um campo, alterar o tipo do campo).

Ter esse controle ajuda um time no desenvolvimento das aplicações envolvendo o banco de dados, pois quando outra pessoa pegar o código, ela só vai precisar executar as migrations dentro do knex e automaticamente vai identificar o que já foi executado e o que não foi, e fará as alterações no banco.

**CORS**

Permite que aplicações de endereços diferentes acesse a nossa API.

<a name="mobile"></a>

### Mobile

A construção de interfaces no ReactNative é com interface nativa do IOS e do Android.

Criar projeto utilizando o [Expo](https://docs.expo.io/).

Se tiver algum problema com o expo, entre nesse [repositório](https://github.com/Rocketseat/expo-common-issues) da [Rocketseat](https://rocketseat.com.br/) que contém uma série de erros e suas soluções.

Conseguimos reaproveitar grande parte da base de conhecimento adquirido com ReactJS no React Native, melhorando a produtividade.

**Semelhanças entre React Native e ReactJS**<br>
Temos um componente escrito da mesma forma que temos na Web, ou seja, temos funções que retornam um XML ou muito parecido com HTML (JSX/TSX).

Toda a parte que aprendemos sobre componentização, lidar com estados, propriedades no ReactJS podem ser reaproveitados no react native.

**Diferenças entre React Native e ReactJS**<br>
Nós não usamos as tags do HTML (div, p, h1, section, main, entre outros), nós usamos componentes pré criados pelo pacote do react-native.<br>
Por exemplo, temos a **View** que representa um bloco (semelhante as tag div, main, section, header, footer) e o **Text** que são todos os textos, não importa se é título, parágrafo, negrito.

No mobile temos menos tipos de blocos diferentes (em comparação com a web), isso porque no mobile não temos elementos com resultado semântico. 

```tsx
export default function App() {
  return (
    <View>
      <Text>Hello NLW!</Text>
      <StatusBar style="auto" />
    </View>
  );
}
```

Como não tempos as tags semânticas como no HTML, controlamos os elementos com estilizações, porém não temos classes, ids ou o próprio css da maneira mais tradicional que vemos na web (não existem arquivos css no mobile).

Para estilizar um elemento, usamos o StyleSheet que é importado do react-native. Podemos interpretar a criação da estilização como um objeto do javascript.

**obs**: utilizando o stylesheet, teremos grande parte das propriedades do css e todos os elementos já vem com display flex por padrão, porém diferente da web, todos os elementos com display flex virão como colunas e não como linhas.

```js
const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  },
});
```

Então aplicamos o container dentro do style de algum elemento.

```tsx
export default function App() {
  return (
    <View style={styles.container}>
      <Text>Hello NLW!</Text>
      <StatusBar style="auto" />
    </View>
  );
}
```

Outra diferença é que no react-native, não temos heranças de estilos, se quiser estilizar uma tag/elemento, precisamos adicionar um estilo particular para aquele elemento.<br>
Obs: a tag Text é a única exceção dessa regra, se tiver um Text dentro do outro, o segundo Text vai herdar a estilização do primeiro.

**Importante**
Estilizações são objetos javascript, então não podemos utilizar um hífen na propriedade, então trocamos a próxima letra para maiúscula ao invés do hífen (CamelCase).<br>
Exemplo: **background-color** para **backgroundColor**

Quando trabalhamos com mobile, temos o conceito de densidade de pixel, isso quer dizer que pode caber muito mais pixels em uma tela, mesmo ela tendo a mesma resolução de uma outra tela.<br> 
Por exemplo, uma tela de 1000px de largura, mas a densidade de pixel dessa tela é 3, dando um total de 3000px de largura, precisaremos de uma imagem 3 vezes maior.

Então todas as imagens que utilizamos no react-native possuem no nome **@2x** **@3x** (sem **@** para o tamanho original) e o próprio react-native lida com isso automaticamente.<br>
Exemplo:
- logo.png
- logo@2x.png
- logo@3x.png

**Navegação**

Nesse projeto utilizamos a biblioteca [React Navigation](https://reactnavigation.org/docs/getting-started).

Existem vários tipos de navegação dentro do react native, as três mais comuns são:
- Stack ou pilha: usada quando podemos navegar entre as telas (por exemplo, voltar para a tela anterior);
- Tabs ou abas;
- Drawer: geralmente é um menu lateral.

- - -

<a name="como-usar"></a>

## Como usar

> Clone o repositório
```shell
$ git clone https://github.com/TakaGui/proffy.git
```
> Vá até os repositórios server, web e mobile
```shell
$ cd proffy
$ cd web
```
> Instale as dependências em cada repositório
```shell
$ npm install
```
ou
```shell
$ yarn
```