VIDEO LINK — [Coding Sloth - Does a great job at showing how LLMs can be used effectively](https://www.youtube.com/watch?v=91B2_v-wOaws)

---

# How to Prompt Effectively Use AI (And Why It Matters)

**All content below was formatted by ChatGPT 5.2 and myself, using the same techniques explained below.**

---

## DISCLAIMER

**FOR PEOPLE LEARNING TO PROGRAM**

Just use AI as a helper not a solution. AI is not perfect by ANY means, so please make sure you check code and make sure you understand it before you go pasting or creating it. 

Plus actual coding is fun :)

Or at least I think so...

All credits for the AI explanations below go to the YouTuber who made the video — I highly suggest checking out the Coding Sloth. Even if you don't know what he is talking about 100% of the time, he is still very entertaining and informative. 

Also I have slightly modified the explanations to match more with a finance use case, for obvious reasons... 

---

## USEFUL AI RESOURCES

- MCPs: https://mcpmarket.com/server  
- AGENTS.MD: https://agents.md/#examples  
- Claude prompting best practices: https://docs.anthropic.com/en/docs/claude-code/prompting  
- OpenAI prompting best practices: https://platform.openai.com/docs/guides/prompt-engineering

---

## AI IN THE TERMINAL IS A SUPERPOWER

Using AI directly in your terminal brings the power of AI assistants to your command line workflow. Instead of switching between a browser and your IDE(Integrated Development Enviroment), you can interact with an AI coding agent while staying in your terminal.

**Video:** [What AI in the Terminal Looks Like](https://www.youtube.com/watch?v=MsQACpcuTkU) - Network Chuck is also great, highly recommend.

### How It Works

- **Terminal-based interface** — AI agents run in your terminal alongside your code
- **File access** — AI can read, edit, and create files in your project
- **Command execution** — AI can run shell commands (build, test, lint)
- **Context awareness** — AI understands your project structure and codebase
- **Iterative workflow** — Work back-and-forth with AI on tasks

### Common Terminal AI Tools

- **OpenCode** — Open source AI coding agent (what you're using now)
- **Claude CLI** — Anthropic's command-line interface
- **Aider** — AI pair programming in terminal
- **Warp** — AI-powered terminal

### Benefits

- Stay in one environment (terminal + IDE)
- Faster iteration cycles
- Direct access to build/test output
- Better context than copy-pasting to chat

---

---

## Table of Contents

1. [Why This Matters](#why-this-matters)  
2. [AI Is a Multiplier — Not a Replacement](#ai-is-a-multiplier--not-a-replacement)  
3. [Be As Specific As Humanly Possible](#be-as-specific-as-humanly-possible)  
4. [Bad vs Good Prompt Examples](#bad-vs-good-prompt-examples)  
5. [Break Large Tasks Into Smaller Ones](#break-large-tasks-into-smaller-ones)  
6. [The Three-Section Prompt Pattern](#the-three-section-prompt-pattern)  
7. [Tell AI What You Do Not Want](#tell-ai-what-you-do-not-want)  
8. [Make AI Remember Project Context](#make-ai-remember-project-context)  
9. [Always Give AI a Way to Verify Its Work](#always-give-ai-a-way-to-verify-its-work)  
10. [Use Tools That Extend AI's Capabilities](#use-tools-that-extend-ais-capabilities)  
11. [AI Amplifies Your Existing Habits](#ai-amplifies-your-existing-habits)  
12. [Final Takeaways](#final-takeaways)  

---

## Why This Matters

Many people say:

- “AI is amazing.”  
- “AI is useless.”

The true difference is how well you prompt it.

AI is only as good as the context, clarity, and constraints you provide. Poor prompts create poor outputs. Detailed, structured prompts create high-quality results.

The goal of this guide is to show you how to consistently get better results.


---

## AI Is a Multiplier — Not a Replacement

AI does **not** replace skill. It multiplies what you already know.

If you:

- Understand programming → AI accelerates you.  
- Understand architecture → AI scaffolds effectively.  
- Think clearly → AI executes clearly.

If you do not understand fundamentals, AI guesses. Guessing leads to fragile code that looks correct at first glance but fails under inspection.

### Important Principle

- Let AI type for you.  
- Do **not** let AI think for you.

You should still:

- Design the solution  
- Break down the problem  
- Understand tradeoffs  
- Review the output

AI is a tool, not a brain replacement.

---

## Be As Specific As Humanly Possible

The most common reason people get bad results from AI is lack of specificity.

When AI has to guess:

- The tech stack  
- The architecture  
- The implementation details  
- The design choices  
- The constraints

…it makes assumptions. Assumptions create errors.

The more technical detail you provide, the better the results.

Think of AI like a junior developer:

- If you give vague instructions, you get vague results.  
- If you give detailed specifications, you get strong execution.

---

## Bad vs Good Prompt Examples

### ❌ Bad Prompt (Too Vague)


Build a Quant Algorithm.


**Problems:**

- No tech stack  
- No feature breakdown  
- No design requirements  
- No database specified  
- No performance expectations  
- No verification steps

AI must guess everything.

---

### ⚠️ Average Prompt (Some Detail)


Build a stock tracker for (stock names) and pull off yfinance


Better — but still missing:

- Framework choice  
- Real-time implementation method  
- Database type  
- Styling instructions  
- Architecture constraints  
- Testing requirements

AI still invents technical decisions.

---

### ✅ Strong Prompt (Specific and Structured)

**DISCLAIMER**

This actually is NOT the best practice to ask for this much in a single prompt as is explainned below. BUT, overall this is still great reference for the most successful prompting. 

Build a quantitative finance backtesting and portfolio analysis system using the following specifications:

• DOCUMENTATION TO REFER TO
  - Python documentation: https://docs.python.org/3/
  - pandas documentation: https://pandas.pydata.org/docs/
  - NumPy documentation: https://numpy.org/doc/
  - Matplotlib documentation: https://matplotlib.org/stable/contents.html
  - SciPy documentation: https://docs.scipy.org/doc/scipy/
  - statsmodels documentation: https://www.statsmodels.org/stable/index.html

• TECH STACK
  - Python 3.11+
  - pandas for data manipulation
  - NumPy for numerical computation
  - Matplotlib for visualization
  - SciPy / statsmodels for statistical analysis
  - yfinance (or similar) for historical market data retrieval
  - jupyter for visualization and prototyping

• REQUIREMENTS
  - Download historical daily OHLCV data for a list of equities
  - Implement a moving average crossover strategy
  - Generate trading signals (long/flat)
  - Backtest strategy with realistic assumptions (transaction costs, slippage)
  - Calculate performance metrics:
      • CAGR
      • Sharpe ratio
      • Maximum drawdown
      • Volatility
  - Plot:
      • Equity curve
      • Drawdown curve
      • Rolling Sharpe ratio
  - Support parameter customization (short/long window lengths)

• ARCHITECTURE
  - Modular design:
      • data_loader.py
      • strategy.py
      • backtester.py
      • performance.py
      • main.py
  - Vectorized operations (no unnecessary loops)
  - Clear separation between signal generation and portfolio accounting
  - Configurable parameters stored in a single configuration section

• STYLING / CODE QUALITY
  - PEP8 compliant
  - Type hints throughout
  - Docstrings for all functions
  - Clear variable naming (no ambiguous abbreviations)
  - No hardcoded file paths

• VERIFICATION
  - Include unit tests for:
      • Signal generation logic
      • Performance metric calculations
  - Confirm strategy produces reproducible results
  - Ensure script runs with:
      python main.py
  - No runtime warnings or errors

• DO NOT
  - Use obscure or unnecessary third-party libraries
  - Mix signal generation with execution logic
  - Use global variables
  - Hardcode parameters inside functions
  - Overengineer with classes if not needed

**Why this works:**

- Removes ambiguity  
- Adds structure  
- Prevents scope creep  
- Includes verification  
- Defines boundaries

**Still not buying it?**

MAKE A PROMPT FOR AI, WITH AI. I know its a little redundant but from my own expirences this has worked.

---

## Break Large Tasks Into Smaller Ones

AI performs much better on small, focused tasks than large, complex ones.

Instead of:

> Build an entire application.

Do:

1. Scaffold project structure  
2. Implement authentication  
3. Add editor component  
4. Add real-time sync  
5. Add commenting system  
6. Add tests

If you cannot break a task into smaller pieces, you do not understand it well enough yet.

This is not just an AI technique — it's fundamental engineering and problem-solving.

---

## The Three-Section Prompt Pattern

A highly effective structure for prompting:

### 1️⃣ Task

Clearly describe what needs to be built. Be detailed.

---

### 2️⃣ Background Information

Provide:

- Relevant files  
- Documentation  
- Screenshots  
- User flow explanations  
- Existing architecture details

The more context AI has, the better it performs.

---

### 3️⃣ Do Not Section

Specify:

- What must not change  
- Which files are off-limits  
- What architecture must remain intact  
- What dependencies must not be added

Constraints dramatically improve results.

---

### Example


TASK:
Implement commenting functionality similar to Google Docs.
When a user selects text, allow them to attach a comment.
Highlight selected text.

BACKGROUND:

Editor built with TipTap

Comments stored in PostgreSQL

Sidebar component already exists

DO NOT:

Modify authentication logic

Refactor editor core

Change database schema unless necessary


This structure significantly reduces mistakes and messy output.

---

## Tell AI What You Do Not Want

This is extremely powerful and often ignored.

AI performs better when it understands:

- Boundaries  
- Architectural constraints  
- Files it must not modify  
- Style it must maintain

When you clearly define limits, you reduce:

- Sloppy output  
- Unnecessary refactoring  
- Overengineering  
- Breaking working systems

---

## Make AI Remember Project Context

AI performs better when it has persistent context.

Create a project-level markdown file such as:

- `guidelines.md`  
- `project_rules.md`

**Include:**

- Project overview  
- Tech stack  
- Important commands  
- Coding standards  
- Architecture rules  
- Workflow guidelines

This reduces repeated explanations and improves consistency.

You can:

- Write it yourself  
- Ask AI to generate it by analyzing your codebase  
- Use a template based on your tech stack

---

## Always Give AI a Way to Verify Its Work

AI should never just write code. It should also verify that the code works.

**Verification methods:**

- Unit tests  
- Integration tests  
- Running the app locally in the browser or CLI  
- CLI build checks  
- CI/CD validation  
- Console error inspection

You can:

- Write verification yourself  
- Or ask AI to generate tests and confirm they pass

Never trust output blindly. Verification prevents silent failures.

---

## Use Tools That Extend AI's Capabilities

AI becomes significantly more powerful when it can:

- Fetch documentation automatically  
- Inspect build errors  
- Access browser developer tools  
- Read logs  
- Analyze performance metrics  
- Query databases

When AI can see the real state of your project, it stops guessing.

More visibility = better decisions.

(See **USEFUL AI RESOURCES** at the top for MCPs, AGENTS.MD, and official prompting guides.)

---

## AI Amplifies Your Existing Habits

AI does not fix bad engineering habits. It amplifies whatever habits you already have.

If you:

- Write tests  
- Think about edge cases  
- Document clearly  
- Break problems down properly

You get excellent results.

If you:

- Skip testing  
- Avoid planning  
- Ignore architecture  
- Let AI think for you

AI will amplify those weaknesses too.

The programmers who benefit most from AI already have strong fundamentals.

---

## Final Takeaways

1. AI is a multiplier, not a brain replacement.  
2. Specificity determines output quality.  
3. Break large tasks into small steps.  
4. Use structured prompts.  
5. Always include constraints.  
6. Always verify output.  
7. Maintain strong engineering fundamentals.

---

## The Real Shift

AI increases the importance of:

- Clear thinking  
- Communication  
- Architectural awareness  
- Problem decomposition

The developers who benefit most from AI are those who already think clearly.

**The future belongs to people who can think well — and prompt precisely.**
