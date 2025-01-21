<div align="center">
<h1>🌐 RosieExplorer: An Intelligent Web Navigation Agent</h1>
<p>Powered by Large Multimodal Models for Seamless Web Interaction</p>

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Python](https://img.shields.io/badge/python-3.10.13-green.svg)](https://www.python.org/)
[![Selenium](https://img.shields.io/badge/Selenium-4.15.2-red)](https://www.selenium.dev/)
</div>

<div align="center">
<img src="https://cdn.prod.website-files.com/674396c59212c6ea348b24e0/678ffda831f58705c1e28ca7_rosieee.png" width="800px" alt="Rosie Explorer Logo">
</div>

## 🚀 What is RosieExplorer?

RosieExplorer is a cutting-edge web automation agent that leverages the power of Large Multimodal Models (LMMs) to navigate and interact with real-world websites. By combining visual and textual understanding, RosieExplorer can execute complex web tasks autonomously while maintaining natural interaction patterns.

### Key Features

- 🎯 **End-to-End Task Completion**: Handles complex web interactions from start to finish
- 🖼️ **Visual-Text Integration**: Processes both visual and textual webpage elements
- 🌐 **Universal Compatibility**: Works across diverse websites and interfaces
- 📊 **Comprehensive Evaluation**: Built-in tools for performance assessment

## 🛠️ Quick Start

### Prerequisites
- Python 3.10+
- Chrome browser
- For Linux users: Chromium browser (e.g., `yum install chromium-browser` for CentOS)

### Installation

```bash
# Clone the repository
git clone https://github.com/rosieexplorer/web-agent.git
cd web-agent

# Set up Python environment
conda create -n rosie python=3.10
conda activate rosie
pip install -r requirements.txt
```

### Basic Usage

1. Configure your task in `data/tasks_test.jsonl`
2. Set your OpenAI API key in `run.sh`
3. Execute:
```bash
bash run.sh
```

## 📚 Dataset & Tasks

Our testing framework includes:
- 643 curated task queries
- Coverage of 15 popular websites
- 40+ diverse queries per website
- Time-sensitive tasks for booking and flight searches
- Integration with GAIA dataset validation tasks

### Task Examples
- Flight booking and price comparison
- Product research and information gathering
- News and article retrieval
- Dynamic content interaction

## ⚙️ Configuration Options

### Core Settings
```bash
python run.py \
    --test_file ./data/tasks_test.jsonl \
    --api_key YOUR_OPENAI_API_KEY \
    --headless \
    --max_iter 15 \
    --max_attached_imgs 3
```

### Visual vs Text-Only Mode
For text-only operation:
```bash
python run.py \
    --text_only \
    --api_model gpt-4-1106-preview
```

### Advanced Parameters

#### Model Configuration
- `--api_model`: Choose between vision-enabled and text-only models
- `--temperature`: Control response randomness
- `--seed`: Enable reproducible results (Beta feature)
- `--max_attached_imgs`: Manage context window size

#### Browser Settings
- `--window_width`: Default 1024
- `--window_height`: Default 768
- `--headless`: Enable background operation
- `--force_device_scale`: Optimize for accessibility tree
- `--fix_box_color`: Standardize interactive element highlighting

## 📊 Evaluation

### Automated Assessment
```bash
cd evaluation
bash run_eval.sh
```

The evaluation tool utilizes GPT-4V to analyze:
- Task completion accuracy
- Navigation efficiency
- Response appropriateness

### Results Storage
- Screenshots captured during task execution
- Interaction logs
- Performance metrics

## 🔧 Customization

### Prompt Engineering
- System prompts located in `prompts.py`
- Extensible action framework
- Customizable parsing logic

### Task Generation
Expand the task dataset using our GPT-4 prompt template:
```
Generate diverse tasks for {website} considering:
1. No video content requirements
2. Clear, achievable goals
3. Reasonable time constraints
4. Varied interaction patterns
```

## 📫 Issues and Support

For questions, issues, or contributions, please visit our [GitHub repository](https://github.com/rosieexplorer/web-agent).
