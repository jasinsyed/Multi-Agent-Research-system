🔬 Multi-Agent Research System

An intelligent multi-agent AI research platform that autonomously researches a given topic across the web, analyzes the latest and most relevant sources, generates a structured research paper, and uses multiple AI reviewer agents to evaluate, debate, score, and improve the final result.

The system is designed around a collaborative agent architecture where each agent has a specialized role rather than relying on a single LLM to perform the entire research process.

---

🚀 Key Features

- 🔎 Automated Web Research
  
  - Searches the web for the latest information
  - Collects exactly 10 strong and relevant sources
  - Prioritizes recent articles, authoritative sources, and high-quality evidence
  - Removes duplicate and low-quality sources

- 🧠 Research Analysis Agent
  
  - Reads and analyzes the collected sources
  - Extracts key findings, statistics, evidence, and viewpoints
  - Identifies contradictions and knowledge gaps
  - Builds research conclusions from the available evidence

- ✍️ AI Research Writer
  
  - Generates a structured research paper from the analyzed evidence
  - Creates sections such as Abstract, Introduction, Methodology, Findings, Discussion, and Conclusion
  - Maintains source-based citations and references

- 👨‍🏫 Three AI Guide Agents
  
  - Evidence Reviewer — evaluates sources, facts, citations, and evidence quality
  - Reasoning Reviewer — evaluates logical reasoning, arguments, conclusions, and potential bias
  - Academic Reviewer — evaluates structure, methodology, writing quality, and completeness

- 💬 Agent-to-Agent Communication
  
  - Reviewer agents communicate with each other
  - Challenge and defend findings
  - Identify disagreements
  - Correct weak reasoning
  - Reach a consensus before final evaluation

- ⚖️ Final Judge Agent
  
  - Reviews the research paper and reviewer discussions
  - Calculates a weighted final score
  - Provides an approval or revision decision
  - Produces detailed improvement recommendations

- 🔄 Automatic Revision Loop
  
  - If the paper does not meet the required quality threshold, feedback is sent back to the Research Writer
  - The paper is revised and evaluated again
  - Supports controlled review cycles to prevent endless agent loops

- 📄 Research Paper Generation
  
  - Generates professionally formatted research reports
  - Supports PDF/DOCX output
  - Includes citations, references, findings, and final evaluation score

---

🏗️ System Architecture

                         ┌─────────────────────┐
                         │        USER         │
                         │   Research Topic    │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │    ORCHESTRATOR     │
                         │ Workflow Controller │
                         └──────────┬──────────┘
                                    │
                                    ▼
                    ┌──────────────────────────────┐
                    │     AGENT 1: WEB RESEARCH   │
                    │                              │
                    │ Search → Filter → Rank       │
                    │ → Select 10 Strong Sources   │
                    └──────────────┬───────────────┘
                                   │
                                   ▼
                    ┌──────────────────────────────┐
                    │     AGENT 2: RESEARCH        │
                    │          ANALYST             │
                    │                              │
                    │ Read → Extract → Compare     │
                    │ → Analyze → Conclude         │
                    └──────────────┬───────────────┘
                                   │
                                   ▼
                    ┌──────────────────────────────┐
                    │     AGENT 3: RESEARCH        │
                    │          WRITER              │
                    │                              │
                    │ Evidence → Research Paper   │
                    └──────────────┬───────────────┘
                                   │
                                   ▼
              ┌─────────────────────────────────────────┐
              │          MULTI-AGENT REVIEW             │
              │                                         │
              │  ┌──────────┐ ┌──────────┐ ┌──────────┐ │
              │  │ Evidence │ │Reasoning │ │ Academic │ │
              │  │ Reviewer │↔│ Reviewer │↔│ Reviewer │ │
              │  └──────────┘ └──────────┘ └──────────┘ │
              │          ↕         ↕         ↕          │
              │       Agent-to-Agent Discussion        │
              └───────────────────┬─────────────────────┘
                                  │
                                  ▼
                       ┌─────────────────────┐
                       │     FINAL JUDGE     │
                       │                     │
                       │ Consensus + Score   │
                       └──────────┬──────────┘
                                  │
                         ┌────────┴────────┐
                         │                 │
                     Score ≥ 8          Score < 8
                         │                 │
                         ▼                 ▼
                    FINAL PAPER       REVISION LOOP
                         │                 │
                         │                 └──→ Writer
                         │
                         ▼
                  ┌─────────────────┐
                  │ DOCUMENT ENGINE │
                  │                 │
                  │ PDF / DOCX      │
                  └────────┬────────┘
                           │
                           ▼
                     📥 FINAL REPORT

---

🤖 Multi-Agent Workflow

1. Web Research Agent

The Web Research Agent receives the user's research topic and searches the web for relevant information.

It prioritizes:

- Recent publications
- Authoritative publishers
- Research papers
- Government/official sources
- Industry reports
- Relevant evidence
- High-quality journalism

The agent selects 10 strong sources and stores their metadata, including:

Title
Author
Publisher
Publication Date
URL
Summary
Key Findings
Source Quality
Relevance

---

2. Research Analyst Agent

The Research Analyst processes the 10 selected sources.

It:

Sources
   ↓
Content Extraction
   ↓
Evidence Extraction
   ↓
Cross-Source Comparison
   ↓
Contradiction Detection
   ↓
Pattern Identification
   ↓
Research Findings
   ↓
Preliminary Conclusions

The objective is to ensure that the Research Writer works from evidence gathered from multiple sources instead of generating unsupported information.

---

3. Research Writer Agent

The Research Writer transforms the analyzed evidence into a structured research paper.

A typical paper contains:

Title
Abstract
Introduction
Background
Methodology
Literature Review
Findings
Analysis
Discussion
Limitations
Conclusion
References

The writer is instructed to use the collected sources and maintain traceable citations.

---

👨‍🏫 Multi-Agent Evaluation

The system uses three specialized AI guide agents.

🔍 Evidence Reviewer

Focuses on:

- Source credibility
- Factual accuracy
- Citation correctness
- Evidence strength
- Recency
- Unsupported claims

🧠 Reasoning Reviewer

Focuses on:

- Logical consistency
- Strength of arguments
- Conclusions
- Assumptions
- Contradictions
- Bias
- Missing perspectives

🎓 Academic Reviewer

Focuses on:

- Research structure
- Academic writing
- Methodology
- Clarity
- Completeness
- Organization
- Overall presentation

---

💬 Agent-to-Agent Discussion

The three reviewers do not simply produce independent scores.

They can review each other's findings and discuss disagreements.

Example:

Evidence Reviewer:
"The conclusion is not sufficiently supported."

Reasoning Reviewer:
"I agree. The source demonstrates correlation,
but the paper describes it as causation."

Academic Reviewer:
"The conclusion should therefore be rewritten
and the limitation explicitly mentioned."

Evidence Reviewer:
"Agreed."

This creates a collaborative evaluation process before the final score is produced.

---

⚖️ Final Evaluation

The Final Judge combines the reviewer feedback and calculates a weighted score.

Example:

Category| Weight
Evidence & Sources| 30%
Reasoning & Logic| 30%
Academic Quality| 20%
Completeness| 10%
Writing & Structure| 10%

Example result:

Evidence & Sources     8.8 / 10
Reasoning & Logic      8.5 / 10
Academic Quality       9.0 / 10
Completeness            8.3 / 10
Writing & Structure     9.1 / 10
────────────────────────────────
Overall Score           8.7 / 10

Decision: APPROVED

---

🔄 Revision Mechanism

The system can automatically send reviewer feedback back to the Research Writer.

Research Paper
      ↓
Multi-Agent Review
      ↓
Final Score
      ↓
   ┌──┴──┐
   │     │
 ≥ 8    < 8
   │     │
   │     ▼
   │   Revision
   │     │
   │     ▼
   │  Re-evaluation
   │     │
   └─────┘
      ↓
Final Paper

A maximum number of revision cycles can be configured to prevent infinite loops.

---

🛠️ Technology Stack

Core

- Python
- LangGraph
- LLM APIs
- Pydantic

AI / Agents

- Large Language Models
- Multi-agent orchestration
- Structured agent outputs
- Agent-to-agent communication

Web Research

- Tavily
- BeautifulSoup
- Web content extraction
- Source validation

Frontend

- Streamlit

Document Generation

- ReportLab
- python-docx

Data / State

- JSON-based research state
- Structured Pydantic models
- Optional database integration

---

📁 Project Structure

multi-agent-research/
│
├── app.py
│
├── agents/
│   ├── researcher.py
│   ├── analyst.py
│   ├── writer.py
│   ├── evidence_reviewer.py
│   ├── reasoning_reviewer.py
│   ├── academic_reviewer.py
│   └── final_judge.py
│
├── orchestration/
│   ├── workflow.py
│   ├── state.py
│   └── communication.py
│
├── tools/
│   ├── web_search.py
│   ├── webpage_reader.py
│   ├── source_validator.py
│   └── citation_manager.py
│
├── research/
│   ├── source_collector.py
│   ├── source_ranker.py
│   └── evidence_extractor.py
│
├── documents/
│   ├── pdf_generator.py
│   └── docx_generator.py
│
├── models/
│   ├── research_models.py
│   ├── evaluation_models.py
│   └── paper_models.py
│
├── prompts/
│   ├── researcher.txt
│   ├── analyst.txt
│   ├── writer.txt
│   ├── reviewers.txt
│   └── judge.txt
│
├── data/
│   ├── research/
│   ├── papers/
│   └── evaluations/
│
├── .env
├── requirements.txt
└── README.md

---

🎯 Example

Input

Impact of Generative AI on Software Engineering Jobs

System

🔎 Searching latest sources...
📚 Selecting 10 high-quality sources...
🧠 Analyzing evidence...
✍️ Writing research paper...
🔍 Evidence review...
🧠 Reasoning review...
🎓 Academic review...
💬 Agents discussing findings...
⚖️ Final evaluation...
🔄 Revising paper...
📄 Generating final document...

Output

Research Paper
────────────────────────────
Sources:          10
Review Agents:     3
Revision Cycles:   1
Final Score:       8.7 / 10
Status:            Approved

📄 Download PDF
📄 Download DOCX

---

🌟 Why This Project?

Traditional AI research tools often rely on a single model to search, analyze, write, and evaluate information.

This project separates those responsibilities into specialized autonomous agents.

The system demonstrates:

- Multi-agent AI architecture
- Autonomous web research
- Evidence-based reasoning
- LLM orchestration
- Agent-to-agent collaboration
- Automated peer review
- Self-correction and revision
- Source-grounded content generation
- AI-assisted document generation

The goal is to create a research workflow where AI agents research, reason, write, critique, communicate, improve, and finally deliver a validated research report.

---

📌 Future Improvements

- [ ] Add academic paper search using Semantic Scholar / Crossref
- [ ] Add citation styles such as APA, IEEE, and MLA
- [ ] Add source credibility scoring using external metadata
- [ ] Add browser-based research tools
- [ ] Add research history and user accounts
- [ ] Add interactive research graphs
- [ ] Add citation graph visualization
- [ ] Add human-in-the-loop approval
- [ ] Add multilingual research support
- [ ] Add long-term research memory
- [ ] Deploy as a cloud application

---

👨‍💻 Author

Syed Jasin

Built as an exploration of Multi-Agent AI, autonomous research, LLM orchestration, and AI-assisted knowledge generation.