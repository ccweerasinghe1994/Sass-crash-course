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
