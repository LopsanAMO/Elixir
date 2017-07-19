# Elixir

# Instalacion de Elixir

## Mac OS X
* Homebrew
  * Actualizar homebrew
    ```
    brew update
  ```
  * Instalar Elixir
    ```
    brew install elixir
    ```

* Macports
  * Instalar Elixir
    ```
    sudo port install elixir
    ```

## Ubuntu
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

## Windows
* Instalador Web
  * [Descargalo picando aqui 7u7](https://repo.hex.pm/elixir-websetup.exe)
  * Y le picas next, next y asi :3

* Instalar con Chocolatey
  * cinst elixir


# Instalacion de Erlang

## Mac OS X
* Homebrew
  ```
  brew install erlang
  ```

* Macports
  ```
  port install erlang
  ```

## Ubuntu y Debian
  ```
  sudo apt-get install erlang
  ```    

## Windows
* 32-bit
  * [Descargalo picando aqui 7u7](http://erlang.org/download/otp_win32_19.0.exe)
  * Y le picas next, next y asi :3

* 64-bit
  * [Descargalo picando aqui 7u7](http://erlang.org/download/otp_win64_19.0.exe)
  * Y le picas next, next y asi :3

## Exporta la variable path
  ```
  export PATH="$PATH:/path/to/elixir/bin"
  ```
