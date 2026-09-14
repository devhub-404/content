# Numbers, BigInt, and Math

Number uses IEEE-754 double-precision floating point. Integers are exact only within the safe-integer range, and many decimal fractions cannot be represented exactly in binary. `Number` provides conversion and validation helpers, while `Math` provides common numeric functions and constants.

```js
const average = (10 + 15 + 20) / 3;
const rounded = Math.round(average);
const safe = Number.isFinite(rounded);

const huge = 9_007_199_254_740_993n;
```

BigInt values use an `n` suffix and represent integers without Number's safe-integer limit. BigInt arithmetic requires BigInt operands and integer division truncates. BigInt is for genuinely large integer arithmetic, not ordinary decimal money calculations. Financial code normally uses integer minor units or a decimal arithmetic solution rather than assuming binary floating point is exact.
