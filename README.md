# 🧠 AI-Augmented SBCL Security Research: Methodology & Showcase

## ⚠️ Responsible Disclosure & Code Access
This repository serves as a **Technical Showcase** of the research methodology, fuzzing architecture, and binary analysis workflow. 

To adhere to **Responsible Disclosure** standards and protect the integrity of the affected software (SBCL), the full **Proof-of-Concept (PoC) exploit code** and specific vulnerability triggers are currently kept in a **private repository**. 

These assets will be made public once the coordinated disclosure process with **MITRE** and **CERT-IL** (Ref #11265) is finalized and a patch is available.

---

## 🎯 Research Overview
This research originated from a core architectural question: *"In Lisp macros, where there is no traditional call stack, what protects the lexical scope from being bypassed by an external attacker?"*

Instead of spending weeks on manual fuzzing and reverse engineering, this project was driven by an **AI-Augmented Security Research** approach. By orchestrating AI agents (GitHub Copilot Agent Pro) with precise architectural constraints, a deep-dive research cycle was completed in a fraction of the traditional time.

## 🚨 Key Findings (Coordinated Disclosure in Progress)
Through the custom semantic fuzzer developed during this research, three distinct vulnerabilities were identified in the SBCL compiler (v2.3.2):
1. **Dynamic Binding Attack (Logical Flaw):** A method to bypass lexical scope isolation by injecting dynamic bindings (`proclaim`), successfully overriding protected lexical variables.
2. **Buffer Overflow (DoS):** Memory boundary violation in the compiler's parser when processing variable names exceeding 50,000 characters, leading to a 100% reproducible crash.
3. **Stack Exhaustion (DoS):** Missing recursion depth enforcement in the macro expansion engine.

## 🛠️ Showcase Contents
This public showcase demonstrates the *methodology* and *tooling* built during the research:
* `RESEARCH_METHODOLOGY.md` - The architectural approach to semantic fuzzing and binary analysis.

## 👤 Author
**Shay Mordechai**
Security Researcher | Network & Web Architecture | AI-Augmented Threat Hunting
