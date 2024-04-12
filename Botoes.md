# Aprimorando a acessibilidade em botões

## Utilize Elementos HTML Semânticos

O primeiro passo crucial é utilizar os elementos HTML semânticos corretos para os seus botões. Evite usar elementos genéricos como `<div>` ou `<span>` como botões. Em vez disso, opte pelo elemento `<button>`, que oferece diversos benefícios de acessibilidade:

- **Semântica clara**: Comunicadores assistidos, como leitores de tela, podem facilmente identificar e interpretar a função do botão, facilitando a navegação para usuários com deficiência visual.

- **Acessibilidade por teclado**: Por padrão, os botões HTML são navegáveis por meio da tecla Tab e podem ser ativados com a tecla Enter ou Return. Isso garante que os usuários que navegam pelo site com o teclado possam interagir com os botões sem precisar de um mouse.

- **Estilos predefinidos**: Os navegadores modernos aplicam estilos predefinidos aos botões HTML, proporcionando uma aparência consistente e familiar para a maioria dos usuários. Isso facilita a criação de interfaces intuitivas e acessíveis sem a necessidade de estilização excessiva.

```html
<button type="submit">Enviar Formulário</button>
```

## Forneça Rótulos Descritivos

Os rótulos dos botões são cruciais para comunicar o propósito e a funcionalidade do botão aos usuários. Rótulos claros e descritivos garantem que todos os usuários, incluindo aqueles com deficiência visual, compreendam o que o botão faz ao interagir com ele.

### Diretrizes para rótulos:

- **Seja conciso e informativo**: O rótulo deve ser claro e direto, descrevendo a ação principal do botão. Evite rótulos vagos como "Clique aqui" ou "Enviar".

- **Evite gírias e jargões**: Utilize linguagem simples e direta que seja compreensível por todos os públicos.

- **Evite instruções**: O rótulo deve descrever a ação do botão, não instruir o usuário sobre o que fazer.

- **Seja consistente**: Utilize rótulos consistentes para botões com funções semelhantes em todo o site.

### Exemplo correto

```html
<button type="button" aria-label="Abrir Menu Principal">
  Menu Principal
</button>
```

- **`type="button"`**: Indica que o botão não envia dados para um servidor, mas sim executa uma ação JavaScript.

- **`aria-label="Abrir Menu Principal"`**: Define o rótulo alternativo "Abrir Menu Principal" para o botão. Esse rótulo será lido por leitores de tela e outros comunicadores assistidos, garantindo que o usuário compreenda a função do botão, mesmo que o texto visível seja "Menu Principal".

### O que você deve evitar

```html
<button type="button" aria-label="Clique aqui">
  Menu Principal
</button>
```

O rótulo *"Clique aqui"* é vago e não transmite a função real do botão. Rótulos genéricos como este podem confundir usuários com deficiência visual, pois não fornecem informações suficientes sobre o que o botão faz.

## Forneça Feedback Adequado

Ao clicar em um botão, os usuários devem receber feedback claro sobre a interação. Isso pode ser feito visualmente, com uma mudança na aparência do botão, ou auditivamente, com um som ou vibração.

### Tipos de feedback

- **Visual**: O botão pode mudar de cor, aumentar de tamanho ou apresentar uma animação sutil ao ser clicado.

- **Auditivo**: Um som ou vibração pode ser reproduzido ao clicar no botão, fornecendo feedback instantâneo para usuários com deficiência visual.

```js
const button = document.querySelector('button');

button.addEventListener('click', () => {
  button.style.backgroundColor = '#00ff00'; // Verde para indicar sucesso
  setTimeout(() => {
    button.style.backgroundColor = '#007bff'; // Retorna à cor original
  }, 200);

```