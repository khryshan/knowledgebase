# Patterns

## [**ASPECT RATIO BOX**](https://css-tricks.com/aspect-ratio-boxes/)\*\*\*\*

If we wanna responsive element with ratio 16:9 that we can use css styles below.

```text
.element__wrap {
  position: relative;
  padding-top: 56.25%; // ratio 16:9
}
.element {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
```

a perfect square \(500px × 500px\) `padding-top` of 100%

when we wanna use 16:9 ratio we have to use `padding-top` of 56.25% \(9 / 16 = 0.5625\)

