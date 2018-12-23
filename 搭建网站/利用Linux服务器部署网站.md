利用云服务器部署网站

### 1.利用Linux服务器部署网站

1. `下载并安装putty，下载地址如下：`

   - 64-bit：  <https://the.earth.li/~sgtatham/putty/latest/w64/putty.exe>
   - 32-bit：  <https://the.earth.li/~sgtatham/putty/latest/w32/putty.exe>
   - putty 下载官网：  <http://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html>

   http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html

2. 安装成功后，双击打开putty软件，在“Host Name for IP address”中输入ECS实例公网IP地址。完成后，点击“Open”。在弹出的对话框中，输入用户名：root（Linux系统ECS实例默认的登陆用户名）；密码为ECS登陆密码，此时密码不会显示。

3. ![img](https://edu.aliyun.com/lab/static/img-doc/doc-remote-connect-080.png)

   ### 2.安装Apache

   > 1使用yum方式，下载安装Apache

   `yum -y install httpd`

   ![img](https://edu.aliyun.com/lab/files/courses/129136057c2a4d50af22490b5ce8f878/sections/ba70fc3a856948459ee8792994f23447/content/images/course-129136057c2a4d50af22490b5ce8f878-section-ba70fc3a856948459ee8792994f23447-content-image-1492759842255-UbBz2m)

   > 2.执行如下命令，添加一个Linux用户 **siteadmin** 并指定新增用户的远程登录默认访问路径为 **/var/www/html，**忽略警告信息即可。

   `adduser -d /var/www/html siteadmin`

   > 3.执行如下命令，设置新建用户 **siteadmin** 的登录密码：

​             `passwd siteadmin`

	> 4.执行如下命令，授予 **siteadmin** 用户权限：	

​		`chown  -Rf  siteadmin.siteadmin  /var/www/html`

> 5.执行如下命令，启动Apache服务：

`		service httpd start`

	>6 . 本地打开浏览器，并输入 **Linux服务器** 的 **公网IP** 。若页面显示 **Apache 2 Test Page，**则证明Apache已部署成功。

![img](https://edu.aliyun.com/lab/files/courses/129136057c2a4d50af22490b5ce8f878/sections/ba70fc3a856948459ee8792994f23447/content/images/course-129136057c2a4d50af22490b5ce8f878-section-ba70fc3a856948459ee8792994f23447-content-image-1492760637682-xLHx0K)

