
[TOC]
# sublime text 3 使用说明3  
## 一、让sublime text 3支持执行python程序
ecute python in sublime text 3   
Tools--Build System--New Build System,会弹出窗口，将下面内容完全覆盖上去即可。
```
{
    "cmd": ["c:\\python27\\python.exe", "-u", "$file"],
    "file_regex": "^[ ]*File \"(...*?)\", line ([0-9]*)",
    "selector": "source.python"
}
```
最后按ctrl+s保存。


## 二、安装Package Control 
按Ctrl + ` 打开console粘贴代码到console并回车重启Sublime Text 2

```
import urllib.request,os,hashlib; 
h = '2915d1851351e5ee549c20394736b442' +'8bc59f460fa1548d1514676163dafc88';
pf = 'Package Control.sublime-package';
ipp = sublime.installed_packages_path();
urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) );
by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read();
dh = hashlib.sha256(by).hexdigest();
print('Error validating download (got %s instead of %s),
please try manual install' % (dh, h)) if dh != h else
open(os.path.join( ipp, pf), 'wb' ).write(by)
```



## 三、安装Markdown Preview
使用
Markdown Preview较常用的功能是preview in browser和Export HTML in Sublime Text，前者可以在浏览器看到预览效果，后者可将markdown保存为html文件。

快捷键
st支持自定义快捷键，markdown preview默认没有快捷键，我们可以自己为preview in browser设置快捷键。
方法是在Preferences -> Key Bindings User打开的文件的中括号中添加以下代码(可在Key Bindings Default找到格式)：

```
{ "keys": ["alt+m"], "command": "markdown_preview", "args": { "target": "browser"} }
```
"alt+m"可设置为自己喜欢的按键。


## 四、sublimetext3 如何自动取消换行
在sublime菜单栏中单击"查看--自动换行", 把自动换行前面的对勾√去掉即可
如果每次打开文件都不自动换行, 设置如下
在sublime菜单栏选择"选项-->设置-用户","Preferences -> Settings-User"
在打开的配置文件中添加

```
"word_wrap" : false,
```


## 五、markdown
### markdown的页内实现跳转
默认情况下，标准的markdown语法并没有业内跳转的功能, 可以使用html标签来解决。

### markdown的table自动快速格式化
推荐插件：Table Cleaner  
markdown的table写起来很慢，而且最好要对齐。    
How it works    
Select the table you want to clean, and press alt + ; and the table gets cleaned instantly. For cleaning a table pasted from another source press alt + shift + ;“ and the table gets cleaned instantly.  
怎样工作？  
选中你想格式化的table，按 alt加; 组合键，就能实现效果了。  


| lorem | ipsum       | dolor       | sit    |  
| amet  | consectetur | adipisicing | elit   |  
| sed   | do          | eiusmod     | tempor |  






