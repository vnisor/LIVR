### String Rules

#### string {#string}

Checks that value is primitive type and coerces it to the string. Better use more strict rules.

Example:

```javascript
{
    data: 'any' // validator will pass "data" field
    payload: ['required', 'string']
}
```

You can treat this rule as modifier.

#### eq {#eq}

Error code: 'NOT\_ALLOWED\_VALUE'

Example:

```javascript
{ first_name: {'eq': 'Anton'} }
```

#### one\_of {#one-of}

Error code: 'NOT\_ALLOWED\_VALUE'

Example:

```javascript
// new syntax (introduced in v0.4)
{ first_name: {'one_of': ['Anton', 'Igor']} }

// old syntax
{ first_name: {'one_of': [['Anton', 'Igor']]} }
```

#### max\_length {#max-length}

Error code: 'TOO\_LONG'

Example:

```javascript
{ first_name: { max_length: 10 } }
```

#### min\_length {#min-length}

Error code: 'TOO\_SHORT'

Example:

```javascript
{ first_name: { min_length: 2 } }
```

#### length\_between {#length-between}

Error code: 'TOO\_LONG' or 'TOO\_SHORT'

Example:

```javascript
{ first_name: { length_between: [2, 10] }
```

#### length\_equal {#length-equal}

Error code: 'TOO\_LONG' or 'TOO\_SHORT'

Example:

```javascript
{ first_name: { length_equal: 7 }
```

#### like {#like}

Error code: 'WRONG\_FORMAT'

Example:

```javascript
{ first_name: { like: '^\w+?$' }
{ first_name: { like: ['^\w+?$', 'i'] } // with flags
```

Only 'i' flag is currently required by specification.

**Be aware** that regular expressions can be language dependent. Try to use most common syntax. This rule is experimental as it requires more strict semantics.
