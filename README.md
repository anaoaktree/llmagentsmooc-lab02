# LLM Security, Writing Attack Prompts

## Overview
This project is designed to evaluate the effectiveness of different prompt hacking techniques in extracting sensitive information (secret keys) from Large Language Models (LLLMs). The goal is to use attack prompts to successfully extrack the secret keys in the system prompts. More information in Instructions.md.
This is a solution to lab02 from the [LLM Agents MOOC](https://llmagents-learning.org/f24)

---

## How It Works

1. **Design System Prompts**
- `system_prompt_1` is designed to be naive. `system_prompt_1_1` is a variation. 
- `system_prompt_2` is designed to be more robust and include some defense mechanisms. `system_prompt_2_1` is a variation. 

2. **Design Attack Prompts**
- `attack_1` is an attack for `system_prompt_1` (and `system_prompt_1_1`).
- `attack_2` is an attack for `system_prompt_2` (and `system_prompt_2_1`).

I found useful to have two attack files when starting (`attack_1_1`), to quickly test some changes side by side, but it is optional. I used  `attack_1` and `attack_2` for the lab submission. 

3. **Test the Attacks**
- `test_attacks` generates N random secret keys and tests each attack against each system prompt N times.
At the time of submission, `attack-2` fails 1 test in 15 with `system_prompt_2` and passes all tests with `system_prompt_2_1`
---

## Setup and Installation

1. **Clone the Repository**:
 ```bash
 git clone <repository_url>
 cd <repository_name>
 ```

2. **Create and Activate a Virtual Environment**:
 ```bash
python3 -m venv env
source env/bin/activate  # For macOS/Linux
.\env\Scripts\activate   # For Windows
  ```

3. **Install Dependencies**:
 ```bash
pip install -r requirements.txt
  ```

4. **Set Up OpenAI API Key**:
- Create an OpenAI API key [here](https://platform.openai.com/docs/quickstart).
- Store it as an environment variable

 ```bash
export OPENAI_API_KEY=your_api_key  # For macOS/Linux
set OPENAI_API_KEY=your_api_key    # For Windows
  ```
---

## Running the Project

1. **Run the Main Script**:
 ```bash
python test_attacks.py
  ```
