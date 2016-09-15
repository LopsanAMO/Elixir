# **Enum**
  Un conjunto de algoritmos para hacer enumeración sobre colecciones.

## **Enum**

El módulo ```Enum``` incluye más de cien funciones para trabajar con las colecciones que aprendimos en la última lección.

Esta lección solo cubrirá un subconjunto de las funciones disponibles. Para ver la lista completa de funciones visita la documentación oficial ```Enum```; para enumeración diferida usa el módulo ```Stream```.

### **aall?**

Cuando usas ```all?```, y muchas de las funciones de ```Enum```, proveemos una función para aplicar a los elementos de nuestra colección. En el caso de ```all?```, la colección entera debe ser evaluada a ```true```, en otro caso ```false``` será retornado:
```ex
iex> Enum.all?(["foo", "bar", "hello"], fn(s) -> String.length(s) == 3 end)
false
iex> Enum.all?(["foo", "bar", "hello"], fn(s) -> String.length(s) > 1 end)
true
```

### **any?**

Diferente a lo anterior, ```any?``` retornará ```true``` si al menos un elemento es evaluado a ```true```:
```ex
iex> Enum.any?(["foo", "bar", "hello"], fn(s) -> String.length(s) == 5 end)
true
```

### **chunk**

Si necesitas dividir tu colección en pequeños grupos, ```chunk``` es la función que probablemente estás buscando:
```ex
iex> Enum.chunk([1, 2, 3, 4, 5, 6], 2)
[[1, 2], [3, 4], [5, 6]]
```

Hay algunas opciones para ```chunk``` pero no vamos a entrar en ellas, revisa ```chunk/2``` en la documentación oficial para aprender más.

### **chunk_by**

Si necesitas agrupar una colección basándose en algo diferente al tamaño, podemos usar la función ```chunk_by```:
```ex
iex> Enum.chunk_by(["one", "two", "three", "four", "five"], fn(x) -> String.length(x) end)
[["one", "two"], ["three"], ["four", "five"]]
```

### **each**

Puede ser necesario iterar sobre una colección sin producir un nuevo valor, para este caso podemos usar ```each```:
```ex
iex> Enum.each(["one", "two", "three"], fn(s) -> IO.puts(s) end)
one
two
three
```

**Nota**: La función ```each``` retorna el átomo ```:ok```.

### **map**

Para aplicar una función a cada elemento y producir una nueva colección revisa la función ```map```:
```ex
iex> Enum.map([0, 1, 2, 3], fn(x) -> x - 1 end)
[-1, 0, 1, 2]
```

#### **min**

Retorna el mínimo valor de la colección:
```ex
iex> Enum.min([5, 3, 0, -1])
-1
```

### **max**

Retorna el máximo valor de la colección:
```ex
iex> Enum.max([5, 3, 0, -1])
5
```

### **reduce**

Con ```reduce``` podemos transformar nuestra colección a un único valor, para hacer esto aplicamos un acumulador opcional (```10``` en este ejemplo) que será pasado a nuestra función; si no se provee un acumulador, el primer valor es usado:
```ex
iex> Enum.reduce([1, 2, 3], 10, fn(x, acc) -> x + acc end)
16
iex> Enum.reduce([1, 2, 3], fn(x, acc) -> x + acc end)
6
```

### **sort**

Ordenar nuestras colecciones se hace fácil con no una, sino dos funciones de ordenación. La primera opción disponible para nosotros utiliza el criterio de Elixir para determinar el orden de ordenación:
```ex
iex> Enum.sort([5, 6, 1, 3, -1, 4])
[-1, 1, 3, 4, 5, 6]

iex> Enum.sort([:foo, "bar", Enum, -1, 4])
[-1, 4, Enum, :foo, "bar"]
```

La otra opción nos permite proveer una función de ordenación:
```ex
# con nuestra función
iex> Enum.sort([%{:val => 4}, %{:val => 1}], fn(x, y) -> x[:val] > y[:val] end)
[%{count: 4}, %{count: 1}]

# sin nuestra función
iex> Enum.sort([%{:count => 4}, %{:count => 1}])
[%{count: 1}, %{count: 4}]
```

### **uniq**

Podemos usar ```uniq``` para eliminar duplicados de nuestras colecciones:
```ex
iex> Enum.uniq([1, 2, 2, 3, 3, 3, 4, 4, 4, 4])
[1, 2, 3, 4]
```
