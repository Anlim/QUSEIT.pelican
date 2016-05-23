# QUSEIT.pelican
> 这里是优趣工作室的博客

## 使用方法

### 准备工作
```
# 安装依赖
pip install pelican markdown
# 克隆本仓库
git clone https://github.com/QUSEIT/QUSEIT.pelican.git
git submodule sync
git submodule update
# 进入仓库目录
cd QUSEIT.pelican
```

### 写博文
```
# 进入 content 目录
cd content
# 在里面创建一个新的文件以 .md 为后缀
vim hello_world.md
#-- 示例内容如下 --
Title: Hello world
Date: 2015-05-18 13:50
Category: article

# 这里是博文内容
#-- 示例内容结束 --
```

当然你可以用任何的 markdown 工具编写后保存至 content 目录下，在线版推荐[马克飞象](https://maxiang.io/)
如果你是第一次接触 markdown 推荐直接看这篇说明[markdown 语法说明](http://markdown.tw/)

### 生成静态站点
```
# 回到项目根目录 QUSEIT.pelican
cd ../

# 清空output目录，并确认
cd output && git checkout master && rm -fr * && cd ..

# 生成静态站点到 output 文件夹
pelican content
# 进入 output
cd output
# 查看并提交变动
git status
git commit -am'提交了一篇新的博文'
git push
# 回到 QUSEIT.pelican 查看并提交变动
cd ../
git status
git commit -am'提交了一篇新的博文'
git push
```

> 当第二次需要提交博文时，请在 QUSEIT.pelican 与 QUSEIT.pelican/output 目录下分别执行 git pull 以避免不必要的冲突

# 常见问题

```
1 Mac下解决这个问题的方法

    from six.moves.html_parser import HTMLParser
ImportError: No module named html_parser

参考：
https://www.douban.com/note/485820796/
```
