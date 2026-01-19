# _uni_music Claude Code Tutorial
by _uni_music (https://www.threads.com/@_uni_music)

The complete Claude Code tutorial.  
Link: <https://www.threads.com/@_uni_music/post/DTpMoTYAozi?xmt=AQF00wJs_qUhMecnPYSNrv1nqlATQt8KEeHXjF0Vi44cNA>  
N.B.: some copyedits by [band](https://hachyderm.io/@band)  

The number 1 mind shift most people miss.  
Think first, type later.  

Jumping straight into prompts usually backfires. Hit Shift + tab twice to activate the plan mode — spend those 5 minutes thinking deeply. Outputs dramatically because the input is cleaner.  

No deep engineering background? Chat back-and-forth with an LLM first: describe the goal, explore options, ask questions, settle on architecture. This habit alone levels up everything you build next...

....which brings us to architecture — the hidden multiplier.  
Vague asks like "build an auth system" invite over-engineering or weird choices. Be surgical:  

"Build email/password auth using the existing User model, store sessions in Redis (24h expiry), add middleware for /api/protected routes"

Specific architecture + constraints = clean, production-ready code.  
Skip this and you will debug for hours. Plan mode is your best friend here. 

Now meet your secret weapon: CLAUDE.md  
Claude reads this file automatically at session start — it is permanent project memory. Keep it short (150-200 instructions max), project-specific and explain why behind every rules to give it more context about the instructions.

Example:  
"Use TypeScript strict mode because we have had prod bugs from implicit any types". The "why" helps Claude make smart judgment calls.

Update it constantly as the conversation proceeds — it evolves with your codebase. 

Context is gold, but it degrades fast.  
Even with huge context windows, quality drops noticeably around 20-40% usage. Do not let one mega-conversation handle auth + DB + UI.  
Keep each conversation scope tight: one chat per feature/task. Use external file like SCRATCHPAD.md or plan.md for durable progress.  
Remember: Fresh context = sharp Claude Code performance.  

Prompting is communication skill — master it.  
Bad input = bad output.  
1. Be hyper-specific, list what NOT to do you can use these:  
- Keep simple, no extra abstractions, one file if possible.  
2. Give constraints; e.g.:  "This runs on every request — prioritize speed", and provide why.

Cross-check outputs — Claude still makes mistakes. Recognize them early ,iterate and keep updating CLAUDE.md .

If results suck consistently, fix your prompting before blaming the model. 

Model choice matters too.  
1. Sonnet: fast, cheap, great for clear-path execution (boilerplate, refactoring).  
2. Opus: slower, pricier, excels at deep reasoning, planning, tradeoffs.  

Sweet workflow: Opus for architecture/planning, then Sonnet (Shift+Tab) for implementation. CLAUDE.md keeps rules consistent across both. 

When Claude loops or gets stuck — don't double down. 
Clear the chat (/clear) for fresh start.  
Simplify: break into tiny steps.  
Show: give a minimal example of desired output. Reframe the problem entirely.  
Spot the loop after 2–3 failed explanations — more words will not fix it. Change approach instead.

If you want to be more advanced: 

Use: MCP, hooks, custom commands.  
1. MCP connects Claude to external tools (Slack, GitHub, DBs, APIs) — no more manual copy-paste.  
2. Hooks run code before/after actions (auto-Prettier, type-check).  
3. Custom slash commands: drop MD files in .claude/commands/ for repeatable workflows (e.g., /review, /deploy). If you are on Pro/Max, experiment — new features drop often. Retry what failed last month.  

Level up further: build systems, not one-offs in the long run.  
Use -p (headless) mode to script Claude: run prompts non-interactively, pipe outputs, chain with bash, automate PR reviews or docs.  

Log mistakes → improve CLAUDE.md/hooks → Claude gets better next time.  
This flywheel compounds fast. Enterprises already use it for auditable, improving automation. 

So, folks, here is the quick recap — the levers that matter most:  
- Think/plan first  
- Sharp, short CLAUDE.md with "why"  
- Scope chats tightly + reset context proactively  
- Specific prompts + constraints  
- Experiment with MCP/hooks/commands  
- Build automated systems  

Modern AI coding is capable when used right.  
Apply these patterns to your projects — ship cleaner code faster.  

If this helped, drop a reply. More AI dev tips coming - follow along. 
