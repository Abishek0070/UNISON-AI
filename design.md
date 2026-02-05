# System Design – UNISON AI-An Agentic Content Management System

## 1. Architecture Overview
The system is built around a single fine-tuned Large Language Model (LLM) that is orchestrated as multiple task-specific agents using an agentic workflow.

## 2. Core Model
- Base Model: LLaMA-3-8B / Mistral-7B
- Fine-tuning Method: Instruction tuning using LoRA
- Hosting Platform: Hugging Face Model Hub / Inference Endpoint

## 3. Agent Design

### 3.1 Creator Agent
- Responsible for generating and transforming content.
- Uses prompts focused on creativity and platform awareness.

### 3.2 Optimizer Agent
- Improves content quality, hooks, and CTAs.
- Focuses on engagement optimization.

### 3.3 Analyzer Agent
- Tags content by topic and intent.
- Predicts engagement level.

### 3.4 Planner Agent
- Selects best content variant.
- Suggests content planning decisions.

## 4. Agentic Workflow
1. User submits content idea
2. Creator Agent generates initial content
3. Optimizer Agent refines the content
4. Analyzer Agent evaluates and tags the content
5. Planner Agent produces the final output

## 5. Data Design
- Training data consists of instruction–input–output pairs
- Data sources include public social media content and synthetic samples

## 6. Deployment Design
- Fine-tuned model is hosted on Hugging Face
- Agents communicate with the model via API calls
- Backend orchestrates agent execution sequentially

## 7. Design Advantages
- Single model reduces complexity
- Agentic workflow improves content quality
- Modular design allows easy extension

## 8. Frontend Design
- The frontend is implemented as a web application.
- It communicates with the backend via REST APIs.
- Key views include:
  - Content input screen
  - Agent output comparison screen
  - Final content preview screen

## 9. Backend Design
- The backend is built using a lightweight API server.
- It orchestrates agent execution sequentially.
- It integrates with Hugging Face Inference APIs.
