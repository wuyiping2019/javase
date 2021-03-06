# 1 流程控制语句

- 流程控制语句可以分为顺序结构、分支结构、循环结构;
- 顺序结构就是按代码的编写顺序进行执行，写在前面的代码先执行，写在后面的代码后执行，每一行的代码从左到右执行;

## 1.1 分支结构

### 1.1.1 IF语句

- 简单结构

  - 格式：if(关系表达式){语句体;}
  - 当关系表达式为true，则执行语句体；否则，不执行;
  - 语句体没有返回值(scala中语句体有返回值);

- 复杂结构
  
  - 格式：if(关系表达式1){语句体1;} else if(关系表达式2){语句体2;}else{语句体3};
  - 可以包含0个或多个else if;

### 1.1.2 SWITCH语句

- 格式：switch(表达式){case 值1:语句体1;break;case 值2:语句体2;break;default:语句体3;[break;]}
- 注意：表达式的取值可以是byte、short、int、char、枚举和String;
- switch语句存在case穿透现象，当case语句匹配上之后，就会执行该case后面的语句体，如果该语句体后面没有跟break，则会继续执行后续case的语句体直到遇到break语句;总而言之，switch语句只会匹配一次，匹配上之后，就会执行之后的所有语句块直到遇到beak;

## 1.2 循环语句

### 1.2.1 FOR循环

- 格式：for(初始化语句;条件判断语句;条件控制语句){循环体;}
- 初始化语句:开始循环之前对变量进行初始化操作;
- 条件判断语句:判断是否进入循环;
- 条件控制语句:当一次循环结束之后进行的操作;

```java
/**
* 表示开始循环之前对变量i赋值为0
* 进入循环之前判断是否进入循环，首先i=0，i < 10为true,进入循环，执行循环体
* 循环体执行一次之后，执行i++操作，此时i = 2,然后再次判断i < 10为true,再次执行循环体
* 当循环体执行10次之后, i = 10,i < 10为false,则跳出循环
**/
for(int i = 0;i<10;i++){
    循环体;
}
```

### 1.2.2 WHILE循环

- 格式:while(表达式){循环体;}
- 表达式的值为true或false;
- 每次执行循环体之前都对表达式的值进行判断，如果为true,则执行循环体;直到表达式为false,则退出循环;

### 1.2.3 DO WHILE循环

- 格式:do{循环体;}while(表达式);
- 表达式的值为true或false;
- 该循环首先会执行一次循环体,执行完一次之后判断表达式为true or false,如果为true则继续执行循环体,之后每执行一次循环体都会对表达式进行判断,直到表达式的值为false,则退出循环;

### 1.2.3 break/continue关键字

- 一般break;continue;会结合if语句使用;
- break用于在满足某种条件时,提前跳出循环;
- continue用于在满足某种条件时,跳过continue之后循环体的代码,进入到下一次循环,如果是FOR循环则再次根据条件控制语句判断是否开始循环;如果是WHILE语句或DO WHILE语句则再次判断其WHILE后的表达式;  
