# TypeScript Notes

> Beginner-friendly notes about TypeScript history and why it exists.
> English-এর সাথে সহজ Bangla explanation দেওয়া হয়েছে, যেন বুঝতে সুবিধা হয়।

------------------------------------------------------------------------

## 1. A Short History of TypeScript

JavaScript was originally created to add interactivity to websites. পরে
JavaScript দিয়ে বড় বড় applications তৈরি করা শুরু হয়---যেমন enterprise
software, dashboards, complex web apps.

Project বড় হওয়ার সাথে কিছু সমস্যা দেখা দেয়:

-   Type-related bugs সহজেই হতে পারে।
-   বড় codebase বুঝতে ও maintain করতে কঠিন হয়।
-   Refactoring করলে অন্য জায়গায় unexpected bugs হতে পারে।
-   বড় team-এর সাথে code manage করা কঠিন হয়ে যায়।

**Codebase:** একটি project-এর সব code-এর collection.

**Maintain:** Code update করা, bug fix করা এবং future-এ সহজে কাজ করার
মতো অবস্থায় রাখা।

### Microsoft's Role

Microsoft introduced **TypeScript in 2012**.

Anders Hejlsberg, যিনি **C# language-এর key designer**, তিনি TypeScript
design-এর সাথেও যুক্ত ছিলেন।

C# design করার experience TypeScript-এর design-এ influence করেছে---বিশেষ
করে type system এবং developer tools-এর ক্ষেত্রে।

তবে মনে রাখবে:

**TypeScript C# থেকে তৈরি হয়নি।** TypeScript তৈরি হয়েছে JavaScript-এর
উপর ভিত্তি করে, যেখানে optional static typing এবং কিছু additional features
যোগ করা হয়েছে।

### Relationship between JavaScript and TypeScript

-   **JavaScript:** Browser এবং Node.js সরাসরি execute করে।
-   **TypeScript:** JavaScript-এর উপর type checking এবং extra features
    যোগ করে।
-   TypeScript code compile/transform হয়ে JavaScript-এ convert হয়, তারপর
    run করে।

**Compile / Transpile:** এক language বা code format থেকে অন্য format-এ
convert করা।

------------------------------------------------------------------------

## 2. Why TypeScript Exists: The Problem with Plain JavaScript

JavaScript flexible এবং শুরুতে শেখা সহজ। কিন্তু JavaScript সাধারণত program
run হওয়ার আগে variable-এর type check করে না।

**Type:** Data কী ধরনের---যেমন number, string, boolean.

### Example: JavaScript

``` javascript
function add(a, b) {
  return a + b;
}

console.log(add(10, 20));   // 30
console.log(add("10", 20)); // "1020"
```

এখানে:

-   `10 + 20` করলে result হয় `30`.
-   `"10" + 20` করলে JavaScript number যোগ না করে string combine করে
    `"1020"` বানায়।

**String:** Text data, যেমন `"Hello"` বা `"10"`.

এ ধরনের unexpected behavior থেকে bug হতে পারে।

### How TypeScript solves this

``` typescript
function add(a: number, b: number): number {
  return a + b;
}

add(10, 20);   // 30
add("10", 20); // TypeScript error
```

TypeScript বলে দেয় যে `"10"` একটি string, কিন্তু function এখানে number আশা
করছে।

**Static Type Checking:** Code run হওয়ার আগেই type-related ভুল detect
করার চেষ্টা করা।

### Understanding the TypeScript syntax

``` typescript
function add(a: number, b: number): number
```

-   `a: number` --- `a` অবশ্যই number হতে হবে।
-   `b: number` --- `b` অবশ্যই number হতে হবে।
-   `): number` --- function-এর return value number হওয়া উচিত।

**Parameter:** Function-এ input হিসেবে পাঠানো value.

**Return value:** Function কাজ শেষ করে যে result দেয়।

------------------------------------------------------------------------

## 3. JavaScript vs TypeScript

  -----------------------------------------------------------------------
  JavaScript                          TypeScript
  ----------------------------------- -----------------------------------
  Dynamically typed                   Static type checking যোগ করে

  Type-related mistakes runtime-এ ধরা অনেক type-related mistake আগেই
  পড়তে পারে                           detect করতে পারে

  Flexible এবং দ্রুত code লেখা যায়      বড় project maintain করা সহজ হয়

  Browser এবং Node.js সরাসরি run করে  JavaScript-এ compile/transform করতে
                                      হয়
  -----------------------------------------------------------------------

**Runtime:** যখন program execute বা run হচ্ছে, সেই সময়।

> TypeScript সব ধরনের bug prevent করতে পারে না। তবে অনেক type-related
> error আগেই ধরতে সাহায্য করে।

------------------------------------------------------------------------

## 4. Important Things to Remember

**TypeScript = JavaScript + Static Type Checking**

-   TypeScript হলো JavaScript-এর **superset**। অর্থাৎ সাধারণভাবে valid
    JavaScript code TypeScript-এও valid.
-   TypeScript developer-কে error আগেই ধরতে সাহায্য করে।
-   বড় project এবং team-এর ক্ষেত্রে TypeScript বিশেষভাবে useful.
-   Browser সাধারণত TypeScript সরাসরি execute করে না। TypeScript
    JavaScript-এ convert হয়, তারপর run করে।

**Superset:** এমন language যা অন্য language-এর features-এর পাশাপাশি
additional features support করে।

### One-line Summary

**TypeScript exists to make JavaScript development safer, more
predictable, and easier to maintain---especially as projects grow.**

সহজভাবে: JavaScript-এর flexibility রেখে code-এ type checking যোগ করে ভুল
কমানো এবং বড় project manage করা সহজ করাই TypeScript-এর মূল উদ্দেশ্য।
