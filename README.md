# mc-server
在云服务器中搭建MC服务器（基于Fabric）

作者：(Kkun)困困    本章保姆级教学

----------------

# 章节

本章分为三节。如果自己已有云服务器或本地部署，请跳过第一节

([●第一节、搭建云服务器平台](https://github.com/Kkun1225/mc-server/blob/main/README.md#%E7%AC%AC%E4%B8%80%E8%8A%82%E6%90%AD%E5%BB%BA%E4%BA%91%E6%9C%8D%E5%8A%A1%E5%99%A8%E5%B9%B3%E5%8F%B0))

([●第二节、部署mc服务框架](https://github.com/Kkun1225/mc-server/blob/main/README.md#%E7%AC%AC%E4%BA%8C%E8%8A%82%E9%83%A8%E7%BD%B2mc%E6%9C%8D%E5%8A%A1%E6%A1%86%E6%9E%B6))

([●第四节、测试]())

----------------

## ●第一节、搭建云服务器平台

作者在本章中使用腾讯云服务器来教大家

这里我们进入([腾讯云](https://cloud.tencen.com/))官网并登陆

### 在web页面中下滑点击轻量应用服务器

![屏幕截图 2025-04-07 154710](https://github.com/user-attachments/assets/577b3c9d-e700-42b2-8e20-6d7b5b230644)

### 接下来我们来选配服务器

![屏幕截图 2025-04-07 155347(1)](https://github.com/user-attachments/assets/20f6c432-c156-480e-95a8-42aa0f949ac2)

![屏幕截图 2025-04-07 160402(1)](https://github.com/user-attachments/assets/9440bae9-9685-4e6b-b46e-e165fe3e846b)

![屏幕截图 2025-04-07 161116(1)](https://github.com/user-attachments/assets/6a41c485-4c09-4baf-85ab-5772c4e4ced3)


### 点击右上角进入 控制台

![屏幕截图 2025-04-07 163016](https://github.com/user-attachments/assets/80073ba9-51c3-4f09-b52e-0b3029b71e5f)

### 点击轻量应用服务器

![屏幕截图 2025-04-07 163156](https://github.com/user-attachments/assets/efbe1304-0850-4d68-a050-dd4ee9794c8b)

### 接下来就可以看到我们选配的服务器

![屏幕截图 2025-04-077 163301](https://github.com/user-attachments/assets/0ae52c70-1e4f-4ab5-9cda-bbbea88bde18)

### 在电脑本地链接你的云服务器

这里作者使用的是MobaXterm终端，如果需要请自行([MobaXterm](https://mobaxterm.mobatek.net/))官网下载

![屏幕截图 2025-04-07 164305(1)](https://github.com/user-attachments/assets/203e6cf4-3c41-4e33-bcb6-4031e3178005)

![屏幕截图 2025-04-07 165134(1)](https://github.com/user-attachments/assets/67c59f31-7573-4248-89f1-109c307fb547)

### 看到下面界面代表已经连接到我们的云服务器了

![屏幕截图 2025-04-07 165542](https://github.com/user-attachments/assets/388838e5-74b8-41bb-8870-fffa7039c933)

----------------

## ●第二节、部署mc服务框架

本章搭建我的世界服务器基于Fabric，使用相关说明请查看([Fabric](https://fabricmc.net/))官网进行阅读

我们进入([Fabric服务器下载界面](https://fabricmc.net/use/server/))

![屏幕截图 2025-04-07 170640(1)](https://github.com/user-attachments/assets/45bc3fa4-34d0-4440-bbed-ad7181ffa1e9)

粘贴到服务器终端 回车，如下图所示，代表框架下载成功

![屏幕截图 2025-04-07 171019](https://github.com/user-attachments/assets/41855cf6-948b-43d3-b041-fdca5b59c470)

### 由于框架是java脚本来编译的，所以接下来我们要在云服务器中安装JDK21

在终端输入以下(sudo后要输入我们的服务器管理员密码)

```
sudo apt update -y #更新ubuntu apt
sudo apt install openjdk-21-jdk -y #安装JDK21
java -version # 查看jdk版本验证是否安装成功
```

回车后等待(大约下载5分钟)，如输出一下内容 代表我们的JDK21已经安装在云服务器中了

![屏幕截图 2025-04-07 172427](https://github.com/user-attachments/assets/33c6c961-7e0e-4117-9c88-2f8d67dc84c8)


### 接下来编译我的世界服务器的框架

浏览器回到([Fabric服务器下载界面](https://fabricmc.net/use/server/))

复制以下界面的第二段代码框内容

![屏幕截图 2025-04-07 172943](https://github.com/user-attachments/assets/f944ed06-666b-4af8-8a72-3f71d83030fd)

回到终端，粘贴进来并回车

![屏幕截图 2025-04-07 173243](https://github.com/user-attachments/assets/458b821b-dfdc-492f-b069-99ebdc35570e)

显示Downloading Minecraft server 表示正在下载我的世界服务器 （如失败请查看jdk是否版本匹配你的mc服务器版本）

下载完成后的的界面

![屏幕截图 2025-04-07 173623](https://github.com/user-attachments/assets/b61743b5-ce89-4d33-ae4a-a93a5916d02d)

### 接下来我们要进入修改一下配置

```
vim eula.txt # 云服务器中没有vim编辑器的话请下载或vi eula.txt
```

进入eula.txt后

![屏幕截图 2025-04-07 183511(1)](https://github.com/user-attachments/assets/37aeb6df-252c-470e-95f0-81a7b2d1dd41)

按esc键 再按shift+： 再按wq键回车保存退出

### 接下来我们进入我的世界服务器配置文件

```
vim server.properties
```

![屏幕截图 2025-04-07 184247](https://github.com/user-attachments/assets/41908456-0903-40f7-8236-a988bd57c60a)

按esc键 再按shift+： 再按wq键回车保存退出

### ok大功告成，接下来我们就差启动服务器了

我们再回到([Fabric服务器下载界面](https://fabricmc.net/use/server/))

再次复制以下界面的第二段代码框内容

![屏幕截图 2025-04-07 172943](https://github.com/user-attachments/assets/f944ed06-666b-4af8-8a72-3f71d83030fd)

再次回到终端，粘贴进来并回车

当回车后看到以下内容时代表我们的服务器以圆满搭建完成并成功启动了它

![屏幕截图 2025-04-07 185105](https://github.com/user-attachments/assets/da29709d-9684-45c9-8f54-a162448a4f3e)

## 大功告成，接下来我们要开放一下云服务器的我的世界服务端口以便客户端加入

![屏幕截图 2025-04-07 190045(1)](https://github.com/user-attachments/assets/730a2314-43a7-428b-854f-eb0b6cc07f18)

![屏幕截图 2025-04-07 190555](https://github.com/user-attachments/assets/1df9aab1-96a3-4342-bb2f-fb7fba39feee)

点击确定，就此你的mc服务器已搭好并开放了端口可以进行与小伙伴们联机了

----------------

## ●第四节、测试

我们打开我的世界启动器下载与服务器对应的版本后启动它

依次点击游戏   多人游戏—————添加服务器—————输入你云服务器的IP（以下内容）

![屏幕截图 2025-04-07 191214](https://github.com/user-attachments/assets/0e9c1c8e-f527-4202-be4e-aa6083169454)

添加后进入游戏

![屏幕截图 2025-04-07 191332](https://github.com/user-attachments/assets/fa7e04e3-ca68-47ef-bfd3-a3a4389aefe6)

### 测试完毕，本章到此end，愿诸位都能完美成功，拜了个拜

----------------

作者：Kkun
