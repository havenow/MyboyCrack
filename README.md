# client改为30s connect

![](https://github.com/havenow/MyboyCrack/blob/master/pic/client%2030s.png)

# 本地对战改为跑30帧后连接

![](https://github.com/havenow/MyboyCrack/blob/master/pic/30%20frame.png)

# 问题
```
1、serversocket(port),解决热点连不上
不要指定server的ip地址
ServerSocket e = e(strServerIp, strServerPort);
改为
ServerSocket e = e(strServerPort);


2、按键导致对战总有一个人进不去

    public void onGameKeyChanged() {
        key_states = menuView.getKeyStates();
        //对战bug onSetKey();
    }
    
 ui线程应该是只改变key_states的值，模拟器线程每一帧去主动获取key_states的值，而不能在ui线程里面去调模拟器的方法 this.n.a.setKeys(key_states);
 ```
