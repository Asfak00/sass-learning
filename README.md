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

> আমরা যখন Sass ব্যবহার করবো তখন ফাইলের extension টি হবে ( style.scss ) আর এই ফাইলকে যখন আমরা html ফাইল এর সাথে link করতে চাইবো তখন আমরা সবসময় যেভাবে style ফাইল link করি ঠিক ওই ভাবে করবো। কিন্তু মনে রাখতে হবে html ফাইলে যখন Sass ফাইল link করবো তখন Sass ফাইলের extension ( .css ) দিবো মানে s দিবো না ।

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

# Partials

partial এর মাধ্যমে আমরা কোডকে সেপারেট করতে পারি ছোট ছোট কিছু ফাইলের মাধ্যমে যেটা আমরা পরবর্তীতে যেকোনো জায়গায় ব্যবহার করতে পারবো। partial এর মাধ্যমে আপনি আপনার যেকোনো কোডকে আলাদা ফাইলে রেখে সেখান থেকে import করার মাধ্যমে ব্যবহার করতে পারবেন এতে করে আপনি কোনো কোড তাড়াতাড়ি খুজে পাবেন এবং আপনি কখনো যদি চান কোনো কোডে কিছু পরিবর্তন করতে তাহলে তা খুব সহজেই করতে পারবেন।

### partial ফাইল নাম দেওয়ার নিয়মঃ

```scss
_file_name.scss
```

> উপরে ( _ ) দেওয়া বাধ্যতামুলক যখন আপনি একটি partial ফাইল তৈরি করতে চাচ্ছেন তখন। ( _ ) দেয়ার পর আপনি আপনার partial ফাইলের নাম দিবেন এবং ফাইলের extension হিসেবে আপনি ( .scss ) ব্যবহার করবেন।

### partial ফাইল অ্যাক্সেস করার নিয়মঃ

```scss
@forward "path_name";
```

> উপরে ( @forward ) দিয়েই আপনি আপনার partial ফাইলটি অ্যাক্সেস করতে পারবেন এবং হে অবশ্যই আপনাকে আপনার partial ফাইলের ( path ) টি বলে দিতে হবে যা @forward এর পরে হবে " " এর মধ্যে।

### আরেকটা উপায়ের মাধ্যমে আপনি সবসময় আপনার মেইন sass ফাইলে @forward লিখা থেকে বাচতে পারবেন।

আপনি \_index.scss নামে একটা ফাইল বানাই নিতে পারেন এবং ওই ফাইলের মধ্যে আপনার যত patial ফাইল রয়েছে সবগুলোকে @forward ব্যবহার করে import করে ফেলবেন।
তারপর আপনি আপনার মেইন যে sass ফাইল রয়েছে সেটাতে গিয়ে শুধু ওই \_index.scss ফাইলটি @forward এর মাধ্যমে import করে নিলেই কিন্তু আপনি আপনার সব partial কোড ও ফাইল পেয়ে যাবেন আপনি যেখানে চান সেখানে ব্যবহার করতে পারবেন।

### আর আপনি যদি কোনো partial ফাইল থেকে আলাদা আলাদা করে কিছু import করতে চান তাহলে আপনি যখন ওই partial ফাইলটি import করবেন তখন @forward এর পরিবর্তে @use ব্যবহার করবেন এবং যখন আপনি @use ব্যাবহার করবেন তখন কিন্তু আপনি আলাদা আলদা ভাবে আপনার partial ফাইল থেকে যেকোনো variable, mixing etc অ্যাক্সেস করতে পারবেন। যখন আপনি কোনো একটা জিনিস ওই partial থেকে অ্যাক্সেস করতে যাবেন তখন আপনাকে ওই partial ফাইলের নাম লিখে ( . ) দিতে হবে এবং পরে আপনার ওই কাংকিত ফাইলের অথবা variable or mixing এর নাম লিখতে হবে।

### উদাহরণ

This file make in another folder

```scss
$header_text: white;
$bg_color: red;
```

when I want to use it any file in individually

```scss
@use "./file_location;

body {
  background-color: file_location.$bg_color;
  color: file_location.$header_text;
}
```

<b>Official Sass Docs For Partial - </b>https://sass-lang.com/guide/#partials

<b>Official Sass Docs For Modules - </b>https://sass-lang.com/guide/#modules

# Mixin

mixin এর মধ্যে আমরা কিছু css কোড রাখতে পারবো যা পরবর্তীতে যেকোনো স্টাইলসিটে reuse করতে পারবো। mixin ব্যবহার করলে আমরা একই কোড বার বার লেখার প্রয়োজন নেই। মানে আমরা এমন একটা স্টাইল করতে চাচ্ছি যেটা অনেক জায়গায় ব্যবহার করার প্রয়োজন হতে পারে, এক্ষেত্রে আমরা একই কোড বার বার না লিখে একটি mixin তৈরি করে সেটার মধ্যে রাখতে পারি এবং আমাদের ওই স্টাইলটি যেখানে যেখানে প্রয়োজন ওইখানে এই mixin ব্যবহার করে স্টাইল apply করতে পারবো।

<b>mixin এর আরেকটা বড় সুবিধা হচ্ছে এতে আমরা কোনো প্রপার্টির জন্য ডায়নামিক value আনতে পারবো এবং সেটা mixin এ বসাতে পারবো।</b>

### initialize mixin in sass file

```scss
@mixin mixin_name {
  your_style_here.....
}
```

### use mixin in any stylesheet

```scss
@include mixin_name;
```

> উপরে যেটা উদাহরণ দেখলাম সেটা হচ্ছে নরমাল ভাবে আমরা একটা mixin declear করলাম এবং সেটা একটা স্টাইল ফাইলে ব্যবহার করলাম।

### mixin initialize with dynamic value receive

```scss
@mixin mixin_name($font_size,$text_color) {
  your_style_here.....
}
```

> আমরা যখন mixin এ কোনো parameter receive করতে যাবো তখন $ ( ডলার ) চিহ্ন দেয়ার পর আমাদের parameter যে নামে ধরতে চাই ওই নাম দিবো। এবং আমরা এই parameter আকারে যত খুশি তত parameter গ্রহণ করতে পারবো ডায়নামিক ভাবে।

### mixin use in our stylesheet with given some parameter

```scss
@include mixin_name(10px, red);
```

> মনে রাখতে হবে আমরা যখন mixin এ parameter টি receive করছিলাম তখন যে order এ parameter টিকে receive করেছিলাম ঠিক সেইম order এ আমরা যখন mixin এ value pass করবো তখন value গুলো দিতে হবে এবং value দেয়ার সময় আমাদের $ ( ডলার ) সাইন দিতে হবে না শুধু value টি দিলেই হবে।

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

</br>

# Sass এর ফোল্ডার stacture

### for small project

<ul>
 <li><b>_base.scss</b> -> (boiler plate codes) can includes reset, variables, mixins and utility classes.</li>
 <li><b>_layout.scss</b> -> layout such as container, grid systems etc.</li>
 <li><b>_component.scss</b> -> reusable things like buttons, cards, navbar etc.</li>
 <li><b>main.scss</b> -> it should ONLY contain the imports from other files.</li>

</ul>

### for a medium to large project follow 7-1 pattern (7 folders 1 file)

<ul>
 <li><b>SASS folder</b>
 <ul>
<li>  <b>abstracts / utilities folder</b></li>
  <ul>
  <li><b>_index.scss </b>-> forwarding all others file in this folder</li>

  <li><b>_variables.scss</b></li>

  <li><b>_functions.scss</b></li>

  <li><b>_mixins.scss</b></li>

  </ul>
  <li>  <b>abstracts / utilities folder</b>

  <ul>
  <li><b>_index.scss </b>-> forwarding all others file in this folder</li>

  <li><b>_reset.scss</b></li>

  <li><b>_typography.scss</b></li>
  </ul></li>

   <li>  <b>components/modules folder
</b>

  <ul>
  <li><b>_index.scss</b> -> forwarding all others file in this folder
</li>

  <li><b>_buttons.scss
</b></li>

  <li><b>_slider.scss</b></li>
  <li><b>_cards.scss</b></li>
  <li><b>_navbar.scss</b></li>
  </ul></li>

   <li>  <b>layout folder</b>

  <ul>
  <li><b>_index.scss</b> -> forwarding all others file in this folder</li>

  <li><b>_navigation.scss</b></li>

  <li><b>_grid.scss</b></li>
  <li><b>_header.scss</b></li>
  <li><b>_footer.scss</b></li>
  <li><b>_sidebar.scss</b></li>
  <li><b>_forms.scss</b></li>
  </ul></li>

   <li>  <b>pages folder</b>

  <ul>
  <li><b>_index.scss</b> -> forwarding all others file in this folder</li>

  <li><b>_home.scss</b></li>

  <li><b>_contact.scss</b></li>
  <li><b>_about.scss</b></li>
  <li><b>_courses.scss</b></li>

  </ul></li>

   <li>  <b>themes folder</b>

  <ul>
  <li><b>_index.scss</b> -> forwarding all others file in this folder</li>
  <li><b>_theme.scss</b></li>
  <li><b>_admin.scss</b></li>
  </ul></li>

   <li>  <b>vendors folder</b>

  <ul>
  <li><b>_index.scss</b>_index.scss -> forwarding all others file in this folder</li>
  <li><b>_bootstrap.scss</b></li>
  <li><b>_jquery-ui.scss</b></li>
  </ul></li>
 </ul>
 </li>

 <li><b>main.scss file</b></li>
</ul>
