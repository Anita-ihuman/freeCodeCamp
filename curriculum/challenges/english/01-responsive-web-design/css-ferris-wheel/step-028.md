---
id: 6169b1357fcb701bb5efc619
title: Step 28
challengeType: 0
dashedName: step-28
---

# --description--

Create a new `25%` selector between your `0%` and `50%` selectors. Give this new selector the `background-color` property set to `yellow`.

# --hints--

You should create a new `25%` selector in your `@keyframes cabins` rule.

```js
const rules = new __helpers.CSSHelp(document).getCSSRules('keyframes')?.[1]?.cssRules;
assert(rules?.[0]?.keyText === '25%' || rules?.[1]?.keyText === '25%' || rules?.[2]?.keyText === '25%' || rules?.[3]?.keyText === '25%');
```

Your `25%` selector should be between your `0%` and `50%` selectors.

```js
assert(new __helpers.CSSHelp(document).getCSSRules('keyframes')?.[1]?.cssRules?.[1]?.keyText === '25%');
```

Your `25%` selector should have a `background-color` property set to `yellow`.

```js
assert(new __helpers.CSSHelp(document).getCSSRules('keyframes')?.[1]?.cssRules?.[1]?.style?.backgroundColor === 'yellow');
```

# --seed--

## --seed-contents--

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title> Learn CSS Animations by Building a Ferris Wheel</title>
    <link rel="stylesheet" href="./styles.css">
  </head>
  <body>
    <div class="wheel">
      <span class="line"></span>
      <span class="line"></span>
      <span class="line"></span>
      <span class="line"></span>
      <span class="line"></span>
      <span class="line"></span>

      <div class="cabin"></div>
      <div class="cabin"></div>
      <div class="cabin"></div>
      <div class="cabin"></div>
      <div class="cabin"></div>
      <div class="cabin"></div>
    </div>
  </body>
</html>
```

```css
.wheel {
  border: 2px solid black;
  border-radius: 50%;
  margin-left: 50px;
  position: absolute;
  height: 55vw;
  width: 55vw;
  max-width: 500px;
  max-height: 500px;
  animation-name: wheel;
  animation-duration: 10s;
  animation-iteration-count: infinite;
  animation-timing-function: linear;
}

.line {
  background-color: black;
  width: 50%;
  height: 2px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform-origin: 0% 0%;
}

.line:nth-of-type(2) {
  transform: rotate(60deg);
}
.line:nth-of-type(3) {
  transform: rotate(120deg);
}
.line:nth-of-type(4) {
  transform: rotate(180deg);
}
.line:nth-of-type(5) {
  transform: rotate(240deg);
}
.line:nth-of-type(6) {
  transform: rotate(300deg);
}

.cabin {
  background-color: red;
  width: 20%;
  height: 20%;
  position: absolute;
  border: 2px solid;
  transform-origin: 50% 0%;
  animation: cabins 10s ease-in-out infinite;
}

.cabin:nth-of-type(1) {
  right: -8.5%;
  top: 50%;
}
.cabin:nth-of-type(2) {
  right: 17%;
  top: 93.5%;
}
.cabin:nth-of-type(3) {
  right: 67%;
  top: 93.5%;
}
.cabin:nth-of-type(4) {
  left: -8.5%;
  top: 50%;
}
.cabin:nth-of-type(5) {
  left: 17%;
  top: 7%;
}
.cabin:nth-of-type(6) {
  right: 17%;
  top: 7%;
}

@keyframes wheel {
   0% {
     transform: rotate(0deg);
   }
   100% {
     transform: rotate(360deg);
   }
}

--fcc-editable-region--
@keyframes cabins {
  0% {
    transform: rotate(0deg);
  }
  50% {
    background-color: purple;
  }
  100% {
    transform: rotate(-360deg);
  }
}
--fcc-editable-region--
```