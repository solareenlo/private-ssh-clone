# private-ssh-clone
プライベートリポジトリをssh経由でcloneする方法

### githubへのssh接続を確立する
- ssh鍵を生成
- sshを設定
```
$ vim ~/.ssh/config
--------------------------------
Host github
  Hostname github.com
  Port 22
  User git
  IdentityFile ~/.ssh/github_rsa
--------------------------------
$ chmod 0600 ~/.ssh/config
```

### GitHubでssh接続を設定する
- GitHubの右上の自分の写真をクリック
- Settingsをクリック
- SSH and GPG keysをクリック
- ssh鍵を追加

### 自分のPCからGitHubへssh接続してみる
```
$ ssh github
> PTY allocation request failed on channel 0
> Hi solareenlo! You've successfully authenticated, but GitHub does not provide shell access.
> Connection to github.com closed.
```
な感じで返ってきたらOK

### Private repositoryをcloneしてみる
```
$ git clone github:solareenlo/private.git
```

# Reference
GitHub関係
- https://akiyoko.hatenablog.jp/entry/2014/03/04/072855

SSH関係
- https://qiita.com/tag1216/items/5d06bad7468f731f590e
- https://qiita.com/0084ken/items/2e4e9ae44ec5e01328f1
- https://qiita.com/m1220/items/9dc3856bbcf985577023
