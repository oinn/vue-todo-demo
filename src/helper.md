## Стили HeaderBlock

```scss
// Знак "@" является ссылкой на /src
@import "@/styles/variables.scss";

.header-block {
  padding: 32px 0 0 0;
  height: 200px;
  display: flex;
  flex-direction: column;

  background: $blue-lighten;

  color: $white;

  &.teal {
    background: $teal-lighten;

    > input {
      border-color: $teal;
    }
  }
}
```