# ECNU-class2ics

进入网站 👉 [https://class2ics.billc.io](https://class2ics.billc.io) 即可使用。

## What's this

ics 是最流行的日历文件之一，受到几乎所有日历软件的支持。这个程序能根据指定的提醒策略，将高校的课程表信息生成一个可以导入到各个日历软件的 ics 文件。
![2020-05-29-ZZtweS](https://billc.oss-cn-shanghai.aliyuncs.com/img/2020-05-29-ZZtweS.jpg)

此外，如果你是 iOS 用户，可以试试由 @JJAYCHEN 开发的 iOS 捷径，也许可以解决一些本工具无法解决的特殊情况：[https://github.com/JJAYCHEN1e/ECNU_Bring-Your-Timetable-to-Calendar-App](https://github.com/JJAYCHEN1e/ECNU_Bring-Your-Timetable-to-Calendar-App)

## Why we made this

- 使用日历软件管理课程表可以让你不再把丑陋的课程表设置成桌面壁纸。
- 每节课上课前都会收到关于下一节课的提醒。（美观程度取决于系统和日历软件）
- 对于 iOS 和 macOS，系统会自动为你查找上课地点并接入苹果地图。
- 不想每学期都手动添加。~~（懒）~~
  
## How to deploy this

基于 flask + apache2，依赖以下库：

```
sudo apt-get install tesseract-ocr nodejs
sudo apt-get install python3-pip libapache2-mod-wsgi-py3 python-dev
pip3 install flask lxml requests pillow pyexecjs
pip3 install pytesseract
```

如果运行的时候还缺了什么，请 pip / pip3 上。

此外，使用 python 命令行交互获取课程表的 python 脚本可以在 `legacy(deprecated)` 目录下找到。以下是使用教程：

> - 对于华东师范大学的学生，程序可以自行登陆公共数据库获取本学期的课表信息。请先后运行 crawller.py （用于获取课程 json）和 main.py （用于生成 ics 文件）。
>  
> - 对于其他高校的学生，请先在`conf_classTime.json`中配置每节课的启示时间，然后手动填写`classinfo.xlsx`。具体操作可以参照文末的[官方文档]("http://xiejiadong.com/?p=419")。（crawller.py 仅支持华东师范大学教务系统）
>
> 最后生成的文件为同目录下的 class.ics。你可以用他来干些快乐的事情。

## About this

Contributor|Website
---|---
Bill Chen|https://billc.io
Xiejiadong|http://xiejiadong.com/

> Old Doc:

Want to know how to make the timetable? 
http://xiejiadong.com/?p=419
