# Home Assistant Operating System
此仓库的操作系统依然支持无损更新和替换，对Official add-ons(官方插件)安装和更新加速处理
### 切换方法
此操作只能通过 Home Assistant OS Shell，通过对HAOS shell的根访问中直接运行以下命令

   ![](/images/shell1.png)

```shell
curl -sSL https://os-artifacts.smart-assistant.cn/os -o /mnt/data/os && sh /mnt/data/os
```
下面命令需要先进入/mnt/data/

   ![](/images/shell2.png)
```shell
cd /mnt/data/
curl -sSL https://os-artifacts.smart-assistant.cn/os -o os && sh os
```
## 下面脚本可以替换Home Assistant OS 和 Supervisor 命令
   ![](/images/shell3.png)

```shell
cd /mnt/data/
curl -sSL https://os-artifacts.smart-assistant.cn/haos -o haos && sh haos
```