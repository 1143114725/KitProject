
## RouteManager 类

`RouteManager` 是一个用于管理 Android 应用页面跳转的工具类。它封装了常见的页面跳转逻辑，并提供了携带参数、处理返回结果等功能。

### 主要功能

1. **页面跳转**：支持普通页面跳转和带返回结果的页面跳转。
2. **参数传递**：支持通过 `Bundle` 传递参数。
3. **动画效果**：支持设置页面跳转和返回时的动画效果。
4. **返回结果处理**：支持注册回调函数处理页面返回结果。

### 方法说明

#### `getIntent(cls: Class<*>, context: Context, bundle: Bundle? = null): Intent`
- **功能**：获取跳转页面的 `Intent` 对象。
- **参数**：
  - `cls`：目标页面的 `Class` 对象。
  - `context`：上下文对象。
  - `bundle`：携带的参数，可选。
- **返回值**：`Intent` 对象。

#### `routePage(cls: Class<*>, context: Context? = null, bundle: Bundle? = null)`
- **功能**：跳转到指定页面。
- **参数**：
  - `cls`：目标页面的 `Class` 对象。
  - `context`：上下文对象，可选，默认为 `MyApplication.getInstance()`。
  - `bundle`：携带的参数，可选。

#### `getBundle(intent: Intent): Bundle?`
- **功能**：获取目标页面传递过来的 `Bundle` 对象。
- **参数**：
  - `intent`：目标页面的 `Intent` 对象。
- **返回值**：`Bundle` 对象，如果没有数据则返回 `null`。

#### `setStartPageTransition(context: Activity)`
- **功能**：设置页面跳转时的动画效果。
- **参数**：
  - `context`：当前页面的 `Activity` 对象。

#### `setFinishPageTransition(context: Activity)`
- **功能**：设置页面返回时的动画效果。
- **参数**：
  - `context`：当前页面的 `Activity` 对象。

#### `activityResultRegistry(context: ComponentActivity, key: String = "key", cls: Class<*>, bundle: Bundle? = null, onActivityResult: (result: ActivityResult) -> Unit)`
- **功能**：跳转页面并注册返回结果回调。
- **参数**：
  - `context`：当前页面的 `ComponentActivity` 对象。
  - `key`：注册的键值，默认为 `"key"`。
  - `cls`：目标页面的 `Class` 对象。
  - `bundle`：携带的参数，可选。
  - `onActivityResult`：返回结果回调函数。

### 使用示例

```kotlin
// 普通页面跳转
RouteManager.routePage(SecondActivity::class.java, this, bundle)

// 带返回结果的页面跳转
RouteManager.activityResultRegistry(this, cls = SecondActivity::class.java) { result ->
    // 处理返回结果
}
```

### 注意事项

1. 使用 `activityResultRegistry` 方法时，当前页面必须是 `ComponentActivity` 或其子类。
2. 页面跳转时，如果 `context` 不是 `Activity`，会自动添加 `FLAG_ACTIVITY_NEW_TASK` 标志。

通过 `RouteManager`，开发者可以简化页面跳转的代码，提高开发效率。

        