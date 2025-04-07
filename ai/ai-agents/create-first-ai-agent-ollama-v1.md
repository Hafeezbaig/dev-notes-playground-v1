## 🧠 Build Your First AI Agent with CrewAI (Zero Coding, Zero Cost)

We learned how to build AI agents that **perform tasks autonomously** using **CrewAI**, an open-source framework. Unlike assistants like ChatGPT that require prompts for every step, agents can **take initiative, collaborate, and complete full tasks** on our behalf.

We used **local LLMs (like LLaMA 3.1)** with CrewAI to avoid API cost and security concerns.

---

### ✅ What We Did

1. **Understood the difference between Assistants and Agents**
2. **Explored open-source agent frameworks**: CrewAI, AutoGen, LangGraph
3. **Installed and configured CrewAI**
4. **Created 2 agents** (researcher + reporting analyst)
5. **Gave them a task** to research latest Kubernetes trends and summarize them
6. **Executed agents using local LLaMA 3.1** model via Ollama
7. **Generated a final `report.md` file**

---

### 📁 Project Structure

CrewAI CLI auto-generated a project with this structure:

```
devops-ai-project/
├── .gitignore
├── README.md
├── config/
│   ├── agents.yaml
│   └── tasks.yaml
├── src/
│   ├── main.py
│   └── crew.py
└── crew-virtual-env/
```

---

### ⚙️ Setup Instructions

#### 1. ✅ Prerequisites

- Python 3.10 to 3.13
- [Ollama](https://ollama.com) installed and configured
- A supported LLM like LLaMA 3.1 pulled via Ollama

#### 2. 🛠 Create Project Environment

```bash
mkdir crew-example
cd crew-example
python3 -m venv crew
source crew/bin/activate
```

#### 3. 📦 Install CrewAI

```bash
pip install crewai
```

---

### 🚀 Create the Agent Project

```bash
crewai create devops-ai-project
```

Then select:
- LLM Provider: **ollama**
- Model: **llama3:latest**

> Make sure LLaMA 3.1 is already downloaded:
```bash
ollama pull llama3
```

---

### 🧠 Configuring the Agents

#### config/agents.yaml

```yaml
agents:
  - role: "Kubernetes Researcher"
    goal: "Uncover cutting-edge developments in Kubernetes"
    backstory: "You are a seasoned researcher skilled at identifying Kubernetes trends."
    allow_delegation: true
    verbose: true

  - role: "Kubernetes Reporting Analyst"
    goal: "Generate a concise Markdown report from research findings"
    backstory: "You specialize in compiling technical data into clear reports."
    allow_delegation: true
    verbose: true
```

#### config/tasks.yaml

```yaml
task:
  description: "Research the top 10 latest trends in Kubernetes for 2025."
  expected_output: "A detailed Markdown report listing and explaining the 10 trends."
  agent: "Kubernetes Researcher"
  context: []
  output_file: "report.md"
  delegated_task:
    description: "Summarize the findings and generate a Markdown report."
    expected_output: "Final Kubernetes report in Markdown."
    agent: "Kubernetes Reporting Analyst"
```

---

### ✏️ Update main.py

#### src/main.py

Update the topic from default to “kubernetes” in the `main()` function:

```python
def main():
    topic = "kubernetes"
    ...
```

No other changes are needed in `crew.py`.

---

### 🧪 Running the Project

#### Install Project Dependencies

```bash
crewai install
```

This will generate a `uv.lock` file (dependency tracker).

#### Run the Agents

```bash
crewai run
```

CrewAI will:
1. Load the agents and tasks from the config
2. Use Ollama to interact with LLaMA 3.1
3. Let the first agent perform research
4. Pass findings to the second agent
5. Generate a final `report.md` file

---

### 📄 Output Example

Sample output after the run:

```
report.md

# Kubernetes Trends - 2025

1. Introduction of Sidecar-less Service Mesh
2. KubeEdge for Enhanced Edge Computing
3. Rust Adoption in Kubernetes Components
...
10. Better GPU Scheduling and Support for AI Workloads
```

> You can open and preview the `report.md` using any Markdown viewer or VS Code.

---

### 🔄 Notes

- The report may be slightly outdated if the local LLM is not trained on latest data.
- Newer LLaMA models (e.g., 3.3) can improve output once supported by CrewAI.
- For production use, switch to **OpenAI/Gemini APIs** (cost + accuracy tradeoff).

---

### 📌 Summary

- Used **CrewAI** to create multi-agent AI automation
- Ran agents locally using **LLaMA 3.1 with Ollama**
- No coding required beyond editing YAML files
- Learned how agents can collaborate to complete real-world DevOps research tasks

---

Youtube View URL - https://www.youtube.com/watch?v=fLWP5d-1jiM

