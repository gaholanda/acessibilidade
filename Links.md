# Links

## Texto Descritivo

### Texto de Link Significativo:

Use textos de link que descrevam claramente o destino ou a ação que ocorrerá ao clicar no link. Evite textos genéricos como "clique aqui" ou "saiba mais".

**Bom exemplo:**

```html
<a href="documento.pdf">Leia o relatório anual</a>
```

O texto do link é claro e descreve exatamente o que o usuário encontrará ao clicar.

**Mau exemplo:**

```html
<a href="documento.pdf">Clique aqui</a>
```

O texto do link é genérico e não informa o destino ou a finalidade do link.

## Atributos e ARIA

### Atributo `title`:

O atributo title pode fornecer informações adicionais, mas não deve ser usado como substituto para um texto de link claro, pois nem todos os usuários de tecnologias assistivas terão acesso a ele.

**Bom exemplo:**

```html
<a href="documento.pdf" title="Baixar o relatório anual em PDF">Leia o relatório anual</a>
``` 

O atributo `title` fornece informações adicionais úteis.

**Mau exemplo:**

```html
<a href="documento.pdf" title="Clique aqui para baixar">Clique aqui</a>
```

O `title` é redundante e não compensa a falta de um texto de link significativo.

### ARIA (Accessible Rich Internet Applications):

Use atributos ARIA para fornecer informações adicionais sobre o link, se necessário. Por exemplo, `aria-label` pode ser usado para fornecer uma descrição mais detalhada.

**Bom exemplo:**

```html
<a href="documento.pdf" aria-label="Baixar o relatório anual em PDF">Leia o relatório anual</a>
```

O `aria-label` fornece uma descrição clara para usuários de tecnologias assistivas.

**Mau exemplo:**

```html
<a href="documento.pdf" aria-label="Clique aqui para baixar">Clique aqui</a>
```

Assim como o `title`, o `aria-label` não deve ser usado para compensar um texto de link genérico.

## Foco e Navegação

### Foco Visível

Assegure-se de que os links tenham um estado de foco visível para que os usuários que navegam com o teclado possam ver claramente qual link está ativo.

**Bom exemplo:**

```html
<style>
a:focus { 
    outline: 2px solid #000;
}
</style>
```

**Mau exemplo:**

```html
<style>
a:focus {
    outline: none;
}
</style>
```

Remover o foco torna difícil para usuários de teclado verem qual link está ativo.

### Navegação por Teclado:

Todos os links devem ser acessíveis via teclado. Verifique se eles podem ser navegados usando a tecla `Tab` e ativados com `Enter` ou `Space`.

## Estrutura e Contexto

### Estrutura Semântica:

Certifique-se de que os links estejam corretamente aninhados dentro de um contexto semântico apropriado, como listas `<ul>`, `<ol>`, ou dentro de parágrafos `<p>`.
Evite o uso excessivo de links em um só bloco de texto, o que pode ser confuso para leitores de tela.

**Bom exemplo:**

```html
<ul>
    <li><a href="page1.html">Página 1</a></li>
    <li><a href="page2.html">Página 2</a></li>
    <li><a href="page3.html">Página 3</a></li>
</ul>
```

Links estruturados em uma lista semântica, facilitando a navegação.

**Mau exemplo:**

```html
<a href="page1.html">Página 1</a>
<a href="page2.html">Página 2</a>
<a href="page3.html">Página 3</a>
```

Links soltos sem estrutura semântica, o que pode ser confuso para usuários de tecnologias assistivas.


### Links Abertos em Nova Janela/Aba:

Informe aos usuários se um link abrirá uma nova janela ou aba. Isso pode ser feito através de texto de link ou com um aviso, e também usando `aria-label`.

**Bom exemplo:**

```html
<a href="http://exemplo.com" target="_blank" aria-label="Visite nosso parceiro, abre em nova aba">Visite nosso parceiro</a>
```

Informa ao usuário que o link abre em uma nova aba, tanto visualmente quanto para tecnologias assistivas.

**Mau exemplo:**

```html
<a href="http://exemplo.com" target="_blank">Visite nosso parceiro</a>
```

Não informa ao usuário que o link abrirá em uma nova aba, o que pode ser confuso.

## Consistência e Feedback

### Consistência:

Mantenha o estilo e comportamento dos links consistente em todo o site. Isso ajuda os usuários a saberem o que esperar ao interagir com os links.

### Feedback Visual e Auditivo:

Ofereça feedback visual ao clicar em um link, como uma mudança de cor ou sublinhado, para indicar que a ação foi registrada. Se possível, forneça feedback auditivo para usuários de leitores de tela indicando que o link foi ativado.

**Bom exemplo:**

```html
<style>
a {
    color: #1a0dab;
    text-decoration: none;
}

a:hover, a:focus {
    color: #d21f3c;
    text-decoration: underline;
}
</style>

<a href="page.html">Leia mais sobre acessibilidade</a>
```

Consistência no estilo dos links e feedback visual ao passar o mouse ou ao focar no link.

**Mau exemplo:**

```html
<style>
a {
    color: #000;
    text-decoration: none;
}

a:hover {
    color: #000;
}
</style>

<a href="page.html">Leia mais sobre acessibilidade</a>
```

Falta de feedback visual perceptível ao passar o mouse ou ao focar no link.

## Melhoria Contínua

### Testes de Acessibilidade:

- Realize testes regulares com ferramentas de acessibilidade automatizadas e testes manuais para garantir que os links funcionem corretamente e sejam acessíveis.

- Envolva usuários reais com deficiências para testar a usabilidade dos links e identificar possíveis melhorias.

Seguindo essas práticas, você pode melhorar significativamente a acessibilidade dos links no seu site, garantindo que todos os usuários possam navegar e interagir com o conteúdo de forma eficaz e inclusiva.
