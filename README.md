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

<b>Official Sass Docs For Mixing - </b>https://sass-lang.com/guide/#mixins

# Extend & Inheritance

Inheritance এর মাধ্যমে আমরা কোনো সিলেক্টরকে অন্য কোনো সিলেক্টরে ব্যবহার করতে পারবো। এবং তা করার জন্য আমাদের সাহায্য করতে @extend নামর একটা keyword. extend এর মাধ্যমেই আমরা কোনো সিলেক্টরকে অন্য কোনো সিলেক্টরের মধ্যে inheritance করতে পারবো। ( <b>হয়তো এগুলো খুব ঝামেলার লাগছে আপনাদের, চিন্তা করবেন না নিচে উদাহরণের মাধ্যমে সব সহজ করে দিবো</b>)

### কিভাবে কোনো সিলেক্টরকে অন্য কোনো সিলেক্টরে inheritance করতে হয় সেটা নিচে দেখানো হয়েছে

> সাধারণ ভাবে একটা সিলেক্ট দরে কিছু স্টাইল করা হয়েছে

```scss
.name_input {
  border: 1px solid gray;
  outline: none;
  border-radius: 10px;
  padding: 0.5rem 1rem;
}
```

এখন এই সিলেক্টরটি অন্য একটি সিলেক্টরের মধ্যে inheritance করা হবে

> অন্য আরেকটা সিলেক্টরে "name_input" নামে সিলেক্টরটি extend করা হলো

```scss
.email_input {
  @extend .name_input;
  background-color: purple;
}
```

> উপরে আমরা একটি সিলেক্টরকে অন্য আরেকটি সিলেক্টরে extend করলাম @extend keyword এর মাধ্যমে। এবং আপনারা অবশ্যই দেখেছেন যে আমি .email_input এ আরেকটা সিলেক্টর extend করার পরও আরো property যুক্ত করেছি, হে আপনিও চাইলে কোনো সিলেক্টর extend করার পরও আরো property যুক্ত করতে পারবেন।

<b>Official Sass Docs For Inheritance - </b>https://sass-lang.com/guide/#inheritance

# Conditional Control Statement

Conditional Statement বলতে বুঝানো হয়েছে ( if, else if, else ) এইগুলাকে। আমরা ইতিমধ্যে এগুলো সম্পর্কে JS থেকে জেনে এসেছি, তাই আমরা জানি যে এগুলা কিভাবে কাজ করে।

> আমরা JS এর মধ্যে যেভাবে if, else ব্যবহার করতাম ঠিক ওইভাবেই Sass এ এগুলা ব্যবহার করতে পারবো শুধু Sass এ আমাদের @if, @else এইভাবে ব্যবহার করতে হবে।

### তাহলে একটি উদাহরণ দেখা যাক কিভাবে if,else Sass এ ব্যবহার করা হয়

> আমরা প্রথমে একটা mixin তৈরি করে নিচ্ছি এবং ওই mixin একটি value receive করবে। আর আমরা এই mixin এর মধ্যেই if, else ব্যবহার করবো।

```scss
@mixin setFontSize($value) {
  @if ($value == "small") {
    font-size: 10px;
  } @else if($value == "medium") {
    font-size: 20px;
  } @else if($value == "large") {
    font-size: 40px;
  } @else {
    font-size: 5px;
  }
}
```

> উপরে আমরা condition এর মাধ্যমে বলেছি যে আমাদের value সমান সমান যদি small, medium, large কোনোটি হয় তাহলে আমরা যে কাজগুলো করতে বলেছি ওই কাজ করবে ( মানে ফন্ট সাইজ ছোট অথবা বড় করবে )। আর যদি কোনো value দেওয়া না হয় তাহলে আমাদের else কাজ করবে। এভাবে আমরা if, else ব্যবহার করে যেকোনো condition চেক করতে পারবো। আমি তো শুধু font size দিয়ে উদাহরণ দেখালাম কিন্তু এই if, else আপনি যেকোনো condition এ ব্যবহার করতে পারবেন।

<b>Official Sass Docs For if, else condition - </b><b>Official Sass Docs For Partial - </b>https://sass-lang.com/guide/#partials

# For & While Loop

আমরা যদি JS শিখে থাকি তাহলে অবশ্যই আমরা For Loop এবং While Loop সম্পর্কে জানা হয়ে গেছে যে এগুলা কি কাজ করে।
কিন্তু আমরা যখন এই Loop গুলো Sass এ ব্যবহার করবো তখন সবকিছুই ঠিক থাকবে শুধু Stacture টি পরিবর্তন হবে। আর এটা For Loop ও While Loop এর ক্ষেত্রে হবে।

### For Loop Stacture In Sass

```scss
@for %x from 1 through 12 {
  // logic here
}
```

> উপরে আমরা যে @for দিয়েছি সেটা হচ্ছে For loop শুরু করার keyword এর পরে আমরা যে $x দিয়েছি সেটা হচ্ছে একটি variable এবং আমরা এই variable এর মাধ্যমে বুঝতে পারবো যে আমাদের loop টি কত সংখ্যায় আসছে তারপর আমরা যে 1 through 12 লিখলাম এর মানে হচ্ছে আমরা বলছি যে আমাদের loop টি 1 থেকে 12 পর্যন্ত চালাউ, এখানে আমরা আরেকটা শব্দ ব্যাবহার করতে পারতাম through এর বদলে সেটা হচ্ছে To আর এটা যদি ব্যবহার করতাম তাহলে আমাদের loop টি 1 থেকে 11 পর্যন্ত চলত ( মানে এক কম চলত )। যার জন্য আমরা যদি চাই যে আমাদের loop আমরা যা সংখ্যা দিবো একবারে ওই সংখ্যা পর্যন্ত চলবে তাহলে আমরা through ব্যবহার করতে পারি আর যদি চাই যে এক কম চলবে তাহলে আমরা To ব্যবহার করতে পারি।

### While Loop Stacture In Sass

```scss
// declear a variable before write while loop
$x: 1;

@while $x < 13 {
  // logic here

  // increment variable data
  $x: $x + 1;
}
```

> উপরে আমরা প্রথমে একটা variable ডিক্লেয়ার করলাম। পরে আমাদের while loop শুরু করলাম। এবং সেইম for loop এর মত প্রথমে একটা @while নামে keyword দিলাম পরে আমাদের সেই ডিক্লেয়ার করা variable টি দিলাম এবং operator এর মাধ্যমে বলে দিলাম যে 13 পর্যন্ত চলবে আমদের loop টি কিন্তু শুরু হবে কত থেকে? হে, শুরু হবে ( $x ) নামের variable এ যত value দেয়া থাকবে তত থেকে। এখন আমরা তো আমাদের loop চালালাম কিন্তু loop এক এক করে বাড়বে? উত্তর না। কারণ আমরা এখনও ওই কোডটি লেখি নি। আর ওই কোডটি আমরা while loop এর মধ্যে নিচে লেখবো আমাদের সব logic পরে। আর সেটা stacture এ দেখানো হয়েছে।

# Map & @each

@each এটা সেইম loop এর মত কাজ করে। মানে আপনি @each initialize করলেন এবং একটা কাজ চালালেন সেটা কিন্তু loop এর মত একটি একটি করতে সব করে দেয়। নিচের উদাহরণ এর মাধ্যমে clear হতে পারবেন।

### উদাহরণ

```scss
@each $colors in blue, red, green {
  .#{$colors}-text {
    color: $colors;
  }
}
```

### html এ class নাম সেট করা হচ্ছে

```html
<h1 class="red-text">Mapping & @each</h1>
<h2 class="blue-text">Mapping & @each</h2>
<h3 class="green-text">Mapping & @each</h3>
```

> উপরে আমরা @each যেটা হচ্ছে keyword এবং তার পরে একটা variable নাম দিলাম ( যেকোনো নাম হতে পারে আপনার ইচ্ছা )। তারপর in লিখতে হবে এবং এর পরে আপনি আপনার ইচ্ছা মত value দিবেন। এখন সেটা হতে পারে উদাহরণ এর মত color অথবা text-size অথবা অন্য কিছু। এরপর নিচের লাইনে আমরা .# দিবো এবং {} এর ভিতরে আমরা আমাদের variable নামটা দিবো ( যেটা @each এর পাশে দিয়েছিলাম ) এরপর - দিয়ে আমাদের ক্লাসের নামটা শেষ করবো। এখানে আসলে আমরা একটা dynamic ক্লাসের নাম সেট করতেছি যেটা আমাদের দেয়া value থেকে আসবে। এবং এর পরে আমরা {} দিয়ে যেভাবে css কোড লিখি ওইভাবে আমাদের value অনুসারে প্রপার্টি দিবো। এবং প্রপার্টি এর value টা dynamic থাকবে মানে ওই value এর জায়গায় আমরা আমাদের variable এর নাম দিয়ে দিবো তাহলে ওইটা dynamic হয়ে যাবে। তারপর নিচের html এ যেভাবে দেখানো হয়েছে ওইভাবে আমরা আমাদের html ফাইলে যেকোনো element এর class সেট করে দিলেই আমাদের কোডটি কাজ করবে, মানে class নামটা হবে {$colors}-text মত সেইম আর colors কোন value আসবে সেটা তো আপনি জানেন কারণ আপনি value সেট করেছেন আর ওই value আনুসারে ওই জায়গায় dynamic নাম আসবে।

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
