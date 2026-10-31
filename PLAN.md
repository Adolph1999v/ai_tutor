# AI Tutor — Learning Plan

## Current stopping point

Updated October 31, 2026.

The previous application was removed locally so we can learn and rebuild from
the beginning. Its GitHub snapshot is commit
`757d03fc6a2dddede61c9775cd657147828e31cc` in
[Adolph1999v/ai_tutor](https://github.com/Adolph1999v/ai_tutor/tree/757d03fc6a2dddede61c9775cd657147828e31cc).

The project and GitHub repository are named `ai_tutor`. The local branch is
`main`. The reset and updated plan have been committed and pushed. The old
application files have been removed from GitHub's current version. The project
owner handles commits and pushes for subsequent documentation and code changes.

We have agreed on the product requirements below. New application code has not
been approved. The next step is a theory discussion about how document retrieval,
conversation memory, and a tutoring workflow work together.

## Purpose and scope

Build a local AI tutor that teaches from uploaded study material, explains its
evidence, checks understanding, and maintains continuity through a conversation.
The project is for learning RAG and producing a GitHub portfolio and LinkedIn demo.

AI teaching material will be the showcase corpus. The same application must also
work with documents about other subjects. Subject knowledge and lesson structure
must come from the selected material rather than an AI-only list built into the app.

The collection-size target is more than 100,000 words. Our working interpretation
is the total material in a selected study collection; the exact document set and
file formats will be agreed during ingestion planning. Large material must be
indexed and retrieved in relevant sections, with a separate outline for navigating
and teaching the collection. The target will be verified with measured test data.

## Learning agreement for developing this project

For each small part:

1. Explain the terms, problem, mechanism, alternatives, and tradeoffs.
2. Work through examples and discuss questions until the learner is comfortable.
3. Wait for explicit approval to implement that part.
4. Implement the agreed scope and explain the relevant code and data flow.
5. Verify the behavior and discuss the results and limitations.
6. Save a recap, decisions, open questions, and the next starting point here or
   in a linked lesson note.

Approval for a part does not approve coding later parts. Begin each new session
with a short recap so the learning process remains easy to resume.

Keep [README.md](README.md) updated with the project's purpose, current status,
and setup instructions as they become available. Keep this plan updated with
requirements, decisions, learning notes, and the next starting point. Describe
planned capabilities as targets and record completion only after verification.
Keep GitHub's About description aligned with the current project direction.

## Agreed tutor behavior

### Document structure and discovery

- Choose or create AI study material with clear headings and subheadings.
- Preserve the hierarchy and the source locations needed for citations.
- When asked "What can you teach me?", give a broad, approachable description
  based on the available material.
- Show the detailed topics when the learner asks for them.
- Teach a selected topic one subheading at a time in a sensible order.
- Clearly acknowledge when the material does not cover a requested subject.

### Teaching and collaboration

- Explain manageable portions and answer the learner's questions using the material.
- Give useful examples and identify generated examples as illustrations.
- Check understanding from time to time, with feedback and hints where useful.
- Suggest a relevant next subtopic or topic based on the lesson and learner input.
- Allow the learner to choose the direction, ask questions, or interrupt a lesson.
- Keep follow-ups useful; do not end every message with an obligatory question.

### Interactive quizzes inside the chat

- Render quiz questions as interactive chat elements with clickable answer choices.
- Also let the learner type an answer in their own words.
- Evaluate the meaning of a typed answer against the source and question criteria.
- Explain correct, partially correct, or mistaken answers with relevant evidence.
- Give targeted feedback that helps the learner understand the concept.
- Track the active quiz so an interruption does not lose the question or answer state.
- Agree on quiz frequency and feedback details during the quiz design discussion.

### Conversation continuity and topic changes

- Keep relevant context from current and previous conversations about the selected
  study material.
- Remember the active topic, current subheading, lesson position, covered material,
  and any unfinished quiz.
- When the learner changes topic, answer the new question and preserve the paused
  lesson position so the tutor can return to it immediately.
- Resolve follow-ups using the relevant history and document evidence.
- Preserve learning progress independently of the model's limited context window.
- Avoid confusing an explanation given during a detour with completion of the
  paused lesson.
- Define how saved sessions and summaries carry context forward during the memory
  discussion. Scope memory to the relevant learner and study collection.

### Evidence spotlight

- Cite the material that supports important factual claims.
- Let the learner click a citation to inspect the supporting passage in its document.
- Preserve original source text when displaying quotations and evidence.

### Challenge a claim

- Let the learner submit a claim about the material.
- Retrieve evidence and report support, contradiction, or insufficient evidence.
- Explain the result with citations.
- Do not treat a failure to find support as proof that a claim is false.

## Language and personality order

1. Build and evaluate the English tutor in normal mode.
2. Add pirate and Mario-style text personalities, then compare factual accuracy,
   source support, and teaching clarity with normal mode.
3. Explore multilingual tutoring after personalities. Tamil is the intended first
   additional language because the learner can read and validate Tamil and English.

Personality should change expression while preserving facts, citations, feedback
criteria, and lesson progress. We must test whether this requirement holds.

Spoken audio and voice agents are outside the current scope.

## Evaluation we will learn and use

Choose a small set of useful metrics for each part, with reviewed examples and
saved baselines. Compare changes using the same test cases.

- Retrieval: Precision@k, Recall@k, MRR, and nDCG as appropriate to the labels.
- Generation: answer correctness, relevance, and support from retrieved evidence.
- Citations: source existence, support for the associated claim, and claim coverage.
- Missing evidence: appropriate abstention and honest insufficient-evidence results.
- Tutoring: explanation clarity, topic coverage, quiz validity, and useful feedback.
- Continuity: follow-ups, topic interruptions, resuming lessons, and unfinished quizzes.
- Robustness: irrelevant or conflicting passages and instructions embedded in documents.
- Performance: ingestion time, retrieval and generation latency, and memory use.
- Later: factual preservation across personalities and accuracy and naturalness in Tamil.

Explore RAGAS and LLM judges alongside deterministic checks and human review.
Treat automated judge scores as measurements to inspect, rather than proof that
the tutor teaches correctly. Grounding in a document and the real-world truth of
that document are separate questions.

## Frameworks and development preferences

- Study LangChain, LangGraph, and LlamaIndex, including their overlapping responsibilities.
- Choose one or a combination after understanding the workflow and its requirements.
- Keep model inference local. Use the available Qwen model as the initial candidate;
  verify its exact configuration during setup on the M4 Max with 48 GB memory.
- Use project-local Python environments managed by `uv` and ignored environment files.
- React and Vite remain the frontend preference for the chat and interactive quizzes.
- Recreate dependencies and setup deliberately when the relevant part is approved.
- Work only in the AI Tutor (`ai_tutor`) repository in this task.

## Proposed learning sequence

This sequence is a discussion aid. Each implementation still needs its own approval.

| Part | Learning and implementation focus | Status |
| --- | --- | --- |
| 1 | RAG fundamentals, document hierarchy, conversation memory, and the tutoring workflow | Theory pending |
| 2 | Reproducible setup and document ingestion with headings, subheadings, and source metadata | Pending |
| 3 | English retrieval and cited answers, with an evaluation baseline and tests over 100,000 words | Pending |
| 4 | Lesson progression, conversation continuity, topic detours, and relevant follow-ups | Pending |
| 5 | Interactive quizzes, feedback, evidence spotlight, and claim checking | Pending |
| 6 | Integrated English evaluation, interface refinement, and a repeatable showcase | Pending |
| 7 | Pirate and Mario-style personalities with comparison against normal mode | Pending |
| 8 | Tamil retrieval and tutoring with human validation | Pending |

## Decisions still to discuss

- The source documents, formats, and reliable way to preserve their hierarchy.
- The learner's initial level and the amount of material in one teaching turn.
- How topic outlines are created and checked for coverage.
- Quiz timing, answer criteria, and how the learner resumes an interrupted lesson.
- How history and learning state persist between sessions and influence new chats.
- Framework responsibilities and the initial embedding, storage, and retrieval choices.
- Concrete acceptance checks for the English showcase.

## Decision log

| Date | Decision | Reason |
| --- | --- | --- |
| 2026-10-03 | Restart the implementation and learn one approved part at a time. | Rebuild understanding and retain context between learning sessions. |
| 2026-10-04 | Include RAGAS and other evaluation methods. | Measure what works and compare changes with evidence. |
| 2026-10-31 | Build a document tutor with AI as the showcase subject and support other subjects. | Give the project a focused demo and reusable behavior. |
| 2026-10-31 | Include evidence spotlight, claim checking, teaching, quizzes, and feedback. | Support active learning and source inspection. |
| 2026-10-31 | Build English normal mode, then personalities, then Tamil. | Validate the core teaching behavior before expanding presentation and language. |
| 2026-10-31 | Put clickable quizzes and typed answers inside chat; preserve lesson state across detours. | Make the tutor interactive and able to collaborate through a continuing lesson. |
| 2026-10-31 | Rename the local project and existing GitHub repository to `ai_tutor`; the owner will commit and push the restart. | Match the name to the tutor's purpose while keeping the repository history. |
| 2026-10-31 | Maintain README.md, PLAN.md, and the GitHub About description as the project progresses. | Make current status and learning decisions easy to follow without presenting planned features as implemented. |
