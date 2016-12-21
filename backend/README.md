# Padrão de Desenvolvimento CITi (Backend)
__Autor:__ Renato Vieira Leite de Barros

__Contato:__ renato.barros@citi.org.br

__GitHub:__ rvlb-19

### 1. Django

1. Use Python 3.

2. Use Django 1.10.

3. Use `'aspas simples'` quando for necessário.

4. Use a formatação CamelCase para nomear classes e lower_case (com um _underscore_ separando as palavras) para o restante.

    ```python
    class Foo:
        def __init__(self, bar):
            self.bar = bar
    
    def do_something(foo):
        print(foo.bar)
    
    foo = Foo(1)
    do_something(foo)
    ```

5. Garanta acoplamento fraco, ou seja, cada _app_ deve "cuidar" apenas das suas funções, conhecendo minimamente (preferencialmente nada) do que os outros _apps_ fazem.

6. Use herança de _templates_ para evitar repetição desnecessária de código.

7. Arrume a _root_ do projeto da seguinte forma:

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