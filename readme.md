
```markdown
# 🔐 SecureChain Backend

A lightweight FastAPI backend integrated with the `Enhanced-Slither-Auditor-7B` LLM (GGUF format), designed to detect vulnerabilities in Solidity smart contracts.

---

## 🚀 Features

- Smart contract auditing via local LLM (no OpenAI keys needed)
- Lightweight, fast, and Dockerized
- CORS-enabled for seamless frontend integration
- Deployable to Fly.io or Railway

---

## 🧱 Project Structure

```

securechain-backend/
├── main.py                # FastAPI app
├── requirements.txt       # Python dependencies
├── Dockerfile             # Container config
├── start.sh               # Server launch script
└── models/
└── Enhanced-Slither-Auditor-7B.Q4\_K\_M.gguf

````

---

## ⚙️ Requirements

- Python 3.10+
- `llama-cpp-python`
- GGUF model (e.g., [Enhanced-Slither-Auditor-7B](https://huggingface.co/securechain/Enhanced-Slither-Auditor-7B))

---

## 🔧 Local Setup

```bash
# Clone the repo
git clone https://github.com/your-username/securechain-backend.git
cd securechain-backend

# Install dependencies
pip install -r requirements.txt

# Run the API
uvicorn main:app --reload
````

---

## 🐳 Docker Usage

```bash
# Build the image
docker build -t securechain-backend .

# Run the container
docker run -p 8000:8000 securechain-backend
```

---

## ☁️ Deployment Options

### ▶️ Fly.io

```bash
curl -L https://fly.io/install.sh | sh
fly auth login
fly launch      # Accept defaults
fly deploy
```

### ▶️ Railway

1. Push your code to GitHub.
2. Go to [https://railway.app/new](https://railway.app/new)
3. Select “Deploy from GitHub.”
4. Railway auto-detects your Dockerfile.

---

## 🌐 Frontend Integration Example

```html
<textarea id="contractInput"></textarea>
<button onclick="auditContract()">Audit</button>
<pre id="result">Audit output will appear here...</pre>

<script>
  async function auditContract() {
    const code = document.getElementById("contractInput").value;
    const formData = new FormData();
    formData.append("code", code);

    const res = await fetch("https://your-backend-url.com/audit", {
      method: "POST",
      body: formData
    });

    const data = await res.json();
    document.getElementById("result").textContent = data.result;
  }
</script>
```

---

## 🧠 Credits

Built using:

* [FastAPI](https://fastapi.tiangolo.com)
* [llama-cpp-python](https://github.com/abetlen/llama-cpp-python)

Model: `Enhanced-Slither-Auditor-7B.Q4_K_M.gguf` by SecureChain AI

---

## 🛡️ License

MIT License

```
```
