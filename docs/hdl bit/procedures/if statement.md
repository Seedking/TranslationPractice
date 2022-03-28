Always if
---------
An if statement usually creates a 2-to-1 multiplexer, selecting one input if the condition is true, and the other input if the condition is false.

```verilog
always @(*) begin
    if (condition) begin
        out = x;
    end
    else begin
        out = y;
    end
end
```

This is equivalent to using a continuous assignment with a conditional operator:

```verilog
assign out = (condition) ? x : y;
```

However, the procedural if statement provides a new way to make mistakes. The circuit is combinational only if out is always assigned a value.  

A bit of practice
-----------------
Build a 2-to-1 mux that chooses between a and b. Choose b if both `sel_b1` and `sel_b2` are true. Otherwise, choose a. Do the same twice, once using assign statements and once using a procedural if statement.  

|sel_b1|sel_b2|out_assign<br>out_always|
|------|------|------------------------|
|0|0|a|
|0|1|a|
|1|0|a|
|1|1|b|

<!--------------------------------------------------------------------------------------------->


Always 中的 If 语句
---------
if 命令经常用来创造二选一数据选择器，如果条件为 `true` 选择这个 `input` ，如果条件为 `false` 则选择另一个 `input` 。

```verilog
always @(*) begin
    if (condition) begin
        out = x;
    end
    else begin
        out = y;
    end
end
```
这等同于带条件运算符的连续赋值：

```verilog
assign out = (condition) ? x : y;
```

虽然，程序性 if 语句提供了一种犯错误的新方式。只有在 `out` 总是被赋值的情况下电路才是闭合的。

一点练习
--------
开发一个在 a 和 b 之间选择的二选一数据选择器。如果 `sel_b1` and `sel_b2` 都为 `true` 则选择 b ，否则选择 a 。同样的事情做两次，一次使用 `assign` 语句然后一次使用程序性 `if` 语句。

|sel_b1|sel_b2|out_assign<br>out_always|
|------|------|------------------------|
|0|0|a|
|0|1|a|
|1|0|a|
|1|1|b|

!!! note "生词表"
    * selecting v.选择
    * condition n.条件
    * equivalent n.
    * continuous adj.不断地 持续地
    * assignment n.分配 ->赋值
    * continuous assignment 连续赋值
    * conditional adj.有条件的
    * operator n.运算符
    * conditional operator 条件运算符
    * however 虽然
    * procedural adj.程序上的
    * provides v.提供
    * mistakes n.错误
    * circuit n.电路
    * combinational 组合的