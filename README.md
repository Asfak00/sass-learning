# SASS কী?

### Sass এর পুনরূপ :

SASS = <b>S</b>yntactically <b>A</b>wesome <b>S</b>yle <b>S</b>heet.

=> Sass হচ্ছে css এর একটি extension.

Sass ডিজাইন করেছেন Hampton Catlin এবং ডেভেলপ করেছেন Nataile Weizenbaum আর ২০০৬ সালে প্রকাশ করা হয়েছিলো।

### কেন আমরা Sass ব্যবহার করবো

=> Sass এর মধ্যে অনেক extra জিনিস রয়েছে যা দিয়ে খুব সহজে স্টাইল এর কাজ করতে পারবো। আর যেহেতু Sass হচ্ছে css এর একটি extension তাই Sass এর মধ্যে যা কিছু ব্যবহার করা হবে সেটা css রিলেটেড হবে। Sass ব্যবহার করণে আমরা একই style কে বার বার repeat করার প্রয়োজন হয় না। Sass ব্যবহার করে কোডকে Simple করা যাবে ও কোডকে maintable করা যাবে।

# SASS USE

### Sass কীভাবে ব্যবহার করা যায় ?

=> Sass ব্যবহার করতে গেলে আমাদের একটি extension এর প্রয়োজন হবে (vs code) এ সেটা

হচ্ছে ( live Sass compile ).

> আমরা যখন Sass ব্যবহার করবো যাবে ফাইলের extension টি হবে ( style.scss ) আর এই ফাইলকে যখন আমরা html ফাইল এর সাথে link করতে চাইবো তখন আমরা সবসময় যেভাবে style ফাইল link করি ঠিক ওই ভাবে করবো। কিন্তু মনে রাখতে হবে html ফাইলে যখন Sass ফাইল link করবো তখন Sass ফাইলের extension ( .css ) দিবো মানে s দিবো না ।

সবার শেষে Sass ফাইল থেকে style এর আউটপুট পেতে watch sass বলে একটা button থাকবে vs code এর নিচের মেনুবারে ( অবশ্যই যদি আপনি extension টি ইন্সটল করে থাকেন তাহলে ) ওইখানে click করে Sass ফাইলটিকে watch করাতে হবে।

# SASS VARIABLES

আমরা css এ যেরকম variable করে ব্যবহার করতে পারতাম ঠিক তেমনভাবেই আমরা sass এ ও variable ব্যবহার করতে পারবো।
কিন্তু আমরা যখন css এ variable ব্যবহার করতাম তখন এর syntext হতো এরকম

```css
:root {
  --variable_name: value;
}
```

আর যখন Sass এ variable ডিকলেয়ার করবো তখন এর syntext হবে

```scss
$variable_name: value;
```

> variable এর মাধ্যমে একই জিনিস অনেক জায়গায় ব্যবহার করতে পারবো এতে করে কোড repeat করা লাগবে না। আর যখন কোডে কোনো পরিবর্তন করার প্রয়োজন হবে তখন শুধু variable এর মধ্যে পরিবর্তন করলে সব জায়গায় পরিবর্তন হয়ে যাবে।

<b>Official Sass Docs For Variable - </b> https://sass-lang.com/guide/#variables

# Nesting

Nesting শব্দটার মধ্যেই রয়েছে এর অর্থ রয়েছে। nesting এর মাধ্যমে আমরা কোডকে অনেক simple করতে পারবো।

> example how to style a code in CSS

```css
nav {
  margin: 10px;
}

nav ul {
  list-style-type: none;
}

nav ul li {
  display: flex;
  gap: 10px;
}
```

> Now use this example in SASS using nesting

```scss
nav {
  margin: 10px;
  ul {
    list-style-type: none;
    li {
      display: flex;
      gap: 10px;
    }
  }
}
```

### তাহলে বুঝা গেলো যে nesting ব্যবহার করে আমরা কোডকে অনেক simple করে ফেলতে পারবো এবং তা বুঝতেও সুবিধা হবে। আর nesting ব্যাবহার করার ফলে আমাদের কিন্তু বার বার nav nav লিখতে হয় নি এবং কোনো ট্যাগ repeat করতে হয় নি।

<b>Official Sass Docs For Nesting - </b>https://sass-lang.com/guide/#nesting

# Sass এর ফোল্ডার stacture

# Edit your " live sass compile " settings

```json
"liveSassCompile.settings.formats": [
    {
      "format": "compressed",
      "extensionName": ".css",
      "savePath": "/dist"
    }
  ]
```
