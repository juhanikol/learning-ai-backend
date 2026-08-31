# learning-ai-backend
A local-first AI backend for experimenting with retrieval-augmented generation, local LLMs, tool calling and Model Context Protocol.

# Local AI Backend Platform

A local-first AI backend for experimenting with retrieval-augmented
generation, local LLMs, tool calling and Model Context Protocol.

The project explores production-oriented AI backend architecture including:

- local inference with Ollama
- document ingestion and chunking
- PostgreSQL + pgvector
- semantic and hybrid retrieval
- RAG with source attribution
- configurable AI assistants
- MCP tools and resources
- retrieval evaluation
- API testing
- containerized deployment
- observability

## Status

Early development. The project is currently establishing its foundation before implementing other features.

## Why this project exists

This repository is  my structured learning environment for modern AI backend engineering. Each milestone introduces a new capability and documents the engineering decisions, experiments and results.

## AI Backend Engineer Learning Roadmap
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

# Prequisites
* Learn from online sources
* Make notes
* Document ideas and realizations

# AI related consept detailed

Consept detailed according to lessons learned and available technologies.

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

# Preliminary solution structure:

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


-- TO BE MOVED TO OTHER DOCS
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


