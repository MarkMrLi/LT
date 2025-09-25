    # 使用官方的 Node.js 20 镜像作为基础
    FROM node:20-slim

    # 在镜像中创建一个工作目录
    WORKDIR /app

    # 将配置文件和依赖清单复制到镜像中
    COPY package.json .
    COPY package-lock.json .
    COPY .secretlintrc.json .

    # 安装依赖
    RUN npm ci

    # 设置容器的入口点，当容器运行时默认执行这个命令
    ENTRYPOINT ["npx", "secretlint", "--secretlintrc", "/app/.secretlintrc.json"]
    
