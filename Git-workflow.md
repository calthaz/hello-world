# Git团队协作规范

## 新feature的开发过程

1. `git checkout -b dev` (对于没有分支的人)
    新建dev分支
2. `git pull origin dev`
    拉取最新数据
3. `git checkout -b $feature`
    建立一个新分支，名称为具体内容，用于开发新功能
4. `git commit -a -m "msg"`
    在修改工作目录的文件后提交修改
5. `git checkout dev`
    切换回dev分支
6. `git pull origin dev`
    下载服务器最新的dev数据，保证dev分支是最新的数据
7. `git merge $feature --no-ff`
    把feature的内容合并到dev，并且保留分支结构
8. 如果有，则处理conflicts(即进行第6,7步,保证数据是最新的)
9. `git commit -a -m "merge msg"`
    处理完再提交一次
10. `git branch -d $feature`
    此时可以删除这个分支
11. `git push origin dev`
    推送到服务器

[Image: img_20170124_203046_1485317240582.jpg]

