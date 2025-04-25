# ArithmeticUtils 类技术文档

## 1. 类概述
`ArithmeticUtils` 是一个用于高精度数学运算的工具类，基于 `BigDecimal` 实现，提供了精确的加法、减法、乘法、除法、四舍五入、取余数和比较大小等操作。该工具类适用于需要高精度计算的场景，如金融计算、科学计算等。

## 2. 方法说明

### 2.1 精确加法
#### 2.1.1 加法（`double` 参数）
```java
public static double add(double v1, double v2)
```
- **功能**：提供精确的加法运算。
- **参数**：
    - `v1`：被加数（`double` 类型）。
    - `v2`：加数（`double` 类型）。
- **返回值**：两个参数的和（`double` 类型）。
- **使用示例**：
  ```java
  double result = ArithmeticUtils.add(1.23, 4.56); // 结果为 5.79
  ```

#### 2.1.2 加法（`String` 参数）
```java
public static BigDecimal add(String v1, String v2)
```
- **功能**：提供精确的加法运算。
- **参数**：
    - `v1`：被加数（`String` 类型）。
    - `v2`：加数（`String` 类型）。
- **返回值**：两个参数的和（`BigDecimal` 类型）。
- **使用示例**：
  ```java
  BigDecimal result = ArithmeticUtils.add("1.23", "4.56"); // 结果为 5.79
  ```

#### 2.1.3 加法（带精度控制）
```java
public static String add(String v1, String v2, int scale)
```
- **功能**：提供精确的加法运算，并指定结果的小数位数。
- **参数**：
    - `v1`：被加数（`String` 类型）。
    - `v2`：加数（`String` 类型）。
    - `scale`：结果保留的小数位数。
- **返回值**：两个参数的和（`String` 类型）。
- **使用示例**：
  ```java
  String result = ArithmeticUtils.add("1.2345", "4.5678", 2); // 结果为 "5.80"
  ```

### 2.2 精确减法
#### 2.2.1 减法（`double` 参数）
```java
public static double sub(double v1, double v2)
```
- **功能**：提供精确的减法运算。
- **参数**：
    - `v1`：被减数（`double` 类型）。
    - `v2`：减数（`double` 类型）。
- **返回值**：两个参数的差（`double` 类型）。
- **使用示例**：
  ```java
  double result = ArithmeticUtils.sub(5.79, 4.56); // 结果为 1.23
  ```

#### 2.2.2 减法（`String` 参数）
```java
public static BigDecimal sub(String v1, String v2)
```
- **功能**：提供精确的减法运算。
- **参数**：
    - `v1`：被减数（`String` 类型）。
    - `v2`：减数（`String` 类型）。
- **返回值**：两个参数的差（`BigDecimal` 类型）。
- **使用示例**：
  ```java
  BigDecimal result = ArithmeticUtils.sub("5.79", "4.56"); // 结果为 1.23
  ```

#### 2.2.3 减法（带精度控制）
```java
public static String sub(String v1, String v2, int scale)
```
- **功能**：提供精确的减法运算，并指定结果的小数位数。
- **参数**：
    - `v1`：被减数（`String` 类型）。
    - `v2`：减数（`String` 类型）。
    - `scale`：结果保留的小数位数。
- **返回值**：两个参数的差（`String` 类型）。
- **使用示例**：
  ```java
  String result = ArithmeticUtils.sub("5.79", "4.56", 2); // 结果为 "1.23"
  ```

### 2.3 精确乘法
#### 2.3.1 乘法（`double` 参数）
```java
public static double mul(double v1, double v2)
```
- **功能**：提供精确的乘法运算。
- **参数**：
    - `v1`：被乘数（`double` 类型）。
    - `v2`：乘数（`double` 类型）。
- **返回值**：两个参数的积（`double` 类型）。
- **使用示例**：
  ```java
  double result = ArithmeticUtils.mul(2.5, 4.0); // 结果为 10.0
  ```

#### 2.3.2 乘法（`String` 参数）
```java
public static BigDecimal mul(String v1, String v2)
```
- **功能**：提供精确的乘法运算。
- **参数**：
    - `v1`：被乘数（`String` 类型）。
    - `v2`：乘数（`String` 类型）。
- **返回值**：两个参数的积（`BigDecimal` 类型）。
- **使用示例**：
  ```java
  BigDecimal result = ArithmeticUtils.mul("2.5", "4.0"); // 结果为 10.0
  ```

#### 2.3.3 乘法（带精度控制）
```java
public static double mul(double v1, double v2, int scale)
```
- **功能**：提供精确的乘法运算，并指定结果的小数位数。
- **参数**：
    - `v1`：被乘数（`double` 类型）。
    - `v2`：乘数（`double` 类型）。
    - `scale`：结果保留的小数位数。
- **返回值**：两个参数的积（`double` 类型）。
- **使用示例**：
  ```java
  double result = ArithmeticUtils.mul(2.5, 4.0, 2); // 结果为 10.00
  ```

#### 2.3.4 乘法（带精度控制，`String` 参数）
```java
public static String mul(String v1, String v2, int scale)
```
- **功能**：提供精确的乘法运算，并指定结果的小数位数。
- **参数**：
    - `v1`：被乘数（`String` 类型）。
    - `v2`：乘数（`String` 类型）。
    - `scale`：结果保留的小数位数。
- **返回值**：两个参数的积（`String` 类型）。
- **使用示例**：
  ```java
  String result = ArithmeticUtils.mul("2.5", "4.0", 2); // 结果为 "10.00"
  ```

### 2.4 精确除法
#### 2.4.1 除法（默认精度）
```java
public static double div(double v1, double v2)
```
- **功能**：提供精确的除法运算，精度默认为 10 位小数。
- **参数**：
    - `v1`：被除数（`double` 类型）。
    - `v2`：除数（`double` 类型）。
- **返回值**：两个参数的商（`double` 类型）。
- **使用示例**：
  ```java
  double result = ArithmeticUtils.div(10.0, 3.0); // 结果为 3.3333333333
  ```

#### 2.4.2 除法（带精度控制）
```java
public static double div(double v1, double v2, int scale)
```
- **功能**：提供精确的除法运算，并指定结果的小数位数。
- **参数**：
    - `v1`：被除数（`double` 类型）。
    - `v2`：除数（`double` 类型）。
    - `scale`：结果保留的小数位数。
- **返回值**：两个参数的商（`double` 类型）。
- **使用示例**：
  ```java
  double result = ArithmeticUtils.div(10.0, 3.0, 2); // 结果为 3.33
  ```

#### 2.4.3 除法（带精度控制，`String` 参数）
```java
public static String div(String v1, String v2, int scale)
```
- **功能**：提供精确的除法运算，并指定结果的小数位数。
- **参数**：
    - `v1`：被除数（`String` 类型）。
    - `v2`：除数（`String` 类型）。
    - `scale`：结果保留的小数位数。
- **返回值**：两个参数的商（`String` 类型）。
- **使用示例**：
  ```java
  String result = ArithmeticUtils.div("10.0", "3.0", 2); // 结果为 "3.33"
  ```

### 2.5 四舍五入
#### 2.5.1 四舍五入（`double` 参数）
```java
public static double round(double v, int scale)
```
- **功能**：提供精确的小数位四舍五入处理。
- **参数**：
    - `v`：需要四舍五入的数字（`double` 类型）。
    - `scale`：小数点后保留的位数。
- **返回值**：四舍五入后的结果（`double` 类型）。
- **使用示例**：
  ```java
  double result = ArithmeticUtils.round(3.14159, 2); // 结果为 3.14
  ```

#### 2.5.2 四舍五入（`String` 参数）
```java
public static String round(String v, int scale)
```
- **功能**：提供精确的小数位四舍五入处理。
- **参数**：
    - `v`：需要四舍五入的数字（`String` 类型）。
    - `scale`：小数点后保留的位数。
- **返回值**：四舍五入后的结果（`String` 类型）。
- **使用示例**：
  ```java
  String result = ArithmeticUtils.round("3.14159", 2); // 结果为 "3.14"
  ```

### 2.6 取余数
#### 2.6.1 取余数（`String` 参数）
```java
public static String remainder(String v1, String v2, int scale)
```
- **功能**：提供精确的取余数运算，并指定结果的小数位数。
- **参数**：
    - `v1`：被除数（`String` 类型）。
    - `v2`：除数（`String` 类型）。
    - `scale`：结果保留的小数位数。
- **返回值**：余数（`String` 类型）。
- **使用示例**：
  ```java
  String result = ArithmeticUtils.remainder("10.0", "3.0", 2); // 结果为 "1.00"
  ```

#### 2.6.2 取余数（`BigDecimal` 参数）
```java
public static BigDecimal remainder(BigDecimal v1, BigDecimal v2, int scale)
```
- **功能**：提供精确的取余数运算，并指定结果的小数位数。
- **参数**：
    - `v1`：被除数（`BigDecimal` 类型）。
    - `v2`：除数（`BigDecimal` 类型）。
    - `scale`：结果保留的小数位数。
- **返回值**：余数（`BigDecimal` 类型）。
- **使用示例**：
  ```java
  BigDecimal result = ArithmeticUtils.remainder(new BigDecimal("10.0"), new BigDecimal("3.0"), 2); // 结果为 1.00
  ```

### 2.7 比较大小
```java
public static boolean compare(String v1, String v2)
```
- **功能**：比较两个数字的大小。
- **参数**：
    - `v1`：被比较数（`String` 类型）。
    - `v2`：比较数（`String` 类型）。
- **返回值**：如果 `v1` 大于 `v2`，返回 `true`，否则返回 `false`。
- **使用示例**：
  ```java
  boolean result = ArithmeticUtils.compare("5.0", "3.0"); // 结果为 true
  ```

## 3. 使用场景
`ArithmeticUtils` 类适用于以下场景：
- **金融计算**：如货币转换、利息计算等，需要高精度的数学运算。
- **科学计算**：如物理公式计算、化学反应的定量分析等。
- **数据处理**：如统计分析、数据报表生成等，需要精确的数值处理。

## 4. 注意事项
- 在使用除法运算时，确保除数不为零，否则会抛出异常。
- 在使用精度控制的方法时，`scale` 参数必须是非负整数，否则会抛出 `IllegalArgumentException`。
- 对于需要高精度计算的场景，建议优先使用 `String` 参数的方法，以避免 `double` 类型的精度问题。

## 5. 版本信息
- **作者**：EraJieZhang
- **日期**：2020年05月24日
- **版本**：1.0