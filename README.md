# Inko FastJSON
This is an Inko package that makes creating big JSON objects somewhat less painful than using `std.Json`

## Examples
```js
import fastjson(obj, arr)

let my_object = obj
    .str("name", "John")
    .int("age", 25)
    .arr("hobbies", arr
        .str("programming")
        .str("swimming")
    ).to_string
```
The resulting object is:
```json
{"name":"John","age":25,"hobbies":["programming","swimming"]}
```

### Example with nested objects
```js
import fastjson(obj, arr)

let city = obj
    .obj("library", obj
        .str("name", "City Library")
        .obj("branch", obj
            .str("name", "Main Branch")
            .obj("book", obj
                .str("title", "1984")
                .str("author", "George Orwell")
            )
        )
    ).to_string
```
The resulting object is:
```json
{"library":{"name":"City Library","branch":{"name":"Main Branch","book":{"title":"1984","author":"George Orwell"}}}}
```
