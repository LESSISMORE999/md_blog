# md_blog
用markdown写博客的集成部署demo项目。

[我的博客](http://znote.gitee.io/note)就是基于本项目完成。

## 本机部署环境

力求简单，跨平台，本项目环境依赖非常简单：

1. 可以方便书写markdown的工具，记事本都可以，推荐[Typora](https://www.typora.io/)

2. 安装[git](https://git-scm.com/)

3. 安装[python](https://www.python.org/)2.7

这套环境windows和linux安装都比较方便，现在的大部分手机也可以安装。

## 部署步骤

1. 注册一个git管理平台帐号，推荐[码云](https://gitee.com/)，国内访问更快更稳定

2. fork本项目并clone本项目到本地

3. 编写你的博客文件，直接创建目录和md文件就行，注意：

   * 修改initNavigation.py中的如下代码配置你自己目录和博客说明：

     ```python
     navigation = [u"关于我",u"Java",u"数据库",u"设计模式",u"集成框架",u"Linux",u"Go",u"Python",u"Docker",u"大前端",u"工具",u"解决方案",u"管理相关",u"面试题"]

     fileinfo.write(u'# 非专业Java程序员博客'+next_line_tag)
     ```
    * 根目录下的文件夹包含在navigation中才会写入博客
    * 受mdwiki限制，文件夹最多建两层

4. 执行pushnote.sh文件（可以在git bash中直接执行sh）

   ```shell
   sh pushnote.sh
   ```

5. 开启git管理平台pages功能就可以访问你自己的博客了

6. 修改博客后再次执行pushnote.sh文件，你的博客就更新了

这里只简单说明部署过程，详细的技术介绍和搭建思想请参考本人博客：[搭建简易博客](http://znote.gitee.io/note/#!工具/工具笔记/搭建简易博客.md)

## 其他扩展

* 个人信息替换

  修改config.json如下配置，填写自己的信息

  ```json
      "title":"非专业Java程序员博客",

      "additionalFooterText": "All content and images &copy; by xi.yang | ",
  ```

  ​

* 如果你想用自己的域名，除了配置pages自定义域名外，还要将你的域名写入CNAME

* 主题更换

  可以去[Bootswatch](https://bootswatch.com/)选取你喜欢的主题，下载css后放在根目录，并且修改navigation.md（执行pushnote.sh会自动生成）中的代码：

  ```markdown
  [gimmick:theme](slate)
  ```

* 如果你想用自己的域名，除了配置pages自定义域名外，还要将你的域名写入CNAME

## 所用技术

以下是本项目所涉及的技术点，想研究的同学可以参考：

1. [mdwiki](http://dynalon.github.io/mdwiki/#!index.md)
2. [码云](https://gitee.com/)平台
3. [git](https://git-scm.com/)
4. [python](https://www.python.org/)2.7
5. shell
6. json

## 待改进的点

1. mdwiki没有提供搜索功能
2. 目前只支持两级目录
3. 目前目录是按文本编码排序，不能自定义顺序

## 致谢

感谢搭建本博客用到的所有开源技术的作者，让我们能免费搭建这么个小博客。如发现本文有任何问题或改进意见，请提交Issues或者pull request，谢谢！