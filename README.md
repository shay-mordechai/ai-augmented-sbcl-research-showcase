### 🔬 Compiler Behavior Exploration: SBCL Scope Analysis

An automated exploration of variable scope behavior using AI-assisted testing.

---

### 🎯 The Research Question

This project started with a curiosity about compiler behavior:

> “During macro expansion (compile-time), how is variable isolation maintained without a traditional runtime stack?”

To explore this, I used SBCL (Steel Bank Common Lisp) and built an automated testing approach.

---

### 🛠️ Methodology: AI-Assisted Testing

Instead of writing tests manually, I used AI tools (GitHub Copilot) to help generate structured Lisp inputs.

A simple Python-based script was used to:

* execute SBCL with generated inputs
* automate repeated testing
* observe crashes and unexpected behavior

---

### 🔍 Key Observations

Through this process, I identified several interesting edge cases:

1. **Scope Interaction Behavior**
   In some cases, dynamic binding (`proclaim special`) affected expected lexical behavior.

2. **Extreme Input Handling**
   Very long symbol names caused reproducible crashes.

3. **Macro Expansion Limits**
   Deep or recursive macro usage could lead to resource exhaustion.

> These are presented as **unexpected behaviors and edge cases**, not confirmed security vulnerabilities.

---

### 📂 Repository Contents

* `fuzzer/` – Python script used for automated testing
* `RESEARCH_ROADMAP.md` – exploration plan and ideas
* `analysis/` – initial notes and experiments

---

### 👤 About Me

Shay Mordechai
Junior Developer | Automation & Systems Exploration | AI-Assisted Research
