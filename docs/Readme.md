# Sass Crash Course

> css reset

```sass
*{
    box-sizing: border-box;
    padding: 0;
    margin: 0;
}
```

> sass variable

```sass
$light-color:#f4f4;
```

> install sass globally

```bash
sudo npm i -g sass
```

> to watch sass

```bash
sass --watch scss/style.scss css/style.css
```

> nesting

```sass

.showcase {
  background-color: $primary-color;
  color: #fff;
  height: 600px;
  nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    ul {
      display: flex;
      list-style-type: none;
      li {
        padding: 15px;
      }
    }
  }
}

```

> using `&` in the code

```sass
&-content {
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    img {
      width: 50%;
    }
```

> partials

any file with `_fileName.scss` is a partial file

> imports

```sass
@import 'config';
```

> using % and @extend

```sass
%btn {
  display: inline-block;
  border-radius: 5px;
  padding: 8px 20px;
  margin: 3px;

  &:hover {
    transform: scale(0.95);
  }
}

.btn-primary {
  @extend %btn;
}
.btn-secondary {
  @extend %btn;
}
```

> using conditionals and functions

```sass
@function set-text-color($color) {
  @if (lightness($color) >70) {
    @return #333;
  } @else {
    @return #fff;
  }
}
```

> @ mixings

```sass
@function set-text-color($color) {
  @if (lightness($color) >70) {
    @return #333;
  } @else {
    @return #fff;
  }
}

// set back and text color

@mixin set-background($color) {
  background-color: $color;
  color: set-text-color($color);
}
```

> when using

```sass
.btn-primary {
  @extend %btn;
  @include set-background(lighten($primary-color, 10%));
}
.btn-secondary {
  @extend %btn;
  @include set-background($secondary-color);
}
```

> using loops

```sass
$spaceList: (1, 2, 3, 4, 5);
@each $space in $spaceList {
    // margin
  .m-#{$space} {
    margin: #{$space}rem;
  }
  .my-#{$space} {
    margin: #{$space}rem 0;
  }
// padding
  .p-#{$space} {
    padding: #{$space}rem;
  }
  .py-#{$space} {
    padding: #{$space}rem 0;
  }
}
```

> output

```css
.m-1 {
  margin: 1rem;
}

.my-1 {
  margin: 1rem 0;
}

.p-1 {
  padding: 1rem;
}

.py-1 {
  padding: 1rem 0;
}

.m-2 {
  margin: 2rem;
}

.my-2 {
  margin: 2rem 0;
}

.p-2 {
  padding: 2rem;
}

.py-2 {
  padding: 2rem 0;
}

.m-3 {
  margin: 3rem;
}

.my-3 {
  margin: 3rem 0;
}

.p-3 {
  padding: 3rem;
}

.py-3 {
  padding: 3rem 0;
}

.m-4 {
  margin: 4rem;
}

.my-4 {
  margin: 4rem 0;
}

.p-4 {
  padding: 4rem;
}

.py-4 {
  padding: 4rem 0;
}

.m-5 {
  margin: 5rem;
}

.my-5 {
  margin: 5rem 0;
}

.p-5 {
  padding: 5rem;
}

.py-5 {
  padding: 5rem 0;
}
```

> @media quearies

```sass
@media (max-width: 700px) {
  .showcase {
    height: 400px;
    &-content {
      text-align: center;
      img {
        display: none;
      }
    }
  }
}
```
