# Colecciones
  Listas, tuplas, listas de palabras clave, mapas, diccionarios y combinadores funcionales

## **Listas**
  Las listas son simples colecciones de valores. Estas pueden incluir múltiples tipos; las listas pueden incluir valores no únicos:
  ```
  iex> [3.14, :pie, "Apple"]
  [3.14, :pie, "Apple"]
  ```

  Elixir implementa las listas como listas enlazadas. Esto significa que acceder a la longitud de la lista es una operación ```O(n)```. Por esta razón, normalmente es más rápido agregar un elemento al inicio que al final:
  ```
  iex> list = [3.14, :pie, "Apple"]
  [3.14, :pie, "Apple"]
  iex> ["π"] ++ list
  ["π", 3.14, :pie, "Apple"]
  iex> list ++ ["Cherry"]
  [3.14, :pie, "Apple", "Cherry"]
  ```

### **Concatenacion de listas**
  La concatenación de listas usa el operador '''++/2''':
  ```
  iex> [1, 2] ++ [3, 4, 1]
  [1, 2, 3, 4, 1]
  ```

### **Sustraccion de listas***
    El soporte para sustracción es provisto por el operador ```--/2```; es seguro sustraer un valor que no existe:
    ```
    iex> ["foo", :bar, 42] -- [42, "bar"]
    ["foo", :bar]
    ```

    Tenga en cuenta los valores duplicados. Para cada elemento de la derecha, la primera ocurrencia de la misma se retira de la izquierda.
    ```
    iex> [1,2,2,3,2,3] -- [1,2,3,2]
    [2, 3]
    ```

### **Cabeza/Cola**
  Cuando usas listas es común trabajar con la cabeza y la cola de la lista. La cabeza es el primer elemento de la lista y la cola son los elementos restantes. Elixir provee dos funciones útiles, ```hd``` y ```tl```, para trabajar con estas partes:
  ```
  iex> hd [3.14, :pie, "Apple"]
  3.14
  iex> tl [3.14, :pie, "Apple"]
  [:pie, "Apple"]
  ```

  Además de la funciones citadas, puedes usar el operador tubería ```|```; veremos este patrón en futuras lecciones:
  ```
  iex> [h|t] = [3.14, :pie, "Apple"]
  [3.14, :pie, "Apple"]
  iex> h
  3.14
  iex> t
  [:pie, "Apple"]
  ```
