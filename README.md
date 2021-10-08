# git_submodule_task
```Shell
$ mkdir submodule_task
$ cd submodule_task
$ mkdir tensorflow
$ cd tensorflow
$ git init
$ git remote add origin https://github.com/matveevi/submodule_task_contrib.git
$ git branch -M main
$ git pull origin https://github.com/tensorflow/tensorflow.git r1.14
```
Delete all without contrib:
```Shell
$ ls | grep -v tensorflow | xargs rm -rfv 
$ mv tensorflow/contrib .
$ rm -r tensorflow
$ git add .
$ git commit -m "delete_all_without_contrib"
$ git push origin main
```
```Shell
$ cd ../
$ git init
$ git remote add origin https://github.com/matveevi/git_submodule_task.git
$ git branch -M main
$ git submodule add https://github.com/matveevi/submodule_task_contrib.git
$ git commit -am "add_contrib_module"
$ git push origin main
```
