# Code Examples for Video 1

## LangSmith Tracing Integration
```python
import os
from langsmith import LangSmithTracer
from langchain import OpenAI, LLMChain

# Set environment variables
os.environ["LANGCHAIN_TRACING_V2"] = "true"
os.environ["LANGCHAIN_API_KEY"] = "<your_api_key>"

# Initialize tracer and LLM
tracer = LangSmithTracer()
llm = OpenAI(temperature=0)
chain = LLMChain(llm=llm, prompt_template="You are a helpful assistant.")

# Run chain within tracer context
with tracer:
    result = chain.run("Hello, world!")
print(result)
```

## Langfuse Tracing Integration
```python
import os
from langfuse import LangfuseTracer
from langchain import OpenAI, LLMChain

# Set environment variables
os.environ["LANGFUSE_API_KEY"] = "<your_api_key>"
os.environ["LANGFUSE_PROJECT"] = "<your_project_id>"

# Initialize tracer and LLM
tracer = LangfuseTracer()
llm = OpenAI(temperature=0)
chain = LLMChain(llm=llm, prompt_template="You are a helpful assistant.")

# Run chain with Langfuse tracer enabled
with tracer:
    result = chain.run("Hello, world!")
print(result)
```
