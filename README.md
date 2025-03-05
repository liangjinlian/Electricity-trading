# 灰山石能源交易算法平台

这是一个电力负荷预测与分析系统，可以帮助用户预测电力负荷并进行分析。

## 项目说明

本项目包含以下功能：

- 电力负荷预测
- 电价预测
- 数据可视化分析

## 部署说明

### 方法一：使用 Vercel 部署（简化版）

当前版本为简化版，预测功能使用模拟数据。完整功能需要部署后端服务。

1. 在 GitHub 上创建一个新仓库
2. 将代码推送到该仓库：
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/你的用户名/仓库名.git
   git push -u origin main
   ```
3. 在 [Vercel](https://vercel.com) 上注册账号并连接 GitHub
4. 导入刚刚创建的仓库
5. 部署设置保持默认即可
6. 点击部署，等待部署完成
7. 部署完成后，Vercel 会提供一个可访问的 URL

### 方法二：完整功能部署（需要后端服务）

如果需要完整的预测功能，需要同时部署前端和后端：

1. **前端部署**：按照方法一部署到 Vercel
2. **后端部署**：

   - 在支持 Python 的服务器上部署后端（如 Heroku、PythonAnywhere 等）
   - 安装所需依赖：
     ```bash
     pip install flask flask-cors pandas numpy scikit-learn imblearn joblib tensorflow xgboost openpyxl
     ```
   - 上传 `app.py`、`load_prediction.py` 和 `随机森林算法` 文件夹
   - 启动后端服务：
     ```bash
     python app.py
     ```
   - 记录后端服务的 URL
3. **连接前后端**：

   - 修改前端代码中的 API 调用地址，指向你的后端服务 URL
   - 重新部署前端

## 本地开发

如果要在本地开发和测试：

1. 克隆仓库：

   ```bash
   git clone https://github.com/你的用户名/仓库名.git
   cd 仓库名
   ```
2. 安装后端依赖：

   ```bash
   pip install flask flask-cors pandas numpy scikit-learn imblearn joblib tensorflow xgboost openpyxl
   ```
3. 启动后端服务：

   ```bash
   python app.py
   ```
4. 使用任意 HTTP 服务器启动前端，例如：

   ```bash
   # 如果安装了 Python
   python -m http.server 8000

   # 或使用 Node.js 的 http-server
   npx http-server
   ```
5. 在浏览器中访问 `http://localhost:8000`

## 注意事项

- 简化版使用 JavaScript 模拟数据，不具备真实预测能力
- 完整功能需要部署 Python 后端服务
- 预测模型需要足够的训练数据才能提供准确预测
