# <font color='hotpink'><strong>Learn HTML Forms by Building a Registration Form</strong></font> :books:

<br>

> [!NOTE]
> Módulo de treinamento para a certificação _Responsive Web Design Certification_ da plataforma  [FreeCodeCamp](https://www.freecodecamp.org/learn/2022/responsive-web-design/).

<br><br>

## :memo: <font color='turquoise'><strong>Notas de Aula</strong></font>

<br>

- [x] A unidade `vh` representa a altura da janela de visualização (viewport), e é igual a 1% da altura da viewport. Isso a torna relativa à altura da janela de visualização.
- [x] Uma barra de rolagem horizontal é adicionada por alguns navegadores e pode ser removida definindo `margin: 0`
- [x] O atributo `method` especifica como os dados do formulário serão enviados para a URL definida no atributo `action`. Os dados do formulário podem ser enviados por meio de uma requisição **GET**, como parâmetros na URL (`method="get"`), ou por meio de uma requisição **POST**, como dados no corpo da requisição (`method="post"`).
- [x] A unidade `rem` significa *root em* e é relativa ao tamanho da fonte do elemento `<html>`.
- [x] Como os elementos `<label>` são exibidos como *inline* por padrão, eles aparecem lado a lado na mesma linha, tornando o texto difícil de ler. Para exibi-los em linhas separadas, adicione `display: block` ao elemento `<label>` e um `margin` de `0.5rem 0` para separá-los uns dos outros.
- [x] Seguindo as melhores práticas de acessibilidade, associe os elementos `<input>` aos elementos `<label>` utilizando o atributo `for`. O valor do atributo `for` deve corresponder ao `id` do campo de entrada correspondente, garantindo que a etiqueta esteja corretamente vinculada ao campo de formulário.  

### :star: <font color='#a90dec'><strong>Exemplo</strong></font> :star:

```html
<label for="email">E-mail:</label>
<input type="email" id="email" name="email">
```

<br>

- [x] Especificar o atributo `type` de um elemento `<input>` é importante para que o navegador saiba que tipo de dado ele deve esperar. Se o tipo não for especificado, o navegador usará o tipo padrão, que é *text*.

### :star: <font color='#a90dec'><strong>Exemplo</strong></font> :star:

```html
<form>
  <label for="name">Nome:</label>
  <input type="text" id="name" name="name" required>

  <label for="surname">Sobrenome:</label>
  <input type="text" id="surname" name="surname" required>

  <label for="email">E-mail:</label>
  <input type="email" id="email" name="email" required>

  <label for="password">Senha:</label>
  <input type="password" id="password" name="password" required>
  
  <button type="submit">Registrar</button>
</form>
```
<br>

- [x] O primeiro elemento `<input>` com o tipo `submit` é automaticamente configurado para submeter o formulário mais próximo.

Aqui está um exemplo de como adicionar o botão de envio após o último elemento `<fieldset>`:

```html
<form>
  <fieldset>
    <legend>Informações Pessoais</legend>
    <label for="name">Nome:</label>
    <input type="text" id="name" name="name" required>

    <label for="surname">Sobrenome:</label>
    <input type="text" id="surname" name="surname" required>
  </fieldset>

  <fieldset>
    <legend>Informações de Contato</legend>
    <label for="email">E-mail:</label>
    <input type="email" id="email" name="email" required>

    <label for="password">Senha:</label>
    <input type="password" id="password" name="password" required>
  </fieldset>

  <input type="submit" value="Enviar">
</form>
```