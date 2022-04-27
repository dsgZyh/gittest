## Git配置
Git提供了一个叫做git config的工具，专门用来配置或读取相应工作环境变量。
- /etc/gitconfig文件:系统中对所有用户都普遍使用的配置。若使用git config时用 --system选项，读写就是这个文件。
- ~/.gitconfig文件:用户目录下的配置文件只适用于该用户。若使用git config时用 --global选项，读写的就是这个文件。
- 当前项目的Git目录中的配置文件(也就是工作目录中的.git/config文件):这里的配仅仅针对当前项目有效。每一个级别的配置都会覆盖上层的相同配置，所以.git/config里的配置会覆盖/etc/gitconfig中间同名的变量。

在Window系统上，Git会找寻用户主目录下的.gitconfig文件。主目录即$HOME变量指定的目录，一般都是C:\Documents and Settings\$USER
此外,Git还会尝试找寻/etc/gitconfig文件，只不过看当初Git装在什么目录，就以此作为根目录来定位。

### 用户信息

配置个人用户的用户名称和电子邮件:
```
	$ git config --global user.name "runoob"
	$ git config --global user.email test@runoob.com
```
如果用了--global选项，那么更改的配置文件就是位于你用户主目录下的那个，以后你所有的项目都会默认使用这里配置的用户信息。
如果要在某个特定的项目中使用其他名字或电邮，只要去掉--global选项重新配置即可，新的设定保存在当前项目的.git/config文件里。

### 文本编辑器

设置Git默认使用的文本编辑器，一般可能会是Vi或者Vim。如果你有其他偏好，比如Emacs的话，可以重新设置：

```
	$ git config --global core.editor emacs
```

### 差异分析工具

还有一个比较常用的是，在解决合并冲突时使用那种差异分析工具。比如要改用vimdiff的话：

```
	$ git config --global merge.tool vimdiff
```