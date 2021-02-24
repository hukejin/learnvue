# vuebegin

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn serve
```

### Compiles and minifies for production
```
yarn build
```

### Lints and fixes files
```
yarn lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

# 用来一步步记录整个vue的知识点，通过例子、注释等完成vue整个框架的学习

## 安装
1.node安装，通过nodejs官网进行对应系统版本的安装  
2.装好nodejs后，进行环境变量设置  
3.设置好环境变量后，通过命令行查询 node -v看是否安装成功  
4.然后可以通过npm安装vue,国内先将npm的淘宝镜像注册好    
   
```
npm install vue -g
``` 
      
5.装好后，再装vue脚手架   
   
```
npm install @vue/cli -g
```
   
6.装好后，通过命令行查询 vue --version看看是否安装成功
一切顺利进行后，那么可以创建vue工程了，现在vue推出了UI界面创建工程，很方便。
2种方式创建工程。

第一种，创建空工程，然后通过vscode/webstorm等进行命令行配置
```
vue create mydemo
```
第二种，通过vue提供的界面进行选择，很方便，推荐使用
```
vue ui
```

## 安装告一段落了，现在开始创建好了工程。该工程创建时提前加好了vuex和路由功能，是手懒。
### 生命周期
在home.vue里测试了生命周期,页面初始化后，调用了
```
beforeCreate/created/beforeMount/mounted
```
当数据刷新后,添加了以下2个周期
```
beforeUpdate/updated
```
此时加入了$nextTick方法，会在updated后进行调用，这个方法是用在进行数据获取后马上调用
这样有回调可以在数据刷新界面后做下一步操作

## git学习
#### 默认加入了master，并与远程的github上的项目连接
#### 创建dev分支
```
git branch dev
git checkout dev
```

#### 在分支上实现修改这段话，然后再合并到master上
```
git merge dev
```





