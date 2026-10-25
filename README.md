# AI Agent with Structured Output

A hands-on project showing how to build an AI agent that returns **structured output** instead of free-form text. Responses follow a defined schema, so they are predictable, easy to validate, and ready to use in downstream code.

## Why Structured Output?

Free-form LLM responses are hard to parse reliably. Structured output solves this by:

- Guaranteeing a consistent response format (for example JSON that matches a schema)
- Making results easy to validate with typed models
- Letting agents plug directly into databases, APIs, and other programs

## Features

- Agent that returns responses matching a defined schema
- Typed output models for validation
- Step-by-step Jupyter notebooks you can run and modify

## Getting Started

### Prerequisites

- Python 3.10 or newer
- Jupyter Notebook or JupyterLab
- An API key for your LLM provider

### Installation

```bash
git clone https://github.com/razangit5-pixel/ai-agent-with-structured-output.git
cd ai-agent-with-structured-output
python -m venv .venv
source .venv/bin/activate    # Windows (Git Bash): source .venv/Scripts/activate
pip install jupyter pydantic
```

Install any other packages the notebooks import (for example your agent framework or LLM client).

### Configuration

Keep secrets out of the repository. Set your API key as an environment variable or in a `.env` file that is listed in `.gitignore`.

```bash
export API_KEY="your-key-here"
```

### Running

```bash
jupyter notebook
```

Open the notebook and run the cells in order.

## Example

A schema defines the shape of the agent's answer:

```python
from pydantic import BaseModel

class Answer(BaseModel):
    summary: str
    confidence: float
    sources: list[str]
```

The agent is then asked to return data matching `Answer`, and the result is validated automatically.

## Project Structure

```
ai-agent-with-structured-output/
├── *.ipynb        # lesson notebooks
└── README.md
```

## Roadmap

- [ ] Add more schema examples (nested models, enums, lists)
- [ ] Add error handling for invalid outputs
- [ ] Add a `requirements.txt`

## Author

Razan — [@razangit5-pixel](https://github.com/razangit5-pixel)
