## TypeScript বিষয়ক ব্লগ পোস্ট

### keyof keyword এর ব্যবহার এবং উদাহরণ
`keyof` ব্যবহার করা হয় একটি Object type-এর সকল key বের করতে।

উদাহরণ:
```ts
type Person = {
  name: string;
  age: number;
};

type PersonKeys = keyof Person;

let key: PersonKeys;
key = 'name';
key = 'age';  

``` 
`keyof` মূলত object keys access করার জন্য ব্যবহার করা হয়।

---

### any, unknown, এবং never type-এর মধ্যে পার্থক্য
TypeScript-এ `any`, `unknown`, এবং `never` type-এর ব্যবহারে পার্থক্য রয়েছে:

1. **any**: যেকোনো ধরনের মান রাখা যায়, type-checking সম্পূর্ণ এড়িয়ে যায়। এটি type-safe নয়।
```ts
let value: any;
value = 10;
value = 'hello';
value = true;
```

2. **unknown**: যেকোনো ধরনের মান রাখা যায়, কিন্তু এটি ব্যবহার করার আগে type-checking করতে হয়। এটি type-safe।
```ts
let value: unknown;
value = 10;
value = 'hello';

if (typeof value === 'string') {
  console.log(value.toUpperCase());
}
```

3. **never**: এমন type যা কখনো কোনো মান ধারণ করে না। সাধারণত function যা exception throw করে বা কখনো return করে না, তার জন্য ব্যবহৃত হয়।
```ts
function errorFunction(): never {
  throw new Error('This function never returns');
}
```

`any` = unsafe, `unknown` = safe, `never` = কোন মান রাখে না।

