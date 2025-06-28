# **DialectAI: Multi-Agent Debate DAG**


A fully modular, LangGraph-powered system where two AI agents (Scientist vs. Philosopher) engage in an 8-round structured debate on a user-provided topic. The system features isolated memory views, strict turn validation, and an automated judging mechanism — all running from a clean CLI interface.

---

##  Features Delivered

-  8 Rounds of alternating agent arguments  
-  Isolated memory access — no full-state leakage  
-  Turn validation and duplicate argument prevention  
-  Judge node with summary, rationale, and winner  
-  CLI-based execution and interaction  
-  Complete logging with timestamps (`debate_log.txt`)  
-  LangGraph-style DAG diagram  
-  Fully modular Python architecture  
-  Examples of real debates included

---

## How to Run

### 1. Set Up Environment

```bash
python3.10 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### 2. Add Your OpenAI API Key

Create a `.env` file in the root directory:

```
OPENAI_API_KEY=your-api-key-here
```

Alternatively, you can export it directly:

```bash
export OPENAI_API_KEY=your-api-key-here
```

### 3. Run the System

```bash
python main.py
```

You’ll be prompted to enter a debate topic via CLI. The full 8-round debate will then play out automatically, ending with the judge's summary and verdict.

---

## File Structure

```
DialectAI_multi_agent_debate.zip/
│
├── main.py                     # CLI entry point + LangGraph setup
│
├── nodes/
│   ├── user_input_node.py      # Accepts topic from user
│   ├── agent_node.py           # Logic for Scientist & Philosopher agents
│   ├── memory_node.py          # Stores relevant agent memory
│   ├── judge_node.py           # Summarizes and scores debate
│   ├── validation_node.py      # Enforces turn rules and uniqueness
│   └── validators.py           # Helper validation utilities
│   └── __init__.py
│
├── utils/
│   ├── logging_utils.py        # Logs all transitions with dual time
│   └── __init__.py
│
├── schema.py                   # Central schema for LangGraph state
├── dag_diagram.py              # Graphviz diagram generator
├── requirements.txt            # All dependencies including LangGraph & Graphviz
├── .env                        # (Here the API Key needs to be added) 
├── debate_log.txt              # Output log with all state transitions
├── dag_diagram.png             # Visual DAG layout
└── Debate Transcript_Sample.pdf         # Four completed debate transcripts (for review)
└── Presentation_AgentDebate_DialectAI.pdf
```

---

## DAG Visualization

The LangGraph DAG is rendered using `graphviz`. It shows the flow between:

- UserInput → Validate → Agent → Memory → Repeat (8 rounds) → JudgeNode

You can generate or preview the DAG via:

```bash
python dag_diagram.py
```

Output is saved as: `dag_diagram.png`

---

## Additional Examples

To showcase system consistency, we've included:

**`Debate Transcript_Sample.pdf`** — a document with **4 fully recorded debate examples** across diverse topics. Each contains all 8 rounds and the final judgment.

---

## Logging and Traceability

All major events — from node inputs/outputs to final decisions — are logged in:

```text
debate_log.txt
```

Each entry includes both UTC and local timestamps for auditability.

---

## Final Delivery Checklist

- [x] Structured 8-Round Debate
- [x] Memory Isolation Per Agent
- [x] Turn Enforcement + Duplicate Check
- [x] CLI Topic Input and Flow
- [x] Judge with Summary, Rationale, Winner
- [x] DAG Diagram via Graphviz
- [x] Full Logging to `debate_log.txt`
- [x] Modular Source Code
- [x] Easy Setup with `requirements.txt`
- [x] Additional Examples Provided

---

## Demo video link :

https://1drv.ms/v/c/f5acb3ec174cc281/EXrfn8gWGGVCmbr0IzE_gaABBPU3DIlbMoFk4tUlqEbvPQ

---
## License
This repository is part of project-based contribution. All components are modular, testable, and production-aligned. Redistribution or open-sourcing is not intended.

---
### Author
Alekya Rani Seerapu
