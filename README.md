# Truthight
## get_nfs_server.sh
nfsサーバに対してssh接続を行い，showmountコマンドを実行する．
コマンドの実行結果は以下のようになる．
![image](https://github.com/user-attachments/assets/48bf3ebf-d16f-40de-b196-a24d31348043)
これによって，マウントしているNFSクライアントの情報を取得する．
## show-nfs.timer
show-nfs.serviceを毎日0:00に起動するように設定する．
## show-nfs.service
get_nfs_server.shを実行する．
## 動作方法
1. show-nfs.timerとshow-nfs.serviceを`/etc/systemd/system`ディレクトリに配置する．
2. get_nfs_server.shを`/home/c0a21030/develop`ディレクトリに配置する．この配置場所は決まりはないが，配置場所を変更した場合，show-nfs.serviceの内容を変更する必要がある．
3. 次のコマンドを順番に実行していく
```
sudo systemctl daemon-reload
sudo systemctl enable show-nfs.timer
sudo systemctl start show-nfs.timer
```
4. `systemctl list-timers`を実行して，show-nfs.timerがセットされていることを確認する．
![image](https://github.com/user-attachments/assets/d78dde90-1856-413d-9bc6-8f14c3c71334)
