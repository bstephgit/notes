## <a name='strings'>[Strings](index.md#strings)</a>

### <a name="create">[Creation](index.md#strings_create)</a>

```go
var s string = "I am a string"
```
or
```go
s := "I am a string"
```
### <a name="runes">[Runes literals](index.md#strings_runes)</a>
* Rune literals
```go
s := "After a backslash, certain single character escapes represent
    special values\nn is a line feed or new line \n\t t is a tab"
```
* Raw strings literals: with backticks. 
Keep format as it is, with line feeds etc..
```go
s := `After a backslash, certain single character escapes represent
    special values
    n is a line feed or new line
    t is a tab`
```
### <a name="concat">[Concatenating strings](index.md#strings_concat)</a>
* Combaning strings into single string
```g
 s := "Oh sweet ignition" + " be my fuse
```
* Concatenation with assignment operator
```go
s := "Can you hear me?"
s += "\nHear me screaming?"
```
### <a name="types">[Concatenation and types](index.md#strings_types)</a>

```go
var i int = 1
var s string = "egg"
var breakfast string = i + s // compilation error
```
rather do
```go
```go
var i int = 1
var s string = "egg"
intToString := strconv.Itoa(i)
var breakfast string = intToString + s // OK
```
