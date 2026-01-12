# JavaScript Learning Summary

เอกสารฉบับนี้สรุปการเรียนรู้พื้นฐานภาษา JavaScript ผ่านกิจกรรมหลัก โดยอธิบายการทำงานของโค้ดและผลลัพธ์ที่ได้

---

## 01-variables.js: Variables & Data Types

ไฟล์นี้สาธิตพื้นฐานการจัดเก็บข้อมูลและการจัดการประเภทข้อมูลในภาษา JavaScript

### การทำงานของโค้ด

#### Scoped Variables

ใช้ `const` สำหรับค่าคงที่ที่ไม่เปลี่ยนค่า  
และใช้ `let` สำหรับตัวแปรที่สามารถเปลี่ยนแปลงค่าได้

#### Data Types

แสดงการใช้งานประเภทข้อมูลพื้นฐาน ได้แก่

- Number
- String (ใช้ Template Literals)
- Boolean
- null
- undefined

#### Type Coercion

สาธิตการแปลงประเภทข้อมูลอัตโนมัติ (Implicit Type Conversion)  
เช่น การใช้เครื่องหมาย `+` และ `-` ร่วมกับ String และ Number

### ตัวอย่างโค้ด

```js
const firstName = "John";
const fullName = `${firstName} Doe`; // Template Literal

console.log("'5' + 2:", "5" + 2); // "52" (String Concat)
console.log("'5' - 2:", "5" - 2); // 3 (Numeric)
```

## ผลลัพธ์ใน Console

MAX_USERS: 100

typeof []: object

## 02-functions.js: Functions & Arrow Functions

ไฟล์นี้เน้นการสร้างฟังก์ชันในรูปแบบต่าง ๆ และ Syntax สมัยใหม่

### การทำงานของโค้ด

#### Arrow Functions

- ใช้ `=>` เพื่อเขียนฟังก์ชันให้สั้นลง
- รองรับ Implicit Return เมื่อมีคำสั่งเดียว

#### Rest Parameters

- ใช้ `...numbers` เพื่อรับพารามิเตอร์หลายค่า
- ข้อมูลจะถูกเก็บในรูปแบบ Array

#### Destructuring

- ดึงค่าจาก Object มาใช้เป็นพารามิเตอร์ได้ทันที

### ตัวอย่างโค้ด

```js
const square = (x) => x * x;

const sum = (...nums) => nums.reduce((total, n) => total + n, 0);
```

# ผลลัพธ์ใน Console

square(5): 25

sum(1, 2, 3): 6

## 03-control-flow.js: Control Flow & Logic

ไฟล์นี้เน้นการควบคุมทิศทางการทำงานของโปรแกรมด้วยเงื่อนไข

### การทำงานของโค้ด

- ใช้ `if / else` และ `switch` ในการตัดสินใจ
- ใช้ `||` สำหรับกำหนดค่าเริ่มต้น
- ใช้ `?.` (Optional Chaining) เพื่อป้องกัน error
- ใช้ Ternary Operator เพื่อเขียนเงื่อนไขแบบย่อ

### ตัวอย่างโค้ด

```js
const userName = admin?.name || user.name || "Anonymous";

const isWeekend = (day) => (day === 6 || day === 7 ? "Weekend" : "Weekday");
```

## ผลลัพธ์ใน Console

Age 15: Teenager

Can drive: true

## 04-loops.js: Loops & Array Methods

ไฟล์นี้เน้นการจัดการข้อมูลใน Array ด้วยเมธอดสมัยใหม่

### การทำงานของโค้ด

- `map()` ใช้แปลงค่าข้อมูล
- `filter()` ใช้คัดกรองข้อมูลตามเงื่อนไข
- `reduce()` ใช้รวมข้อมูลให้เหลือค่าเดียว
- Method Chaining ใช้หลายเมธอดต่อกันในคำสั่งเดียว

### ตัวอย่างโค้ด

```js
const numbers = [1, 2, 3, 4, 5];

const evenStrings = numbers
  .filter((n) => n % 2 === 0)
  .map((n) => `${n}² = ${n * n}`)
  .join(", ");
```

## ผลลัพธ์ใน Console

Class average: 87.00

Top scorer: Alice (95)

## 05-integration.js: Quiz Application

ไฟล์นี้เป็นการประยุกต์ใช้ความรู้ทั้งหมดร่วมกันในรูปแบบแอปพลิเคชันแบบทดสอบ (Quiz)

### การทำงานของโค้ด

- ใช้ Array of Objects เก็บข้อมูลคำถามและคำตอบ
- ใช้ `forEach` วนลูปตรวจคำตอบของผู้ใช้
- ใช้ `filter` และ `reduce` วิเคราะห์คะแนนรวม
- ใช้ `Math.random()` เพื่อสุ่มคำถามหรือคำตอบ

### ตัวอย่างโค้ด

```js
const questions = [
  { question: "2 + 2 = ?", answer: 4 },
  { question: "5 - 3 = ?", answer: 2 },
  { question: "3 * 3 = ?", answer: 9 },
  { question: "10 / 2 = ?", answer: 5 },
  { question: "6 + 1 = ?", answer: 7 },
];

let score = 0;

questions.forEach((q) => {
  const userAnswer = q.answer; // จำลองการตอบถูก
  if (userAnswer === q.answer) {
    score++;
  }
});

const percentage = (score / questions.length) * 100;
```

## ผลลัพธ์ใน Console

FINAL SCORE: 4/5 (80.0%)

GRADE:B

All activities completed!
