# Padrão de Desenvolvimento CITi (iOS)
__Autor:__ Renato Vieira Leite de Barros

__Contato:__ renato.barros@citi.org.br

__GitHub:__ rvlb-19

1. O conteúdo deste documento é baseado no _guideline_ de Swift desenvolvido pela Apple e disponível neste [link](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/), assim como no padrão proposto pelo GitHub, disponível neste [link](https://github.com/github/swift-style-guide). Este padrão de desenvolvimento é válido para a versão 3.0.1 de Swift.

2. Prefira utilizar `let` (constantes) ao invés de `var` (variáveis). Para isso, declare sempre constantes e altere-as para variáveis apenas caso seja imprescindível.

3. Use camelCase para nomes de funções, variáveis e constantes e CamelCase para nomes de structs, classes, enumerações, protocolos e extensões.

4. Não utilize `;` ao fim de _statements_.

5. Prefira structs ao invés de classes.

6. Evite a _pyramid of doom_. Use `guard` quando for possível retornar rapidamente de uma função quando uma condição não for atingida.

    ```swift
    // Sim
    guard let foo = foo else {
        print("There is a nil in foo.")
        return
    }
    guard foo > 0 else {
        print("Oops, foo isn't positive.")
        return
    }
    print("foo is positive. Yay!")
    // Não
    if let foo = foo {
        if foo > 0 {
            print("foo is positive. Yay!")
        } else {
            print("Oops, foo isn't positive.")
        }
    } else {
        print("There is a nil in foo.")
    }
    ```

7. Use `"aspas duplas"`.

8. Evite, quando possível, forçar o _unwrapping_ de uma variável (`foo!`). Prefira a seguinte forma:
    ```swift
    if let foo = foo {
        foo.callFunction()
    } else {
        print("There's nothing in foo.")
    }
    ```
Também é possível utilizar o _Optional Chaining_ de Swift em alguns casos:
    ```swift
    // A forma a seguir fará com que o método só seja chamado caso foo != nil.
    foo?.callFunction()
    ``` 
9. Use a palavra reservada `self` apenas quando for essencial.

10. Quando estiver identificando o tipo de um elemento, use o seguinte formato:
    ```swift
    /* Nome do elemento, seguido de dois pontos (:), espaço em branco e nome do tipo. */
    let foo: Int = 1
    func someFunction(parameter: Int) {
        // Function body
    }
    ```

11. Os arquivos .swift criados devem conter apenas uma _class_/_struct_/_extension_/etc. _top-level_ por vez, onde o nome da estrutura é igual ao nome do arquivo.
    ```swift
    // Arquivo LoginViewController.swift
    class LoginViewController: UIViewController {
        // Class body.
    }
    ```
12. Ao abrir um novo bloco, use `{` (chaves) na mesma linha.
    ```swift
    // Certo
    if foo == 2 {
        // Do stuff...
    } else {
        // Do stuff...
    }
    // Errado
    if foo == 2
    {
        // Do stuff...
    } else 
    {
        // Do stuff...
    }
    ```