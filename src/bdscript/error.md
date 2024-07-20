# $error
Can only be used inside $catch block. Return information about the error.

## Syntax
```
$error[Type]
```

### Parameters 
- `Type` `(Type: Enum || Flag: Required)`: The type of message that gets returned for the error.

### Types
You can use the following "types" within `$error[]`:
- `message` - Returns the error message.
- `row` - Returns the row the error is in.
- `column` - Returns the column the error is in.
- `command` - Returns the function the error is in.
- `source` - Returns the function with all arguments the error is in.

## Example
```
$nomention
$try
  $roleGrant[Intentional;Error]
$catch
  $description[The function: `$error[command]` returned an error in `$error[row]:$error[column]`.
  Source: `$error[source]`
  Error message: `$error[message]` 
  $color[#FF0000]
]
$endtry
```

![example](https://media.discordapp.net/attachments/1247968915091492965/1264207501700890634/image.png?ex=669d087c&is=669bb6fc&hm=8e4e16ecc87efff42c89804dbc6f9cc9be4500a5913e1f2121c05bc884eab642&=&format=webp&quality=lossless)

> How [`$catch[]`](./catch.md) and [`$try[]`](./try.md) works?