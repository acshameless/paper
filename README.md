


2026W 20260706 
- [ ] https://arxiv.org/pdf/2606.22902
- [ ] https://arxiv.org/pdf/2606.15991
- [ ] https://arxiv.org/pdf/2606.23521
- [ ] https://arxiv.org/pdf/2605.15184
- [ ] https://arxiv.org/pdf/2606.24775
- [ ] https://arxiv.org/pdf/2607.01640





---
- [ ] https://github.com/ARahim3/mlx-dspark
- [ ] https://docs.sglang.io/docs/advanced_features/speculative_decoding#jump-to-sections
- [ ] https://www.cnblogs.com/SCCQ/p/19837997
- [ ] https://arxiv.org/pdf/2401.15077
- [ ] https://caomaolufei.github.io/AIInfraGuide/guides/ai-infra%E5%AD%A6%E4%B9%A0%E8%B7%AF%E7%BA%BF/
- [ ] https://charlestar.github.io/2026/05/11/2026%E5%A4%A7%E6%A8%A1%E5%9E%8B%E6%8E%A8%E7%90%86%E5%BC%95%E6%93%8E%E5%85%A8%E6%99%AF%E5%AF%B9%E6%AF%94/
- [ ] https://charlestar.github.io/2026/05/12/%E6%8E%A8%E6%B5%8B%E8%A7%A3%E7%A0%81SpeculativeDecoding%E5%8E%9F%E7%90%86%E4%B8%8E%E5%AE%9E%E8%B7%B5/
- [ ] https://quant67.com/post/llm-infra/15-speculative-mtp/15-speculative-mtp.html
- [ ] https://quant67.com/post/series/index.html
- [ ] https://juejin.cn/post/7622853036008980518
- [ ] https://github.com/ggml-org/llama.cpp
- [ ] https://unsloth.ai/docs/zh/ji-chu/inference-and-deployment/saving-to-gguf/speculative-decoding
- [ ] https://blog.csdn.net/gitblog_01139/article/details/150959228
- [ ] https://lilianweng.github.io/posts/2026-07-04-harness/


---
- [ ] https://lilianweng.github.io/posts/2026-07-04-harness/
- [ ] https://openai.com/index/unrolling-the-codex-agent-loop/
- [ ] https://arxiv.org/abs/2510.04618
- [ ] https://arxiv.org/abs/2601.21557


---
# RSI

[TOC]

## Concept



The concept of **recursive self-improvement (RSI)** dates back to [I. J. Good (1965)](https://philpapers.org/rec/GOOSCT), where he defined an “ultraintelligent machine” as a system that can surpass humans in all intellectual activities and design better machines to improve itself. [Yudkowsky (2008)](https://www.lesswrong.com/posts/JBadX7rwdcRFzGuju/recursive-self-improvement) used the phrase “recursive self-improvement” for a specific feedback loop: an AI uses its current intelligence to improve the cognitive machinery that produces its intelligence.





This feedback loop in modern AI may indicate the model rewriting its own weights directly, or more broadly the model improves the *training pipeline* and the *deployment system*, which in turn enables a better successor model with improved performance across economically valuable tasks. The speed of research development in AI has been shown to drastically accelerated in frontier labs ([Anthropic](https://www.anthropic.com/institute/recursive-self-improvement); [OpenAI](https://openai.com/index/how-agents-are-transforming-work/)).







## Famous work

I explicitly mention *“deployment system”* because the layer between the raw model and the real-world context seems to be as important as the model’s raw intelligence (i.e. the evals right after pretraining).





Harnesses are important components of AI deployment, as shown by successful coding agent products such as Claude Code and Codex. A **harness** is the system surrounding a base model that orchestrates execution and decides how the model thinks and plans, calls tools and acts, perceives and manages context, stores artifacts, and evaluates results.











## Limit

算力固定

效率提升









## Road Map



auto-research, self-improving agents, and evolutionary program search





model self-play, synthetic data, test-time training and a broader theme of continual learning

https://arxiv.org/abs/2401.10020

https://arxiv.org/abs/2401.01335

https://arxiv.org/abs/2505.03335







Context Engineering

https://arxiv.org/abs/2510.04618

https://arxiv.org/abs/2601.21557

https://arxiv.org/abs/2603.28052



Workflow Design

https://www.nature.com/articles/s41586-026-10265-5

https://arxiv.org/abs/2605.26340

https://arxiv.org/abs/2606.25996



https://arxiv.org/abs/2408.08435





![img](https://lilianweng.github.io/posts/2026-07-04-harness/aflow.png)

https://arxiv.org/abs/2410.10762





https://arxiv.org/abs/2605.27276

https://arxiv.org/abs/2605.09998







https://arxiv.org/abs/2605.30621



https://arxiv.org/abs/2606.09498



https://arxiv.org/abs/2604.25850





**prompt templates**

agent = LLM + memory + tools + planning + action



**runtime**

workflow design (e.g. loop engineering), evaluation, permission controls, and persistent state management.

how the model observes, acts, memorizes, checks itself, and improves.





**Workflow Automation**

Karpathy’s autoresearch repo (https://github.com/karpathy/autoresearch) 



**File System as Persistent Memory**

Learning how to read, write, and edit the file system









## latest 



[First Steps Toward Automated AI Research - Recursive](https://www.recursive.com/articles/first-steps-toward-automated-ai-research)

[AIDE²: First Evidence of Recursive Self-Improvement | Weco AI](https://www.weco.ai/blog/first-evidence-of-recursive-self-improvement)







## idea

1. RSI概念：广义、狭义，回答问题怎样才是自进化？
2. 如何评价RSI？有哪些指标或者方法？比如说固定成本、固定算力、固定时间
3. RSI 存在一个 Agentic Loop ，这是一个加速器，比如说提高同等效率以前 100年，现在只需要1年
4. 为什么 RSI 中 coding agent 如此重要？
5. Joint Optimization with Model Weights via improvements in the model training pipeline or continual learning at test time. 
6. 有固定的workflow 和 无固定 workflow 问题
7. 









1. Harness engineering will evolve in the direction of meta-methodology (i.e. improving the machinery for getting better answers, not just improving the answer itself). The harness system itself becomes an optimization target, with fewer heuristic rules and more general mechanisms.
2. In turn, mature harnesses enable auto-research for model self-improvement loop and smarter models prevents harnesses from overengineering and keep the system sustainable.

Eventually it is possible that many harness improvements will be *internalized* into core model behavior, but the interface with external context and tools should remain. We have seen a softer version of this pattern with [prompt engineering](https://lilianweng.github.io/posts/2023-03-15-prompt-engineering/): manual prompt tricks became less central as instruction tuning and model reasoning improved, but *the need to specify goals, constraints, context, and evaluation did not disappear*.







https://lilianweng.github.io/posts/2026-07-04-harness/
