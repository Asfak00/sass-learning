# SASS কী?

### Sass এর পুনরূপ :

SASS = <b>S</b>yntactically <b>A</b>wesome <b>S</b>yle <b>S</b>heet.

=> Sass হচ্ছে css এর একটি extension.

Sass ডিজাইন করেছেন Hampton Catlin এবং ডেভেলপ করেছেন Nataile Weizenbaum আর ২০০৬ সালে প্রকাশ করা হয়েছিলো।

### কেন আমরা Sass ব্যবহার করবো

=> Sass এর মধ্যে অনেক extra জিনিস রয়েছে যা দিয়ে খুব সহজে স্টাইল এর কাজ করতে পারবো। আর যেহেতু Sass হচ্ছে css এর একটি extension তাই Sass এর মধ্যে যা কিছু ব্যবহার করা হবে সেটা sass রিলেটেড হবে। Sass ব্যবহার করণে আমরা একই style কে পার যার repeat করার বিয়োজন হয় না। Sass ব্যবহার করে কোডকে Simple করবে ও কোডকে maintable করবে।

# SASS USE

### Sass কীভাবে ব্যবহার করা যায় ?

=> Sass ব্যবহার করতে গেলে আমাদের একটি extension এর প্রয়োজন হবে (vs code) এ সেটা

হচ্ছে ( live Sass compile ).

> যে আমরা যখন Sass ব্যবহার করবো তখন মাইলের extension টি হবে ( style.scss ) আর এই ফাইলকে যখন আমরা html ফাইল এর সাথে link করতে চাইলো তখন সবসময় না সাধারণভাবে আমরা যেভাবে style ফাইল link পারি ঠিক ওই ভাবে করবো। কিন্তু মনে রাখতে হবে html ফাইলে যখন Sass ফাইল link করবো তখন Sass ফাইলের extension .css দিবো মানে s দিবো না ।

সবার শেষে Sass ফাইল থেকে style এর আউটপুট পেতে watch sass বলে একটা button থাকবে vs code এর নিচের মেনুবারে ওইখানে click করে Sass ফাইলটিকে watch করাতে হবে।

# SASS VARIABLES

আমরা css এ যেরকম variable করে ব্যবহার করতে পারতাম ঠিক তেমনভাবেই আমরা পর sass এ ও variable ব্যবহার করতে পারবো।
কিন্তু যখন css এ variable ব্যবহার করতাম তখন এর syntext হতো এরকম

```css
:root {
    --variable name: value;
};
```

আর যখন Sass এ variable ডিকলেয়ার করবো তখন এর syntext হবে

```scss
$variable-name: value;
```

> variable এর মাধ্যমে একই জিনিস অনেক জায়গায় ব্যবহার করতে পারবো এতে করে কোড repeat করা লাগবে না। আর যখন কোডে কোনো পরিবর্তন করার প্রয়োজন হবে তখন শুধু variable এর মধ্যে পরিবর্তন করলে সব জায়গায় পরিবর্তন করলে হয়ে যাবে।

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

### তাহলে বুঝা গেলো যে nesting ব্যবহার করে আমরা কোডকে অনেক simple করে ফেলতে পারবো এবং তা বুঝতেও সুবিধা হবে।
