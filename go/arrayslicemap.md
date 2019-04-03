## <a name='arrayslicemap'>[Array, Slice, Map](index.md)</a>

### <a name='array'>[Array](index.md#)</a>

length fixed at declaration
var nomvar [nb_elem] type

ex:

```go
var beatles[4] string
//initilaized in declaration
numbers := []{1, 2, 3, 4}
```

### <a name='slice'>Slice</a>

Slices are not fixed size array.

```go
var my_slice = make([] type_var, size)
```
* access element: 

```go
my_slice[index]
```
* append element(s): 

```go
my_slice := append( my_slice, elem1[, elem2, etc...])
```
* deleting elem: 

```go
my_slice := append(my_slice[:2], my_slice[2+1:]...)
```
* copying: 

```go
copy( copy_slice, my_slice ) 
```
or to copy sub range:

```go
copy( copy_slice, my_slice[1:] ) 
```


### <a name='map'>Map</a>

* initialization

```
var players = make(map[string]int)
```
* assignation

```go
players["cook"] = 32
```

* delete:

```go
delete(player,"cook")
```
