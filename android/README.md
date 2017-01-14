# Padrão de Desenvolvimento CITi (Android)
__Autor:__ Renato Vieira Leite de Barros

__Contato:__ renato.barros@citi.org.br

__GitHub:__ rvlb-19

### 1. XML

1. Todos os elementos devem conter um `id`.

2. Os identificadores dos elementos devem ser nomeados em *lower_case*, utilizando _underscores_ para separar palavras.
    ```xml
    android:id="@+id/my_id"
    ```
3. Os identificadores dos elementos devem ser nomeados da seguinte forma: [abreviação do tipo de elemento]_[nome do elemento].

    ```xml
    <!-- Exemplos -->
    android:id="@+id/bt_button" <!-- Button -->
    android:id="@+id/rl_layout" <!-- RelativeLayout -->
    android:id="@+id/et_text" <!-- TextView -->
    android:id="@+id/cb_check" <!-- Checkbox -->
    ```
4. Todos os layouts devem ter um `RelativeLayout` como elemento raiz.

5. Os elementos `Button` (em geral) não devem ter um elemento `onClick` definido no arquivo XML.

### 2. Java

1. Variáveis globais devem ser `private` por padrão.

2. Classes devem ser nomeadas usando CamelCase e variáveis devem ser nomeadas usando camelCase.

3. Variáveis `private` devem ser nomeadas da seguinte forma: m[nome do elemento].

    ```java
    private int mAwesomeInt;
    ```

4. Variáveis `Button` devem definir um `onClickListener` caso não tenha sido definido um elemento `onClick` no arquivo XML.









