# Redux

## Actions

Определение типов действий - namespace: action\_name: status



## Redux или не Redux?

1. Нужно ли множеству других частей приложения знать об этом участке со- стояния или функциональности? Если да, вероятно, это должно быть в хранилище Redux. Если состояние полностью локализовано в компоненте, вы должны оставить его вне хранилища Redux.
2. Будет ли состояние, с которым вы имеете дело, упрощено или луч- ше выражено в Redux? Если вы ради этого берете состояние и действия компонента и переводите их в Redux, то, вероятно, все для себя усложняете, а выгода оказывается незначительной. Но если состояние сложное или довольно детальное, так что Redux упростит его работу, можете включить его в хранилище

