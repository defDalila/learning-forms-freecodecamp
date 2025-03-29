# <p align="center"><font color='#FF79C6'><strong>Learn HTML Forms by Building a Registration Form</strong></font></p>

<p align="center"> <i>Módulo de treinamento para a certificação <a href="https://www.freecodecamp.org/learn/2022/responsive-web-design/"><em>Responsive Web Design Certification</em></a> da plataforma FreeCodeCamp</i>.
<p>

<p align="center">
    <img src="https://skillicons.dev/icons?i=html,css,md,vscode,git,github" height="30px">
</p>


<br>

## :memo: <font color='#8BE9FD'><strong>Notas de Aula</strong></font>

<br>

:ballot_box_with_check: A unidade `vh` representa a altura da janela de visualização (viewport), e é igual a 1% da altura da viewport. Isso a torna relativa à altura da janela de visualização.


:ballot_box_with_check: Uma barra de rolagem horizontal é adicionada por alguns navegadores e pode ser removida definindo `margin: 0`


:ballot_box_with_check: O atributo `method` especifica como os dados do formulário serão enviados para a URL definida no atributo `action`. Os dados do formulário podem ser enviados por meio de uma requisição **GET**, como parâmetros na URL (`method="get"`), ou por meio de uma requisição **POST**, como dados no corpo da requisição (`method="post"`).


:ballot_box_with_check: A unidade `rem` significa *root em* e é relativa ao tamanho da fonte do elemento `<html>`.


:ballot_box_with_check: Como os elementos `<label>` são exibidos como *inline* por padrão, eles aparecem lado a lado na mesma linha, tornando o texto difícil de ler. Para exibi-los em linhas separadas, adicione `display: block` ao elemento `<label>` e um `margin` de `0.5rem 0` para separá-los uns dos outros.


:ballot_box_with_check: Seguindo as melhores práticas de acessibilidade, associe os elementos `<input>` aos elementos `<label>` utilizando o atributo `for`. O valor do atributo `for` deve corresponder ao `id` do campo de entrada correspondente, garantindo que a etiqueta esteja corretamente vinculada ao campo de formulário.  


<details>
  <summary><font color='#50FA7B'><strong>Exibir Exemplo de Código</strong></font></summary>

### :star: <font color='#BD93F9'><strong>Exemplo</strong></font> :star:

```html
<label for="email">E-mail:</label>
<input type="email" id="email" name="email">
```

</details>
<br>

:ballot_box_with_check: Especificar o atributo `type` de um elemento `<input>` é importante para que o navegador saiba que tipo de dado ele deve esperar. Se o tipo não for especificado, o navegador usará o tipo padrão, que é *text*.


<details>
  <summary><font color='#50FA7B'><strong>Exibir Exemplo de Código</strong></font></summary>

### :star: <font color='#BD93F9'><strong>Exemplo</strong></font> :star:

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

</details>

<br>

:ballot_box_with_check: O primeiro elemento `<input>` com o tipo `submit` é automaticamente configurado para submeter o formulário mais próximo.


<details>
  <summary><font color='#50FA7B'><strong>Exibir Exemplo de Código</strong></font></summary>

### :star: <font color='#BD93F9'><strong>Exemplo</strong></font> :star:

```html
<form>
  <input type="submit" value="Enviar">
</form>
```
</details>

<br>


:ballot_box_with_check: Certos valores do atributo `type` vêm com validação incorporada no formulário. Por exemplo, `type="email"` exige que o valor seja um endereço de e-mail válido. Para adicionar validação personalizada ao campo de senha, você pode adicionar o atributo `minlength` com o valor de 8, o que impede que senhas com menos de 8 caracteres sejam enviadas.


<details>
  <summary><font color='#50FA7B'><strong>Exibir Exemplo de Código</strong></font></summary>

### :star: <font color='#BD93F9'><strong>Exemplo</strong></font> :star:

```html
<form>
  <fieldset>
    <legend>Informações de Contato</legend>
    <label for="email">E-mail:</label>
    <input type="email" id="email" name="email" required>

    <label for="password">Senha:</label>
    <input type="password" id="password" name="password" required minlength="8">

  </fieldset>

  <input type="submit" value="Enviar">
</form>
```  

</details>

<br>


:ballot_box_with_check: Com `type="password"`, você pode usar o atributo `pattern` para definir uma expressão regular que a senha deve corresponder para ser considerada válida.


<details>
  <summary><font color='#50FA7B'><strong>Exibir Exemplo de Código</strong></font></summary>

### :star: <font color='#BD93F9'><strong>Exemplo</strong></font> :star:

Se você quiser que a senha tenha pelo menos uma letra maiúscula, uma letra minúscula, um número e um caractere especial, você pode usar o seguinte padrão:

```html
<form>
  <fieldset>
    <label for="password">Senha:</label>
    <input type="password" id="password" name="password" required minlength="8" 
           pattern="(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}" 
           title="A senha deve ter pelo menos 8 caracteres,
                uma letra maiúscula, 
                uma letra minúscula,
                um número,
                um caractere especial.">
  </fieldset>
</form>
```

Neste exemplo, o padrão exige que a senha tenha:

- Pelo menos 8 caracteres.
- Pelo menos uma letra minúscula.
- Pelo menos uma letra maiúscula.
- Pelo menos um número.
- Pelo menos um caractere especial, como `@$!%*?&`.  

O atributo `title` fornece uma mensagem de erro personalizada para o usuário caso a senha não atenda ao padrão.

</details>

<br>

:ballot_box_with_check: Para garantir que apenas uma das opções de entrada do tipo rádio possa ser selecionada por vez, você deve atribuir o mesmo valor ao atributo `name` para todas as opções de rádio relacionadas. Isso garante que as entradas de rádio pertencem ao mesmo grupo e que o formulário só permitirá a seleção de uma delas.


<details>
  <summary><font color='#50FA7B'><strong>Exibir Exemplo de Código</strong></font></summary>

### :star: <font color='#BD93F9'><strong>Exemplo</strong></font> :star:

```html
<form>
  <fieldset>
    <legend>Escolha o Tipo de Conta</legend>
    
    <label for="personal">Pessoal</label>
    <input type="radio" id="personal" name="account-type" value="personal">

    <label for="business">Negócios</label>
    <input type="radio" id="business" name="account-type" value="business">
  </fieldset>

  <input type="submit" value="Enviar">
</form>
```

Ao atribuir `name="account-type"` aos dois inputs de rádio, o formulário agora garante que apenas uma das opções possa ser selecionada ao mesmo tempo.

</details>

<br>

:ballot_box_with_check: Para garantir que os usuários selecionem uma das opções de entrada de rádio, você pode adicionar um elemento `<legend>` dentro do `<fieldset>` para fornecer contexto, indicando que o tipo de conta é necessário. Além disso, você pode adicionar o atributo `checked` ao primeiro campo de rádio (Pessoal) para que ele seja selecionado por padrão, o que evita o envio do formulário sem uma seleção.


<details>
  <summary><font color='#50FA7B'><strong>Exibir Exemplo de Código</strong></font></summary>

### :star: <font color='#BD93F9'><strong>Exemplo</strong></font> :star:

```html
<form>
  <fieldset>
    <legend>Escolha o Tipo de Conta (obrigatório)</legend>
    
    <label for="personal">Pessoal</label>
    <input type="radio" id="personal" name="account-type" value="personal" checked>

    <label for="business">Negócios</label>
    <input type="radio" id="business" name="account-type" value="business">
  </fieldset>

</form>
```

- **Legenda (legend)**: A legenda "Escolha o Tipo de Conta (obrigatório)" fornece contexto para os usuários sobre a exigência de seleção.
- **Atributo `checked`**: O atributo `checked` foi adicionado ao campo de rádio "Pessoal" para garantir que uma opção seja selecionada por padrão ao enviar o formulário. 

</details>

<br>

:ballot_box_with_check: Para garantir que o usuário leu os termos e condições, você pode adicionar uma caixa de seleção (checkbox) ao formulário e torná-la obrigatória para o envio. Também é importante incluir o atributo `id` para a caixa de seleção e o atributo `for` no rótulo para melhorar a acessibilidade.


<details>
  <summary><font color='#50FA7B'><strong>Exibir Exemplo de Código</strong></font></summary>

### :star: <font color='#BD93F9'><strong>Exemplo</strong></font> :star:

```html
<form>
  <fieldset>
    <label for="terms-and-conditions">
      <input type="checkbox" id="terms-and-conditions" name="terms-and-conditions" required>
      Eu li e concordo com os Termos e Condições
    </label>
  </fieldset>
</form>
```

- **Checkbox**: A caixa de seleção foi adicionada, com o atributo `required` para garantir que o usuário não possa enviar o formulário sem concordar com os termos.
- **Atributo `id`**: A caixa de seleção recebe o `id="terms-and-conditions"`.
- **Atributo `for`**: O elemento `<label>` usa o `for="terms-and-conditions"`, que vincula o rótulo à caixa de seleção.

</details>

<br>

:ballot_box_with_check: Para permitir que o usuário faça o upload de uma foto de perfil, você pode usar o tipo de entrada `file`, que permite que o usuário selecione um arquivo para enviar. Aqui está um exemplo de como adicionar esse campo ao seu formulário:


<details>
  <summary><font color='#50FA7B'><strong>Exibir Exemplo de Código</strong></font></summary>

### :star: <font color='#BD93F9'><strong>Exemplo</strong></font> :star:

```html
<form>
  <fieldset>
    <label for="profile-picture">Upload de uma foto de perfil:</label>
    <input type="file" id="profile-picture" name="profile-picture">
  </fieldset>

  <input type="submit" value="Enviar">
</form>
```

- **Tipo `file`**: O input com `type="file"` permite que o usuário escolha um arquivo para fazer o upload.
- **Rótulo**: O texto "Upload de uma foto de perfil" foi adicionado para indicar claramente o propósito do campo.
- **Atributo `id`**: O campo de upload recebe o `id="profile-picture"` para a associação com o rótulo (`for="profile-picture"`).

</details>

<br>

:ballot_box_with_check: Para adicionar o campo de idade, você pode usar o tipo de entrada `number`, permitindo que o usuário insira apenas números. Também podemos adicionar os atributos `min` e `max` para restringir a idade dos usuários entre 13 e 120 anos.


<details>
  <summary><font color='#50FA7B'><strong>Exibir Exemplo de Código</strong></font></summary>

### :star: <font color='#BD93F9'><strong>Exemplo</strong></font> :star:

```html
<form>
  <fieldset>
    <label for="age">Digite sua idade (anos):</label>
    <input type="number" id="age" name="age" min="13" max="120" required>
  </fieldset>

  <input type="submit" value="Enviar">
</form>
```

- **Campo de idade**: O campo de entrada para a idade usa o tipo `number`, com os atributos `min="13"` e `max="120"`, para garantir que a idade esteja dentro do intervalo válido.
- **Rótulo**: O texto "Digite sua idade (anos)" é adicionado para informar o usuário sobre o campo.
- **Atributos `min` e `max`**: Restringem a idade dos usuários para não ser inferior a 13 e não superior a 120 anos.

</details>

<br>

:ballot_box_with_check: Adicionar um campo de seleção (dropdown) ao formulário é simples usando o elemento `<select>`. O elemento `<select>` funciona como um contêiner para um grupo de elementos `<option>`, e o elemento `<option>` age como o rótulo para cada opção no menu suspenso. Ambos os elementos exigem tags de fechamento.


<details>
  <summary><font color='#50FA7B'><strong>Exibir Exemplo de Código</strong></font></summary>
  
### :star: <font color='#BD93F9'><strong>Exemplo</strong></font> :star:

```html
<form>
  <fieldset>
    <label for="user-role">Selecione o cargo:</label>
    <select id="user-role" name="user-role" required>
      <option value="admin">Administrador</option>
      <option value="editor">Editor</option>
      <option value="viewer">Visualizador</option>
    </select>
  </fieldset>

  <input type="submit" value="Enviar">
</form>
```

- **Elemento `<select>`**: O `<select>` cria o menu suspenso.
- **Elementos `<option>`**: Cada `<option>` define uma escolha dentro do menu suspenso, com o valor correspondente atribuído ao atributo `value`.
- **Rótulo para o campo de seleção**: "Selecione o cargo" foi adicionado como rótulo para o dropdown.

</details>

<br>

:ballot_box_with_check: Cada opção dentro do elemento `<select>` precisa ter um atributo `value` para garantir que um valor significativo seja enviado ao servidor. Se o atributo `value` não for especificado, o próprio texto visível da opção será enviado.

<details>
  <summary><font color='#50FA7B'><strong>Exibir Exemplo de Código</strong></font></summary>

### :star: <font color='#BD93F9'><strong>Exemplo</strong></font> :star:

```html
<form>
  <fieldset>
    <label for="user-role">Selecione o cargo:</label>
    <select id="user-role" name="user-role" required>
      <option value="">Selecione uma opção</option>
      <option value="admin">Administrador</option>
      <option value="editor">Editor</option>
      <option value="viewer">Visualizador</option>
    </select>
  </fieldset>

  <input type="submit" value="Enviar">
</form>
```

1. **Atributo `value`**: Cada `<option>` agora tem um atributo `value` correspondente.
2. **Opção padrão vazia**: A primeira opção (`value=""`) serve como um placeholder, garantindo que o usuário selecione uma opção válida antes de enviar o formulário. Como o campo é obrigatório (`required`), o formulário não será enviado se essa opção permanecer selecionada.

</details>

<br>

:ballot_box_with_check: Para permitir que os usuários registrem uma biografia, podemos adicionar um elemento `<textarea>` ao formulário. Diferente de um `<input type="text">`, o `<textarea>` permite a inserção de múltiplas linhas de texto, tornando-o ideal para capturar descrições mais longas.

<details>
  <summary><font color='#50FA7B'><strong>Exibir Exemplo de Código</strong></font></summary>

### :star: <font color='#BD93F9'><strong>Exemplo</strong></font> :star:


```html
<form>

  <fieldset>
    <label for="bio">Biografia:</label>
    <textarea id="bio" name="bio" rows="4" cols="50" placeholder="Escreva uma breve biografia..."></textarea>
  </fieldset>

  <input type="submit" value="Enviar">
</form>
```

1. **Elemento `<textarea>`**: Permite a entrada de várias linhas de texto.
2. **Atributo `rows` e `cols`**: Define o tamanho inicial da área de texto.
3. **Atributo `placeholder`**: Fornece um exemplo de entrada para orientar os usuários.

</details>

<br>

:ballot_box_with_check: Cada elemento submit em um formulário deve ter um atributo `name`, pois esse atributo identifica o campo quando os dados são enviados para o servidor. Como os inputs de rádio já possuem um nome em comum (`account-type`), adicionaremos nomes únicos aos demais elementos.

<details>
  <summary><font color='#50FA7B'><strong>Exibir Exemplo de Código</strong></font></summary>

### :star: <font color='#BD93F9'><strong>Exemplo</strong></font> :star:

```html
<form>
  <fieldset>
    <legend>Informações Pessoais</legend>
    
    <label for="name">Nome:</label>
    <input type="text" id="name" name="full-name" required>

    <label for="surname">Sobrenome:</label>
    <input type="text" id="surname" name="last-name" required>

    <label for="age">Digite sua idade (anos):</label>
    <input type="number" id="age" name="user-age" min="13" max="120" required>
  </fieldset>

  <fieldset>
    <legend>Escolha o Tipo de Conta (obrigatório)</legend>
    
    <label for="personal">Pessoal</label>
    <input type="radio" id="personal" name="account-type" value="personal" checked>

    <label for="business">Negócios</label>
    <input type="radio" id="business" name="account-type" value="business">
  </fieldset>

  <fieldset>
    <label for="terms-and-conditions">
      <input type="checkbox" id="terms-and-conditions" name="terms-agreement" required>
      Eu li e concordo com os Termos e Condições
    </label>
  </fieldset>

  <fieldset>
    <label for="profile-picture">Upload de uma foto de perfil:</label>
    <input type="file" id="profile-picture" name="profile-image">
  </fieldset>

  <fieldset>
    <label for="user-role">Selecione o cargo:</label>
    <select id="user-role" name="user-role" required>
      <option value="">Selecione uma opção</option>
      <option value="admin">Administrador</option>
      <option value="editor">Editor</option>
      <option value="viewer">Visualizador</option>
    </select>
  </fieldset>

  <fieldset>
    <label for="bio">Biografia:</label>
    <textarea id="bio" name="user-bio" rows="4" cols="50" placeholder="Escreva uma breve biografia..."></textarea>
  </fieldset>

  <input type="submit" value="Enviar" name="submit-button">
</form>
```


1. **Atributo `name` adicionado a todos os campos submittables**:
   - `name="full-name"` → Nome do usuário
   - `name="last-name"` → Sobrenome do usuário
   - `name="user-age"` → Idade do usuário
   - `name="terms-agreement"` → Confirmação de aceite dos termos
   - `name="profile-image"` → Upload de foto de perfil
   - `name="user-role"` → Seleção do cargo
   - `name="user-bio"` → Biografia do usuário
   - `name="submit-button"` → Botão de envio
   
2. **Os inputs de rádio continuam com o mesmo `name="account-type"`**, pois fazem parte do mesmo grupo.

Agora, o formulário está corretamente estruturado para que os dados enviados sejam bem identificados no servidor! 🚀

</details>

<br>

:ballot_box_with_check: Durante o desenvolvimento, as bordas padrão dos `<fieldset>` ajudam a visualizar a organização do formulário, mas podem deixar os elementos muito separados. Para um design mais compacto e harmonioso, podemos ajustar o estilo das bordas e espaçamentos com CSS.

<details>
  <summary><font color='#50FA7B'><strong>Exibir Exemplo de Código</strong></font></summary>

### :star: <font color='#BD93F9'><strong>Exemplo</strong></font> :star:

```css
fieldset {
  border: 1px solid #ccc; /* Borda mais sutil */
  padding: 10px;
  margin-bottom: 15px; /* Reduz a separação entre os fieldsets */
  border-radius: 5px; /* Bordas arredondadas para um visual mais suave */
}

legend {
  font-weight: bold;
  font-size: 1.1rem;
}
```

- Melhorias:
1. **Borda mais sutil (`border: 1px solid #ccc;`)**: Mantém a visibilidade sem ser intrusiva.
2. **Redução do espaçamento (`margin-bottom: 15px;`)**: Diminui a separação entre os `<fieldset>`.
3. **Bordas arredondadas (`border-radius: 5px;`)**: Deixa o design mais moderno e suave.
4. **Estilização do `<legend>`**: Realce no título de cada seção do formulário.

Caso prefira remover completamente as bordas, use:

```css
fieldset {
  border: none;
  padding: 0;
  margin-bottom: 10px;
}
```

Isso manterá os agrupamentos organizados sem separar demais os elementos. 🚀

</details>

<br>

:ballot_box_with_check: Você pode usar o seletor `:last-of-type` para estilizar especificamente o último `<fieldset>` e ajustá-lo para que se integre melhor ao design do formulário.

<details>
  <summary><font color='#50FA7B'><strong>Exibir Exemplo de Código</strong></font></summary>

### :star: <font color='#BD93F9'><strong>Exemplo</strong></font> :star:

```css
fieldset:last-of-type {
  border: none; /* Remove a borda do último fieldset */
  padding-bottom: 0; /* Ajusta o espaçamento inferior */
  margin-bottom: 0; /* Remove a margem extra abaixo */
}
```

### Explicação:
1. **`fieldset:last-of-type`** → Seleciona apenas o último `<fieldset>` do formulário.
2. **`border: none;`** → Remove a borda do último `<fieldset>`, diferenciando-o dos demais.
3. **`padding-bottom: 0;` e `margin-bottom: 0;`** → Ajusta o espaçamento inferior para evitar um espaço extra indesejado.

Isso ajuda a manter o formulário mais uniforme, especialmente se o último `<fieldset>` contiver apenas um botão de envio. 🚀

</details>

<br>

:ballot_box_with_check: Para garantir que os rótulos (`label`) apareçam acima dos elementos do formulário e que os campos ocupem toda a largura do contêiner pai, podemos usar CSS para estilizar os elementos `<input>`, `<textarea>`, e `<select>`.  

<details>
  <summary><font color='#50FA7B'><strong>Exibir Exemplo de Código</strong></font></summary>

### :star: <font color='#BD93F9'><strong>Exemplo</strong></font> :star:


```css
/* Faz com que os labels apareçam acima dos inputs */
label {
  display: block;
  font-weight: bold;
  margin-bottom: 5px; /* Espaçamento entre o label e o campo */
}

/* Faz com que os campos ocupem toda a largura disponível */
input, textarea, select {
  width: 100%;
  padding: 8px;
  margin-bottom: 10px; /* Espaçamento entre os campos */
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box; /* Evita que padding aumente a largura total */
}

/* Ajuste específico para textarea */
textarea {
  resize: vertical; /* Permite redimensionamento vertical */
}
```

### O que foi melhorado:
1. **`display: block;` nos `<label>`** → Agora os rótulos aparecem acima dos campos.
2. **`width: 100%;` nos `<input>`, `<textarea>` e `<select>`** → Todos os elementos ocupam a largura total do contêiner.
3. **Adicionado `padding` e `border-radius`** → Para um design mais moderno e confortável.
4. **`box-sizing: border-box;`** → Garante que `padding` não aumente a largura total do campo.
5. **`resize: vertical;` no `<textarea>`** → Permite redimensionamento vertical sem afetar a largura.

</details>

<br>

:ballot_box_with_check: Para estilizar o botão de envio (`submit`), podemos usar um **seletor de atributo**, que permite selecionar elementos com base em seus atributos.

<details>
  <summary><font color='#50FA7B'><strong>Exibir Exemplo de Código</strong></font></summary>

### :star: <font color='#BD93F9'><strong>Exemplo</strong></font> :star:

```css
/* Seleciona especificamente o botão de envio */
input[type="submit"] {
  background-color: #007bff; /* Cor de fundo azul */
  color: white; /* Texto branco */
  font-size: 1rem;
  padding: 10px 15px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  width: 100%; /* Faz o botão ocupar toda a largura do formulário */
  transition: background-color 0.3s ease-in-out;
}

/* Efeito ao passar o mouse */
input[type="submit"]:hover {
  background-color: #0056b3; /* Azul mais escuro ao passar o mouse */
}
```

### Explicação:
1. **Seletor `input[type="submit"]`** → Aplica o estilo apenas ao botão de envio.
2. **`background-color: #007bff;`** → Define um fundo azul moderno.
3. **`color: white;`** → Deixa o texto legível.
4. **`border-radius: 5px;`** → Deixa as bordas arredondadas para um visual suave.
5. **`cursor: pointer;`** → Indica que o botão é clicável.
6. **`width: 100%;`** → O botão ocupa toda a largura do formulário.
7. **Efeito `hover`** → Ao passar o mouse, o botão escurece, criando um efeito interativo.

</details>

<br>

:ballot_box_with_check: Para garantir que o campo de upload (`<input type="file">`) tenha um tamanho mais consistente com os outros campos do formulário, podemos aplicar estilos personalizados e remover as configurações padrão dos navegadores.

<details>
  <summary><font color='#50FA7B'><strong>Exibir Exemplo de Código</strong></font></summary>

### :star: <font color='#BD93F9'><strong>Exemplo</strong></font> :star:

```css
/* Normaliza o tamanho do input file para combinar com os outros campos */
input[type="file"] {
  width: 100%;
  padding: 8px; /* Igual aos outros inputs */
  border: 1px solid #ccc;
  border-radius: 4px;
  background-color: white;
  cursor: pointer;
  box-sizing: border-box;
}

/* Ajuste para melhorar a aparência ao passar o mouse */
input[type="file"]:hover {
  border-color: #007bff;
}
```

#### O que isso faz?
1. **`width: 100%`** → Garante que o campo ocupe a largura total do formulário.
2. **`padding: 8px`** → Ajusta o preenchimento para ser igual ao dos outros inputs.
3. **`border: 1px solid #ccc;`** → Mantém um estilo uniforme.
4. **`border-radius: 4px;`** → Bordas arredondadas para um visual mais suave.
5. **`cursor: pointer;`** → Indica que o campo pode ser clicado.
6. **`box-sizing: border-box;`** → Evita que o `padding` afete a largura total.

</details>
