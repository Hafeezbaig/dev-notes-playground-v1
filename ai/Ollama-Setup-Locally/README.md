## **Setting Up Ollama Locally**

Ollama is a powerful framework for running and managing open-weight large language models (LLMs) on your local machine. This guide will walk you through installing, configuring, and using Ollama locally.

### **Prerequisites**
- OS: Windows, macOS, or Linux
- Docker (optional, for running in a container)
- Sufficient RAM and Disk Space (varies depending on the model you plan to run)

---

### **1. Install Ollama**
Ollama provides direct installers for different operating systems.

#### **MacOS & Linux**
Run the following command to install Ollama:
```bash
curl -fsSL https://ollama.com/install.sh | sh
```
Alternatively, you can download and install it manually from the official site:  
🔗 [Ollama Download](https://ollama.com/download)

#### **Windows**
For Windows, download the installer from:  
🔗 [Ollama Windows Installer](https://ollama.com/download)

After installation, restart your terminal and verify the installation:
```bash
ollama --version
```

---

### **2. Running Ollama**
Once installed, you can run a model using:
```bash
ollama run <model-name>
```
For example, to run **Mistral**:
```bash
ollama run mistral
```
This command will automatically download and start the **Mistral** model.

---

### **3. Available Models**
Ollama supports a variety of LLMs. You can browse and pull models using:
```bash
ollama list
```
To fetch a specific model, use:
```bash
ollama pull <model-name>
```
Example:
```bash
ollama pull gemma
```
🔗 [List of Ollama Models](https://ollama.com/library)

---

### **4. Creating a Custom Model**
You can create your own custom model using `Modelfile`. Here’s an example:

```bash
ollama create my-model -f Modelfile
```
A **Modelfile** example:
```plaintext
FROM mistral
PARAMETER temperature 0.7
```
After creating the model, run:
```bash
ollama run my-model
```
🔗 [Ollama Model Documentation](https://ollama.com/docs/models)

---

### **5. Running Ollama in Docker**
You can also run Ollama inside a Docker container:

```bash
docker run --rm -it --gpus all ollama/ollama
```
For persistent storage, mount a volume:
```bash
docker run --rm -it --gpus all -v ollama_data:/root/.ollama ollama/ollama
```
🔗 [Ollama Docker Guide](https://ollama.com/docs/docker)

---

### **6. Using Ollama with an API**
Ollama provides an API to interact with models programmatically.

#### **Start the API Server**
```bash
ollama serve
```
Then, send requests using `curl`:
```bash
curl http://localhost:11434/api/generate -d '{
  "model": "mistral",
  "prompt": "What is Ollama?"
}'
```
Or use Python:
```python
import requests

response = requests.post("http://localhost:11434/api/generate", json={
    "model": "mistral",
    "prompt": "What is Ollama?"
})

print(response.json())
```
🔗 [Ollama API Documentation](https://ollama.com/docs/api)

---

### **7. Updating Ollama**
To update Ollama to the latest version, use:

#### **MacOS/Linux**
```bash
curl -fsSL https://ollama.com/install.sh | sh
```

#### **Windows**
Reinstall the latest version from [Ollama Download](https://ollama.com/download).

Check your version after updating:
```bash
ollama --version
```

---

### **8. Uninstalling Ollama**
#### **MacOS & Linux**
```bash
rm -rf ~/.ollama
```
#### **Windows**
1. Open **Apps & Features**.
2. Locate **Ollama** and click **Uninstall**.

---

### **9. Additional Resources**
- 📖 Official Docs: [https://ollama.com/docs](https://ollama.com/docs)
- 📦 Ollama Models: [https://ollama.com/library](https://ollama.com/library)
- 🛠️ API Docs: [https://ollama.com/docs/api](https://ollama.com/docs/api)
- 🐳 Docker Guide: [https://ollama.com/docs/docker](https://ollama.com/docs/docker)
- 🗣️ Community & Support: [https://discord.gg/ollama](https://discord.gg/ollama)

---

### Guide Created by Hafeez Baig
This guide was created and maintained by [Hafeez Baig](https://www.hafeezbaig.in).

---

### Contributing & Updates
This guide is regularly updated, but technology evolves quickly. If you find outdated information or have improvements, please submit a **Pull Request (PR)** to keep it up to date. Contributions are always welcome!
