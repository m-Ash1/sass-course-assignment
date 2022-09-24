# <p id="top" align="center">Sass Course Assignments</p>

Current Progress : <p>![](https://progress-bar.dev/0/?scale=100&width=1100)</p>
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
> To be added

<hr>

### Week 2: Mixin and Loops - from 11 to 19
> To be added



