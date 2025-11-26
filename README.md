# Beancount-Trans-Assets

## 目录结构

为所有用户提供账本组织结构，目录结构如下：

![目录结构](https://daihaorui.oss-cn-hangzhou.aliyuncs.com/djangoblog/202503061727934.png)

## 账单规范

对于 23 年的账单，将 "2022_template" 文件复制粘贴重命名为 2023。23 年的所有账单存储于 2023 目录中。

以月进行记录，以年进行存档。

入门教程：[Beancount 入门教程](https://trans.dhr2333.cn/docs/blog/2024/08/17/%E5%80%9F%E8%B4%B7%E8%AE%B0%E8%B4%A6%E6%B3%95)

## 运行

若是通过 docker compose 运行的 Beancount-Trans 项目可直接通过 <http://127.0.0.1:5000> 访问

### Docker Compose

```yaml
docker compose up -d
```

### Docker Cli

```Shell
docker run -d \
    --name=beancount-trans-assets \
    -v $PWD:/Assets \
    -e BEANCOUNT_FILE=/Assets/main.bean \
    -p 5000:5000 \
    dhr2333/beancount-trans-assets:latest
```

### Command Line

```shell
pipenv install  # 安装虚拟环境
pipenv shell  # 进入虚拟环境
pip install beancount fava  # 安装包
fava main.bean  # 运行该项目
```
