# LLM Workflow Engine (LWE) OpenRouter Provider plugin

Chat Together Provider plugin for [LLM Workflow Engine](https://github.com/llm-workflow-engine/llm-workflow-engine)

Access to [Together](https://api.together.xyz/models) chat models.
## Installation

### From packages

Install the latest version of this software directly from github with pip:

```bash
pip install git+https://github.com/llm-workflow-engine/lwe-plugin-provider-chat-together
```

### From source (recommended for development)

Install the latest version of this software directly from git:

```bash
git clone https://github.com/llm-workflow-engine/lwe-plugin-provider-chat-together.git
```

Install the development package:

```bash
cd lwe-plugin-provider-chat-together
pip install -e .
```

## Configuration

Add the following to `config.yaml` in your profile:

```yaml
plugins:
  enabled:
    - provider_chat_together
    # Any other plugins you want enabled...
  # THIS IS OPTIONAL -- By default the plugin loads all model data via an API
  # call on startup. This does make startup time longer, and the CLI completion
  # for selecting models is very long!
  # You can instead provide a 'models' object here with the relevant data, and
  # It will be used instead of an API call.
  provider_chat_together:
    models:
      # 'id' parameter of the model as it appears in the API.
      # This is also listed on the model's summary page on the OpenRouter
      # website.
      "meta-llama/Llama-3-8b-chat-hf":
        # The only parameter, and it's required.
        max_tokens: 8192
```

## Usage

From a running LWE shell:

```
/provider chat_together
/model model_name meta-llama/Llama-3-8b-chat-hf
```
