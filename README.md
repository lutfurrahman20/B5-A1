# Provide an example of using union and intersection types in TypeScript.
 
=> Union Type:
The easiest way to understand a Union type is to think of it as an “or” condition. For example, let’s say you have a function that takes a user ID. Some users might pass a string like "user123", and others might pass a number like 123. Now, if you want to say, “Hey, I’m okay with either a string or a number,” you can use a Union type. The syntax is string | number. That | symbol is the key — it means “either this or that.”

Where do we use it?
When a function accepts inputs of different types.

In situations where data can be of one type at one time and a different type at another time.

Intersection Type:
Intersection Type in TypeScript means combining multiple types into one, where the new type must include all properties from the combined types. It’s similar to the “AND” logic — meaning the object must satisfy both Type A and Type B. For example, let’s say you have an Admin type that includes a role, and an Employee type that includes a startDate. Now, if you want to create a user who is both an admin and an employee, you use Intersection Type like this: Admin & Employee. This means the user must have both role and startDate — nothing can be left out. It’s mostly used with object types and is very useful when you need to define complex roles or combine multiple type requirements.

In simple words, Intersection Type is like saying: “I want everything together, not separately.

Just example : 
<pre><code>
```ts 
// Union Type 
type Result = "pass" | "fail"; 
let examResult: Result = "pass";

// Intersection Type 
type A = { x: number }; 
type B = { y: number }; 
type C = A & B; 
const point: C = { x: 10, y: 20 }; 
```</code></pre>


# What is the use of the keyof keyword in TypeScript? Provide an example.

=> To understand the keyof keyword in TypeScript, think of it like this — it lets us extract all the keys (property names) of an object and turn them into a separate type. Suppose you have an object with keys like name, age, and email. When you use keyof on that object type, you’ll get a union type like "name" | "age" | "email" — basically, all the property names packed into one type.

So, why is this useful? Let’s say you’re writing a generic function that needs to work with different object keys. If you use keyof, you can make sure the user is only allowed to pass valid keys from the object. If they try something invalid, TypeScript will throw an error right away — even before running the code. That makes your code much safer and prevents silly mistakes.

The cool part is, keyof makes your code dynamic like JavaScript, but safe like TypeScript. It’s super helpful when working with large objects or building reusable functions. Long story short, whenever you're dealing with objects and want to be flexible but still safe, keyof is a total game-changer.

Just example : 
<pre><code>
```ts 
type User = { id: number; username: string }; 
type Keys = keyof User; 
const key: Keys = "id"; 
```</code></pre>