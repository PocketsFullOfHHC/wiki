# 项目概述：


## 第一天工作：
1. **搭建SpringBoot框架**：
    * 修改pom.xml里面的版本号
2. **项目的初始配置**：
    * 编码配置：UTF-8
    * Maven配置：阿里云镜像settings.xml
    * Git配置：通过.gitignore来忽略文件
3. **代码关联Git远程仓库**：
    * github新建仓库Wiki及SSH密钥
    * 相关git命令：push, pull, clone, remote，commit
    * 增加README.md文件
4. **启动日志优化**：
    * 增加logback配置文件
    * 修改启动成功的文案和图案
5. **开发Hello World接口**：
    * 制作接口@GetMapping和@RestController(指定返回字符串Hello World)
    * 项目分层:
        * config层用于放配置类WikiApplication：@ComponentScan指定该wiki启动类扫描的包的范围
        * controller层用于定义接口，是请求的入口
6. **增加hello接口测试test.http**：
    * IDEA自带的HTTP Client测试接口
7. **配置文件**：
    * SpringBoot会自动识别下面这组配置文件：
        * application.properties/yml
        * config/application.properties/yml
    * 如果是SpringCloud，还会自动识别下面这组配置文件：
        * bootstrap.properties/yml
        * config/bootstrap.properties/yml
    * 自定义配置项的使用：用@Value来读。
8. **修改错误命名的test.http和TestController**

## 第二天工作：

9. **集成持久层框架Mybatis**：
    * 集成Mybatis
    * 测试Mybatis：开发/test/list接口，查询test表所有数据
        * 流程：
        1. 程序的入口在TestController
        2. 我们在test.http中访问了/test/list，相当于访问了TestController中的list()方法
        3. 该方法返回TestService.list()，而这个方法会返回TestMapper.list()
        4. 而TestMapper会映射到对应的TestMapper.xml并根据方法名和id的对应关系选择对应的sql语句