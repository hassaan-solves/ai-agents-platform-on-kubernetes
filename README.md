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

👉 [The Infrastructure Behind Production Ready AI Agents](https://lnkd.in/p/digFSPXP)


## Walk-through

<p align="center">

1. Setting Up the Kubernetes Environment<br />
The platform starts with an Amazon EKS cluster where the AI infrastructure
and supporting services are deployed.<br />
<img src="screenshots/01-eks-cluster.png" />

<br /><br />

2. Running the LLM with vLLM<br />
Qwen2.5-3B is served through vLLM on AWS Inferentia using AWS Neuron,
providing the inference layer for the agents.<br />
<img src="screenshots/02-vllm.png" />

<br /><br />

3. Adding a Model Gateway with LiteLLM<br />
LiteLLM provides a common interface for the agents and handles model
routing between the available inference providers.<br />
<img src="screenshots/03-litellm.png" />

<br /><br />

4. Connecting an Agent to the Model<br />
A Strands agent connects to the model through LiteLLM and can reason over
user requests before deciding how to respond or use available tools.<br />
<img src="screenshots/04-strands-agent.png" />

<br /><br />

5. Adding LLM Observability<br />
Langfuse and OpenTelemetry capture the agent's LLM calls, tool invocations,
decisions, latency, and token usage.<br />
<img src="screenshots/05-langfuse.png" />

<br /><br />

6. Adding RAG with Milvus<br />
The agent retrieves relevant product and FAQ information from Milvus
before generating a response.<br />
<img src="screenshots/06-rag-milvus.png" />

<br /><br />

7. Adding Conversation Memory<br />
Previous conversation turns are stored and retrieved from Milvus so the
agent can use relevant context from earlier interactions.<br />
<img src="screenshots/07-memory.png" />

<br /><br />

8. Connecting External Tools through MCP<br />
An MCP server exposes tools such as order lookup, inventory checks, and
return initiation. The agent discovers and invokes these tools dynamically.<br />
<img src="screenshots/08-mcp.png" />

<br /><br />

9. Connecting Multiple Agents with A2A<br />
An orchestrator routes requests to specialized agents. The Order Agent
handles order-related tasks while the Product Agent handles product
knowledge and retrieval.<br />
<img src="screenshots/09-multi-agent-a2a.png" />

<br /><br />

10. Evaluating Agent Responses<br />
A stronger model is used as an LLM-as-a-Judge to evaluate responses from
the self-hosted model for accuracy, helpfulness, and safety.<br />
<img src="screenshots/10-evaluation.png" />

<br /><br />

11. Adding a Knowledge Graph with Neo4j<br />
Customer, order, product, category, and policy relationships are represented
as a graph to support structured relationship-based retrieval.<br />
<img src="screenshots/11-neo4j.png" />

</p>
