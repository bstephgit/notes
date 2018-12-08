# GO reading notes

bool false by default if not assigned

array: var nom_tab [nb_items] type: ex var beatles[4] string
ex: numbers := []{1, 2, 3, 4}

Variable type: reflect pkg => reflect.TypeOf(var)

Type conversion:  pkg strconv
 from string strconv.ParseBool
 from bool strconv.FormatBool(true) 
Type info: pkg reflect => reflect.TypeOf()

## variable declaration:

var <nom-var> <type-var>
several var on same line: var s, t string = "foo", "bar"

different types:
var (
	s string = "foo"
  i int = 4
)

Lazy initialization: <var-name> := <value> Rq: should only be used inside function

constants: example "const i int = 10"

## for statement:

1) for index := 0; index; index++ { } : use classical index

2) for index , value := range container { } : iterate through container with range keyword.

## defer

defer : executed after function execution.

## Array, Slice, Map

### Array:
length fixed at declaration
var nomvar [nb_elem] type

### Slice: 
not fixed size array
var my_slice = make([] type_var, size)
access element: my_slice[index]
append element(s): my_slice := append( my_slice, elem1, elem2, etc... )
deleting elem: my_slice := append(my_slice[:2], my_slice[2+1:]...)
copying: copy( copy_slice, my_slice ) or copy( copy_slice, my_slice[1:] ) to copy sub range

### Map: 
