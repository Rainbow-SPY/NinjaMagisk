# NinjaMagisk 动态链接库
NinjaMagisk 是使用C# .NET Framework 4.7.2 编写, 使用 Microsoft Visual Studio 2022 编译的跨平台动态链接库

## 引用方法

<!-- 这里使用javascript只是为了方便可视化代码-->

```csharp
using NinjaMagisk;
```
NinjaMagisk 给出了多种方法
```csharp
using static NinjaMagisk.LogLibraries;
```

## 所有方法

<!-- 这里使用javascript只是为了方便可视化代码-->

### 控制台打印彩色日志

```javascript 
NinjaMagisk.LogLibries.WriteLog(LogLevel loglevel, LogKind logkind,string message);
NinjaMagisk.LogLibries.WriteLog(LogLevel loglevel,string message);
```



**`LogLevel` 可用枚举:** `Info`,`Warning`,`Error`.

> [!NOTE]
> 当您使用`LogLevel.Error`时,除`LogKind`的显示字符区域外,所有字符均为红色.

**`LogKind` 可用枚举:** `Process`,`Task`,`Service`,`Rgistry`,`Network`,`PowerShell`,`Form`,`System`,`Thread`.

### 写入日志
```javascript
NinjaMagisk.LogLibries.LogToFile(LogLevel loglevel,LogKind logkind, string message);
NinjaMagisk.LogLibries.LogToFile(LogLevel loglevel, string message);
```
> [!NOTE]
> 调用此方法时,会在当前目录下创建`Assistant.log`日志文件,并会以下格式写入文件
> ```javascript
> $"{DateTime.Now:yyyy-MM-dd HH:mm:ss} [{logkind}] [{logLevel}]: {message}";
> ```


**`LogLevel` 可用枚举:** `Info`,`Warning`,`Error`.

**`LogKind` 可用枚举:** `Process`,`Task`,`Service`,`Rgistry`,`Network`,`PowerShell`,`Form`,`System`,`Thread`.


