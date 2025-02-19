# JDeli ImageIO 插件

---

### 原代码仓在[这里](https://github.com/idrsolutions/JDeli-ImageIO)

这是一个用于通过 JDeli 扩展 ImageIO 的插件。如果你尚未拥有 JDeli，你可以在 [这里](https://www.idrsolutions.com/jdeli/) 下载试用版。

# 安装

---

可以通过将存储库或构建的 jar 文件复制到类路径中来完成安装。

我们还提供了一个 [预构建的 JDeli 和 ImageIO 合并 jar](https://www.idrsolutions.com/jdeli/trial-download)，其中包含最新版本的 JDeli 和 ImageIO。

**使用 Maven**

首先按照我们的 [支持页面](https://support.idrsolutions.com/jdeli/tutorials/add-jdeli-as-a-maven-dependency) 指示设置 JDeli。
一旦 JDeli 设置完毕，你可以构建 JDeli_imageIO_Plugin，构建的 jar 文件将包括 JDeli。
然后你可以将该插件作为依赖项添加到 pom 文件中。

```xml
<dependencies>
    <dependency>
        <groupId>com.idrsolutions</groupId>
        <artifactId>jdeli-imageio</artifactId>
        <version>3.0</version>
    </dependency>
</dependencies>
```

# 注册和注销读取和写入格式

---

默认情况下，插件现在已注册 HEIC 格式，JDeli 支持的所有其他格式均未注册。

要注册所有格式：
```java
ImageIOSupport.registerReaders(InputFormat.values());

ImageIOSupport.registerWriters(OutputFormat.values());
```

注册单个格式：
```java
ImageIOSupport.registerReader(InputFormat.BMP);

ImageIOSupport.registerWriter(OutputFormat.BMP);
```

要注销所有格式：
```java
ImageIOSupport.unregisterReaders(InputFormat.values());

ImageIOSupport.unregisterWriters(OutputFormat.values());
```

注销单个格式：
```java
ImageIOSupport.unregisterReader(InputFormat.BMP);

ImageIOSupport.unregisterWriter(OutputFormat.BMP);
```

# 联系人

---

发现了 bug，或有建议/改进意见？请通过问题页面告诉我们。

有任何疑问？你可以 [在这里](https://idrsolutions.atlassian.net/servicedesk/customer/portal/8) 联系我们。

---

根据 Apache 许可证 2.0 版（“许可证”）授权；除非遵守该许可证，否则不得使用此文件。你可以在以下网址获取许可证副本：

http://www.apache.org/licenses/LICENSE-2.0

除非适用法律要求或书面同意，否则根据该许可证分发的软件是按“原样”提供的，不附带任何形式的保证或条件，无论是明示的还是隐含的。
详细信息请参见许可证，了解有关权限和限制的具体规定。
