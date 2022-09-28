# <p id="top" align="center">Sass Course Assignments</p>

Current Progress : <p>![](https://progress-bar.dev/100/?scale=100&width=1100)</p>
<hr>

- ### Table of Contents:
    - [Week 1: Introduction and fundamentals](#week-1-introduction-and-fundamentals---from-1-to-10)
    - [Week 2: Mixin and Loops](#week-2-mixin-and-loops---from-11-to-19)
   
<hr>


### Week 1: Introduction and Fundamentals - from 1 to 10
#### For Lessons 01 To 06
##### Assignment 1 
```scss
.content {
  > .box {
    padding: 15px;
    > .title {
      font-size: 18px;
    }
  }
  .cat {
    padding: 15px;
  }
  &.premium {
    &:before {
      content: "Premium Box";
    }
    &:hover {
      background-color: #eee;
    }
  }
}
```

##### Assignment 2
```scss
.class > {
  .child {
    padding: 10px;
  }
}

.class {
  > .child {
    padding: 10px;
  }
}

.class {
  > {
    .child {
      padding: 10px;
    }
  }
}
```

##### Assignment 3 
```scss
.class {
  font: {
    weight: bold;
    size: 20px;
  }
}
```

##### Assignment 4 
```scss
.parent {
  // & means .parent then + .sibling
  & + .sibling {
    // margin: auto then used the brackets to set margin-top to 10px
    margin: auto {
      top: 10px;
    }
    // & means .parent + .sibling  then ~ .last
    & ~ .last {
      padding: 10px;
    }
  }
}
```

##### Assignment 5 
```scss
.widget {
  background-color: white;
  padding: 20px;
}
.main-border {
  border: 1px solid #ccc;
}
.my-class {
  @extend .main-border;
  @extend .widget;
  font-weight: bold;
  margin: 20px auto;
}
```

##### Assignment 6 
```scss
%widget {
  background-color: white;
  padding: 20px;
}
%main-border {
  border: 1px solid #ccc;
}
.my-class {
  @extend %main-border;
  @extend %widget;
  font-weight: bold;
  margin: 20px auto;
}
```

##### Assignment 7 
```scss
%font-size {
  font-size: 20px;
}
.box {
  p {
    @extend %font-size;
  }
  h2 {
    @extend %font-size;
  }
}
@media (max-width: 575px) {
  %font-size {
    font-size: 16px;
  }
  .box {
    %font-weight {
      font-weight: bold;
    }
    p {
      @extend %font-weight;
    }
    h2 {
      span {
        @extend %font-weight;
      }
    }
  }
}
```

##### Assignment 8 
```scss
// The Code
// Do Not Edit Here
$red: #e91e63;
$green: #009688;

// Add What You Want Here
$link-color: $green;
$link-hover: $red;
// Do Not Edit Here
.box a {
  color: $link-color;
  &:hover {
    color: $link-hover;
  }
}
```
##### Assignment 9
```scss
// Import global rules
@use "sass/Layout/footer";
@use "sass/Layout/header";

@use "sass/Helpers/vars" as *;
@use "sass/Helpers/functions";
```
##### Assignment 10
```scss
.box {
  font-size: 20px;
  &-holder {
    width: 1000px;
    &-content {
      margin: auto;
    }
  }
}
```

#### For Lessons 07 To 10
##### Assignment 1
```scss
// division operatiion (/) is deprecated and will be removed in future version of sass 2.0 so we will use math.div() instead

@use "sass:math";

$main: "school";
$child: "box";
$language: "en"; // English
$gap: 20px;

.#{$main} {
  padding: $gap;
  direction: if($language == "en", ltr, rtl);
  margin-left: $gap;
  &-box{
    padding: math.div($gap, 2);
  }
  &:hover &-box{
    background-color: red;
  }
}
```

##### Assignment 2
```scss
// SASS Code
$main-color: red;
$alt-color: blue;

// Needed Output
/* Theme Version: 1.0 */
/* Website Theme Main Color Is: #{$main-color} */
/* Website Theme Alternate Color Is: #{$alt-color} */
```

##### Assignment 3
```scss
// SASS Code
$number: 10;
$number: 8;
$number: 5;

.class {
  color: if($number > 8, blue, if($number > 5, green, red));
}
```

##### Assignment 4
```scss
// SASS Code
$number: 10;
$color: red;
$theme: "light";

// Write If Condition Code Here
@if ($number > 10 and $color == red and not ($theme == "dark")) {
  .class {
    color: blue;
  }
}
```

##### Assignment 5
```scss
// SASS Code
$number: 10;

// Output
@if ($number >= 8) {
  @if ($number == 9) {
    .box {
      background-color: #eee;
    }
  } @else if ($number == 10) {
    .box {
      background-color: #eee;
      text-align: center;
    }
  } 
}
```
<hr>

### Week 2: Mixin and Loops - from 11 to 19

#### For Lessons 11 To 15

##### Assignment 1
```scss
@mixin arrow($direction) {
  @if ($direction == "right") {
    content: "";
    position: absolute;
    border: 20px solid transparent;
    top: 50%;
    transform: translateY(-50%);
    right: -40px;
    border-left-color: red;
  } @else if($direction == "left") {
    content: "";
    position: absolute;
    border: 20px solid transparent;
    top: 50%;
    transform: translateY(-50%);
    left: -40px;
    border-right-color: red;
  } @else if($direction == "top") {
    content: "";
    position: absolute;
    border: 20px solid transparent;
    top: -40px;
    left: 50%;
    transform: translateX(-50%);
    border-bottom-color: red;
  } @else if($direction == "bottom") {
    content: "";
    position: absolute;
    border: 20px solid transparent;
    left: 50%;
    transform: translateX(-50%);
    bottom: -40px;
    border-top-color: red;
  }
}

.element {
  &:before {
    @include arrow("left");
  }
}
```

##### Assignment 2
```scss
$grid_cols: 16;
@for $i from 1 through $grid_cols {
  .col-#{$i} {
    width: percentage($i/$grid_cols);
  }
}
```

##### Assignment 3
```scss
$names: "books" 20px red 18, "games" 30px green 18, "dvds" 20px blue;

@each $name, $padding, $color, $font_size in $names {
  .#{$name} {
    padding: $padding;
    font-size: if($font_size == null, 16px, #{$font_size}px);
    border-bottom: 2px solid $color;
    color: #444;
  }
}
```

##### Assignment 4
```scss
$init: 1;
@while $init<=5 {
  .circle-#{$init * 100} {
    width: $init * 100px;
    height: $init * 100px;
    border-radius: #{math.div($init * 100, 2)}px;
  }
  $init: $init + 1;
}
```

##### Assignment 5
```scss
$init: 1;
@for $i from $init through 5 {
  .circle-#{$init * 100} {
    width: $init * 100px;
    height: $init * 100px;
    border-radius: #{math.div($init * 100, 2)}px;
  }
  $init: $init + 1;
}
```

##### Assignment 6
```scss
// Write Mixin Code Here
@mixin placeholder {
  &.placeholder {
    @content;
  }
  &:-moz-placeholder {
    @content;
  }
  &::-moz-placeholder {
    @content;
  }
  &:-ms-input-placeholder {
    @content;
  }
  &::-webkit-input-placeholder {
    @content;
  }
}

// Using
textarea {
  @include placeholder {
    color: #777;
  }
}
```

##### Assignment 7
```scss
// Write Mixin Code Here
@mixin flex-center($width...) {
  display: flex;
  justify-content: center;
  align-items: center;
  width: if(length($width) > 0, nth($width, 1) , 400px); // nth($width, 1) returns the first argument something like $width[0]
}

// Using
.box-one {
  @include flex-center(400px);
}
.box-two {
  @include flex-center;
}
```

#### For Lessons 16 To 19

##### Assignment 1
```scss
$num: 2;
$start: 100;
$steps: 5;

@function double($size) {
  @return $size * $num;
}

$i: 1;
@while $i < math.pow(2, $steps) {
  .box-#{$i*$start} {
    width: #{$i * $start}px;
    height: #{double($i * $start)}px;
  }
  $i: $i * 2;
}
```

##### Assignment 2
```scss
@function get-total($values...) {
  $total: 0;
  @each $value in $values {
    $total: $total + $value;
  }
  @return $total;
}

.box {
  top: get-total(100, 50, 20);
  right: get-total(100, 50);
}
```


// ALHAMDULILAH
