**Guide to Deploying Ollama Server on Android Phones**  
[中文文档](./README_CN.md)
📱 **Build a Local AI Server with Just an Android Phone (No Root Required)! Step-by-Step Tutorial**  

✨ **Acknowledgements**  

Special thanks to the following open-source projects and developers for their outstanding contributions to the tech community:  

- `Ollama` Development Team  
- `Termux` Development Team  
- All open-source contributors maintaining backend tools  
- Every developer working in the AI field  

---

### 🧰 **Core Toolchain**  

| Type       | Name           | Version/Notes                                      |  
|------------|----------------|---------------------------------------------------|  
| Device     | iQOO Neo9sp    | Demo device                                       |  
| Terminal   | Termux         | [Official Site](https://termux.dev) / [GitHub Mirror](https://github.com/termux/termux-app/releases) |  
| Environment| proot-distro   | Linux container management tool                   |  
| Engine     | Ollama         | Open-source large model service framework         |  

---

### 🧠 **Demo Models**  

- `DeepSeek-r1:7b` (7B parameter version)  
- `DeepSeek-r1:1.5b` (1.5B parameter lightweight version)  

---

## 1. 🏗️ **Environment Setup**  

### **Install Termux Terminal**  

▸ Official Source: [Termux Website](https://termux.dev)  
▸ Alternative: [GitHub Releases](https://github.com/termux/termux-app/releases)  

> 💡 Recommended to install via F-Droid repository for automatic updates.  

---

## 2. **Installation & Configuration**  

1. **Initialize Termux**  

   ```bash  
   termux-setup-storage  
   pkg install proot-distro  
   ```  

2. **Deploy Debian Environment**  

   ```bash  
   pd install debian  
   pd login debian  
   ```  

3. **Install Ollama Server**  

   ```bash  
   curl -fsSL ollama.com/install.sh | sh  
   ollama serve  
   ```  

---

## 3. **Running & Usage**  

- **Launch a Model**  
  - Create a new Termux session (do not close the original session):  
  ```bash  
  ollama run model_name  
  ```  

---

## 4. **Advanced Optimization**  

- **Frontend App Recommendations**  
  - Recommended tools: `ChatBox`, `Ollama Mobile Frontend`  

- **Background Configuration**  
  - In Android settings, allow Termux to:  
    - Use high power consumption in the background  
    - Run continuously in the background  

---

## 5. **Environment Variables**  

- `OLLAMA_HOST`  
  Open host port in `host:port` format. Alternatively, use `:port` to bind to `localhost:port`.  

- `OLLAMA_MODELS`  
  Absolute path to save models.  

- `OLLAMA_ORIGINS`  
  Configure CORS. Set to `*` to allow all cross-origin requests (required for API usage).  

- `OLLAMA_DEBUG`  
  Set to `1` to enable detailed debug logs during `ollama serve`.  

- ~~`CUDA_VISIBLE_[device]`~~  
  ~~Configure allowed GPUs (requires CUDA installation). Set to non-zero to enable GPU inference.~~  

- ~~`OLLAMA_MAX_LOADER_MODELS`~~  
  ~~Maximum number of models allowed to run simultaneously on a single GPU.~~  

**Note**: Strikethrough variables are irrelevant for most phones, as they lack Nvidia GPU support.  

---

## 6. **Important Notes**  

❗ Keep the Termux session active after running `ollama serve`.  
❗ Ollama installation and model downloads require stable network connectivity.
