# learning-ai-backend
A local-first AI backend for experimenting with retrieval-augmented generation, local LLMs, tool calling and Model Context Protocol.

# Local AI Backend Platform

Looking into a A local-first AI backend for experimenting with retrieval-augmented generation, local LLMs, tool calling and Model Context Protocol. The project explores production-oriented AI backend architecture including:

* local inference with Ollama
* document ingestion and chunking
* PostgreSQL + pgvector
* semantic and hybrid retrieval
* RAG with source attribution
* configurable AI assistants
* MCP tools and resources
* retrieval evaluation
* API testing
* containerized deployment
* observability

## Status

Early development. The project is currently establishing its foundation before implementing other features. This repo documents the journey.

## Why this project exists

This repository is  my structured learning environment for modern AI backend engineering. Each milestone introduces a new capability and documents the engineering decisions, experiments and results.

# Necessary boring details start here (skip if you wish) 

## AI Backend Engineer Learning Roadmap
```
learning-ai-backend/
│
├── Milestone 0 — Engineering foundation
├── Milestone 1 — Local LLM service
├── Milestone 2 — Document ingestion
├── Milestone 3 — Vector retrieval
├── Milestone 4 — Production RAG
├── Milestone 5 — RAG evaluation
├── Milestone 6 — Tool calling + MCP
├── Milestone 7 — Configurable AI assistants
├── Milestone 8 — Security, observability and deployment
└── Milestone 9 — Multimodal / agent experimentation
```

# Prequisites
* Learn from online sources
* Make notes
* Document ideas and realizations

# AI related consept detailed

Consept detailed according to lessons learned and available technologies.
```
FOUNDATION
│
├── Software engineering practices
├── Python / HTTP / APIs
├── Docker / PostgreSQL
└── Testing / CI

LOCAL AI
│
├── Ollama
├── Local models
├── Structured outputs
└── Model abstraction layer

KNOWLEDGE
│
├── Document ingestion
├── Chunking
├── Embeddings
├── pgvector
├── Semantic retrieval
├── Metadata filtering
└── Hybrid retrieval

RAG
│
├── Context construction
├── Citations
├── Reranking
├── Prompt design
└── Evaluation

AGENTS
│
├── Tool calling
├── Agent loop
├── MCP servers
├── MCP clients
└── Tool authorization

PLATFORM
│
├── Configurable assistants
├── Knowledge collections
├── Model selection
├── Tool permissions
└── Assistant configuration

PRODUCTION
│
├── Security
├── Observability
├── Evaluation
├── CI/CD
├── Containers
└── Documentation

EXPERIMENTAL
│
├── Vision
├── Multimodal RAG
├── Agent memory
├── Workflow orchestration
└── Multi-agent experiments
```

# Preliminary solution structure:

```
/apps
    /api
    /mcp-server
/packages
    /rag
    /ingestion
    /llm
    /retrieval
/tests
/docs
    architecture.md
    decisions/
    learning-journal/
    experiments/
docker-compose.yml
README.md
```

# Necessary boring details ends here. Continue to the story.

-- TO BE MOVED TO OTHER DOCS - maybe?

# Prequisites - notes

I have been scrolling many courses from coursera, kaggle, IBM and many others. It seems that the basic courses cover only superficially the details that I look for the most. The basic courses go through the consept and the idea of AI but not the actual details on the technology or the solutions. But some of those basic courses seem very good, because of their superficial content they bring up more questions than answers. And I hope that those questions will lead me to the right direction. Todays questions have been that why the multimodal, foundation models or other models are not trained with more interaction between each other. Or why the models are not trained with interfaces/virtual interfaces of sight, touch, smell or other senses. Because human (and other animal brains) learn almost only through interactions. Via interactions with environment the accuracy and realization of different consepts are so much easier. These are the findings from the neurological studies. These studies indicate that human brain is only "half-baked" and to develop fully humans need interactions to learn - even learn to walk through touch and balance. Same goes to computers which are in this case half-baked with vast knowledge but no experience or interactions to learn from.

## Ideas (in my learning context):
- Shift from "Training" to "Orchestration": As a backend developer, my job is to build the interaction layer. Because "AI has no experience to use knowledge against," the backend engineer's solution to this is RAG (Retrieval-Augmented Generation). RAG gives the model a local "memory" (SQL database) to pull real-world experiences from.
- What if virtual models could replace senses?
- Connect the Senses to APIs:  "Sight" = Vision Language Models (VLMs) processing image frames via a Node.js stream?
- "Touch/Action" = An LLM emitting a JSON tool call that triggers a Go script to execute a command on a server.
- How do we give a text-based model an "interface" to act: Utilizing **Model Context Protocol (MCP)** to build a bridge between the LLM and file systems, turning passive text into active execution.

# Notes - continued
This project was paused for a while because I participated in a hackathon event.

Unfortunately, I cannot share the application or many details about the solution because of an NDA. What I can say is that the challenge was in a completely different area from the work I had been doing here. We were designing the best possible UX/UI experience for a mobile application used in a time-critical healthcare situation. The application needed to work when the user might be stressed, scared, in pain or otherwise unable to concentrate normally, while at the same time supporting healthcare professionals who needed useful information quickly.

The task was fun because the organizers specifically encouraged us to come up with new ideas and approaches.

This time my healthcare background became very useful. I was immediately able to start thinking about the risks, what health information might actually be useful, what existing healthcare applications and services were relevant, what integrations could eventually be needed, and where the dangerous assumptions could be. I actually had enough time to do some proper research instead of immediately starting to build something. We gathered sources, compared existing solutions and looked at research related to the critical situation we were designing for.

Our team also included another healthcare professional and a mother of three. The experiences she shared were extremely valuable. They helped us focus the concept in the right direction: in a critical situation the application must actually help, not increase cognitive load or force the user to operate some complicated interface.Together we were able to identify the important flows and think through how different users would move through the application in different situations. My own background in healthtech helped especially when thinking about things that are not always visible in a UI mockup: safety, privacy, information reliability, risk management, integrations and requirements that may eventually come from healthcare regulation.

After the research phase, when the team felt that we understood the problem well enough, we were faced with another problem: Now we actually had to design the UI. And none of us were UI designers. Well, I had some experience, but not really the kind that would help me create a polished modern mobile UI. My experience was more useful for explaining what good healthcare UX should achieve than deciding exactly what every component should look like. So we started exploring possibilities.

One team member suggested Figma because a UI designer from one of her previous projects had told her that it was an easy way to create UI mockups. So on we went. While the other two team members experimented with different layouts and ideas, I listened carefully to their discussions: what looked good, what felt confusing, what information should be visible and what should not. I decided to approach the problem from another direction. Instead of trying to tell the AI exactly what the screen should look like, I wrote a detailed description of how the application should behave. I explained the user flows, accessibility requirements, cognitive-load constraints, important information, required actions, transitions between states and the risks we had identified during the research.

Then I gave that to Figma's design AI. **And voilà**. It looked like a professional had designed it.

Right in front of me was a surprisingly polished home screen for our application. What impressed me even more was that I had barely specified the visual style. I had described accessibility, usability and the emotional character the interface should have, but I had not given it some carefully designed colour palette. Still, it produced something visually pleasing, calm, inviting and modern. The team liked it, so we decided to use that design as our visual base and continued creating the other views and states around it.

I was honestly amazed by what Figma AI had produced. How was that possible? I soon learned from my teammates and from other developers that Figma does not necessarily produce something that good from a normal prompt. After doing some more research, I started to understand what had happened. The important part was probably not that I had somehow discovered a magical AI tool. It was the input.

Before asking the AI to design anything, we had already spent time defining the users, flows, risks, accessibility requirements, important information and boundaries of the application. The prompt was therefore not simply: "Make me a nice healthcare app." It was closer to a small design specification. By accident — or perhaps partly because of the way I had structured the problem — I also managed to constrain the AI enough that there was very little room for the usual drifting, hallucination or random feature invention. 

We unfortunately did not win the hackathon. The interesting part was how close it actually was. When we asked the judges what had decided the result, they told us that our solution and the winning solution had received exactly the same total score from the four judges using the original criteria. Because the solutions were both strong but very different, the judges discussed an additional deciding factor: how naturally the proposed solution could fit the organisation's existing architecture, capabilities and way of operating. That is where we lost. Our concept included some fairly ambitious future possibilities and technologies. The other solution was simpler and could be fitted more easily into the organisation's current environment. At first I thought: So our solution was too advanced? That was a slightly strange way to lose a hackathon. But after thinking about it, I was not really disappointed anymore. I was proud of what our team had produced.

# Ideas / Insights

And there was actually a very useful product lesson hidden in that result. We had been given a challenge and encouraged to innovate, but we had not been given detailed information about the organisation's existing architecture or technical capabilities. We therefore optimized heavily for the problem, the user experience and what the solution could eventually become. In a real customer project I would now ask another question much earlier: What is the best solution this organisation can realistically adopt, operate and develop right now? The technically most capable solution is not automatically the best first solution.

And then there was another lesson from the whole hackathon. There are now a ridiculous number of AI tools available. Image generators, coding agents, research agents, design tools, assistants and everything in between. But eventually it still comes down to one thing: **A tool is only as useful as the person using it and the process around it.**

If I had opened Figma AI without understanding the problem and simply asked it to design a healthcare application, I doubt we would have ended up with the same result. The research, the team discussions, the domain knowledge, the constraints and the carefully defined user flows came first. The AI accelerated the part where we lacked expertise. That is probably the most important lesson for me: when using AI for something where you are not an expert yourself, first learn enough about the problem, the tool's capabilities and its limitations to recognize whether the result actually makes sense.

This time I was also a lucky bastard.

But at least now I understand a little better why I got lucky.

# Notes - continued again

After the hackathon I returned to local AI. Apparently I had not learned my lesson about choosing small and simple projects. I had another repository called `local-ai-knowledge-vault`, which had originally started as an experiment around local RAG, controlled access to company knowledge and the idea that an LLM should not simply be handed the keys to everything a company owns.

The basic idea was quite simple:

**The model should not have direct access to company systems. It should receive only the information it is allowed to use for the task it is currently doing.**

Simple idea. Naturally this resulted in Docker, Ollama, Open WebUI, an MCP server, synthetic manufacturing data, several services talking to each other and quite a few new opportunities to make something unnecessarily complicated.

## Building something that actually runs

The first versions of the project were mostly architecture and individual building blocks. Document ingestion, chunking, local storage, retrieval, source references and tests. That was useful, but I wanted something I could actually demonstrate. Not another architecture diagram.

Something where I could open a browser, type a question and show how a local model could interact with controlled manufacturing data without giving the model unrestricted access to the underlying files or systems. So I built a separate prototype environment.

The prototype eventually had three main parts:

* **Ollama** running the local language model
* **Open WebUI** providing the user interface
* a small **manufacturing MCP server** exposing only explicitly defined read-only tools

I also created synthetic manufacturing data for the demo. No customer data, no confidential drawings, no mysterious `final_final_revision_7_REAL.xlsx` accidentally committed to GitHub. The MCP server was intentionally boring. It exposed exactly four controlled tools. The model could ask for specific information, but it could not wander around the filesystem, browse databases or suddenly decide that it had always wanted to become an ERP administrator.

That was the point.

Then everything worked. Except for one minor detail.

It was painfully slow.

## The world's slowest "OK"

At some point I reduced the problem to what should have been the easiest possible AI benchmark:

> Reply exactly with: OK

Two letters.

No RAG.

No MCP call.

No reasoning required.

Thinking disabled.

Small local model.

And sometimes I could almost have made coffee while waiting for the answer.

This was running on my old HP ZBook with an 8th generation Core i7, 16 GB of RAM and CPU-only inference, so obviously I was not expecting datacenter performance. But this was ridiculous even for old hardware. So I started removing variables.

I changed the model. I tested cold starts separately from warm inference. I adjusted Docker resource behaviour. I made sure Ollama kept the model loaded instead of constantly evicting and reloading it. I disabled background features in Open WebUI. Autocomplete generation off. Follow-up generation off. Title generation off. Tags off. Search-query generation off. Image generation off. Code execution off. Memories off.

Pretty much everything that could politely be told to stop doing things in the background was told to stop doing things in the background. Performance improved in some cases, but there was still something strange happening. The most confusing clue was that the first request could take several minutes, while later requests suddenly became much faster. That made model loading look guilty. It was not innocent, but it was not the murderer either.

Eventually I stopped looking at the visible settings and looked at what Open WebUI was actually sending to Ollama.

And there it was.

For my magnificent three-word prompt:

> Reply exactly with: OK

Open WebUI was also sending definitions for **34 built-in tools**.

The tool definitions alone were around **21.5 kB of JSON**, corresponding to several thousand prompt tokens. So the little 2B model was not spending most of its time thinking about "OK". Before reaching my three words, it had effectively been handed a small instruction manual explaining dozens of tools it had absolutely no reason to know about. 

On a fast GPU this overhead might have been merely annoying. On an older CPU it became comedy.

The reason later requests were much faster also suddenly made sense: much of the common prompt prefix could be cached. The solution was almost embarrassingly simple.

**Disable Open WebUI's built-in tools and expose only the tools the model actually needs.**

For normal chat: no tools. For document RAG: document context. For the manufacturing demo: exactly the four MCP tools I intentionally created. That changed the whole way I now think about local LLM performance. I had originally been looking at model size, RAM, Docker settings and inference speed. Those things matter. But there is another resource that is just as real:

**context budget.**

Every tool description, system prompt, retrieved document, memory, conversation message and piece of metadata eventually becomes something the model has to process. A 2B model on an old laptop taught me this much more effectively than any diagram about context windows ever could. 

The funniest part is that the final fix was not some exotic AI optimization. It was ordinary engineering:

measure what happens, remove variables, inspect the interfaces and stop sending thousands of tokens nobody asked for. The machine was not stupid. I was simply giving it far too much homework before asking it to say "OK".

## And then I took the prototype into the real world

There is another reason I have been experimenting with these things. I am currently finishing my Production Engineering studies, and I need to start my engineering thesis. This has turned out to be surprisingly difficult. Not because I cannot think of topics. Quite the opposite. I can think of far too many...

AI in manufacturing.
Local AI.
Production data.
Engineering documentation.
RAG.
MCP.
CAD information.
ERP and PDM integrations.
Quality data.
AI governance.
Knowledge management.
Local models.
Multimodal models.

At this rate the thesis title would require its own table of contents. The bigger problem is that I do not yet have the partner company. And without a real company and a real problem, choosing the technical solution first would be exactly the mistake I keep telling myself not to make.  So instead of starting with a thesis title, I have been carrying around a research question.

In simplified form:

**Can a manufacturing company make useful use of generative AI over its internal production and engineering knowledge while still keeping access to that information controlled, traceable and compatible with the realities of the organisation?**

Behind that is a working hypothesis:

The biggest obstacle to industrial AI adoption may not actually be the language model. The harder problems may be the boring ones around it:

* where the data is
* who owns it
* who may access it
* what customer contracts allow
* which systems contain it
* how access rights are inherited
* what information may leave the company
* how results can be verified
* and whether the organisation trusts the whole arrangement enough to use it

I wanted to test whether that assumption survives contact with an actual manufacturing company. So I took the prototype and went to talk with one.

The company is not a tiny workshop experimenting with ChatGPT during coffee breaks. It employs roughly **350 people** and has annual revenue approaching **€100 million**. They manufacture real products for real customers, and some of those customers operate under extremely strict confidentiality requirements. I expected to spend a lot of the discussion explaining what RAG, local models and MCP were. That assumption lasted for approximately five minutes. The person I met was not an AI novice at all. As a hobby project he had already put a small language model on a Raspberry Pi and connected it to Open WebUI.

So there went my planned introduction to local LLMs. What followed was much more useful. We started talking about what prevents these technologies from simply being adopted inside the company. And very quickly the conversation stopped being mainly about model intelligence. It became a discussion about information.

If a model has access to engineering documents, who is allowed to ask questions from them? What happens when two employees have different access rights? Can an AI system process information covered by customer confidentiality agreements? Does keeping the model locally actually solve the contractual problem? Who administers the system? Can even the person who built the AI environment be prevented from seeing confidential source data? How would permissions from existing identity management and file systems carry into the AI layer? What should the LLM see? What should the user see?

And perhaps most importantly:

**Just because something can technically be made secure, does the existing customer agreement actually allow it to be processed this way?**

That was the wall. And it was a very useful wall to run into. My prototype architecture already assumed that the LLM itself should not have unrestricted access to company systems. MCP tools can provide narrow interfaces, RAG can retrieve only selected context and identity management can determine which information the user is permitted to access.

But the meeting made something much clearer.

Technical access control is only one layer. You can build the world's most beautifully isolated local AI server, disconnect it from the Internet, place it behind six firewalls and personally stand beside it holding a fire extinguisher. If the contract says that the information cannot be processed in that way, the answer is still no. And that is exactly why the meeting was so valuable.

## Maybe I finally found the actual thesis problem

I went into the meeting thinking about AI-assisted use of manufacturing information. I came out thinking much more about **controlled AI-assisted use of manufacturing information**. That one word changes quite a lot. The discussion did not prove my hypothesis. One company and one conversation would make for a rather questionable scientific method. But it gave me the first strong practical evidence that the research question is pointing somewhere useful.

The interesting industrial AI problem may not be:
> How do we connect an LLM to company data?

Technically, there are already many ways to do that. The much more interesting question may be:
> How do we give an AI system useful access to company knowledge without accidentally giving either the model or the wrong human access to information they should never see?

That leads immediately into architecture, RAG, MCP, identity management, local inference, auditability, information classification and existing enterprise systems. But it also leads into contracts, governance, organisational responsibility and trust. Suddenly my inability to decide on a thesis title does not feel quite as annoying. Maybe I was trying to name the solution before I properly understood the problem.

Again.

There seems to be a pattern developing here.

The hackathon taught me that the technically most capable solution is not necessarily the solution an organisation can realistically adopt. The local AI prototype taught me that the fastest model is not necessarily the most important optimization if I am accidentally feeding it thousands of useless tokens. And this company discussion taught me that keeping AI local does not magically make confidential information safe or legally usable.

Three fairly different experiences. Same lesson:

**The interesting engineering usually starts where the technology meets reality.**

Which is inconvenient. Reality has terrible documentation.

