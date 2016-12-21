# Padrão de Desenvolvimento CITi (Geral)
__Autor:__ Renato Vieira Leite de Barros

__Contato:__ renato.barros@citi.org.br

__GitHub:__ rvlb-19

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

5. Comente quando necessário:

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

6. Aplique uma indentação de 1 tab quando um novo escopo for aberto:

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

7. Documente o que for implementado:

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
