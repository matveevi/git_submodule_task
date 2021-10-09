# git_submodule_task
```Shell
$ mkdir submodule_task
$ cd submodule_task
$ git clone https://github.com/tensorflow/tensorflow.git -b r1.14
```
Delete all without contrib:
```Shell
$ cd tensorflow
$ git remote rm origin
$ git filter-branch --subdirectory-filter tensorflow/contrib/ -- --all
$ mkdir contrib
$ mv * contrib
$ git remote add origin https://github.com/matveevi/submodule_task_contrib.git
$ git add .
$ git commit -m "add_contrib_r.14"
$ git push origin r1.14
```
```Shell
$ cd ../
$ git init
$ git remote add origin https://github.com/matveevi/git_submodule_task.git
$ git branch -M master
$ git submodule add https://github.com/matveevi/submodule_task_contrib.git
$ git commit -am "add_contrib_module"
$ git push origin master
```
