# misc

Making JS objects immutable

```javascript
const person = {
    name: "Mr. X"
    address: {
        street: "20A"
        city: "Dhaka"
    }
}

```

```javascript
// Object.freeze ⇒ Read only
// Freeze's only the top level object
// Recursively freeze 'address' if that's needed to be frozen

Object.freeze(person)
Object.freeze(person.address)

person.name = "Mr. Y" // TypeError: Cannot assign to read only property
delete person.name // Error
```

```javascript
// Object.seal doesn't allow to add or delete
// But allows update
// Similar to freeze, it only works on top level

Object.seal(person)

person.name = "Mr. Y" // no error
delete person.name // TypeError
person.age = 32 // TypeError

```

```javascript
// Object.preventExtensions allows delete and update
// But not adding new property
// Similar to freeze & seal, it only works on top level

Object.preventExtensions(person)
person.age = 32 // TypeError: Object is not extensible
```

{% code title="to check" %}
```
Object.isFrozen(person)
Object.isSealed(person)
Object.isExtensible(person)
```
{% endcode %}
