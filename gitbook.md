#本地安装 Gitbook 并创建笔记。

根据官网说明 第一步，先安装

npm install gitbook-cli -g
然后，创建一个笔记文件夹

mkdir my-note
然后执行

cd my-note
gitbook init
这样，可以生成两个文件

README.md 的内容会显示在书皮上
SUMMARY.md 是目录
启动服务器，查看和编辑书籍

gitbook serve
这样，可以启动一个服务器，然后到 localhost:4000 端口，就可以看到这本书了。

视频： http://digicity-1253322599.costj.myqcloud.com/gitbook-3-create.mp4

 # 修改笔记

可以修改 SUMMARY.md 来添加书籍目录

# Summary

- [Introduction](README.md)
- [第一章：redux](./redux/index.md)
  - [第一节：state 复习](./redux/1-state.md)
  - [第二节：你好 redux](./redux/2-hello-redux.md)
下一步，创建笔记文件，atom 到 redux 文件夹中创建 1-state.md 和 2-hello-redux.md 文件。

视频： http://digicity-1253322599.costj.myqcloud.com/gitbook-4-change.mp4