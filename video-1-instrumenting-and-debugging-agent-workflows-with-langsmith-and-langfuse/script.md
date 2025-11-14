# Script for Video 1: Instrumenting and Debugging Agent Workflows with LangSmith and Langfuse

## Introduction (0:00–0:30)
**Narration:**
In this video, we will instrument a multi-agent workflow using LangSmith and Langfuse, and see how trace logs help us debug and improve our agents.

## Project Setup (0:30–1:30)
**Narration:**
First, ensure you have Python 3.9+ installed, OpenAI API credentials, and LangSmith and Langfuse accounts. Activate your virtual environment and install dependencies:

```bash
pip install langchain langsmith langfuse openai
```

## Integrating LangSmith (1:30–3:00)
**Narration:**
Next, we will enable LangSmith tracing. Set your environment variables and wrap the agent workflow:

```bash
export LANGCHAIN_TRACING_V2=true
export LANGCHAIN_API_KEY=<your_api_key>
```

In your Python code, import and initialize the tracer:

```python
from langsmith import LangSmithTracer
tracer = LangSmithTracer()
``` 

Wrap your agent execution in the tracer context and run a sample query to see traces in the LangSmith UI.

## Integrating Langfuse (3:00–5:00)
**Narration:**
Now, let's add Langfuse tracing. Import and configure the SDK with your API key and project ID:

```bash
export LANGFUSE_API_KEY=<your_api_key>
export LANGFUSE_PROJECT=<your_project_id>
```
```python
from langfuse import LangfuseTracer
tracer = LangfuseTracer()
``` 

Decorate or wrap your agent workflow with Langfuse tracer and run a test query to generate traces in the Langfuse dashboard.

## Visualizing and Interpreting Traces (5:00–7:00)
**Narration:**
In the LangSmith and Langfuse web UIs, you can explore each agent step, LLM call, and tool invocation. Use filters to isolate errors and latency issues for faster debugging.

## Debugging Common Issues (7:00–8:30)
**Narration:**
Let's simulate an error, like an invalid tool call. With trace metadata, you can pinpoint the failure location and fix it. Rerun the workflow to confirm resolution.

## Summary and Next Steps (8:30–9:00)
**Narration:**
Today we covered instrumentation, trace generation, and debugging with LangSmith and Langfuse. Apply these techniques to your own multi-agent workflows for improved observability and reliability.
