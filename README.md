# NinjaMagisk 动态链接库
NinjaMagisk 是使用C# .NET Framework 4.7.2 编写, 使用 Microsoft Visual Studio 2022 编译的跨平台动态链接库

## 全局引用方法

NinjaMagisk 给出了多种方法
```csharp
using NinjaMagisk;
```

```csharp
using static NinjaMagisk.LogLibraries;
```

```csharp
using static NinjaMagisk.Soft;
```

## 所有方法

<!-- 这里使用javascript只是为了方便可视化代码-->

### 控制台打印彩色日志

<!-- 这里使用javascript只是为了方便可视化代码-->

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
### 清空日志
```javascript
NinjaMagisk.LogLibries.ClearFile(string filePath);
```
> [!NOTE]
> 调用此方法时,请确保`filePath`的文件路径有效,否则会提示`$"fail to clear log file: {ex.Message}"`

### 高速下载
> [!WARNING]
> 此处使用了aria2c库,作者遵循GPL 2.0协议,内容为未修改或修改过的程序,均为在[Github - aria2/aria2](github.com/aria2/ari2)上下载.

```JavaScript
NinjaMagisk.Soft.DownloadAssistant.Downloader(string url);
NinjaMagisk.Soft.DownloadAssistant.Downloader(string url,string Downloadvocation);
NinjaMagisk.Soft.DownloadAssistant.Downloader(string url,string Downloadvocation,bool log);
NinjaMagisk.Soft.DownloadAssistant.Downloader(string url,string Downloadvocation,string outputName);
NinjaMagisk.Soft.DownloadAssistant.Downloader(string url,string Downloadvocation,string outputName,bool log);
```
**`url` 下载链接**

**`Downloadvocation` 下载位置:** 请确保位置有效

**`log` 是否启用日志输出:** 当`bool`为`true`时,日志会输出到`"{Directory.GetCurrentDirectory()}\\aria2c.log\`文件内,反之为`false`则不会.

**`outputName` 文件的输出名称:** 下载完后会以`outputName`为命名储存在`Downloadvocation`文件夹内.

### 模块下载

```JavaScript
NinjaMagisk.Soft.DownloadAssistant.ModuleDownloader(Module module);
```

> [!WARNING]
> 使用时请注意,在无网络的情况下,`MessageBox`会弹出提示询问是否进行下一步操作.
> 
> Visual++运行库产品来自Microsoft,© Microsoft 2025,作者未对模块和DLL进行修改.
>
> `7-zip` 产品来自[ww.7-zip.org](www.7-zip.org),Copyright (C) 2024 Igor Pavlov.作者未对此进行任何修改,遵循 GNU LGPL license.

**`Module`可用枚举:** `zip`,`VC`.

> [!NOTE]
> 当您使用`DownloadAssistant.ModuleDownlaoder(DownloadAssistan.Nodule.VC)`时,请注意! 此文件会保存在 `%USERPROFILLE%\Appdata\Local\Temp`文件夹内.
> 
> 当您使用`DownloadAssistant.ModuleDownlaoder(DownloadAssistan.Nodule.zip)`时,请注意! 此文件会保存在`$"{Directory.GetCurrentDirectory()}\\bin"`文件夹内.

### 应用下载

```JavaScript
NinjaMagisk.Soft.DownloadAssistant.ApplicationDownloader(App app);
```
**`App`可用枚举:** `EasiNote5`,`EasiCamera`,`SeewoService`,`WeChat`.

> [!WARNING]
> 请注意! `EasiNote5`,`EasiCamera`,`SeewoService`产品来自广州视源电子科技股份有限公司,Copyright © 2023 seewo. All Rights Reserved. Shirui Electronics.作者只提供了直链下载链接,未对产品做出任何修改行为.
>
> `WeChat`产品来自腾讯公司,Copyright © 1998-2025 Tencent All Rights Reserved.作者只提供了网页链接,未对产品做出任何修改.

> [!NOTE]
> 请注意!文件会保存在 `%USERPROFILLE%\Appdata\Local\Temp`文件夹内

### 安全软件检测

> [!WARNING]
> 此举未对火绒安全软件和360安全软件做出任何修改、抹黑、分发,仅对相关进程检测提示防止安全软件误杀其他程序或组件.

```javascript
NinjaMagisk.Soft.AntiSecurity.Anti360Security()
```






