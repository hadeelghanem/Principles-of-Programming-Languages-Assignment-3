# Principles of Programming Languages — Assignment 3

Third assignment for **Principles of Programming Languages**.  
Focus: designing and implementing **L52**, a typed language extending L5 with **set-based type operators** and **type predicates**.  

---

## Overview
- **Part 1 – Theory:**  
  - Typing judgments for higher-order functions and closures.  
  - Reasoning about environments, closures, and evaluation rules.  

- **Part 2 – L52 Types & Predicates:**  
  - New type expressions:  
    - `any` (supertype of all types).  
    - `never` (subtype of all types, empty type).  
    - `(union T1 T2)` – type union.  
    - `(inter T1 T2)` – type intersection.  
    - `(diff T1 T2)` – set difference of types.  
  - Type predicates `(Any -> is? T)` for flow-sensitive typing (like TypeScript’s `x is T`).  

- **Part 3 – Implementing L52:**  
  - Extended the **AST** and **parser** with new type forms and predicates.  
  - Implemented **normalization rules**:  
    - Flatten unions/intersections.  
    - Remove duplicates.  
    - Sort lexicographically.  
    - Convert intersections into **Disjunctive Normal Form (DNF)**.  
  - Added `makeDiffTExp` for difference types.  
  - Extended the **subtyping relation** to handle `any`, `never`, union, intersection, and difference.  
  - Updated the type checker (`typeofIf`, `typeOfApp`, `typeOfProc`) to integrate **predicate-based refinements**.  

---

## Tech Stack
- **TypeScript (strict mode)**  
- **L5 / L52 interpreters**  
- **Set-theoretic types & predicates**  
- **Jest** for testing  

---

## Skills Gained
- Type system design & implementation.  
- AST and parser extension in TypeScript.  
- **Subtyping** with union, intersection, difference, `any`, and `never`.  
- Predicate-based flow typing.  
- Language normalization strategies (flattening, dedup, DNF).  
- Rigorous unit testing with Jest.  

---

## ▶️ Run
Clone the repo and run:
```bash
npm install
npm test
