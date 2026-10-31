# AI Tutor

AI Tutor is a learning and portfolio project for building a local tutor using
Retrieval-Augmented Generation (RAG). The goal is to turn uploaded study material
into a continuing lesson with explanations, source evidence, practice, and feedback.

**Status: Planning.** This repository currently contains the project documentation.
Application implementation has not started. The capabilities described below are
planned, and setup instructions will be added as each part is built and verified.

AI teaching material will be used for the showcase. The tutor is also intended to
work with documents about other subjects, with its content guided by the selected
study material.

The planned learning experience will let a user:

- Ask what the tutor can teach, receive a broad overview, and request a topic list
  based on document headings and subheadings.
- Learn a chosen topic one subheading at a time, ask questions, and receive relevant
  suggestions for what to study next.
- Answer quizzes inside the chat by clicking an answer or typing in their own words,
  then receive explanations, hints, and feedback.
- Ask about a different topic during a lesson and return to the previous lesson
  position, including any unfinished quiz.
- Inspect the source passage behind a citation through an evidence spotlight.
- Challenge a claim and see supporting evidence, contradicting evidence, or a clear
  explanation that the material provides insufficient evidence.

The collection-size target is **more than 100,000 words** across a selected study
collection. The system will index the material and retrieve relevant sections for
each interaction. A document outline will support lesson navigation and coverage.
This target will be validated with test material and measured results.

Development will follow this order:

1. Build and evaluate the English tutor in normal mode, including citations,
   lesson continuity, quizzes, and feedback.
2. Add pirate and Mario-style text personalities and evaluate whether they preserve
   factual accuracy, source support, and teaching clarity.
3. Explore Tamil tutoring, with human review by a reader fluent in Tamil and English.

We will study LangChain, LangGraph, and LlamaIndex, then choose tools according to
the tutor's requirements. Python with `uv`, project-local virtual environments,
local Qwen inference, and a React/Vite interface are the current development
preferences. Framework responsibilities, document formats, embeddings, storage,
and retrieval methods are still to be discussed and selected.

Evaluation is part of the learning process. We will explore RAGAS alongside
retrieval metrics, answer correctness, faithfulness to sources, citation checks,
conversation continuity, quiz quality, response time, and memory use. Reviewed
test questions and human feedback will help us interpret automated scores. Saved
baselines will make later changes comparable.

Each part follows the same development process: explain the theory, discuss
examples and questions, obtain approval for that part, implement it, test the
behavior, and record a recap. The project is intended to make the design decisions
and RAG techniques understandable as they are introduced.

The detailed requirements, learning sequence, decisions, and current stopping
point are maintained in [PLAN.md](PLAN.md). These documents will be updated as
the project progresses, with planned features and verified results identified
clearly.
