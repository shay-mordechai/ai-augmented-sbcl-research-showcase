# 🔬 Compiler Behavior Exploration: SBCL Scope Analysis

## 💡 Why This Project?

During my studies, I became interested in how compile-time systems enforce isolation rules internally.

One question kept bothering me:

> If macros execute during compilation without a traditional runtime stack, what actually enforces variable isolation and scope separation?

Instead of approaching this only theoretically, I designed a small automated research experiment around SBCL (Steel Bank Common Lisp) to explore compiler behavior in practice.

---

## 🎯 Research Goal

The goal of this project was to explore how SBCL handles:

* lexical vs dynamic scope interactions
* macro expansion behavior
* symbol handling edge cases
* compiler stability under unusual structured inputs

This was approached as a lightweight AI-assisted fuzzing and behavior exploration project.

---

## 🛠️ Methodology: AI-Assisted Research

To accelerate experimentation, I used AI-assisted tooling (GitHub Copilot / Claude Agent in Copilot) to help generate structured Lisp test inputs and automate repetitive testing workflows.

The research process itself — including hypothesis selection, experiment direction, target selection, and result analysis — was performed manually.

A lightweight Python harness was used to:

* execute SBCL with generated inputs
* automate repeated test execution
* monitor crashes, hangs, and unexpected behavior
* iterate quickly over structured edge-case scenarios

---

## 🔍 Key Observations

During testing, several interesting edge cases and unexpected behaviors were identified:

### 1. Scope Interaction Behavior

Certain combinations involving dynamic binding (`proclaim special`) produced behavior that interacted unexpectedly with lexical assumptions during macro-related flows.

### 2. Extreme Input Handling

Very long symbol names triggered reproducible instability and crash conditions.

### 3. Macro Expansion Limits

Deep or recursive macro expansion patterns could lead to resource exhaustion and compiler stress conditions.

> These findings are presented as compiler edge cases and unexpected behaviors, not confirmed security vulnerabilities.

Some behaviors were reported as security-relevant observations (CERT-IL #11265).

---

## 🧪 Research Approach

### 1. Hypothesis-Driven Exploration

Rather than performing fully random fuzzing, the project focused on targeted experimentation around:

* scope isolation
* compile-time execution behavior
* symbol resolution
* macro expansion mechanics

### 2. Structured Input Generation

AI-assisted tooling was used to accelerate generation of structured test cases and edge-condition variations.

This significantly reduced manual effort and enabled rapid iteration.

### 3. Automated Execution

A Python wrapper automated:

* SBCL subprocess execution
* input feeding
* crash observation
* output/error collection

---

## 📂 Repository Structure

* `automation/` — Python automation harness
* `analysis/` — research notes and observations
* `RESEARCH_ROADMAP.md` — hypotheses, ideas, and exploration directions

---

## 📘 What I Learned

This project helped me develop practical experience in:

* hypothesis-driven security research
* lightweight fuzzing methodology
* automation for behavioral testing
* compiler/runtime experimentation
* structured edge-case exploration
* AI-assisted research workflows

It also demonstrated how AI-assisted tooling can accelerate exploratory research while still requiring human-driven analysis, validation, and direction.
