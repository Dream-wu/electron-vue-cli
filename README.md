# electron-vue-cli-new
## 框架
 - electron(v9.x)
 
 - vue-cli(v4.x)

## 入口文件
src/background.js

## 生成各平台图标
提前准备一张png图标，执行以下命令：
```
yarn electron:generate-icons
```

## 安装依赖
```
yarn install
```

### 开发环境启动
```
yarn electron:serve
```

### 编译打包
```
yarn electron:build
```
