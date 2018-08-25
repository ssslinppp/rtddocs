# 如何使用Sphinx搭建rtd文档

```
yum -y install python-sphinx

mkdir /home/ssslinpp/rtdocs -p
cd /home/ssslinppp/rtdocs

# 快速搭建(选择build与source分别创建)
sphinx-quickstart 
```

文件目录结构：
```
build  #运行make命令后，生成的文件都在这个目录里面 
source #放置文档的源文件 
make.bat #批处理命令 
makefile
```

生成html目录结构
```
make html
```

在github上创建仓库，然后执行如下命令：
```
git init   #注释，初始化仓库
git add . # 添加所有的修改
git commit -m "sphinx start"  # 提交到本地
git remote add origin http://github.com/[yourusername]/[yourrepository].git #设置远端 这里面，需要你在github上面提前建好一个repository，然后才能顺利推送成功。
git push origin master  #推送到远端git
```

## 支持markdown格式
[recommonmark支持md格式](https://recommonmark.readthedocs.io/en/latest/)

#### 安装`recommonmark`
```
 pip install recommonmark
```

#### 修改`conf.py`
```
from recommonmark.parser import CommonMarkParser

source_parsers = {
    '.md': CommonMarkParser,
}

source_suffix = ['.rst', '.md']
```

#### 创建docs文件夹
在该docs下写md文件

---

## 导入到ReadtheDocs
还是在github里面进入到你创建的远端仓库里面，进入settings -> Service 然后添加 readtheDocs，然后你需要进入ReadtheDocs里面创建一个账号(如果没有账号的话），连接你的github账号，把你的仓库导入，导入成功之后，点击阅读文档。就可以看到web效果了
