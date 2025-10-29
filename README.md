# crewai Crew

Welcome to the My_Sk_Crew Crew project, powered by [crewAI](https://crewai.com). This template is designed to help you set up a multi-agent AI system with ease, leveraging the powerful and flexible framework provided by crewAI. Our goal is to enable your agents to collaborate effectively on complex tasks, maximizing their collective intelligence and capabilities.

### Local LLM :

I'm using local LLM for this crew . 
1. In the .env file . 

```
MODEL=ollama/llama3.1:8b
API_BASE=http://localhost:11434
```

### Using different LLM for a specific Agent
In the `agents.yaml`.  add the llm provider details . Make sure the `GOOGLE_API_KEY=<yourkey>` is added in the .env file

`llm: 'gemini/gemini-2.0-flash'`

example :
```
researcher:
  role: >
    {topic} Senior Data Researcher
  goal: >
    Uncover cutting-edge developments in {topic}
  backstory: >
    You're a seasoned researcher with a knack for uncovering the latest
    developments in {topic}. Known for your ability to find the most relevant
    information and present it in a clear and concise manner.
  current_date: {current_date}
  llm: 'gemini/gemini-2.0-flash'

```

:stop: NOTE : The model prefix 'gemini/' is important to tell LiteLLM which provider to use.

In the .env file add the following to disable the telemetry if you are in secured server policies and stay completely local llm

```
# Disable CrewAI telemetry
CREWAI_DISABLE_TELEMETRY=true
OTEL_SDK_DISABLED=true
CREWAI_DISABLE_TRACKING=true
```


---

## Installation

Ensure you have Python >=3.10 <3.14 installed on your system. This project uses [UV](https://docs.astral.sh/uv/) for dependency management and package handling, offering a seamless setup and execution experience.

First, if you haven't already, install uv:

```bash
pip install uv
```

Next, navigate to your project directory and install the dependencies:

(Optional) Lock the dependencies and install them by using the CLI command:
```bash
crewai install
```
### Customizing

**Add your `OPENAI_API_KEY` into the `.env` file**

- Modify `src/my_sk_crew/config/agents.yaml` to define your agents
- Modify `src/my_sk_crew/config/tasks.yaml` to define your tasks
- Modify `src/my_sk_crew/crew.py` to add your own logic, tools and specific args
- Modify `src/my_sk_crew/main.py` to add custom inputs for your agents and tasks

## Running the Project

To kickstart your crew of AI agents and begin task execution, run this from the root folder of your project:

```bash
$ crewai run
```

This command initializes the my_sk_crew Crew, assembling the agents and assigning them tasks as defined in your configuration.

This example, unmodified, will run the create a `report.md` file with the output of a research on LLMs in the root folder.

## Understanding Your Crew

The my_sk_crew Crew is composed of multiple AI agents, each with unique roles, goals, and tools. These agents collaborate on a series of tasks, defined in `config/tasks.yaml`, leveraging their collective skills to achieve complex objectives. The `config/agents.yaml` file outlines the capabilities and configurations of each agent in your crew.

## Support

For support, questions, or feedback regarding the MySkCrew Crew or crewAI.
- Visit our [documentation](https://docs.crewai.com)
- Reach out to us through our [GitHub repository](https://github.com/joaomdmoura/crewai)
- [Join our Discord](https://discord.com/invite/X4JWnZnxPb)
- [Chat with our docs](https://chatg.pt/DWjSBZn)

Let's create wonders together with the power and simplicity of crewAI.
