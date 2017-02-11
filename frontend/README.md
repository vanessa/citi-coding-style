# Padrão de Desenvolvimento CITi (Frontend)
__Autor:__ Renato Vieira Leite de Barros

__Contato:__ renato.barros@citi.org.br

__GitHub:__ rvlb-19

### 1. Geral

1. Separe HTML, CSS e Javascript em pelo menos um arquivo diferente para cada um.

2. Organize os arquivos em subdiretórios no _root_ do projeto:

    * `static`, para armazenar arquivos .css, imagens, _fonts_, etc. (dentro desse, crie outros subdiretórios para organizar os arquivos por tipo);
    * `scripts`, para armazenar os arquivos .js.


3. **_Don't Repeat Yourself_**

    ```css
    /* Boa prática */
    :root {
        /*
            Declaramos uma pseudo-classe para 
            guardar algumas constantes.
        */
        --secondary-color: red;
    }
    
    p, a {
        color: var(--secondary-color)
    }
    
    /* Má prática */
    p {
        color: red;
    }
    
    a {
        color: red;
    }
    ```

4. Use `"aspas duplas"` em HTML e `'aspas simples'` para o restante.

### 2. HTML & CSS

1. **Sempre** utilize a estrutura de HTML5. Além disso, garanta compatibilidade com o IE:

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <meta charset="UTF-8">
            <meta http-equiv="X-UA-Compatible" content="IE=Edge">
            <title>Foo</title>
            <!-- Imports de CSS -->
        </head>
        <body>
            <!-- Conteúdo do body -->
            <!-- Imports de Javascript -->
        </body>
    </html>
    ```

2. Utilize `class` e `id` apropriadamente:
    * Se o elemento é usado apenas uma vez no documento, use `id`.
    * Caso contrário, use `class`.

3. Evite usar _tags_ `<br>`.

4. **Não** use _style inline_:

    __Errado__
    ```html
    <div id="div-1">
        <p style="text-align:justify; color: #f00;">
            Please no.
        </p>
    </div>
    ```
    
    __Certo__
    ```html
    <!-- HTML -->
    <div id="div-1">
        <p>Thank you!</p>
    </div>
    ```
    
    ```css
    /* CSS */
    #div-1 p {
        text-align: justify;
        color: #f00;
    }
    ```

5. Adicione o atributo `alt` em elementos `img`.

    ```html
    <!-- Sim -->
    <img src="static/imgs/foo.png" alt="Foo">
    <!-- Não -->
    <img src="static/imgs/foo.png">
    ```

6. Nomeie elementos usando _lower-case_, separando palavras com hífens.

    ```html
    <div id="my-div">
        <!-- Sim -->
    </div>
    <div id="My_DIV">
        <!-- Não -->
    </div>
    ```

7. Elementos HTML que são considerados "viúvos" (ou seja, que não possuem uma segunda tag que os fecha) não devem conter uma barra invertida. Isso inclui, por exemplo, elementos `img`.

8. Atributos de elementos HTML devem vir nesta ordem:

- `class`
- `id`, `name`
- `data-*`
- `src`,`for`,`type`,`href`,`value`
- `title`,`alt`
- `role`,`aria-*`

9. Evite ao máximo gerar HTML a partir do Javascript, visto que isso torna o processo de _debugging_ mais complicado.

10. Prefira utilizar códigos de cor hexadecimal e em letra minúscula. Quando possível, utilize a versão reduzida dos códigos:

    ```css
    #certo {
        color: #fff;
        background-color: #f00;
    }
    
    #errado {
        color: #FFFFFF;
        background-color: #red;
    }
    ```

11. Aplique um único espaço entre o nome do seletor de CSS e a chave de abertura:
    
    ```css
    #errado-1{
        color: #fff;
    }
    
    #errado-2
    {
        color: #fff;
    }
    
    #certo {
        color: #fff;
    }
    ```

12. Separe os seletores de CSS com uma quebra de linha:

    __Certo__
    ```css
    #seletor-1 {
        color: #abc;
    }
    
    #seletor-2 {
        color: #cba;
    }
    ```

    __Errado__
    ```css
    #seletor-1 {
        color: #abc;
    }
    #seletor-2 {
        color: #cba;
    }
    ```

13. Não especifique unidade de medida para valores que sejam nulos.
    ```css
    #certo {
        margin: 0;
    }

    #errado {
        margin: 0px;
    }
    ``` 

14. Sempre adicione `;` ao fim de cada declaração, mesmo quando opcional.

15. Todo `:` e toda `,` devem ser sucedidos por um espaço em branco.

16. Grupos de seletores devem ter seus componentes separados linha-a-linha, desta forma:
    ```css
    #seletor-1, 
    #seletor-2, 
    #seletor-3 {
        color: #fff;
    }
    ``` 

### 3. Javascript

1. Inicialize variáveis no momento da declaração:

    ```javascript
    // Não
    var myVar;
    myVar = 19;
    // Sim
    var myVar = 19;
    ```

2. Sempre use `var` para declarar variáveis e `;` ao fim de um _statement_.

    ```javascript
    var good = 1; // Sim
    bad = 1 // Não
    ```

3. Use camelCase para nomes de funções e variáveis e CamelCase para classes.

    ```javascript
    // Sim
    var myVar = 1;
    function myFunction(myParam) {
        // ...
    }
    class MyClass {
        // ...
    }
    // Não
    var my_var = 1;
    function myfunction(MyParam) {
        // ...
    }
    class myclass {
        // ...
    }
    ```

4. Restrinja variáveis ao bloco em que elas fizerem sentido:

    ```javascript
    // Não
    var i = 0;
    for(i = 0 ; i < 10 ; i++) {
        console.log(i);
    }
    // Sim
    for(var i = 0 ; i < 10 ; i++) {
        console.log(i);
    }
    ```
    
5. Seja consistente na forma de englobar um novo bloco. Use apenas uma das formas abaixo durante o projeto:

    ```javascript
    // Assim...
    function myFunc()
    {
        console.log('Nada contra quem prefere esta...');
    }
    // Ou assim...
    function myFunc() {
        console.log('... mas esta é a melhor.');
    }
    //Jamais as duas...
    ```

6. Agrupe o código de forma que _statements_ relacionados fiquem próximos uns dos outros:

    ```javascript
    // Não
    var myVar = 10;
    for(var i = 0 ; i < 10 ; i++) {
        console.log(i);
    }
    console.log('Hello World.');
    console.log('I\'m waiting to much to print myVar.');
    console.log(myVar);
    
    // Sim
    var myVar = 10;
    console.log(myVar);
    for(var i = 0 ; i < 10 ; i++) {
        console.log(i);
    }
    console.log('Hello World.');
    ```
