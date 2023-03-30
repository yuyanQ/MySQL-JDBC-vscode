# MySQL-JDBC-vscode
如果没有使用Maven，可以手动下载 MySQL Connector/J 驱动程序（即 JAR 文件），然后将其添加到 Java 项目的类路径中，以便 Java 代码可以使用该驱动程序。
以下是在 VS Code 中手动添加 JAR 文件的步骤：

1. 下载 MySQL Connector/J 驱动程序 JAR 文件。可以从 MySQL 官网下载，也可以从 Maven 仓库等第三方网站下载。

2. 将下载的 JAR 文件复制到 Java 项目中的某个目录下，例如 lib 目录。

3. 在 VS Code 的左侧菜单栏中，选择 Explorer 视图。

4. 找到并展开 Java 项目文件夹。

5. 在目录下创建一个新目录，例如 lib 目录，用于存放下载的 JAR 文件。

6. 在 lib 目录下右键点击鼠标，在弹出的菜单中选择 New File 创建一个空的 .classpath 文件。

7. 在 .classpath 文件中添加以下代码：
    ```
    <classpath>
        <classpathentry kind="lib" path="lib/mysql-connector-java-8.0.32.jar"/>
        <classpathentry kind="output" path="bin"/>
    </classpath>
    ```
8.其中 path 属性的值应该是你下载的 MySQL Connector/J 驱动程序 JAR 文件的实际路径。

9. 保存 .classpath 文件并关闭它。

10. 在 VS Code 的左下角找到并打开 Terminal 视图。

11. 在 Terminal 视图中输入以下命令以编译和运行你的 Java 代码：
    ```
    javac -d bin *.java
    java -cp bin;.\lib/mysql-connector-j-8.0.32.jar mypackage.MyClass
    ```
    其中 mypackage.MyClass 应该替换为你的 Java 代码中的实际类名。
