# step0: Fork项目
进入原项目的 GitHub 页面，点击右上角：
```
Fork → Create fork
```

# step1: 克隆自己的项目
```
git clone https://github.com/winterbamboo60/RLinf_yuzhang.git
```

# step2: 添加原项目为 upstream
```
git remote add upstream https://github.com/winterbamboo60/RLinf_yuzhang.git
```

检查配置：
```
git remote -v
```

正常情况下会看到：
```bash
origin    https://github.com/winterbamboo60/RLinf_yuzhang (fetch)
origin    https://github.com/winterbamboo60/RLinf_yuzhang (push)
upstream  https://github.com/RLinf/RLinf (fetch)
upstream  https://github.com/RLinf/RLinf (push)
```

# step3: 日常开发管理
## 3.1 创建开发分支
```
git switch main
git switch -c dev
```

## 3.2 修改并提交代码
```
git status
git add .
git commit -m "feat: add robot training module"
```

## 3.3 推送到自己的 GitHub
```
第一次提交：
git push -u origin dev
后续提交：
git push
```

# step4: 同步原项目的最新更新
## 4.1 获取 upstream 更新
```
git fetch upstream
```

## 4.2 更新本地 main
```
git switch main
git merge --ff-only upstream/main
```

## 4.3 把更新整合进自己的开发分支
```
git switch dev
git merge main

# 无冲突可直接提交
git push -u origin dev

# 有冲突处理完成了提交
git add .
git commit -m "merge: resolve upstream conflicts"
git push
```



