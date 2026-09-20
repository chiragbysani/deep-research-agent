# Deep Research Agent  Multi-Model AI Reasoning System:
A multi-model AI research agent that combines live web search with advanced LLM reasoning techniques — Chain-of-Thought, Self-Consistency, Sequential Revision, and Tree-of-Thoughts — to produce accurate, well-reasoned answers to complex questions.

#What It Does:

-Searches the web live using DuckDuckGo to fetch up to date information.

-Uses Chain of Thought (CoT) prompting for step by step reasoning.

-Runs Self-Consistency  multiple reasoning paths with majority voting for higher accuracy.

-Applies Sequential Revision  iteratively refines answers across multiple passes.

-Explores Tree of Thoughts (ToT)  beam search based thought exploration and scoring.

-Runs entirely on device using two open source LLMs via Ollama no paid API needed.

#Tech Stack:

-Primary LLM (Reasoning):	DeepSeek R1 8B (via Ollama).

-Secondary LLM:	Llama 3.2 3B (via Ollama).

-Web Search:	DuckDuckGo Search (DDGS).

-LLM Framework:	LangChain + OpenAI-compatible API.

-ML Libraries:	PyTorch, Transformers.

-Runtime:	Google Colab (T4 GPU).

#Sample Output:

Input: "What is photosynthesis?"

Draft 1: Photosynthesis is the process by which plants convert light energy
into chemical energy, producing glucose and oxygen.

Draft 2: (Revised — cleaner and more accurate)
Photosynthesis requires three inputs: water, CO2, and light energy
6 CO2 + 6 H2O + light → C6H12O6 + 6 O2

Final Answer: Photosynthesis is the process by which plants, algae, and
some bacteria convert light energy into chemical energy, producing glucose
and releasing oxygen — essential for life on Earth.

Input: "What are the best resources to learn ML in 2025?"
→ Agent searched the web, synthesized results across multiple sources,
   and produced a structured, categorized resource guide

#Reasoning Techniques Implemented:

* Chain-of-Thought(CoT): Forces step-by-step reasoning before the final answer.
  
*Self-Consistency: Runs multiple CoT paths, picks the most common answer via majority vote.

*Sequential Revision: Iteratively improves the draft answer across multiple passes.

*Tree-of-Thoughts(ToT): Explores multiple reasoning branches, scores and selects the best path.

#How to Run:

# Install dependencies
!apt-get install -y zstd
!curl -fsSL https://ollama.com/install.sh | sh
!pip install -q torch==2.9.0 transformers==4.57.1
!pip install -q langchain==0.3.26 langchain-openai==0.3.27 langchain-community==0.3.27
!pip install -q openai==1.86.0 ddgs==9.4.0 ollama

# Start Ollama server
import subprocess, time
subprocess.Popen(["ollama", "serve"])
time.sleep(5)

# Pull both models
!ollama pull llama3.2:3b
!ollama pull deepseek-r1:8b

# Run the notebook
# Open research_agent.ipynb in Google Colab and run all cells

#Author:
Chirag A Bysani

GitHub: chiragbysani

Email: chiragbysani98@gmail.com

