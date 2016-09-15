# Elixir

#Instalacion de Elixir

##Mac OS X
* Homebrew
  * Actualizar homebrew 
    ```
    brew update
  ````
  * Instalar Elixir
    ```
    brew install elixir
    ```
    
* Macports
  * Instalar Elixir
    ```
    sudo port install elixir
    ```
    
##Ubuntu
* Agregar el repo de Erlang Solutions
  ```
  wget https://packages.erlang-solutions.com/erlang-solutions_1.0_all.deb && sudo dpkg -i erlang-solutions_1.0_all.deb
  ```
  
* Lo tipico
  ```
  sudo apt-get update
  ```
  
* Instalar la plataforma Erlang/OTP y todas sus aplicaciones
  ```
  sudo apt-get install esl-erlang
  ```
  
* Instalar Elixir
  ```
  sudo apt-get install elixir
  ```
  
##Windows
* Instalador Web
  * [Descargalo picando aqui 7u7](https://repo.hex.pm/elixir-websetup.exe)
  * Y le picas next, next y asi :3

* Instalar con Chocolatey
  * cinst elixir


#Instalacion de Erlang

##Mac OS X
* Homebrew
  ```
  brew install erlang
  ```
    
* Macports
  ```
  port install erlang
  ```
    
##Ubuntu y Debian
  ```
  sudo apt-get install erlang
  ```    

##Windows
* 32-bit
  * [Descargalo picando aqui 7u7](http://erlang.org/download/otp_win32_19.0.exe)
  * Y le picas next, next y asi :3

* 64-bit
  * [Descargalo picando aqui 7u7](http://erlang.org/download/otp_win64_19.0.exe)
  * Y le picas next, next y asi :3

###Exporta la variable path
  ```
  export PATH="$PATH:/path/to/elixir/bin"
  ```

# **Modo Interactivo**
  Elixir viene con una consola interactiva, que nos permite evaluar expresiones Elixir.
  
  Para ejecutarla
    ```
    iex
    ```
    
### **Enteros**
  ```
  iex> 255
  255
  ```
  
El soporte para números binarios, octales y hexadecimales también viene incluido:
  ```
  iex> 0b0110
  6
  iex> 0o644
  420
  iex> 0x1F
  31
  ```
  
### **Coma flotante**  
  En Elixir, los números con coma flotante requieren un decimal después de al menos un dígito; estos tienen una precisión de 64 bits y soportan e para números exponenciales
  ```
  iex> 3.14 
  3.14
  iex> .14 
  ** (SyntaxError) iex:2: syntax error before: '.'
  iex> 1.0e-10
  1.0e-10
  ```

### **Booleanos**
  En Elixir, los números con coma flotante requieren un decimal después de al menos un dígito; estos tienen una precisión de 64 bits y soportan e para números exponenciales.
  ```
  iex> 3.14 
  3.14
  iex> .14 
  ** (SyntaxError) iex:2: syntax error before: '.'
  iex> 1.0e-10
  1.0e-10
  ```

### **Átomos**
  Un Átomo es una constante cuyo nombre es su valor, si estás familiarizado con Ruby estos son equivalentes a los Símbolos:
  ```
  iex> :foo
  :foo
  iex> :foo == :bar
  false
  ```
  
NOTA: Booleanos ```true``` y ```false``` son también los átomos ```:true``` y ```:false``` respectivamente.
  ```
  iex> true |> is_atom
  true
  iex> :true |> is_boolean
  true
  iex> :true === true
  true
  ```

### **Cadenas**
  Las cadenas en Elixir están codificadas en utf-8 y están representadas con comillas dobles:
  ```
  iex> "Hello"
  "Hello"
  iex> "dziękuję"
  "dziękuję"
  ```
  
  Las cadenas soportan saltos de línea y secuencias de escape:
  ```
  iex> "foo
  ...> bar"
  "foo\nbar"
  iex> "foo\nbar"
  "foo\nbar"
  ```

## Operadores Basicos

### Aritmetica
  Elixir soporta los operadores básicos ```+```, ```-```, ```*```, y ```/``` como era de esperarse. Es importante resaltar que ```/``` siempre retornará un número con coma flotante:
  ```
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
  ```
  iex> div(10, 5)
  2
  iex> rem(10, 3)
  1
  ```
  
### Operaciones Booleanas
  Elixir provee los operadores booleanos: ```||```, ```&&```, y ```!```, estos soportan cualquier tipo:
  ```
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
  ```
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
