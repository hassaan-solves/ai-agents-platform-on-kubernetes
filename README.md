# AI Agents Platform on Kubernetes

A production-oriented AI agent platform built on Kubernetes that combines
self-hosted LLM inference, model routing, RAG, memory, MCP tools,
multi-agent orchestration, observability, evaluation, and knowledge graphs.


## Overview

This project documents my hands-on work building and operating an AI agent
platform on Kubernetes.

The goal was not simply to deploy an LLM.

The goal was to understand the infrastructure and platform components required
to run AI agents as distributed systems.

The platform brings together:

- Kubernetes / Amazon EKS
- AWS Inferentia + Neuron
- vLLM
- Qwen2.5-3B
- LiteLLM
- Strands Agents SDK
- Milvus
- MCP
- A2A
- Langfuse
- OpenTelemetry
- LLM-as-a-Judge
- Neo4j


## What I Explored

- Self-hosted LLM inference on Kubernetes
- Model routing through LiteLLM
- AI agent deployment with Strands Agents SDK
- RAG and conversation memory with Milvus
- Tool integration through MCP
- Multi-agent communication using A2A
- LLM observability with Langfuse and OpenTelemetry
- LLM evaluation using an LLM-as-a-Judge
- Knowledge graph retrieval with Neo4j


## Related Article

I also documented this work in a LinkedIn article:

👉 [Beyond LLMs: The Infrastructure Behind AI Agents](https://lnkd.in/p/digFSPXP)


## Walk-through

<p align="center">

1. Kubernetes / EKS Environment<br />
<img src="screenshots/01-eks-cluster.png" />

<br /><br />

2. Self-Hosted Model Inference<br />
<img src="screenshots/02-vllm.png" />

<br /><br />

3. LiteLLM Model Gateway<br />
<img src="screenshots/03-litellm.png" />

<br /><br />

4. Strands AI Agent<br />
<img src="screenshots/04-strands-agent.png" />

<br /><br />

5. Langfuse Observability<br />
<img src="screenshots/05-langfuse.png" />

<br /><br />

6. RAG with Milvus<br />
<img src="screenshots/06-rag-milvus.png" />

<br /><br />

7. Conversation Memory<br />
<img src="screenshots/07-memory.png" />

<br /><br />

8. MCP Tool Integration<br />
<img src="screenshots/08-mcp.png" />

<br /><br />

9. Multi-Agent A2A<br />
<img src="screenshots/09-multi-agent-a2a.png" />

<br /><br />

10. LLM-as-a-Judge Evaluation<br />
<img src="screenshots/10-evaluation.png" />

<br /><br />

11. Knowledge Graph with Neo4j<br />
<img src="screenshots/11-neo4j.png" />

</p>
