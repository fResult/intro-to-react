# Create React App

Create React App คือ เครื่องมือที่ Set up environment สำหรับพัฒนา React Application ให้เรียบร้อยแล้วโดยที่เราไม่ต้องไปนั่ง Set up เอาเองตั้งแต่แรก

<br><hr><br>

## Node Package Manager (NPM)

<br>

![NPM](./images/npm-logo.png)

- ปกติแล้วเวลาเราเขียน JS เราสามารถที่จะแชร์ code กับคนอื่น ๆ หรือว่าใช้ code คนอื่นได้ เราจะเรียก code ส่วนนี้ว่าเป็น **"packages"** หรือ **"library"**
- ในโลกของ JS เค้าจะมีตัวเก็บ packages เรียกว่า **npm registry** (npm = **n**ode **p**ackage **m**anager)
- เวลาเราสร้าง project ขึ้นมาเราจะ initialize npm ขึ้นมาก่อนใน project ของเราด้วยคำสั่ง `npm init`
- จากนั้นเราสามารถที่จะติดตั้ง packages ต่าง ๆ ลงใน project ของเราได้ ด้วย `npm install` จากนั้น npm จะทำการ save package ที่ติดตั้งไว้ใน file ที่ชื่อว่า `packages.json`
- เมื่อเรา install เสร็จแล้วมันจำมี folder `node_modules` ขึ้นมาใน project folder ของเรา มันจะเป็น folder ที่เก็บ code ของ packages ที่เรา install ลงมา ( ⚠️ node_modules เป็น folder ที่เราจะไม่ push ขึ้นไปบน git repository นะ )
- เนื่องจากเราไม่ push node_modules ขึ้นไปบน git repository เวลาเรา clone repository นั้น ๆ ลงมา เราจะต้อง `npm install` เพื่อติดตั้ง packages ที่เกี่ยวข้องใน project นั้น ๆ ก่อนเสมอ ซึ่งมันจะ install packages อะไรบ้างนั้น npm จะไปอ่าน package list จากไฟล์ `packages.json` ของเรา

⚠️ ถ้าใครพิมพ์ npm แล้วไม่เจอ command ให้ทำการ install nodejs ลงในเครื่องคอมเราก่อน [ที่นี่](https://nodejs.org/en/)

<br><hr><br>

## Let's Use It !

เราสามารถที่จะเรียกใช้ Create React App ได้ด้วย npx

🌟 **ข้อควรรู้**

- **npx** เป็นเครื่องมือที่ทำให้เราสามารถที่รัน package ของ node ขึ้นมาได้เลยทันที

ให้เราเปิด Terminal ขึ้นมาแล้วพิมพ์คำสั่ง

`npx create-react-app my-app`

⚠️ ถ้าใครพิมพ์ npx แล้วไม่เจอ command ให้ทำการ install nodejs ลงในเครื่องคอมเราก่อน [ที่นี่](https://nodejs.org/en/)

เมื่อ npx ทำการ Install และ Setup React app ให้เราเสร็จเรียบร้อยแล้ว ให้เรา cd ไปที่ React app folder `my-react-app` ด้วยคำสั่ง `cd my-react-app`

จากนั้นให้เราทำการ run React app ขึ้นมาด้วยคำสั่ง `npm start`

<br><hr><br>

## Import and Export

เวลาเราเขียนโค้ดไปเรื่อย ๆ ไฟล์จะเริ่มใหญ่มาก ทำให้เราไม่สามารถเขียนอยู่ในไฟล์เดียวได้ เราเลยมีความจำเป็นต้องแยกไฟล์ออกมา เพื่อให้ง่ายต่อการดูแล เมื่อเราแยกไฟล์ออกมาแล้วเราจะต้องมีวิธีการที่จะ Import functions อื่น ๆ เข้ามาใช้งาน และ Export functions ต่าง ๆ ไปให้ไฟล์อื่นใช้งาน

**1. Named Import & Export**

```js
// อยู่ในไฟล์ Counter.js

function Counter() {
  return <h1>Counter</h1>
}

export Counter
```

เวลา Import เข้ามาใช้ในไฟล์ App

```js
// อยู่ในไฟล์ App.js
import { Counter } from "./Counter";

function App() {
  return (
    <div className="app-container">
      <Counter />
    </div>
  );
}
```

**2. Module Import & Export**

```js
// อยู่ในไฟล์ Counter.js

function Counter() {
  return <h1>Counter</h1>;
}

export default Counter;
```

```js
// อยู่ในไฟล์ App.js
import Counter from "./Counter";

function App() {
  return (
    <div className="app-container">
      <Counter />
    </div>
  );
}
```

<br><hr><br>

## Exercises 🏅

A) ให้สร้าง Component `GreetingMessage` ที่แสดงข้อความทักทาย ซึ่งข้อความสามารถทักทายแต่ละคนได้

**เงื่อนไข:** สร้างไว้อีก File แล้ว Import เข้ามาใช้ใน App Component

B) ให้สร้าง Component `ProductItem` ที่แสดงข้อมูล Product แตกต่างกันออกไป

ข้อมูล Product มีดังนี้

- title: "XiaoMi Air Purifier"
- description: "Lorem ipsum dolor sit amet."
- price: 500

**เงื่อนไข:** สร้างไว้อีก File แล้ว Import เข้ามาใช้ใน App Component

<br><hr><br>

[Table of Contents](https://github.com/napatwongchr/intro-to-react/blob/main/README.md)
