# Truthight
## get_nfs_server.sh
nfsサーバに対してssh接続を行い，showmountコマンドを実行する．
これによって，マウントしているNFSクライアントの情報を取得する．
## show-nfs.timer
show-nfs.serviceを毎日0:00に起動するように設定する．
## show-nfs.service
get_nfs_server.shを実行する．
