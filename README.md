# BT Panel
BT Panel v7.7.0

&nbsp;

**Ubuntu & Debian python3.7**

```Bash
apt-get update -y && apt-get install curl -y
```

```Bash
curl -sSO https://raw.githubusercontent.com/loadream/BTPanel/main/install/install_panel.sh && bash install_panel.sh
```

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

```Bash
sed -i "s|bind_user == 'True'|bind_user == 'XXXX'|" /www/server/panel/BTPanel/static/js/index.js
```

```Bash
rm -f /www/server/panel/data/bind.pl
```

/www/server/panel/data/plugin.json 
Search string: "endtime": -1 Replace all with "endtime": 999999999999

```Bash
chattr +i /www/server/panel/data/plugin.json
```
