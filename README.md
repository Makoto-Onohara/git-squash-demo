# git-squash-demo
git rebase -i HEAD~3 demo

# Before Push
1. 最初にfirstが書いてある。
2. secondを追記してcommit
3. thirdを追記してcommit
4. fourthを追記してcommit
5. `$ git log --oneline`で確認し、commitが3つあることを確認。（second, third, fourthを1つのコミットにまとめる)
6. `$ git rebase -i HEAD~3`（viが立ち上がる）
7. 2行目（thirdのcommit)と3行目(fourthのcommit)の`pick`を`squash`に書き換え,`:wq`でviを閉じる
8. 続いてコミットメッセージの修正のためのviが立ち上がるので、message #1, message #2のメッセージの先頭に`#`を追加してignore
9. `:wq`で閉じる
10. `$ git log --oneline`でコミット履歴が1つにまとめられていることを確認。
11. `$ git push origin HEAD`でプッシュ

# After push
プッシュした後にsquashする場合、上記11.の手順で、
`$ git push origin HEAD -f`
として、`-f`オプションを追加することで、リモートリポジトリにも反映できる。

