# baidu_speark
百度智能音箱 tty中断解决  

![0432B4DBA3DFBD24DB2DA4CC497AFBBD](https://user-images.githubusercontent.com/107302470/173182645-8ab3366a-130c-4767-83d0-05e3aaec4a20.png)
焊上晶晨的usb下载总线接口

安装晶晨刷机工具 
Amlogic_Flash_Tool_v6.0.0 使用bin中的update.exe 可以更新单一分区和所有分区 百度智能音箱系统为buildroot构建的Linux
![image](https://user-images.githubusercontent.com/107302470/173182701-2dcba1f2-59a2-496b-bbb6-dc4e63f92b4f.png)

update bulkcmd "run usb_burning"

update bulkcmd "setenv bootdelay 30"

update bulkcmd "saveenv"

百度智能音箱登录tty账号密码破解


![image](https://user-images.githubusercontent.com/107302470/173183220-3c14f55d-b29e-464d-af99-818e5003b199.png)


rlogin程序直接在arm上直接跑 需要补全rlogin的配置 放在/data/etc/bdinfo 只需修改 find 蓝框位置改成 登录时的rid的下划线之前的 其他的一律可有可无

![image](https://user-images.githubusercontent.com/107302470/173183247-abb1fb9a-b2a3-44e3-9512-18f26d2cc30e.png)


在arm板子上运行ida pro远程调试工具 上传rlogin 在ida pro上调试修改v4=rand()寄存器的值然后进去chech_sum中s1 即为登录密码

![image](https://user-images.githubusercontent.com/107302470/173183062-ef210801-4671-45e1-baf4-a3de9262f17c.png)
