
# 前言


* 之前有提供免费开源的基于vben2\.8版本的abp vnext pro版本 [abp vnext pro vben admin 2\.8](https://github.com)
* vben2\.8作者已经重构一个版本，命名为vben5，而vben2\.x 目前已存档，仅进行重大问题修复。所以abp vnext pro vue版本前端也重新升级。
* 新版本(vben5\)与旧版本(vben2\.8\)不兼容。
* 相对于vben2\.8版本，vben5集成了国内最新的最新技术栈，开发起来更加丝滑。


## 链接


* [AbpPro Vben2预览](https://github.com)
* [AbpPro Vben5预览](https://github.com)
* [文档地址](https://github.com)
* [国内文档地址](https://github.com)
* [视频教程](https://github.com)


## 系统功能


* 用户管理
* 角色管理
* 审计日志
* 后台任务
* 集成事件
* 多语言
* FreeSql
* 容器化部署
* 单元测试
* ES 日志
* Setting 管理
* 多租户
* 数据字典模块
* 消息通知模块
* 多语言模块


# 快速开始


## 前置准备


::: info 环境要求
在启动项目前，你需要确保你的环境满足以下要求：


* [dotnet core 8\.0](https://github.com)
* [nodejs 20\.15\.0\+](https://github.com):[楚门加速器](https://chuanggeye.com)
* [pnpm](https://github.com)
* [mysql](https://github.com)
* [redis](https://github.com)
* [rabbitmq 可选](https://github.com)


:::


## 后端


### 安装 CLI 工具



```
dotnet tool install Lion.AbpPro.Cli -g

```

### 更新 CLI 工具



```
dotnet tool update Lion.AbpPro.Cli -g

```

### 创建项目



```
lion.abp new -t pro -c 公司名称 -p 项目名称  -o 输出路径(可选)
lion.abp new -t pro.all -c 公司名称 -p 项目名称  -o 输出路径(可选)
lion.abp new -t pro.module -c 公司名称 -p 项目名称  -m 模块名称  -o 输出路径(可选)

```

::: danger 注意
VS 编译项目字符串超过 256 个字符,把项目拷贝到磁盘根目录 OR 使用 Rider 开发
:::


### 修改配置


* 修改service下 xxx.HttpApi.Host\-\> appsettings.Development.json 配置
	+ Mysql 连接字符串
	+ Redis 连接字符串
	+ RabbitMQ 连接字符串(可选)



```
  "ConnectionStrings": {
    "Default": "Data Source=localhost;Port=3306;Database=LionAbpProDB;uid=root;pwd=1q2w3E*;charset=utf8mb4;Allow User Variables=true;AllowLoadLocalInfile=true"
  },
  "Redis": {
    "Configuration": "localhost:6379,password=1q2w3E*,defaultdatabase=5"
  }，
  "Cap": {
    "Enabled": true,
    "RabbitMq": {
      "HostName": "localhost",
      "UserName": "admin",
      "Password": "1q2w3E*",
      "Port": 5672
    }
  }  

```

* 修改 DbMigrator\-\> appsettings.Development.json 数据库连接字符串



```
  "ConnectionStrings": {
    "Default": "Data Source=localhost;Port=3306;Database=LionAbpProDB;uid=root;pwd=1q2w3E*;charset=utf8mb4;Allow User Variables=true;AllowLoadLocalInfile=true"
  } 

```

* 右键单击.DbMigrator 项目,设置为启动项目运行，按 F5(或 Ctrl \+ F5\) 运行应用程序
* 启动后端service下的host项目，访问后台 `http://localhost:44315/login`
* 登录账号密码 admin/1q2w3E\*


::: danger 注意


* 初始的种子数据在数据库中创建了 admin 用户(密码为1q2w3E\*) 用于登录应用程序. 所以, 对于新数据库至少使用 .DbMigrator 一次.
* 如果是通过lion.abp new \-t pro.all创建的项目，请在Lion.AbpPro.EntityFrameworkCore目录下执行dotnet ef migrations add init 生成迁移文件
:::


## 前端Vben2\.8


* 安装[pnpm](https://github.com)


在你的代码目录内打开终端，并执行以下命令:


::: danger 注意


注意存放代码的目录及所有父级目录不能存在中文、韩文、日文以及空格，否则安装依赖后启动会出错。


:::


### 获取源码项目


* 代码生成的文件夹下Vben28



```
# 进入项目目录
cd vben28

# 安装依赖
pnpm install

# 启动项目
pnpm run dev

```

### 访问


::: tip 注意


* 访问 `http://localhost:4200`
* Vben2\.8版本本地调试首次访问会比较慢，长达几分钟，请耐心等待(Vben5已解决)。
* 登录账号密码 admin/1q2w3E\*
:::


## 前端Vben5


* 安装[pnpm](https://github.com)
在你的代码目录内打开终端，并执行以下命令:


::: danger 注意


注意存放代码的目录及所有父级目录不能存在中文、韩文、日文以及空格，否则安装依赖后启动会出错。


:::


::: tip 注意


* Vben5 版本的前端项目,需要找作者购买源码
* 联系方式: 510423039@qq.com
* 微信号：WJLXRzzZ
:::


### 获取源码项目



```
# 此地址需要找作者购买源码
git clone https://github.com/abp-vnext-pro/abp-vnext-pro-vben5.git

```

执行以下命令运行项目:



```
# 在项目根目录下执行
pnpm i

# 运行指定项目 and版本(apps/web-antd)
pnpm run dev:antd

```

### 访问


::: tip 注意


* 访问 `http://localhost:4200`
* 登录账号密码 admin/1q2w3E\*
:::


