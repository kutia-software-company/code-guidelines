# Laravel

First and foremost, Laravel provides the most value when you write things the way Laravel intended you to write. If there's a documented way to achieve something, follow it. Whenever you do something differently, make sure you have a justification for why you didn't follow the defaults.

# General PHP Rules
Code style must follow PSR-1, PSR-2 and PSR-12. Generally speaking, everything string-like that's not public-facing should use camelCase. Detailed examples on these are spread throughout the guide in their relevant sections.

#### CLASS DEFAULTS

By default, we don't use final. In our team, there aren't many benefits that final offers as we don't rely too much on inheritance. For our open source stuff, we assume that all our users know they are responsible for writing tests for any overwritten behaviour.

#### NULLABLE AND UNION TYPES

Whenever possible use the short nullable notation of a type, instead of using a union of the type with `null`.

```php
// in a class

// good
public ?string $variable;

// bad
public string | null $variable;
#VOID RETURN TYPES
If a method returns nothing, it should be indicated with void. This makes it more clear to the users of your code what your intention was when writing it.

// good

// in a Laravel model
public function scopeArchived(Builder $query): void
{
    $query->
        ...
}
```