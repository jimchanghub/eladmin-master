<h1 style="text-align: center">el-admin 后台管理系统</h1>
<div style="text-align: center">

[![AUR](https://img.shields.io/badge/license-Apache%20License%202.0-blue.svg)](https://github.com/elunez/eladmin/blob/master/LICENSE)
[![star](https://gitee.com/elunez/eladmin/badge/star.svg?theme=white)](https://gitee.com/elunez/eladmin)
[![GitHub stars](https://img.shields.io/github/stars/elunez/eladmin.svg?style=social&label=Stars)](https://github.com/elunez/eladmin)
[![GitHub forks](https://img.shields.io/github/forks/elunez/eladmin.svg?style=social&label=Fork)](https://github.com/elunez/eladmin)

</div>
http://qdall01.baidupcs.com/file/3c3220a682b515da5be8caae6f6de053?bkt=en-2e2b5030dd6ff0377a60f10ec7e303ddc1cac9ba2dfcf0cfe7ac8983a61a6100fffca42019380fde&fid=2287030762-250528-564380071931069&time=1574046165&sign=FDTAXGERLQBHSKfWa-DCb740ccc5511e5e8fedcff06b081203-gLp4qyvYtQv3Dr9CiZR7theVpdE%3D&to=34&size=1983455832&sta_dx=1983455832&sta_cs=2&sta_ft=rar&sta_ct=2&sta_mt=2&fm2=MH%2CYangquan%2CAnywhere%2C%2Cshanghai%2Ccnc&ctime=1573623403&mtime=1573623403&resv0=cdnback&resv1=0&resv2=rlim&resv3=5&resv4=1983455832&vuk=2287030762&iv=0&htype=&randtype=em&newver=1&newfm=1&secfm=1&flow_ver=3&pkey=en-71070bdbd8234811b87a14f94287c63b994a73b108c0a69bbea465ba8ea71cd098baefba27078f2c&sl=81068110&expires=8h&rt=pr&r=647842516&mlogid=7455570785095245850&vbdid=-&fin=of.rar&bflag=34-34&rtype=1&dp-logid=7455570785095245850&dp-callid=0.1.1&tsl=10&csl=50&csign=y3mmFqHTCIiBQQjCJQ3Yf6SY1qU%3D&so=1&ut=6&uter=1&serv=0&uc=566704430&ti=26fa64dbec28822412e09b5bfc8bb3bd7bebdb20f7811021305a5e1275657320&reqlabel=250528_l_835ad5eb7ce35f66320044a01c9aa1d3&by=themis
#### 项目简介
eladmin基于 Spring Boot 2.1.0 、 Jpa、 Spring Security、redis、Vue的前后端分离的后台管理系统， 权限控制的方式为RBAC，项目支持数据字典与数据权限管理，支持一键生成前后端代码，支持前端菜单动态路由

**开发文档**  [https://docs.auauz.net/](https://docs.auauz.net)

**体验地址**  [https://auauz.net/](https://auauz.net/)

**账号密码** ```admin/123456```(默认密码都是123456)

#### 项目源码

|     |   后端源码  |   前端源码  |
|---  |--- | --- |
|  github   |  https://github.com/elunez/eladmin   |  https://github.com/elunez/eladmin-qd   |
|  码云   |  https://gitee.com/elunez/eladmin   |  https://gitee.com/elunez/eladmin-qt   |

####  系统功能
- 用户管理：提供用户的相关配置，新增用户后，默认密码为123456
- 角色管理：对权限与菜单进行分配，可根据部门设置角色的数据权限
- 权限管理：权限细化到接口，可以理解成按钮权限
- 菜单管理：已实现菜单动态路由，后端可配置化，支持多级菜单
- 部门管理：可配置系统组织架构，树形表格展示
- 岗位管理：配置各个部门的职位
- 字典管理：应广大码友的要求加入字典管理，可维护常用一些固定的数据，如：状态，性别等
- 操作日志：记录用户操作的日志
- 异常日志：记录异常日志，方便开发人员定位错误
- 系统缓存：使用jedis将缓存操作可视化，并提供对redis的基本操作，可根据需求自行扩展
- SQL监控：采用druid 监控数据库访问性能，默认用户名admin，密码123456
- 定时任务：整合Quartz做定时任务，加入任务日志，任务运行情况一目了然
- 代码生成：高灵活度一键生成前后端代码，减少百分之80左右的工作任务
- 邮件工具：配合富文本，发送html格式的邮件
- 免费图床：使用sm.ms图床，用作公共图片上传使用
- 七牛云存储：可同步七牛云存储的数据到系统，无需登录七牛云直接操作云数据
- 支付宝支付：整合了支付宝支付并且提供了测试账号，可自行测试

#### 项目结构
项目采用分模块开发方式，将通用的配置放在公共模块，```system```模块为系统核心模块也是项目入口模块，```logging``` 模块为系统的日志模块，```tools``` 为第三方工具模块，包含了图床、邮件、七牛云、支付宝，```generator``` 为系统的代码生成模块
- eladmin-common 公共模块
    - exception 项目统一异常的处理
    - mapper mapstruct的通用mapper
    - redis redis缓存相关配置
    - swagger2 接口文档配置
    - utils 系统通用工具类
- eladmin-system 系统核心模块（系统启动入口）
	- config 配置跨域与静态资源，与数据权限
	- modules 系统相关模块(登录授权、定时任务等)
- eladmin-logging 系统日志模块
- eladmin-tools 系统第三方工具模块
- eladmin-generator 系统代码生成模块

#### 系统预览
<table>
    <tr>
        <td><img src="https://i.loli.net/2019/05/18/5cdf77fa8144d68788.png"/></td>
        <td><img src="https://i.loli.net/2019/05/18/5cdf7763993e361778.png"/></td>
    </tr>
    <tr>
        <td><img src="https://i.loli.net/2019/05/18/5cdf7763971d453615.png"/></td>
        <td><img src="https://i.loli.net/2019/05/18/5cdf77632e85a60423.png"/></td>
    </tr>
    <tr>
        <td><img src="https://i.loli.net/2019/05/18/5cdf77632b4b090165.png"/></td>
        <td><img src="https://i.loli.net/2019/05/18/5cdf77639929277783.png"/></td>
    </tr>
    <tr>   
 <td><img src="https://i.loli.net/2019/05/18/5cdf78969adc389599.png"/></td>
    </tr>
</table>

#### 项目捐赠
如果你用爽了，可以请作者喝杯咖啡表示支持 ☕️！ [Donate](https://docs.auauz.net/#/jz)
#### 反馈交流
- QQ交流群：891137268
