# .muttrc
# GnuPG でパスワードを暗号化する
鍵がすでにある場合は飛ばします。
$ gpg --full-gen-key

パスワードのファイルを作成します。
$ vi .my_pass
----------------------------
set my_pass="your password"
----------------------------
$ gpg --encrypt .my_pass
$ vi .muttrc
----------------------------
source "gpg -dq $HOME/.your.gpg.file.gpg |"
を追加して
set my_pass="your password"
を削除します
----------------------------
