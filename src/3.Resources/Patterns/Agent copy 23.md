1. **Single agent system performing single task**  
   A single AI agent autonomously plans, executes, and completes an entire task using its internal reasoning capabilities. This is the foundational letter—fastest and simplest for well-scoped problems. Unlike multi-agent variants that add coordination overhead, it shines in deterministic scenarios but is frequently embedded as a child node inside hierarchical or graph-based patterns when a sub-problem is truly atomic.

2. **Multi-agent parallel, performing task in different ways**  
   Several independent agents tackle the same task simultaneously with distinct strategies. Outputs are compared side-by-side. This letter injects diversity from the very first step and is distinctly different from a swarm because it lacks shared memory or voting; it is typically used as the starting block for ensemble voting or parallel-with-refinement patterns to surface the strongest initial candidates quickly.

3. **Multi-agent parallel with iterative refinement**  
   Parallel agents exchange partial results across rounds, each refining its output based on collective feedback. Natural convergence occurs without central control. It builds directly on simple parallel execution for higher-quality outcomes and differs from pure critique patterns by emphasizing mutual improvement rather than rejection; it is commonly layered inside coordinator or graph workflows for scalable polishing.

4. **Multi-agent coordinator with a manager agent to optimize iterative refinement**  
   A dedicated manager routes subtasks, scores progress, and reallocates resources dynamically. This orchestration letter eliminates waste that plain parallel refinement can suffer. It is the natural upgrade when flat parallel patterns encounter noisy workloads, and it is almost always paired with hierarchical decomposition to prevent the manager from becoming a bottleneck.

5. **Multi-agent hierarchical decomposition by a manager breaking a task into sub-tasks**  
   A top-level manager decomposes the original task into dependent subtasks and assigns each to a specialized child agent. Clean dependency management emerges for complex work. Distinct from flat parallel patterns because subtasks have explicit ordering and reporting, it is the letter most often combined with ReAct loops at the leaves or human-in-the-loop checkpoints at the root.

6. **Multi-agent swarm in which many agents brainstorm and vote on best approach**  
   A large population generates ideas freely in a shared workspace, then uses majority or weighted voting to choose direction. This is the letter of emergent creativity and collective intelligence. Unlike parallel patterns that compare outputs once, swarms evolve directionally through repeated voting; they are typically layered on top of any iterative loop to inject diversity before critique or reflection steps.

7. **Single agent loop until stop condition is met, reasoning and acting (ReAct) upon base model, modifying base model per lessons learned in performing task**  
   One agent repeatedly observes the environment, reasons about the next action, executes it, and stores lessons to update its internal model or prompt. The loop terminates on success or a maximum iteration count. This core self-improving engine is the minimal letter that every multi-agent variant extends, yet it differs from pure reflection by interleaving action and observation in real time rather than post-hoc auditing.

8. **Multi-agent ReAct iterative loop until a stop condition is met**  
   Multiple agents run synchronized or asynchronous ReAct cycles, sharing observations and partial plans at each step. The collective loop accelerates exploration while preserving the same clear termination logic. It multiplies the power of the single-agent ReAct letter and is frequently fused with critique or voting to keep the group aligned without central command.

9. **Multi-agent review and critique, during iterative loops, one agent proposes, then others critique and vote on best next step**  
   A proposer drafts the next action; the remaining agents critique it for risks or flaws and vote on revisions. Only the approved step is executed, creating built-in safety rails. This quality-control letter is distinctly different from simple ensemble voting because it operates inside the loop rather than at the end; it is inserted into almost any other pattern—parallel, hierarchical, or swarm—to raise reliability without adding new agents.

10. **Human-in-the-loop, generally like any of the previous, except that agents pause at point until human approves continuation or finish**  
   Any pattern above is augmented with explicit pause points where the team surfaces its current state and proposed next action for human review, modification, or abort. This injects irreplaceable human judgment that pure automation cannot replicate. Unlike fully autonomous patterns, it works uniformly as a wrapper across single-agent, ReAct, or graph flows and is most commonly paired with high-stakes hierarchical or critique systems in enterprise settings.

11. **Custom logic that is especially tailored to a particular kind of problem**  
   When domain constraints exceed standard letters, developers assemble bespoke combinations of decomposition, voting, critique, and ReAct loops with problem-specific guardrails or external tools. The resulting flow is documented as its own named pattern for reuse within the same domain. This is the evolutionary letter—every other pattern serves as a proven template to modify surgically—making it the bridge from general idioms to domain-specific dialects.

12. **Tool-Use / Code-Act Pattern**  
   Agents invoke external tools, APIs, or code interpreters to act beyond internal knowledge. This letter turns pure reasoning into real-world execution. It is not merely an add-on but the essential complement to every ReAct or planning pattern, and it differs from blackboard coordination because tools provide external state rather than shared internal memory.

13. **Reflection / Reflexion Pattern**  
   An agent generates output, then self-audits, identifies gaps or errors, and iteratively revises using stored lessons before proceeding or finalizing. This self-correction letter dramatically raises reliability and is the internal counterpart to external critique. It is distinctly different from ReAct because it occurs after an action or output rather than interleaved, and is typically stacked inside single-agent loops or multi-agent debate for deeper self-improvement.

14. **Plan-and-Execute (Planning) Pattern**  
   The agent first creates an explicit multi-step plan (often via LLM), then executes the plan step-by-step with tools or sub-agents. This separates strategic thinking from tactical execution for longer-horizon reliability. Unlike pure ReAct, which reacts moment-to-moment, planning provides a stable roadmap; it is most often combined with hierarchical decomposition when the plan itself requires sub-agents.

15. **Tree of Thoughts (ToT) Pattern**  
   The agent explores multiple parallel reasoning branches in a tree structure, evaluates and prunes paths at each level via self-assessment or voting, then selects the best trajectory. This letter enables systematic exploration of creative or complex solution spaces. It differs from graph workflows by being strictly tree-shaped (no merging of branches) and is commonly paired with reflection to score each node before expansion.

16. **Handoff Pattern**  
   Control and full context are dynamically transferred from one specialized agent to the next as subtasks complete. This efficient sequential letter popularized by OpenAI Swarm avoids the overhead of persistent managers. It is distinctly different from sequential pipelines because handoffs are opportunistic rather than fixed-order and is typically used inside role-based crews when one expert’s work naturally feeds another.

17. **Router / Dispatcher / LLM-as-Router Pattern**  
   A central LLM analyzes input or state and dynamically routes the task to the best agent, tool, or sub-pattern. This adaptive traffic-control letter enables heterogeneous handling without hard-coded logic. Unlike a manager in hierarchical patterns that decomposes, the router simply directs and is most often embedded in graph-based workflows for conditional branching.

18. **Sequential Pipeline / Orchestration Pattern**  
   Agents or steps execute in a fixed linear order, each passing enriched state or output to the next. This predictable assembly-line letter is easy to monitor and debug. It differs from handoff patterns by enforcing a rigid sequence rather than dynamic transfer and is frequently combined with tool-use or reflection at each stage for enterprise-grade reliability.

19. **Ensemble / Voting / Aggregation Pattern**  
   Multiple independent runs (different agents, temperatures, or samplings) produce outputs for the same subtask; results are aggregated via weighted voting, averaging, or meta-LLM. This robustness letter reduces hallucination and variance. Unlike swarm voting, which influences direction mid-process, ensemble voting happens once at the end and is the natural closer for parallel or ToT patterns.

20. **Multi-Agent Debate Pattern**  
   Agents adopt opposing or diverse viewpoints and engage in structured critique and rebuttal rounds (with optional judge or voting) until consensus emerges. This letter sharpens factuality and creativity through productive conflict. It is distinctly different from simple critique because debate is adversarial and iterative, and is most effectively paired with reflection or human-in-the-loop to resolve stalemates.

21. **Graph-Based Workflow / Graph of Thoughts (GoT) Pattern**  
   Reasoning and actions are structured as a persistent directed graph with nodes, conditional edges, cycles, and merges. This letter handles truly non-linear, stateful systems far beyond trees or chains. Unlike tree-of-thoughts, graphs allow branches to reconverge; it is the backbone that most often incorporates routers, memory, and reflection for production-grade agentic applications.

22. **Role-Based Crew Collaboration Pattern**  
   Agents are assigned explicit roles, goals, backstories, and tools to form a “crew” that collaborates on sequenced or parallel tasks under a manager. This human-readable team letter makes complex workflows intuitive. It extends hierarchical patterns with persistent personality and is typically combined with conversational chat or debate for richer interpersonal dynamics.

23. **Conversational / Group-Chat Multi-Agent Pattern**  
   Agents communicate freely via natural-language messages in a shared chat space, taking turns based on roles or triggers until the goal or consensus is reached. This letter enables emergent, dynamic collaboration without rigid orchestration. Unlike blackboard patterns that use structured postings, conversation is free-form and is most often fused with role-based crews or debate for fluid idea exchange.

24. **Blackboard / Shared Workspace Pattern**  
   Agents read from and post to a central shared knowledge repository asynchronously while performing subtasks. This scalable loose-coordination letter prevents messaging overload in large populations. It differs from conversational chat by being structured and persistent rather than turn-based and is commonly layered inside swarms or graph workflows as the memory backbone.

25. **Agentic RAG + Adaptive / Meta-Learning Pattern**  
   Retrieval is driven by agent reasoning, planning, and tool-use loops with iterative query refinement, plus persistent long-term memory and cross-task adaptation. This letter turns static knowledge into continuously improving, living expertise. Unlike traditional RAG, the agent decides what and when to retrieve; it is the natural pairing for reflection or evolutionary adaptation patterns.

26. **Persistent Memory and Evolutionary Adaptation Pattern**  
   Agents maintain multi-level memory (short-term, vector, procedural) and evolve their own prompts, tools, or strategies across sessions or tasks. This “language-growth” letter lets vocabularies and idioms improve autonomously over time. Distinct from single-loop reflection by operating across multiple episodes, it is typically combined with graph or meta-learning patterns to create self-evolving agentic systems.

