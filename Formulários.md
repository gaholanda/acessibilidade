# Formulários

## Uso de Etiquetas `<label>`

Certifique-se de que cada campo de formulário tenha uma etiqueta `<label>` associada.

```html
<form>
  <div>
    <label for="name">Nome:</label>
    <input type="text" id="name" name="name" required>
  </div>
  <div>
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required>
  </div>
  <div>
    <label for="message">Mensagem:</label>
    <textarea id="message" name="message" required></textarea>
  </div>
  <button type="submit">Enviar</button>
</form>
```

## Utilização de Atributos ARIA

Use atributos ARIA (Accessible Rich Internet Applications) para fornecer informações adicionais aos leitores de tela.

```html
<form aria-labelledby="form-title">
  <h2 id="form-title">Formulário de Contato</h2>
  <div>
    <label for="name">Nome:</label>
    <input type="text" id="name" name="name" required aria-required="true">
  </div>
  <div>
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required aria-required="true">
  </div>
  <div>
    <label for="message">Mensagem:</label>
    <textarea id="message" name="message" required aria-required="true"></textarea>
  </div>
  <button type="submit">Enviar</button>
</form>
```

## Indicação de Campos Obrigatórios

Informe claramente quais campos são obrigatórios.

```html
<form>
  <div>
    <label for="name">Nome: <span aria-hidden="true">*</span></label>
    <input type="text" id="name" name="name" required aria-required="true">
  </div>
  <div>
    <label for="email">Email: <span aria-hidden="true">*</span></label>
    <input type="email" id="email" name="email" required aria-required="true">
  </div>
  <div>
    <label for="message">Mensagem: <span aria-hidden="true">*</span></label>
    <textarea id="message" name="message" required aria-required="true"></textarea>
  </div>
  <button type="submit">Enviar</button>
</form>
```

## Feedback de Validação

Forneça feedback claro e acessível para a validação de formulários.

```html
<form id="contact-form">
  <div>
    <label for="name">Nome:</label>
    <input type="text" id="name" name="name" required aria-required="true">
    <span id="name-error" class="error-message" aria-live="polite"></span>
  </div>
  <div>
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required aria-required="true">
    <span id="email-error" class="error-message" aria-live="polite"></span>
  </div>
  <div>
    <label for="message">Mensagem:</label>
    <textarea id="message" name="message" required aria-required="true"></textarea>
    <span id="message-error" class="error-message" aria-live="polite"></span>
  </div>
  <button type="submit">Enviar</button>
</form>

<script>
document.getElementById('contact-form').addEventListener('submit', function(event) {
  let isValid = true;

  const name = document.getElementById('name');
  const email = document.getElementById('email');
  const message = document.getElementById('message');

  const nameError = document.getElementById('name-error');
  const emailError = document.getElementById('email-error');
  const messageError = document.getElementById('message-error');

  if (!name.value) {
    nameError.textContent = 'O nome é obrigatório.';
    isValid = false;
  } else {
    nameError.textContent = '';
  }

  if (!email.value) {
    emailError.textContent = 'O email é obrigatório.';
    isValid = false;
  } else {
    emailError.textContent = '';
  }

  if (!message.value) {
    messageError.textContent = 'A mensagem é obrigatória.';
    isValid = false;
  } else {
    messageError.textContent = '';
  }

  if (!isValid) {
    event.preventDefault();
  }
});
</script>
```

## Estilização Visível do Foco

Garanta que os elementos de formulário tenham um indicador de foco visível quando navegados com o teclado.

```css
input:focus, textarea:focus, button:focus {
  outline: 2px solid blue;
  outline-offset: 2px;
}

input[type="checkbox"]:focus + label,
input[type="radio"]:focus + label,
select:focus {
  outline: 2px solid blue;
  outline-offset: 2px;
}
```

## Navegação por Teclado

Certifique-se de que todos os elementos do formulário sejam navegáveis via teclado, utilizando a ordem natural do DOM ou ajustando com o atributo `tabindex` quando necessário.

## Texto Alternativo Descritivo

Para botões e elementos de interface, utilize texto descritivo e, se necessário, atributos aria-label para fornecer descrições adicionais.

## Utilização de Fieldset e Legend

Use `<fieldset>` e `<legend>` para agrupar checkboxes e radios logicamente relacionados, melhorando a navegação e compreensão.

```html
<form>
  <fieldset>
    <legend>Escolha suas frutas favoritas:</legend>
    <div>
      <input type="checkbox" id="apple" name="fruit" value="apple">
      <label for="apple">Maçã</label>
    </div>
    <div>
      <input type="checkbox" id="banana" name="fruit" value="banana">
      <label for="banana">Banana</label>
    </div>
    <div>
      <input type="checkbox" id="cherry" name="fruit" value="cherry">
      <label for="cherry">Cereja</label>
    </div>
  </fieldset>

  <fieldset>
    <legend>Escolha seu gênero:</legend>
    <div>
      <input type="radio" id="male" name="gender" value="male">
      <label for="male">Masculino</label>
    </div>
    <div>
      <input type="radio" id="female" name="gender" value="female">
      <label for="female">Feminino</label>
    </div>
    <div>
      <input type="radio" id="other" name="gender" value="other">
      <label for="other">Outro</label>
    </div>
  </fieldset>
</form>
```