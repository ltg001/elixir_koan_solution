# Elixir 语法合集

[优秀的学习方式](https://github.com/elixirkoans/elixir-koans)
边写边记 记的全不全看心情 23333
具体的请参阅 [官方文档](https://elixir-lang.org/docs.html)

## Equalities

1. 使用 `true` 和 `false` 进行 bool 值的表示
2. 在表达式前使用 `!` 进行否定

    ```elixir
    !true == false
    ```

3. elixir 中的除法十分智能 能整除时是 `int` 否则是 `float`

    ```elixir
    1 == 2 / 2
    ```

## String

1. 使用 "#{ x + y }" 的模式进行插值运算 类似 Python3.6 的 f-String (format string)

    ```elixir
    "1 + 1 = #{1 + 1}" == "1 + 1 = 2"
    ```

2. 使用 `<>` 进行字符串的拼接

    ```elixir
    "hello " <> "world" == "hello world" # 注意hello后有一个空格
    ```

3. 使用 `String.split(string, spliter)` 进行字符串的分割 返回一个列表

    ```elixir
    String.split("hello world", " ") == ["hello", "world"]
    ```

4. 使用替换字符串内容 `String.replace(string, what_to_be_replaced, by_what)`

    ```elixir
    String.replace("goodbye world", "goodbye", "hello") == "hello world"
    ```

5. 包含字符串 `String.contains?(string, what_to_find)`

    ```elixir
    String.contains?("hello world", "hello") == true
    ```

6. 反转字符串

    ```elixir
    String.reverse("ananab") == "banana"
    ```

7. （清理字符串）使用 `String.trim(string)`仅保留第一个可见字符和最后一个可见字符中的部分

    ```elixir
    String.trim("\n hello world \n") == "hello world"
    ```

8. 重复字符串 `String.duplicate(string, times)`

    ```elixir
    String.duplicate("a", 3) == "aaa"
    ```

9. 大写 `String.upcase(string)`

    ```elixir
    String.upcase("hello world") == "HELLO WORLD"
    ```

## Numbers

在 elixir 中和 js 相同 区分值相等和类型相等

- `==` 判断值相等
- `===` 判断严格相等（类型 + 值）

1. int 和 float 对应数值相等

    ```elixir
    1 == 1.0 == true
    ```

2. 除法默认返回为 float 类型

    ```elixir
    2 / 2 === 1.0
    ```

3. 使用 `div(x, y)` 表示整数除法（仅保留整数部分）同理用 `rem(x, y)` 表示取余

    ```elixir
    div(5, 2) == 2
    rem(5, 2) == 1
    ```

4. 乘法中若有 float 类型参与运算则结果为 float 否则为 int

    ```elixir
    2 * 2 === 4
    2 * 2.0 === 4.0
    ```

5. 判断奇偶数

    ```elixir
    Integer.is_odd(3) == true
    Integer.is_even(4) == true
    ```

6. 四舍五入

    ```elixir
    round(1.2) === Float.round(1.2) == false
    # round() 在 kernel 中定义 舍入到最近的整数 总是返回 int 类型
    # Float.round() 在 Float 中定义 接受其他的参数表示精度 返回 float 类型
    #   eg. Float.round(5.5674, 3) == 5.567
    ```

7. 从浮点数中截取整数部分

    ```elixir
    trunc(5.4) == 5
    trunc(-5.4) == -5
    ```

8. 获取一个 int 的每一位

    ```elixir
    Integer.digits(58127) == [5, ,8 , 1, 2, 7]
    ```

9. 从一个列表中拼一个 int

    ```elixir
    Integer.undigits([1, 2, 3, 4]) == 1234
    ```

10. 转成字符串

    ```elixir
    "1234" == Integer.to_string(1234)
    ```

11. 进制转换

    ```elixir
    Integer.parse("2A", 16) == {42, ""} 
    # 将16进制下的 2A 化为10进制下的42
    # 后面的括号作用见下个例子
    ```

## Atoms

## Tuples

## Lists

## Keyword Lists

## Maps

## Map Sets

## Structs

## Sigils

## Pattern Matching

## Function

## Enums

## Processes

## Tasks

## Agents

## Genservers

## Protocols

## Comprehensions