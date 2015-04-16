# 本地模拟运行codeskulptor平台

## 背景

codeskulptor 平台上的图形界面基于一个叫simplegui 的模块，如果要在本地模拟运行的话，需要安装如下模块：

+ python模块
    - PySDL2
    - mercurial
    - SimpleGUICS2Pygame（名称很好理解吧）
    - Pygame
+ 非python模块（Mac）
    - sdl 
    - sdl_image
    - sdl_mixer
    - sdl_ttf
    - portmidi
    - ....（以及我不知道的各种可能出现的依赖）

## 开始安装

**前提：默认各位已经有了并会使用pip（或者easy_install，再或者apt-get）**

### Mac环境（ubuntu 跳过）：

输入下面的命令：

```shell
brew install sdl sdl_image sdl_mixer sdl_ttf portmidi
```

### python依赖

依次安装

```shell
pip install PySDL2 
pip install mercurial
pip install SimpleGUICS2Pygame
# 最后一个有点诡异
pip install hg+http://bitbucket.org/pygame/pygame
```
## 开始使用

将在codeskulptor 的代码本地保存为一个.py的文件，将

```python
import simplegui
```
改为：

```python
import SimpleGUICS2Pygame.simpleguics2pygame as simplegui
```

在命令行中运行本地脚本

```shell
python test.py
```

然后就能在本地操作codeskulptor 上的游戏了。就不用连到服务器操作。

## 参考
- [万年素人からHackerへの道](http://shinriyo.hateblo.jp/entry/2015/01/21/Kiviのpipでインストール)
- [Unable to install Pygame using pip](http://stackoverflow.com/questions/17869101/unable-to-install-pygame-using-pip)
- [SimpleGUICS2Pygame](https://bitbucket.org/OPiMedia/simpleguics2pygame/src/4eac7005c7f4a5fbf2c1b25ae191b294722d43b6?at=default)
