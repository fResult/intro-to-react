# JSX

ความเดิมจากหน้าที่แล้ว เมื่อเราสร้างหน้าเว็บที่ใหญ่มากขึ้นเราก็ยังสามารถใช้ function `React.createElement` เพื่อสร้างหน้า UI บนเว็บได้เหมือนกันครับ

แต่เพื่อความสะดวกสบาย ความอ่านง่าย React เลยคิดของขึ้นมานั่นก็คือ **JSX** ที่เข้ามาช่วยทำให้เราสร้าง elements บนหน้าเว็บได้ อย่างกับเราเขียน HTML ปกติ ไปลองเขียนดูกันดีกว่า

<br><hr><br>

## Using JSX

โค้ดจากหน้าที่แล้ว

```html
<body>
  <div id="root"></div>
  <script>
    const rootElement = document.getElementById("root");
    const element = React.createElement(
      "div",
      { className: "container" },
      React.createElement(
        "h1",
        { className: "hello-react-text" },
        "Hello, React !"
      )
    );
    ReactDOM.render(element, rootElement);
  </script>
</body>
```

เรามา refactor ข้างบนให้เป็น JSX กันดีกว่า

```html
<script>
  const rootElement = document.getElementById("root");
  const element = (
    <div className="container">
      <h1>Hello, React !</h1>
    </div>
  );
  ReactDOM.render(element, rootElement);
</script>
```

ดูง่ายขึ้นมั้ยครับ เราจะรู้สึกเหมือนเราเขียน HTML แบบดั้งเดิม จากนั้นเราลองรันโค้ดดูครับ เราจะเห็นว่ามันเกิด Error อะไรสักอย่างขึ้นมา 😶

แน่นอนครับ ตัว browser มันไม่สามารถอ่าน script ที่เราเขียนด้วย JSX ได้ เพราะฉะนั้นเราจะมีตัวช่วยเราซึ่งก็คือ **Babel** เราจะ link Babel เข้ามาในโปรเจ็คเรา และใส่ `type="text/babel"` เข้าไปใน script tag

```html
...
<script src="https://unpkg.com/@babel/standalone@7.8.3/babel.js"></script>
<script type="text/babel">
  const rootElement = document.getElementById("root");
  const element = (
    <div className="container">
      <h1>Hello, React !</h1>
    </div>
  );
  ReactDOM.render(element, rootElement);
</script>
...
```

เนื่องจาก JSX คือ JavaScript เราสามารถเขียน JavaScript Expression เข้าไปได้

```js
const name = "Judie";
const element = (
  <div className="container">
    <h1>Hello, {name} !</h1>
  </div>
);
```

เราสามารถเปลี่ยนค่าของ className ได้ด้วยแบบนี้

```js
const name = "Judie";
const className = "container-open";
const element = (
  <div className={className}>
    <h1>Hello, {name} !</h1>
  </div>
);
```

เรายังสามารถ spread props เข้าไปใน element div แบบนี้ได้ด้วยนะ

```js
const name = "Judie";
const className = "container-open";

const props = {
  className: "container",
  onClick: () => console.log("Hello, everyone !"),
};

const element = (
  <div className={className} {...props}>
    <h1>Hello, {name} !</h1>
  </div>
);
```

**ถามว่าทำไมต้อง JSX ด้วยหล่ะ ?** 🌟

- JSX เป็นการรวม HTML เข้ากับ JavaScript เพราะ React มีแนวคิดว่าการที่เรารวมโค้ดที่ทำงานสัมพันธ์กัน เข้าด้วยกันมันจะทำให้โค้ดของเราดูแลรักษาง่าย และสมเหตุสมผล มากกว่าการแยก HTML และ JavaScript ออกจากกัน จึงเป็นที่มาของคอนเซ็ปที่เรียกว่า **Components**

- เมื่อเราเขียน HTML ด้วย JavaScript สิ่งที่เราได้มาคือความสามารถต่าง ๆ ของ JavaScript อย่างเต็มที่ ตามตัวอย่างโค้ดด้านบน

- JSX ป้องกัน Injection attacks

<br><hr><br>

## Key Takeaway 🌟

- JSX ทำให้เราสร้าง element ต่าง ๆ บนหน้าเว็บด้วย JavaScript เหมือนราวกับเขียน HTML แบบปกติ

- เราสามารถใช้ JavaScript features ต่าง ๆ ได้เนื่องจาก JSX คือ JavaScript

- JSX มีความดีงามตรงที่ตัวมันรวม HTML กับ JavaScript เข้าด้วยกัน ทำให้โค้ดที่ทำงานสัมพันธ์อยู่ด้วยกัน ทำให้โค้ดของเราสมเหตุสมผล และดูแลรักษาง่ายมากขึ้น

ตอนนี้ทุกคนคงจะเข้าใจ JSX มากขึ้นแล้ว ต่อไปเราจะแนะนำให้รู้จัก **Components และ Props**

<br><hr><br>

[Table of Contents](https://github.com/napatwongchr/intro-to-react/blob/main/README.md)
