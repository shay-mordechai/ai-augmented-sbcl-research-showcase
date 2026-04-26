# 🔬 Compiler Behavior Exploration: SBCL Scope Analysis

## 💡 Why This Project?

During my studies, I kept asking a simple question:  
If macros run at compile-time without a runtime stack — what actually enforces variable isolation?

Instead of only exploring this theoretically, I built a small automated experiment to test it in practice.

---

## 🎯 The Research Question

> During macro expansion (compile-time), how is variable isolation maintained without a traditional runtime stack?

To explore this, I used SBCL (Steel Bank Common Lisp) and built an automated testing workflow.

---

## 🛠️ Methodology: AI-Assisted Testing

Instead of writing tests manually, I used AI tools (GitHub Copilot) to help generate structured Lisp inputs.

A simple Python-based script was used to:

- execute SBCL with generated inputs  
- automate repeated testing  
- observe crashes and unexpected behavior  

---

## 🔍 Key Observations

Through this process, I identified several interesting edge cases:

1. **Scope Interaction Behavior**  
   In some cases, dynamic binding (`proclaim special`) affected expected lexical behavior.

2. **Extreme Input Handling**  
   Very long symbol names caused reproducible crashes.

3. **Macro Expansion Limits**  
   Deep or recursive macro usage could lead to resource exhaustion.

> These are presented as **unexpected behaviors and edge cases**, not confirmed security vulnerabilities.

---

## 📂 Repository Contents

- `automation/` – Python script used for automated testing  
- `RESEARCH_ROADMAP.md` – exploration plan and ideas  
- `analysis/` – initial notes and experiments  

---

## 🧪 Approach

### 1. Hypothesis

Macros operate at compile-time and do not rely on a runtime call stack.  
This raises the question: can scope-related assumptions be affected during expansion?

---

### 2. Experimentation Strategy

Instead of random inputs, I focused on structured test patterns targeting:

- scoping rules (lexical vs dynamic)  
- symbol handling  
- macro expansion behavior  

AI tools were used to accelerate test generation and iteration.

---

### 3. Execution

A lightweight Python wrapper was used to:

- run SBCL as a subprocess  
- feed generated inputs  
- monitor output, errors, and crashes  

---

## 📘 What I Learned

- How to design small experiments to test system behavior  
- How to use automation to scale repetitive testing  
- How AI tools can accelerate exploration of unfamiliar domains  

---

## 👤 About Me

Shay Mordechai  
Junior Developer | Automation & Systems Exploration | AI-Assisted Research
