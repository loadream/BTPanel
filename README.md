# BT Panel v7.7.0

**Nginx一定要选择编译版，不要选择极速版安装**

&nbsp;

**Ubuntu 20.04 amd64 python3.7**
&nbsp;

**Debian 11 amd64 python3.7**

```Bash
apt-get update -y && apt-get install curl -y
```

```Bash
curl -sSO https://raw.githubusercontent.com/loadream/BTPanel/main/install/install_panel.sh && bash install_panel.sh
```

&nbsp;

**自动安装开心版脚本**

```Bash
curl -sSO https://raw.githubusercontent.com/loadream/BTPanel/main/bthappy/one_key_happy.sh && bash one_key_happy.sh
```

&nbsp;

**Debian 11 install Docker**

```Bash
sudo apt update
sudo apt upgrade
```

```Bash
sudo apt install apt-transport-https ca-certificates curl gnupg lsb-release -y
```

```Bash
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

```Bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

```Bash
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io -y
```

```Bash
sudo systemctl is-active docker
```

```Bash
sudo systemctl enable docker
```

&nbsp;

**手动安装开心版**

屏蔽手机号

```Bash
sed -i "s|bind_user == 'True'|bind_user == 'XXXX'|" /www/server/panel/BTPanel/static/js/index.js
```

删除强制绑定手机js文件

```Bash
rm -f /www/server/panel/data/bind.pl
```

手动解锁宝塔所有付费插件为永不过期

文件路径：/www/server/panel/data/plugin.json 

搜索字符串："endtime": -1全部替换为"endtime": 999999999999

给plugin.json文件上锁防止自动修复为免费版

```Bash
chattr +i /www/server/panel/data/plugin.json
```

取消屏蔽手机号

```Bash
sed -i "s|if (bind_user == 'REMOVED') {|if (bind_user == 'True') {|g" /www/server/panel/BTPanel/static/js/index.js
```
