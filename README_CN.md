📱 **仅用安卓手机搭建本地AI服务器！手把手教程**

✨ **致谢声明**  

特别鸣谢以下开源项目及开发者对技术界的卓越贡献：  

- `Ollama` 开发团队

- `Termux` 开发团队

- 所有幕后维护工具的开源贡献者  

- 每一个在AI领域耕耘的开发者

---

### 🧰 **本期核心工具链**  

| 类型 | 名称 | 版本/备注 |  
|------|------|-----------|  
| 设备 | iQOO Neo9sp | 演示机型 |  
| 终端 | Termux | [官网下载](https://termux.dev) / [GitHub镜像](https://github.com/termux/termux-app/releases) |  
| 环境 | proot-distro | Linux容器管理工具 |  
| 引擎 | Ollama | 开源大模型服务框架 |  



### 🧠 **演示模型清单**  

- `DeepSeek-r1:7b` (70亿参数版本)  

- `DeepSeek-r1:1.5b` (15亿参数轻量版)  

---

## 一、🏗️ 环境准备  

### **安装Termux终端**  

▸ 官方渠道：[Termux官网](https://termux.dev)  

▸ 备用方案：[GitHub Releases](https://github.com/termux/termux-app/releases)  

> 💡 建议优先从F-Droid仓库安装以获得自动更新

---

## 二、安装与配置  

1. **初始化Termux**  

   ```bash  

   termux-setup-storage  

   pkg install proot-distro  

   ``` 

2. **部署Debian环境**  

   ```bash  

   pd install debian  

   pd login debian  

   ```  

3. **安装Ollama服务端**  

   ```bash  

   curl -fsSL ollama.com/install.sh | sh  

   ollama serve  

   ```  

---

## 三、运行与使用  

- **启动模型**  

  - 新建Termux会话（勿关闭原会话）  

  ```bash  

  ollama run model_name  

  ```  

---

## 四、进阶优化  

- **前端应用推荐**  

  - 可选工具：`ChatBox`、`Ollama手机前端`  



- **后台配置**  

  - 安卓设置中允许Termux：  

    - 后台高耗电  

    - 后台持续运行  

---

## 五、环境变量

 - `OLLAMA_HOST` 开放的主机端口，格式为 `host:port`, 也可以写为:port(有冒号), 代表服务器开放在localhost:port上.



 - `OLLAMA_MODELS` 保存模型的绝对路径.

  

 - `OLLAMA_ORIGINS` 配置跨域，想要使用ollama的api，这一步是必须的，直接设置为代表允许所有跨域请求.

  

 - `OLLAMA_DEBUG` 设置为1时，将在ollama serve命令运行时产生更多调试信息.

  

 - ~~`CUDA_VISIBLE_[device]` 设置允许使用的gpu(应该需要先安装cuda？忘了)，非0时可以使用gpu进行推理.~~

  

 - ~~`OLLAMA_MAX_LOADER_MODELS` 单个GPU最多同时运行的模型数量.~~

  

删除线标记的环境变量没必要看, 因为常规手机不支持 Nvidia 显卡.

---

## 六、注意事项  

❗ 运行`ollama serve`后需保持Termux会话活跃  

❗ `ollama`的安装与模型下载依赖网络稳定性

