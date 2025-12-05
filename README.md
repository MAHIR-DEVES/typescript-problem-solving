# TypeScript Problem Solving – Assignment

Name: Md Meherab Hossain Munna  
Course: TypeScript Problem Solving Assignment  
Date: November 2025

---

## Overview

এই অ্যাসাইনমেন্টে মোট আটটি TypeScript সমস্যা সমাধান করতে হবে এবং সাথে TypeScript
সম্পর্কিত দুইটি টপিক নিয়ে একটি ব্লগ লিখতে হবে।  
সমস্ত কোড একটি ফাইলে রাখা হয়েছে: `solution.ts`  
এবং ব্লগসহ এই README.md ফাইলটি রিপোজিটরিতে যুক্ত করা হয়েছে।

নীচে Blog Section-এ দেওয়া পাঁচটি টপিকের মধ্যে আমি দুইটি টপিক বেছে নিয়ে ব্যাখ্যা
করেছি।

---

# Blog Section

## Topic 1: Interfaces এবং Types এর মধ্যে পার্থক্য

TypeScript-এ interface এবং type—দুটি প্রায় একই উদ্দেশ্যে ব্যবহৃত হয়, অর্থাৎ একটি
object-এর গঠন বা structure নির্ধারণ করতে। তবে তাদের মধ্যে কিছু গুরুত্বপূর্ণ
পার্থক্য রয়েছে।

### ১. Declaration Merging

Interface একাধিকবার ঘোষণা করা যায় এবং তারা merge হয়ে যায়।  
Type alias এর ক্ষেত্রে merge হয় না; একই নামে আবার ঘোষণা করলে error দেয়।

উদাহরণ:

```ts
interface User {
  name: string;
}
interface User {
  age: number;
}
```

```ts
type User = { name: string };
type User = { age: number }; // Error
```

### ২. Extension

Interface সহজে extends করা যায়।  
Type alias extends করা যায় কিন্তু intersection (&) ব্যবহার করে।

### ৩. Flexibility

Type alias দিয়ে union, tuple, primitive সব ধরনের টাইপ define করা যায়, যেমন:

```ts
type ID = string | number;
```

Interface দিয়ে শুধুমাত্র object এর shape নির্ধারণ করা যায়।

### সংক্ষেপে

- Interface মূলত object structure নির্ধারণে বেশি ব্যবহার হয়।
- Type alias বেশি flexible এবং বিভিন্ন ধরনের টাইপ define করতে কাজে লাগে।

---

## Topic 2: any, unknown, এবং never এর মধ্যে পার্থক্য

TypeScript-এ any, unknown এবং never—এই তিনটি advanced টাইপ, এবং তাদের কাজ একে
অন্যের থেকে সম্পূর্ণ আলাদা।

### any

এই টাইপটি সব ধরনের মান গ্রহণ করতে পারে।  
TypeScript এই টাইপের ক্ষেত্রে কোনো ধরনের type-check করে না।  
এটি খুব flexible হলেও ভুল ধরা যায় না।

```ts
let data: any = 'Hello';
data = 20;
data = true;
```

### unknown

এটিও যেকোনো মান গ্রহণ করতে পারে, কিন্তু ব্যবহার করার আগে অবশ্যই type-check করতে
হয়।  
সে কারণে এটি any থেকে নিরাপদ।

```ts
let value: unknown = 'Test';
if (typeof value === 'string') {
  console.log(value.toUpperCase());
}
```

### never

এমন একটি টাইপ যা কখনোই কোনো মান return করে না।  
সাধারণত error throw করা function বা infinite loop-এ এটি দেখা যায়।

```ts
function throwError(msg: string): never {
  throw new Error(msg);
}
```

### সংক্ষেপে

- any সবকিছু হতে পারে কিন্তু type safety নষ্ট করে।
- unknown সবকিছু হতে পারে কিন্তু ব্যবহারের আগে type-check করা জরুরি।
- never এমন জায়গায় ব্যবহৃত হয় যেখানে কোনো মান কখনোই return হওয়ার কথা নয়।

---

# Files Included

- `solution.ts`  
  সমস্যাগুলোর সমাধান এই ফাইলে লেখা হয়েছে।
- `README.md`  
  অ্যাসাইনমেন্টের বিবরণ এবং ব্লগ এই ফাইলে দেওয়া হয়েছে।

---

# Submission Note

এই অ্যাসাইনমেন্টটি প্রয়োজনীয় কাঠামো, ফাইল এবং নির্দেশনা অনুসরণ করে সম্পন্ন করা
হয়েছে।
