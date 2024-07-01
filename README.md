  
# 脚本说明：  
1、脚本用于使用账号密码自动登录京东获取ck，自动更新ck到青龙  
3、程序仅更新被禁用的ck  
5、py脚本需要opencv-python、pyppeteer、Pillow、asyncio、aiohttp等依赖  
7、第一次使用会下载chrome浏览器，生成jdck.ini配置文件，等待即可，后续无需等待  
8、此脚本适合于青龙内部运行，因青龙大部分不支持opencv插件，仅支持linux以及windows运行，建议使用windows版本，定时运行即可。  
9、脚本基于3.12开发，其它版本python自行测试  
10、脚本需要青龙应用权限——环境变量跟脚本管理  

  
# windows使用说明
运行exe即可，无需安装依赖等  第一次登陆面板无需验证码，重启windows后需要验证码
如果windows有python环境，可能会遇到问题  
windows定时任务参考https://blog.csdn.net/renluborenlubo/article/details/128655711  


#### 安装python依赖
```
pip install --break-system-packages pyppeteer Pillow asyncio aiohttp opencv-python
`````

### 定时运行  
```
echo "*/30 * * * * python3.11 /root/autojdck.py" | crontab -  #半小时运行一次，python命令改成自己的，py脚本路径也改自己的
```
注意：这种方式会覆盖当前用户的全部定时任务，所以请确保你已经包含了所有需要保留的定时任务。  



# jdck.ini配置文件位于脚本/程序同目录下
Displaylogin=0  #是否显示登录操作，1显示，0不显示  
qlip=http://192.168.1.1:5700  #填青龙的ip  
client_id=*******    #填青龙对接应用的client_id  
client_secret=*******     #填青龙对接应用的client_secret  

登陆号码#密码#备注          #多账户换行  
例如：  
517123248#ya21udb95#我是备注1  
15611167798#123456789#我是备注2  


### 废案：
```
代理登陆变量  
AutoJDCK_DP = http://192.168.2.1:22332    #设置登录代理（不建议设置代理，基本上要验证码）  
```
京东上车：
除了车头都是随机账号模式
wx机器人自动上车

wx:iot_hh7999


# 免责声明  
本脚本仅供学习参考，请在下载后24小时内删除，请勿用于非法用途。  
作者不对因使用该脚本造成的任何损失或法律问题负责。  
