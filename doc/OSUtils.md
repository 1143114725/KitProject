OSUtils 技术文档
1. 概述
   OSUtils 是一个用于检测 Android 设备 ROM 类型的工具类，能够识别常见的国产 ROM（如 MIUI、EMUI、Flyme 等）以及部分国际品牌 ROM。
2. 功能

检测设备是否运行特定 ROM（MIUI、EMUI、Flyme、OPPO、VIVO、360、Smartisan）获取当前 ROM 的名称和版本号
3. 使用方法
   3.1 检测 ROM 类型
   // 检查是否是 MIUI
   boolean isMiui = OSUtils.isMiui();

// 检查是否是 EMUI
boolean isEmui = OSUtils.isEmui();

// 检查是否是 Flyme
boolean isFlyme = OSUtils.isFlyme();

// 检查是否是 OPPO
boolean isOppo = OSUtils.isOppo();

// 检查是否是 VIVO
boolean isVivo = OSUtils.isVivo();

// 检查是否是 360 或其他基于 360 的 ROM
boolean is360 = OSUtils.is360();

// 检查是否是 Smartisan
boolean isSmartisan = OSUtils.isSmartisan();

3.2 获取 ROM 信息
// 获取当前 ROM 名称
String romName = OSUtils.getName();

// 获取当前 ROM 版本号
String romVersion = OSUtils.getVersion();

4. 实现原理
   OSUtils 通过读取系统属性来判断 ROM 类型，主要实现方式如下：

优先检查已知的 ROM 标识属性：

MIUI: ro.miui.ui.version.nameEMUI: ro.build.version.emuiOPPO: ro.build.version.opporomVIVO: ro.vivo.os.versionSmartisan: ro.smartisan.version
如果上述属性均未找到：

检查 Build.DISPLAY 是否包含 "Flyme" 字样如果都不是，则使用 Build.MANUFACTURER 作为 ROM 名称
特殊处理：

对于 360 ROM，除了检查 ro.build.version.qiku 外，还检查是否包含 "360" 字样

5. 内部方法说明
   5.1 check(String rom)
   核心检测方法，用于确定当前 ROM 类型。

参数：rom - 要检查的 ROM 名称返回值：如果当前 ROM 匹配参数，则返回 true；否则返回 false
5.2 getProp(String name)
执行系统命令获取属性值。

参数：name - 要获取的系统属性名称返回值：属性值字符串，如果获取失败则返回 null
该方法通过执行 getprop 命令并读取其输出来获取系统属性值。
6. 注意事项

权限要求：此工具类需要执行系统命令的权限，在某些定制 ROM 上可能受限。兼容性：不同厂商和版本的 ROM 可能有不同的属性名称，可能需要根据实际情况调整。性能考虑：频繁调用 check() 方法可能会影响性能，建议缓存结果。异常处理：getProp() 方法会捕获 IOException 并返回 null，调用方应做好空值检查。
7. 可能的改进

增加更多 ROM 支持：可以添加对其他厂商或定制 ROM 的支持。优化检测逻辑：对于某些 ROM，可能需要更复杂的检测逻辑。缓存机制：当前实现已经做了简单的缓存，但可以进一步优化。错误处理：增强异常处理，提供更详细的错误信息。
8. 版本历史

2020/6/7 初始版本
9. 作者
   EraJieZhang

以上是 OSUtils 工具类的技术文档，涵盖了其主要功能、使用方法、实现原理以及注意事项。
