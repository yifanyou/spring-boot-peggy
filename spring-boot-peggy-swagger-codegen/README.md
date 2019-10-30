## swagger code 使用方案一

### 版本
swagger 2.0

### 生成代码
首先，根据swagger规范定义接口文件。
项目中swagger定义在src/main/swagger-spec目录下，包含
index.yaml - 总定义文件
user.api.yaml - 接口定义文件
user.model.yaml - model定义文件

然后，通过maven插件swagger-codegen-maven-plugin生成代码
项目下执行命令
```
mvn swagger-codegen:generate
```
根据pom.xml文件中的定义生成相应代码，这里在生成在项目根目录下的swagger-codegen中。

### 生成api.json
通过maven插件groovy-maven-plugin生成。
其中调用了swagger-parser库相关工具类来实现。
```
mvn groovy:execute
```

### 为何使用build-helper-maven-plugin
通过maven插件build-helper-maven-plugin，指定swagger-codegen为代码路径，项目编译的时候也会编译这个路径下的代码。
```
mvn complie
```

### 来源
方案来自[mumutu](https://github.com/mumutu66)
