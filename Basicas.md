# **Modo Interactivo**
  Elixir viene con una consola interactiva, que nos permite evaluar expresiones Elixir.

  Para ejecutarla
    ```
    iex
    ```

### **Enteros**
  ```ex
  iex> 255
  255
  ```

El soporte para números binarios, octales y hexadecimales también viene incluido:
  ```ex
  iex> 0b0110
  6
  iex> 0o644
  420
  iex> 0x1F
  31
  ```

### **Coma flotante**  
  En Elixir, los números con coma flotante requieren un decimal después de al menos un dígito; estos tienen una precisión de 64 bits y soportan e para números exponenciales
  ```ex
  iex> 3.14
  3.14
  iex> .14
  ** (SyntaxError) iex:2: syntax error before: '.'
  iex> 1.0e-10
  1.0e-10
  ```

### **Booleanos**
  En Elixir, los números con coma flotante requieren un decimal después de al menos un dígito; estos tienen una precisión de 64 bits y soportan e para números exponenciales.
  ```ex
  iex> 3.14
  3.14
  iex> .14
  ** (SyntaxError) iex:2: syntax error before: '.'
  iex> 1.0e-10
  1.0e-10
  ```

### **Átomos**
  Un Átomo es una constante cuyo nombre es su valor, si estás familiarizado con Ruby estos son equivalentes a los Símbolos:
  ```ex
  iex> :foo
  :foo
  iex> :foo == :bar
  false
  ```

NOTA: Booleanos ```true``` y ```false``` son también los átomos ```:true``` y ```:false``` respectivamente.
  ```ex
  iex> true |> is_atom
  true
  iex> :true |> is_boolean
  true
  iex> :true === true
  true
  ```

### **Cadenas**
  Las cadenas en Elixir están codificadas en utf-8 y están representadas con comillas dobles:
  ```ex
  iex> "Hello"
  "Hello"
  iex> "dziękuję"
  "dziękuję"
  ```

  Las cadenas soportan saltos de línea y secuencias de escape:
  ```ex
  iex> "foo
  ...> bar"
  "foo\nbar"
  iex> "foo\nbar"
  "foo\nbar"
  ```

## Operadores Basicos

### **Aritmetica**
  Elixir soporta los operadores básicos ```+```, ```-```, ```*```, y ```/``` como era de esperarse. Es importante resaltar que ```/``` siempre retornará un número con coma flotante:
  ```ex
  iex> 2 + 2
  4
  iex> 2 - 1
  1
  iex> 2 * 5
  10
  iex> 10 / 5
  2.0
  ````

  Si tú necesitas una división entera o el resto de una división, Elixir viene con dos funciones útiles para para lograr esto:
  ```ex
  iex> div(10, 5)
  2
  iex> rem(10, 3)
  1
  ```

### **Operaciones Booleanas**
  Elixir provee los operadores booleanos: ```||```, ```&&```, y ```!```, estos soportan cualquier tipo:
  ```ex
  iex> -20 || true
  -20
  iex> false || 42
  42

  iex> 42 && true
  true
  iex> 42 && nil
  nil

  iex> !42
  false
  iex> !false
  true
  ```

  Hay tres operadores adicionales cuyo primer argumento tiene que ser un booleano (```true``` y ```false```):
  ```ex
  iex> true and 42
  42
  iex> false or true
  true
  iex> not false
  true
  iex> 42 and true
  ** (ArgumentError) argument error: 42
  iex> not 42
  ** (ArgumentError) argument error
  ```

### **Comparación**
 Elixir viene con todos los operadores de comparación a los que estamos acostumbrados: ```==```, ```!=```, ```===```, ```!==```, ```<=```, ```>=```, ```<``` y ```>```.
 ```ex
 iex> 1 > 2
 false
 iex> 1 != 2
 true
 iex> 2 == 2
 true
 iex> 2 <= 3
 true
 ```

Para comparación estricta de enteros y flotantes usamos ```===```:
 ```ex
 iex> 2 === 2.0
 true
 iex> 2 === 2.0
 false
 ```

Una característica importante de Elixir es que cualquier par de tipos se pueden comparar, esto es útil particularmente en ordenación. No necesitamos memorizar el orden pero es importante ser consciente de este:
```ex
number < atom < reference < functions < port < pid < tuple < maps < list < bitstring
```

Esto puede conducir a algunas interesantes y válidas comparaciones que no puedes encontrar en otros lenguajes:
```ex
iex> :hello > 999
true
iex> {:hello, :world} > [1, 2, 3]
false
````

### **Interpolacion de cadenas**
 La concatenación de cadenas usa el operador ```<>```:
 ```ex
 iex> name = "Lopsan el crack"
 iex> "Soy " <> name
 "Soy Lopsan el crack"
 ````
