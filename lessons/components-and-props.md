# Components And Props

สมมุติว่าเรามีโค้ดแบบนี้

```html
<script type="text/babel">
  const rootElement = document.getElementById("root");

  const element = (
    <div className="container">
      <h1>Hello, React !</h1>
      <h1>Hello, Judie !</h1>
      <h1>Hello, World !</h1>
    </div>
  );

  ReactDOM.render(element, rootElement);
</script>
```

เราจะเห็นได้ว่า มีการเขียน Hello ด้วย h1 ซ้ำกันอยู่ มีสิ่งที่เปลี่ยนไปคือ คำข้างหลังคือ React, Judie, World เราสามารถสร้างเป็น Function Component ได้ดังนี้

```js
// Skipped codes

function GreetingMessage(props) {
  return <h1>Hello, {props.name}</h1>;
}

// Skipped codes
```

จากนั้น เราสามารถเรียกใช้ฟังก์ชั่นได้แบบนี้

```js
// Skipped codes

function GreetingMessage(props) {
  return <h1>Hello, {props.name}</h1>;
}

const element = (
  <div className="container">
    {GreetingMessage({ name: "React" })}
    {GreetingMessage({ name: "Judie" })}
    {GreetingMessage({ name: "World" })}
  </div>
);

// Skipped codes
```

เนื่องจาก JSX เราสามารถเขียนให้อยู่ในรูปแบบเหมือนเราเขียน HTML ได้เพื่อความอ่านง่าย สบายตา

```js
// Skipped codes

function GreetingMessage(props) {
  return <h1>Hello, {props.name}</h1>;
}

const element = (
  <div className="container">
    <GreetingMessage name="React" />
    <GreetingMessage name="Judie" />
    <GreetingMessage name="World" />
  </div>
);

// Skipped codes
```

🌟 **แล้วเมื่อไหร่เราควรสร้าง Component หล่ะ ?**

- เมื่อ UI มีการใช้ส่วนนั้นเยอะ ๆ เช่น Button, Panel, Avatar, Etc.
- ถ้า Component นั้นใหญ่เกินไป ยากต่อการโฟกัสสิ่งต่าง ๆ

⚠️ **ข้อควรระวัง**

- **Props** ที่ถูกส่งเข้ามาใน Component นั้น ๆ ไม่ว่าจะเป็น Function หรือ Class **ไม่สามารถเปลี่ยนแปลงได้เสมอ ๆ**

- การแยกออกเป็น Component ควรคำนึงถึงการทำงานที่สัมพันธ์กันของตัวโค้ดด้วย ถ้าเราแยกโค้ดที่ทำงานสัมพันธ์กันออกไปมาก ๆ ทำให้โค้ดเราดูแลรักษาได้ยากขึ้น เวลาเราจะแก้ไขโค้ดเกี่ยวกับสิ่งนั้น ๆ มันทำให้เราต้องกระโดดไปกระโดดมา ทำให้เราต้องใช้สมองในการคิดค้นหาสิ่งต่าง ๆ มากยิ่งขึ้น

- Function ที่ไม่สามารถเปลี่ยนแปลงค่า Input ได้ และจะได้ Output ออกมาเหมือนเดิมเสมอ ๆ เราจะเรียกว่าเป็น **Pure Function**

<br><hr><br>

## Key Takeaway 🌟

- เมื่อเราต้องการ Reuse ของเดิม ๆ ซ้ำ ๆ เราสามารถสร้าง Function Component ได้

- เราจะสร้าง Function Component ได้ก็ต่อเมื่อ UI มีการใช้สิ่งนั้น ๆ ซ้ำไปมา หรือ Component นั้น ๆ มันใหญ่เกินไป **(อย่าลืมเรื่องการแยก Component เราควรคำนึงถึงการทำงานที่สัมพันธ์กันของตัวโค้ดด้วย)**

- **Props จะไม่สามารถเปลี่ยนแปลงค่าได้**

ในเมื่อ UI ของเรามันสามารถที่จะเปลี่ยนแปลงได้ตลอดเวลา แล้วถ้า Props เปลี่ยนค่าไม่ได้เราจะใช้อะไรเพื่อทำให้มันเปลี่ยนค่า ? คำตอบก็คือ **State** ในบทต่อไป

<br><hr><br>

[Table of Contents](https://github.com/napatwongchr/intro-to-react/blob/main/README.md)
