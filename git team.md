# 1.拉取到本地，再创建 dev 然后再创建 pravite 私人操作分支

```js
git clone ....
git checkout -b dev
git checkout -b  shihai
```

# 2.在私人分支编写完后提交缓存，切换到 dev 更新下来在合并私人分支

```js
git add .
 git commit -m'私人操作'
 git checkout dev
 git pull
 git merge shihai(合并到dev)
 git push origin dev (合并到远程dev)
```

# 3.组长再把 dev 合并到 master

# 4.当先有远程时，通过与远程建立连接直接传送到远程（不需要通过克隆到本地）
