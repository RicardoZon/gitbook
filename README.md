# ◀ 权限管理

## 1.用户和用户组

### 1.1 添加和删除用户

useradd

{% embed url="https://blog.csdn.net/geol200709/article/details/82116267" %}

### 1.2 用户组

(1)添加用户到用户组

```bash
sudo usermod -aG $用户组 $用户
```

(2)使用wheel组管理su权限

{% embed url="https://blog.csdn.net/annita2019/article/details/106207527" %}

\---新建用户脚本示例---

```bash
useradd -m $1 -s /bin/bash
passwd $1
usermod -a -G user $1
usermod -a -G docker $1

chmod 700 -R /home/$1

echo 'create user data directory...'
mkdir -m 700 /data/$1/

echo 'set user directory group...'
chown $1.user /data/$1/

echo 'copy USER_README.md...'
scp /home/hk1/Documents/docs_for_server/USER_README.md /home/$1/
```

## 2. 文件权限

### 2.1 文件权限管理 chmod

用于指定文件权限

{% embed url="https://www.runoob.com/linux/linux-comm-chmod.html" %}

![](<.gitbook/assets/image (2).png>)

示例

```bash
chmod -R 755 $DIR
```

【注意】递归是-R不是-r

{% embed url="https://zhuanlan.zhihu.com/p/255000117" %}

### 2.2 文件权限管理 chmod
