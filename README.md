# Fara-7B

This repository will host a copy of the [microsoft/fara](https://github.com/microsoft/fara) project so you can run the Fara‑7B agentic model locally.

**Installation instructions**

1. **Clone the official Fara repo**:
   ```bash
   git clone https://github.com/microsoft/fara.git
   cd fara
   ```
2. **Create a Python 3.10+ virtual environment**:
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```
3. **Install the package and dependencies**:
   ```bash
   pip install -e .
   playwright install
   ```
   The project depends on Playwright (>=1.51), OpenAI, Pillow, Tenacity, PyYAML, JSONSchema, Browserbase, and vllm>=0.10.0, as specified in `pyproject.toml`.
4. **Host the model**:
   * **Self-host** (requires a GPU):
     ```bash
     vllm serve "microsoft/Fara-7B" --port 5000 --dtype auto
     ```
   * **Azure Foundry**: Deploy `microsoft/Fara-7B` via Azure Foundry and update `endpoint_configs/fara-7b-hosting-*.json` with your endpoint URL and API key.
5. **Run the agent**:
   ```bash
   fara-cli --task "Your task here" --start_page "https://www.bing.com"
   ```

After cloning `microsoft/fara`, you can copy the project files into this repository (for example by uploading files via the GitHub web interface or using `git remote add` and `git push`). This README summarises the setup steps and will be updated once the code is imported.
