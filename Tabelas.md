# Tabelas

## Usar Elementos Semânticos Corretamente

### O que fazer:

- Use `<table>` para definir a tabela.
- Use `<thead>`, `<tbody>` e `<tfoot>` para estruturar a tabela.
- Use `<th>` para definir células de cabeçalho e `<td>` para células de dados.

```html
<table>
  <thead>
    <tr>
      <th>Nome</th>
      <th>Idade</th>
      <th>Cidade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>João</td>
      <td>25</td>
      <td>Lisboa</td>
    </tr>
    <tr>
      <td>Maria</td>
      <td>30</td>
      <td>Porto</td>
    </tr>
  </tbody>
</table>
```

### O que não fazer:

Não use tabelas para layout visual, pois isso pode confundir leitores de tela e dificultar a navegação.

```html
<!-- Não recomendado para layout -->
<table>
  <tr>
    <td>Conteúdo de layout</td>
    <td>Mais conteúdo de layout</td>
  </tr>
</table>
```

## Associar Cabeçalhos a Células de Dados

### O que fazer:

Use o atributo scope em `<th>` para indicar o escopo (coluna, linha, grupo de colunas ou grupo de linhas).

```html
<table>
  <thead>
    <tr>
      <th scope="col">Nome</th>
      <th scope="col">Idade</th>
      <th scope="col">Cidade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>João</td>
      <td>25</td>
      <td>Lisboa</td>
    </tr>
    <tr>
      <td>Maria</td>
      <td>30</td>
      <td>Porto</td>
    </tr>
  </tbody>
</table>
```

### O que não fazer:

Não omitir os atributos scope ou headers em tabelas complexas, pois isso dificulta a compreensão da relação entre cabeçalhos e células de dados.

## Fornecer Descrições Adequadas

### O que fazer:

Use `<caption>` para fornecer uma descrição da tabela.

```html
<table>
  <caption>Lista de participantes e suas cidades</caption>
  <thead>
    <tr>
      <th>Nome</th>
      <th>Idade</th>
      <th>Cidade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>João</td>
      <td>25</td>
      <td>Lisboa</td>
    </tr>
    <tr>
      <td>Maria</td>
      <td>30</td>
      <td>Porto</td>
    </tr>
  </tbody>
</table>
```

### O que não fazer:

Não deixar de usar `<caption>` quando a tabela não for autoexplicativa, pois isso pode dificultar o entendimento de seu propósito.

## Utilizar Aria Roles e Propriedades (quando necessário)

### O que fazer:

Utilize atributos ARIA (aria-describedby, aria-labelledby) para adicionar informações extras, especialmente em tabelas complexas.

```html
<table>
  <caption id="tableCaption">Lista de participantes e suas cidades</caption>
  <thead>
    <tr>
      <th scope="col" id="nomeHeader">Nome</th>
      <th scope="col" id="idadeHeader">Idade</th>
      <th scope="col" id="cidadeHeader">Cidade</th>
    </tr>
  </thead>
  <tbody>
    <tr aria-labelledby="nomeHeader idadeHeader cidadeHeader">
      <td>João</td>
      <td>25</td>
      <td>Lisboa</td>
    </tr>
    <tr aria-labelledby="nomeHeader idadeHeader cidadeHeader">
      <td>Maria</td>
      <td>30</td>
      <td>Porto</td>
    </tr>
  </tbody>
</table>
```

### O que não fazer:

Não usar ARIA inadequadamente ou em excesso, pois isso pode causar problemas de acessibilidade ao invés de resolvê-los.

## Garantir Contraste Adequado e Tamanho de Fonte

### O que fazer:

Assegure-se de que o texto tenha contraste suficiente com o fundo e que o tamanho da fonte seja legível.

```html
<table style="width:100%; border-collapse:collapse;">
  <thead style="background-color:#333; color:#fff;">
    <tr>
      <th scope="col">Nome</th>
      <th scope="col">Idade</th>
      <th scope="col">Cidade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>João</td>
      <td>25</td>
      <td>Lisboa</td>
    </tr>
    <tr>
      <td>Maria</td>
      <td>30</td>
      <td>Porto</td>
    </tr>
  </tbody>
</table>
```

### O que não fazer:

Não usar cores ou tamanhos de fonte que dificultem a leitura, especialmente para pessoas com deficiências visuais.

```html
<table style="width:100%; border-collapse:collapse;">
  <thead style="background-color:#ddd; color:#ddd;"> <!-- Falta de contraste -->
    <tr>
      <th scope="col">Nome</th>
      <th scope="col">Idade</th>
      <th scope="col">Cidade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>João</td>
      <td>25</td>
      <td>Lisboa</td>
    </tr>
    <tr>
      <td>Maria</td>
      <td>30</td>
      <td>Porto</td>
    </tr>
  </tbody>
</table>
```

Seguindo essas práticas, você pode criar tabelas em HTML que sejam mais acessíveis para todos os usuários, incluindo aqueles que dependem de tecnologias assistivas.