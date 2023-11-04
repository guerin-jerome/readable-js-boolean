# Readable JS boolean

Data :

```js
const person = {
   name: "John Doe",
   yearsOld: 19
}
```

I would like to verify that the person's name is John Doe and doesn't has 18 years old.

```js
// I want to change this code style
const { name, yearsOld } = person

const basic = name === 'John Doe' && yearsOld !== 18

// We can do better =>
Boolean.prototype.and = function (boolean) {
   return this.valueOf() && boolean
}

const not = (boolean) => !boolean

const hasJohnDoeName = name === 'John Doe'
const hasEighteenYearsOld = yearsOld === 18
const hasntEighteenYearsOld = yearsOld !== 18

const first = hasJohnDoeName.and(not(hasEighteenYearsOld))

// OR

const second = hasJohnDoeName.and(hasntEighteenYearsOld)
```

✅ I find this much more readable.
