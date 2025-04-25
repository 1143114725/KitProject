# DensityUtil 类技术文档

## 1. 类概述
`DensityUtil` 是一个用于像素分辨率转换的工具类，提供了多种与屏幕密度相关的转换方法，如 dp 到 px、px 到 dp、px 到 sp、sp 到 px 等，同时还提供了获取屏幕宽度、屏幕高度、设备密度、状态栏高度以及监听输入法弹出等功能。

## 2. 方法说明

### 2.1 dp 转 px
```java
public static int dip2px(Context context, float dpValue)
```
- **功能**：将 dp（密度无关像素）值转换为 px（像素）值。
- **参数**：
    - `context`：上下文对象，用于获取屏幕密度。
    - `dpValue`：要转换的 dp 值。
- **返回值**：转换后的 px 值。
- **使用示例**：
  ```java
  int pxValue = DensityUtil.dip2px(context, 10); // 将 10dp 转换为 px
  ```

### 2.2 px 转 dp
```java
public static int px2dip(Context context, float pxValue)
```
- **功能**：将 px（像素）值转换为 dp（密度无关像素）值。
- **参数**：
    - `context`：上下文对象，用于获取屏幕密度。
    - `pxValue`：要转换的 px 值。
- **返回值**：转换后的 dp 值。
- **使用示例**：
  ```java
  int dpValue = DensityUtil.px2dip(context, 100); // 将 100px 转换为 dp
  ```

### 2.3 px 转 sp
```java
public static int px2sp(Context context, float pxValue)
```
- **功能**：将 px（像素）值转换为 sp（缩放像素）值。
- **参数**：
    - `context`：上下文对象，用于获取屏幕密度。
    - `pxValue`：要转换的 px 值。
- **返回值**：转换后的 sp 值。
- **使用示例**：
  ```java
  int spValue = DensityUtil.px2sp(context, 16); // 将 16px 转换为 sp
  ```

### 2.4 sp 转 px
```java
public static int sp2px(Context context, float spValue)
```
- **功能**：将 sp（缩放像素）值转换为 px（像素）值。
- **参数**：
    - `context`：上下文对象，用于获取屏幕密度。
    - `spValue`：要转换的 sp 值。
- **返回值**：转换后的 px 值。
- **使用示例**：
  ```java
  int pxValue = DensityUtil.sp2px(context, 14); // 将 14sp 转换为 px
  ```

### 2.5 获取屏幕宽度
```java
public static int getScreenWidth(Context context)
```
- **功能**：获取屏幕宽度，单位为 px。
- **参数**：
    - `context`：上下文对象。
- **返回值**：屏幕宽度。
- **使用示例**：
  ```java
  int screenWidth = DensityUtil.getScreenWidth(context); // 获取屏幕宽度
  ```

### 2.6 获取屏幕高度
```java
public static int getScreenHeight(Context context)
```
- **功能**：获取屏幕高度，单位为 px。
- **参数**：
    - `context`：上下文对象。
- **返回值**：屏幕高度。
- **使用示例**：
  ```java
  int screenHeight = DensityUtil.getScreenHeight(context); // 获取屏幕高度
  ```

### 2.7 获取设备密度
```java
public static float getDensity(Context context)
```
- **功能**：获取设备的屏幕密度。
- **参数**：
    - `context`：上下文对象。
- **返回值**：设备的屏幕密度。
- **使用示例**：
  ```java
  float density = DensityUtil.getDensity(context); // 获取设备密度
  ```

### 2.8 获取状态栏高度
```java
public static int getStatusHeight(Activity activity)
```
- **功能**：获取状态栏高度，单位为 px。
- **参数**：
    - `activity`：当前的 Activity。
- **返回值**：状态栏高度。
- **使用示例**：
  ```java
  int statusHeight = DensityUtil.getStatusHeight(activity); // 获取状态栏高度
  ```

### 2.9 移除输入法弹出监听
```java
public static void removeKeyboardVisibilityListener(Activity activity, ViewTreeObserver.OnGlobalLayoutListener listener)
```
- **功能**：移除输入法弹出的监听器。
- **参数**：
    - `activity`：当前的 Activity。
    - `listener`：要移除的监听器。
- **使用示例**：
  ```java
  DensityUtil.removeKeyboardVisibilityListener(activity, listener); // 移除输入法弹出监听器
  ```

### 2.10 设置输入法弹出监听
```java
public static ViewTreeObserver.OnGlobalLayoutListener setKeyboardVisibilityListener(Activity activity, OnKeyboardViListener listener)
```
- **功能**：设置输入法弹出的监听器。
- **参数**：
    - `activity`：当前的 Activity。
    - `listener`：输入法弹出的监听器。
- **返回值**：设置的监听器。
- **使用示例**：
  ```java
  DensityUtil.OnKeyboardViListener keyboardListener = new DensityUtil.OnKeyboardViListener() {
      @Override
      public void onViChange(boolean isShow, int estimatedKeyboardHeight) {
          // 输入法弹出状态改变时的处理逻辑
      }
  };
  DensityUtil.setKeyboardVisibilityListener(activity, keyboardListener); // 设置输入法弹出监听器
  ```

### 2.11 输入法弹出监听接口
```java
public interface OnKeyboardViListener {
    void onViChange(boolean isShow, int estimatedKeyboardHeight);
}
```
- **功能**：输入法弹出监听接口。
- **方法**：
    - `onViChange`：输入法弹出状态改变时回调的方法。
        - `isShow`：输入法是否显示。
        - `estimatedKeyboardHeight`：估算的输入法高度。

## 3. 使用场景
`DensityUtil` 类可用于以下场景：
- 在布局中动态调整控件的大小和位置，以适应不同屏幕密度的设备。
- 获取屏幕的宽度和高度，用于自定义布局或适配不同屏幕尺寸。
- 获取状态栏高度，以便在布局中正确处理状态栏的显示。
- 监听输入法的弹出和隐藏，以便在输入法弹出时调整布局或隐藏其他控件。

## 4. 注意事项
- 在使用 `getStatusHeight` 方法时，需要确保传入的 `activity` 是当前的 Activity，否则可能无法正确获取状态栏高度。
- 在使用输入法弹出监听功能时，需要在合适的时机移除监听器，以避免内存泄漏。
- 该工具类依赖于 Android 的 `Context` 和 `Activity`，因此只能在 Android 应用中使用。

## 5. 版本信息
- **作者**：EraJieZhang
- **版本**：1.0
- **日期**：2025年04月25日