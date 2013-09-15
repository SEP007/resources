# PHP Gotchas

## Automatic Typecasting

...meaning: punch a primitive type until it suits your needs.
@kostas was asking about this example from the CodeAcademy where a simple addition is performed in the way of:

```php
echo "40 + 2 = " +1
```

which gives `41`. One might cry but that's how casting internally works as `(int) "40 + 2 = "` gives `41` as well.
Back to the first example the PHP runtime will discover an operation of type addition. The right hand assignment is a `1`, the operator a `+` and the left hand is a string `"40 + 2 = "` which makes PHP gulp for a second - what's its gonna do now? Operations can only performed on numbers so the left hand side needs to become a number too and by casting it, it becomes `40` cause the *string itself will not be evaluated as an expression!*

## Strings and Variable Interpolation

...is: how to concatinate string with variables and not get surprised.
At some point strings and variables need to be concatinted to get some dynamic output. Consider the following example:

```php
$a = "Adonis!";
echo "Kostas is an $a";
```

This will output "Kostas is an Adonis!" cause the runtime will look into the string and find the variable flying around which then will be replaced with its content in "Adonis!". This after all, makes PHP a decent templating language already. Anyhow, whenever you type something like:

```php
$a = "Adonis!";
echo 'Kostas is an $a';
```

*Note the single quotes!* You are basically promising PHP a string without varibles, telling it not having to look into it and doing the interpolation - which is of course minimally faster. If you wanted to concatinate the a string the hard way, you could do:

```php
$a = "Adonis!";
echo 'Kostas is an' . $a;

# or

echo "Kostas is an" . $a;

```

...in any case "Adonis!" does not be in double quotes as it is never meant to carry a variable.