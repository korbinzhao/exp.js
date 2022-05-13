# expression.js

# Support
* Data type: number/boolean/string/object/array
* Operators: 
    * Mathematical operators: + - * / 
    * Logic operators: && || > >= < <=  === !== 
    * tenary operator
* Context access
* Property access
* Custom functions: 
    * lodash functions
    * but prohibit function params, avoid prototype access

# Advantage
* Security assurance
    * sandbox isolation
    * avoid memory leak by prohibit while etc.
* [lodash](https://lodash.com/docs/4.17.15) functions support

# Usage
```
const interpret = require('expression.js');

// calculate
interpret('1 + 2 / 4 * 6');
interpret('1 + 2 / (4 * 6)');

// compare
interpret('1 > 2');
interpret('1 < 2');
interpret('1 <= 2');
interpret('2 <= 2');
interpret('2 === 2');

// logic
interpret('1 && 2');
interpret('1 || 0');

// context accessing && property accessing
interpret('a + b / c.d.e', { a: 2, b: 3, c: { d: { e: 5 } } });

// lodash functions
interpret(`_.has(obj, 'a.b')`, { obj: { a: { b: 1, c: 2 } } });
interpret('_.indexOf(arr, 1)', { arr: [1, 2, 3, 4] });

```

# license
MIT
