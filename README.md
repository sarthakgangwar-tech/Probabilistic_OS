# Decision Kernel

## What this project is about

Every operating system in common use today, including Linux, Windows, and macOS, was designed around a deterministic model of computation. A process either finishes or it does not. A memory page is either allocated or free. The scheduler's job is to arbitrate demand for a small set of finite resources: CPU cycles, RAM, disk bandwidth, and network throughput.

Systems built around machine learning do not fit this model cleanly. Their outputs are estimates, not facts. Their plans are hypotheses that can later be revised, not fixed scripts. The cost of taking an action is not only computational; it also carries an epistemic cost, meaning how uncertain the system is, and a consequential cost, meaning how bad it would be to act on a wrong answer.

This project explores what an operating system would look like if it treated uncertainty, evidence, expected utility, computation cost, cost of error, latency, and safety constraints as first-class scheduling primitives, on the same footing as the process table and the memory manager in a conventional kernel. The working name for this runtime is the decision kernel.

The central claim is that this is a systems problem, not just a modeling problem. A library that tracks confidence scores on top of a conventional scheduler can advise an application, but it cannot enforce anything. A kernel that treats confidence and expected utility as scheduling inputs can preempt, redirect, or block execution based on them, in the same way a conventional kernel enforces memory protection or preempts a process on priority. The goal of this project is to work out what such a kernel would need to guarantee, and to build a working prototype that tests those guarantees against real domains rather than leaving them as theory.

## Current state

This project is at an early research stage. Work so far has focused on defining the problem clearly, situating it against existing research in metareasoning, probabilistic scheduling, belief representation, and AI agent runtime safety, and identifying the open problems that need to be solved before a working system is possible. No prototype code has been written yet.
