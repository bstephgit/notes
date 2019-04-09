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
Concatenation string with other type (here int) not allowed:
```go
var i int = 1
var s string = "egg"
var breakfast string = i + s // compilation error
```
rather do conversion:
```go
var i int = 1
var s string = "egg"
intToString := strconv.Itoa(i)
var breakfast string = intToString + s // OK
```
### <a name="buffer">[Use a buffer for concatenation](index.md#strings_buffer)</a>
```go
var buffer bytes.Buffer

for i := 0; i < 500; i++ {
  buffer.WriteString("z")
}
```
### <a name="encoding">[Go character encoding](index.md#strings_encoding)</a>
Go encoding is UTF-8 (go source code is always UTF-8 encoded)
```go
  s := "hello"
  fmt.Printf(s[0]) // outputs 104 => 'h' encoded char
  fmt.Println("%q", s[0]) // outputs 'h'
  fmt.Println("%b", s[0]) // outputs 1101000 = 104 in binary format
```
Not ASCII (european) char:
```go
  s := "網站有中"
  fmt.Println(len(s)) // prints 12 because each char is 3 bytes encoded 
```
### <a name="pkg">[Strings package](index.md#strings_pkg)</a>
*strings* package has methods to work on strings. See strings pkg <a href="https://golang.org/pkg/strings/" target="_blank">here</a>

* Lowercase a string
```go
package main
import( 
  "fmt"
  "strings"
  )
  
  func main(){
    fmt.Println( strings.ToLower("VERY IMPORTANT MESSAGE") )
  }
```

* Searching a substring in a string
```go
package main
import( 
  "fmt"
  "strings"
  )
  
  func main(){
    fmt.Println( strings.Index("surface","face") )
  }
```
* Trim leading and trailing whitespaces
```go
package main
import( 
  "fmt"
  "strings"
  )
  
  func main(){
    fmt.Println( strings.TrimSpace("  I don't need all this space   ") )
  }

```
