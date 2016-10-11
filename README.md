# Padrão de Desenvolvimento CITi
__Autor:__ Renato Vieira Leite de Barros

__Contato:__ renato.barros@citi.org.br

__GitHub:__ rvlb-19

### 1. Geral

1. Programe em inglês (recomendado) ou em português.

2. Seja consistente no idioma em que você está programando. Use apenas uma das duas opções para o projeto inteiro.

    ```python
    # Programe em português...
    def soma_numeros(x,y):
        return (x+y)
        
    # ...ou em inglês...
    def multiply_numbers(x,y):
        return (x*y)
    
    # ...seja consistente.
    ```

3. Nomeie os elementos com no máximo 3 palavras:

    ```html
    <!-- HTML & CSS -->
    <div class="my-class">
        <!-- Sim -->
    </div>
    <div class="my-awesome-super-duper-class-and-knuckles">
        <!-- Não -->
    </div>
    ```
    ```javascript
    // Javascript
    var myVar = 1; // Sim
    var myVariableThatHoldsSomething = 1; // Não
    ```
4. Use nomes apropriados para elementos/variáveis:

    ```html
    <!-- Não -->
    <div class="my-class">
        <p>Hello World.</p>
    </div>
    <!-- Sim -->
    <div class="dialog-box">
        <p>Hello World.</p>
    </div>
    ```
    
    ```javascript
    // Não
    var myArray = []; // Nome genérico para variável
    for(var iterator = 0 ; iterator < 10 ; iterator++) {
        // Nome muito extenso para um iterador.
        myArray.push(iterator);
    }
    //Sim
    var digits = [];
    for(var i = 0 ; i < 10 ; i++) {
        // Nomeie iteradores na seguinte ordem: i, j, k...
        digits.push(i);
    }
    ```
5. Use `"aspas duplas"` em HTML e `'aspas simples'` para o restante.

6. Comente quando necessário:

    ```html
    <!-- Comentário em arquivos HTML -->
    ```

    ```css
    /* 
        Comentário em 
        arquivos CSS
    */
    ```

    ```javascript
    // Comentário de linha em arquivos Javascript
    /*
        Comentário de bloco 
        em arquivos Javascript
    */
    ```
    
    ```python
    # Comentário de linha em Python
    ```

7. Aplique uma identação de 4 espaços quando um novo escopo for aberto:

    ```html
    <!-- HTML -->
    <div class="class-1">
        <div class="class-2">
            <p>Some Text...</p>
        </div>
    </div>
    ```
    
    ```css
    /* CSS */
    body {
        width: 100%;
    }
    ```
    
    ```javascript
    // Javascript
    for(var i = 0 ; i < 5 ; i++) {
        console.log(i);
        for(var j = 0 ; j < 5 ; j++) {
            console.log(j);
        }
    }
    ```
    
    ```python
    def myFunction():
        return 'Foo'
    ```

8. Documente o que for implementado:

    ```javascript
    /* function somaNumeros(x,y);
        Retorna a soma de dois números x e y
        passados como parâmetro.
    */
    function somaNumeros(x,y) {
        return (x+y);
    }

    // But don't overuse it...
    /* function imprimeSucessorDe(x);
        Imprime o valor do sucessor de um número
        passado como parâmetro.
    */
    function imprimeSucessorDe(x) {
        /*
            Atribuímos o valor de x à variável criada 
            para guardar o sucessor de x.
        */
        var suc = x;
        // Adicionamos 1 para calcular o sucessor.
        suc = suc + 1;
        // Imprimimos o sucessor de x no console.
        console.log(suc);
        // Fim do fluxo da função.
    }
    ```

### 2. HTML, CSS & Javascript

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

### 3. HTML & CSS

1. **Sempre** utilize a estrutura de HTML5:

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <meta charset="UTF-8">
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

4. Não use _style inline_:

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

6. Nomeie elementos usando lower-case, separando palavras com hífens.

    ```html
    <div id="my-div">
        <!-- Sim -->
    </div>
    <div id="My_DIV">
        <!-- Não -->
    </div>
    ```

7. Prefira utilizar códigos de cor hexadecimal e em letra minúscula:

    ```css
    #certo {
        color: #fff;
        background-color: #f00;
    }
    
    #errado {
        color: #FFF;
        background-color: #red;
    }
    ```

8. Aplique um único espaço entre o nome do seletor de CSS e a chave de abertura:
    
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

9. Separe os seletores de CSS com uma quebra de linha:

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

### 4. Javascript

1. Inicialize variáveis no momento da declaração:

    ```javascript
    // Não
    var myVar;
    myVar = 19;
    // Sim
    var myVar = 19;
    ```

2. Sempre use `var` para declarar variáveis e `;` ao fim de um statement.

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

4. Restrinja variáveis ao escopo em que elas fizerem sentido:

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
    
5. Seja consistente na forma de englobar um novo escopo. Use apenas uma das formas abaixo durante o projeto:

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

### 5. Python

1. Quando possível, use Python 3.

2. Use a formatação CamelCase para nomear classes e lower_case (com um _underscore_ separando as palavras) para o restante.

    ```python
    class Foo:
        def __init__(self, bar):
            self.bar = bar
    
    def do_something(foo):
        print(foo.bar)
    
    foo = Foo(1)
    do_something(foo)
    ```

3. Em aplicações para _desktop_, crie uma função main.

    ```python
    def main():
        print('Hello')
    if __name__ == "__main__":
        main()
    ```

### 6. Django

1. Use Django 1.10.

2. Garanta acoplamento fraco, ou seja, cada _app_ deve "cuidar" apenas das suas funções, conhecendo minimamente (preferencialmente nada) do que os outros _apps_ fazem.

3. Use herança de _templates_ para evitar repetição desnecessária de código.

4. Nos _templates_, quando estiver escrevendo código _Python-like_, continue seguindo as regras de identação previamente especificadas.

5. Arrume a _root_ do projeto da seguinte forma:

```
projeto
│   .gitignore
│   manage.py  
│   <database>
|___projeto
|   |___ ...
|___static
|   |___ ...
|___media
|   |___ ...
|___app_1
|   |___ ...
|___app_2
|   |___ ...
|___ ...
```
