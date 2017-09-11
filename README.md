# bemify
sass中的bem

input

``` scss

@include block('a-menu'){
  float: left;
  @include modifier('bigger'){
    transform: scale(1.2);
  }
  @include element('list'){
    background: #000;
    color:#fff;
    @include modifier('blue'){
      background:blue;
      @include element('item'){
        line-height: 1.5;
        @include state('active'){
          border: solid 1px red;
        }
      }
    }
  }
  @include element('item'){
    line-height: 2;
  }
}

```

output

``` css

.a-menu, .a-menu--bigger {
    float: left;
}

.a-menu--bigger {
    transform: scale(1.2);
}

.a-menu__list, .a-menu__list--blue {
    background: #000;
    color: #fff;
}

.a-menu__list--blue {
    background: blue;
}

.a-menu__list--blue .a-menu__list__item {
    line-height: 1.5;
}

.a-menu__list--blue .a-menu__list__item.is-active {
    border: solid 1px red;
}

.a-menu__item {
    line-height: 2;
}


```
