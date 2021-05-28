>   这是一个未完成的文档！

[![GitHub all releases](https://img.shields.io/github/downloads/AntonVanke/JDBrandMember/total?style=for-the-badge)](https://github.com/AntonVanke/JDBrandMember/releases/)[![GitHub release (latest by date)](https://img.shields.io/github/v/release/AntonVanke/JDBrandMember?style=for-the-badge)](https://github.com/AntonVanke/JDBrandMember/releases/latest)

## 开始之前

### 风险

1.  京东账号有被黑号的风险，即一定时间内不能参与活动
2.  入会（开卡）有礼会将你的个人信息授权给店铺，所以你可能会收到店铺的推广信息
3.  退会比较麻烦
4.  不要泄露你的`config.yaml`

### 你需要

1.  电脑知道如何安装`Python`环境；手机知道该如何在`Termux`上安装`Python`环境，或者在`ios`上安装`Pythonista`
    1.  电脑访问 [Python Mirror (taobao.org)](https://npm.taobao.org/mirrors/python/) 安装`Python`
    2.  安卓手机在各大应用商店搜索`Termux`安装后执行`pkg install python`
2.  会获取京东账号的`cookie`即`pt_key=ABC;pt_pin=123`

>   如果你不能在电脑上安装`Python`环境，你可以去[Release]([Releases · AntonVanke/JDBrandMember (github.com)](https://github.com/AntonVanke/JDBrandMember/releases))查看已经打包好的程序

## 快速开始

在电脑或者`Termux`上运行的方式

1.  下载本项目

    `git clone https://github.com/AntonVanke/JDBrandMember.git`

    或者下载 zip 压缩包

2.  安装所需的包

    `pip install -r requirements.txt`

3.  配置`config.yaml`

    一般你只需要配置好`cookies`字段就行了像是这样：

    ```yaml
    cookies:
      - pt_key=******;pt_pin=******
      - pt_key=******;pt_pin=******
    ```

    每个账号占用一行，`-`前面有两个空格而不是<kbd>Tab</kbd>， 后面有一个空格与`cookie`隔开，如果你不知道怎么获取手机京东`cookie`你可以查看这个：[如何获取京东COOKIE](/docs/HOW_TO_GET_COOKIE.md)
    
    **其它的一些配置**(几乎用不上)
    
    ```yaml
    # 线程数量: 注意！不要超过 8 线程，否则可能会被京东临时禁止访问
    thread: 4
    # 筛选
    screening:
      bean: 0  # 最小获得京豆数少于此的不会获取
      voucher: true  # 是否获取红包？true: 获取, false: 不获取。红包有有效期限！
    # 用户注册时所填写的信息
    register:
      v_sex: 男  # 要求: 男 or 女
      v_birthday: 2000-09-27  # 要求: yyyy-mm-dd
      v_name: 康有为  # 要求: 1 - 10 个字符
    # 用户代理，可自行配置
    user-agent:
        - Mozilla/5.0
    # 获取 shop_id 的连接地址详见 main.py -> get_shopid()
    shop_id_url: https://fionjones.github.io/shopid.yaml
    ```
    
4.  运行

    >   `python main.py`

## LICENSE

>   MIT License
>
>   Copyright (c) 2021 Vanke Anton

