Welcome to the repository Mohsin Raza

## 📌 Table of Contents
- [PowerShell Setup](#powershell-setup)
- [UV Basics](#uv-basics)
- [Creating and Managing Projects](#creating-and-managing-projects)
- [Adding Dependencies](#adding-dependencies)
- [Working with LiteLLM](#working-with-litellm)
- [Understanding Python Decorators](#understanding-python-decorators)
- [CrewAI Installation & Setup](#crewai-installation--setup)
- [Running CrewAI Workflow](#running-crewai-workflow)

---

## ⚡ PowerShell Setup
To begin, run the following command to install UV:

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

Check if UV is installed correctly:

```powershell
uv version
uv help
```

---

## 🎯 UV Basics
Initialize a new project:

```sh
uv init my-project
code .
```

Open the terminal and navigate into the project folder:

```sh
cd ./my-project/
uv run hello.py
```

Modify `hello.py`, rerun the script, and observe changes:

```sh
uv run hello.py
```

---

## 📦 Adding Dependencies
Install additional packages:

```sh
uv add numpy pandas
```

Verify the dependencies in the `pyproject.toml` file.

---

## 🚀 Creating and Managing Projects
Create another project:

```sh
uv init --package another-project
```

Return to VS Code and check the `pyproject.toml` file.
Navigate to `src/` and create `hello.py`:

```python
def my_function():
    print("Hello from my_function()")
```

Now, add a new command in `pyproject.toml`:

```
gloprog = "another_project.hello:my_function"
```

Run the command from the terminal:

```sh
uv run gloprog
```

Install the package in editable mode:

```sh
pip install -e .
```

---

## 🔥 Working with LiteLLM
Initialize a new project:

```sh
uv init --package litellm-project
cd litellm-project
```

Add the LiteLLM dependency:

```sh
uv add litellm
uv venv
```

Activate the virtual environment:

```sh
# Windows
.venv\Scripts\activate

# macOS/Linux
source .venv/bin/activate
```

Now, create `hello.py` in the `src/` folder:

```python
from litellm import completion
import os

os.environ["OPENAI_API_KEY"] = "ADD YOUR API KEY"
os.environ["GEMINI_API_KEY"] = "ADD YOUR API KEY"

def openai():
    response = completion(
        model="openai/gpt-4o",
        messages=[{"content": "Hello, how are you?", "role": "user"}]
    )
    print(response)

def gemini():
    response = completion(
        model="gemini/gemini-1.5-flash",
        messages=[{"content": "Hello, how are you?", "role": "user"}]
    )
    print(response)

def gemini2():
    response = completion(
        model="gemini/gemini-2.0-flash-exp",
        messages=[{"content": "Hello, how are you?", "role": "user"}]
    )
    print(response)
```

Add your API key and run:

```sh
uv run gemini
```

---

## 🧠 Understanding Python Decorators
Python decorators are functions that modify the behavior of another function without changing its structure.

Example:

```python
def my_decorator(func):
    def wrapper():
        print("Before the function is called.")
        func()
        print("After the function is called.")
    return wrapper

@my_decorator
def say_hello():
    print("Hello, world!")

say_hello()
```

Try running this in Google Colab to experiment with decorators.

---

## 🤖 CrewAI Installation & Setup
To install CrewAI, follow these steps:

### Step 1: Install Microsoft C++ Build Tools
Download from the [Visual Studio Official Site](https://visualstudio.microsoft.com/).

### Step 2: During Installation, Select:
✅ MSVC v142 or later  
✅ Windows 10 SDK  
✅ C++ CMake tools for Windows  

Restart your system after installation.

### Step 3: Upgrade Pip & Install CrewAI

```sh
pip install --upgrade pip setuptools wheel
pip install crewai
```

If using a virtual environment:

```sh
# Windows
.venv\Scripts\activate

# macOS/Linux
source .venv/bin/activate
```

If installation issues occur:

```sh
pip install hnswlib
pip install crewai
```

Verify installation:

```sh
crewai version
```

---

## ⚙️ Running CrewAI Workflow
Create a new CrewAI workflow:

```sh
crewai create flow crew_flow
dir
```

Open the project in VS Code and edit `.env`:

```sh
OPENAI_API_KEY= (Replace with GEMINI_API_KEY)
MODEL=gemini/gemini-1.5-flash
```

Run the CrewAI script:

```sh
uv run kickoff
```

---

## 🎯 Conclusion
This revision guide covered:

✅ Setting up UV, LiteLLM, and CrewAI  
✅ Running Python scripts and managing dependencies  
✅ Understanding Python decorators  
✅ Configuring API keys and virtual environments  

🚀 Keep practicing, and happy coding! 🚀
