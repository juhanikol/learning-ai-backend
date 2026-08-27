# learning-ai-backend
A local-first AI backend for experimenting with retrieval-augmented generation, local LLMs, tool calling and Model Context Protocol.

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
This project was paused for a while because I participated on hackathon event. The application and details the about the solution unfortunately cannot be shared because of NDA. But the challenge was totally different area where I have been working. It was about creating best possible UX/UI experience for app used in criticcal healtcare situations. The task was fun and the organizers specifically asked us to come up with new ideas or approaches. This time my background in healthcare was very useful because I was instantly able to scope the risks, needed health information, useful other healthcare applications and the integrations needed. I actually had time to do actual academic work and do proper research about the issues in that critical situation.
Our team also had another healthcare professional and mom of three. The sensitive experiences shared by the mom were extremely valuable to focus our consept in right direction and in a way that in critical situation the application is actually useful, does not increase cognitive load and serves both patient and the healthcare professionals. We were able to identify critical flows and how different user flows should advance in different situation. My own experience from healthtech solutions brought the expertise of thinking the actual requirements that are considered good practice or are regulated by law. 
After this research session when our team felt ready we were faced with the task of creating the UI. Most of the good user experience flows were already identified so UI was the most important part. After discussing together we all realised that none of us have enough experience or knowledge about designing UI. Well I had some, but that experience was not compatible to this case no other ways than explaining consept ideas of good UI practices for healthtech applications.
We decided to explore possibilities. After some discussion about the possibilities team member suggested using figma, because she had heard from UI desigener from previous project of her that using that is very easy way to desing UI mockups. So on we go. While other two were designing different versions to come up with ideas I listened carefully about their ideas, challenges and discussion about their creations. I decided to create detailed explanation how the UI should look like and how the risks, research and flows could connect to their experiments and good ideas. Then I prompted the figma design AI and voila! It was like a professional had done it! Right before my eyes was the home page of our application and what was even more impressive that I did not specify color palettes either than explained accessibility requirements, but still I had visually very pleasing yet still inviting and modern desing with wonderful color palette. We decided to got with that desing as base and followed the design of that creating other views, screens flow etc..
I was astouned about the capability of figma AI designing such a beatiful design. How that was possible? But soon I learnde from my teammates and other developers that figma actually typically does not create that impressive and detailed UI mockups right away. And after some online research I found out that it was actually my carefully explained user flows, accessibility requirements, needed features, buttons and transitions that made that possible. Adn just by a change I managed to prompt it in a way that drifting, hallucination and other AI related problems were avoided.
We unfortunately did not win. We were second. From the judges we asked that what was the deciding factor? They revealed that our solution and other solution had exactly same score combined from 4 judges and their criteria. They also said that they did not even expect such impressive yet different solutions so they decided to come up with new criteria. Judges discussed it and they decided to review solutions comparing applications suitability to their organizations infrastructure and architecture. We lost that because our application was actually too advanced and presented new useful techonologies and frameworks their organization could not yet handle! So our solution was too good? It was too advanced! None of the teams were debriefed about the customers architecture. We could not have anticipated and plan that. Figure that! After hearing that I was not anymore disappointed. I was glad and proud. Proud of my team mates and our work. I totally understand organisations limitations but in this case I did not mind that our solution was too advanced!
However the lesson from this hackathon was that even though there are ton of different AI tools and solutions, still everything comes to a fact: Tools is as good as the tool user. This is a lesson that the limitations, possibilities and good practices should be always first researched before using AI tools in some critical task where you are not an expert at all. This time I was lucky bastard! 

After this research phase and 

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

