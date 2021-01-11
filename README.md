# Koodistandard

Üldised koodistandardi alused.
Javascriptile põhinev.
Typescriptile põhinev.

## Üldised koodistandardi alused

#### Referentsid (references)

1. Kasuta `const` kõikidel mitte-muutuvatel referentsidel. eslint: [prefer-const](https://eslint.org/docs/rules/prefer-const.html)

```js
const x = 0;
const y = 0;
```

2. Kasuta `let` kui referents tulevikus muutub. eslint: [no-var](https://eslint.org/docs/rules/no-var.html) [no-const-assign](https://eslint.org/docs/rules/no-const-assign.html)

```js
let i = 0;
i = 1;
```

#### Objektid (objects)

1. Kasuta parameetri väärtuse lühendit, kuna see on arusaadavam ja lühem. eslint: [object-shorthand](https://eslint.org/docs/rules/object-shorthand.html)

```js
const name = "John Doe";

// halb
const obj = {
  name: name,
};

// hea
const obj = {
  name,
};
```

2. Kasutja objekti laiendamise operaatorit (object spread operator) kui teed objektist koopiat. eslint: [prefer-object-spread](https://eslint.org/docs/rules/prefer-object-spread)

```js
const obj = {
  name: "John",
  age: 30,
};

const newObj = {
  ...obj,
};

const ageObj = {
  ...obj,
  age: 31,
};
```

#### Jadad (arrays)

TODO

#### Sõned (strings)

1. Kasuta `""` asemel `''`. eslint: [quotes](https://eslint.org/docs/rules/quotes.html)

2. Sõnede koostamisel kasuta _template stringe_. eslint: [prefer-template](https://eslint.org/docs/rules/prefer-template.html)

```js
`Tere, ${name}`;
```

#### Destruktureerimine (destructuring)

1. Destruktureeri objekti igal pool kus sa saad. Kood on paremini loetav, ning annab vähem võimalusi vigadeks.

```js
const obj = {
  firstName: "John",
  lastName: "Doe",
};

const { firstName, lastName } = obj;
```

```js
const arr = [
  {
    firstName: "John",
    lastName: "Doe",
  },
  {
    firstName: "Jane",
    lastName: "Doe",
  },
];

arr.map(({ firstName, lastName }) => `${firstName} ${lastName}`);
```

2. Kasutades anonüümset funktsiooni, kasuta noole funktiooni märgendit (arrow function notation). eslint: [prefer-arrow-callback](https://eslint.org/docs/rules/prefer-arrow-callback.html)

```js
[11, 22, 33].reduce((a, b) => a * b);

[6, 2, 4, 3].sort((a, b) => a - b);
```
