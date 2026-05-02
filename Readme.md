🧠 AI Blog Generator using LangGraph + Gemini

An agentic AI pipeline that automatically generates structured, high-quality technical blogs using LLMs.
This project uses a multi-step workflow (LangGraph) to plan, research, write, and compile blog content.

🚀 Features
🔀 Dynamic Routing
Decides whether research is needed (closed_book, hybrid, open_book)
🔎 Automated Research
Uses Tavily API to fetch relevant, up-to-date web results
🧩 Structured Planning
Generates a detailed blog outline with sections, goals, and bullets
✍️ Section-wise Generation
Each section is written independently using LLM workers
🧵 Parallel Execution
Multiple sections generated simultaneously using LangGraph fan-out
📄 Markdown Output
Automatically saves the final blog as a .md file
🏗️ Architecture
            ┌──────────┐
            │  Router  │
            └────┬─────┘
                 │
        ┌────────▼────────┐
        │ Research (opt.) │
        └────────┬────────┘
                 │
        ┌────────▼────────┐
        │ Orchestrator    │
        │ (Plan Builder)  │
        └────────┬────────┘
                 │
         Fan-out to Workers
        ┌───────▼────────┐
        │ Section Writers │
        └───────┬────────┘
                 │
           ┌─────▼─────┐
           │ Reducer   │
           │ (Compile) │
           └───────────┘
🛠️ Tech Stack
LangGraph – Workflow orchestration
Google Gemini API – LLM generation
Tavily Search API – Web research
Pydantic – Structured schemas
Python – Core implementation
📦 Installation
1. Clone the repo
git clone https://github.com/your-username/ai-blog-generator.git
cd ai-blog-generator
2. Install dependencies
pip install -r requirements.txt
3. Setup environment variables

Create a .env file:

GOOGLE_API_KEY=your_google_api_key
TAVILY_API_KEY=your_tavily_api_key
▶️ Usage

Run the script:

python main.py

Or call the function manually:

run("Write a blog on the latest developments in AI agents.")
📄 Output
Generates a complete blog
Saves it as:
<Blog_Title>.md

Example:

Latest Developments in AI Agents.md
🧠 Workflow Explanation
1. Router
Decides:
Does this topic need research?
What mode to use?
2. Research Node
Fetches web data
Filters and deduplicates sources
3. Orchestrator
Creates a structured blog plan:
5–9 sections
Goals
Bullet points
4. Worker Nodes
Each worker:
Writes one section
Follows strict constraints
5. Reducer
Combines all sections
Saves final Markdown file
⚙️ Modes
Mode	Description
closed_book	No research needed (concept-based topics)
hybrid	Some research + reasoning
open_book	Fully research-based (latest/news topics)
🔒 Constraints & Safety
Ensures:
No empty outputs
Structured JSON generation
Controlled hallucination using evidence
In open_book mode:
Only uses verified sources
Adds citations to claims
💡 Example Use Cases
Technical blogging automation
AI content pipelines
Developer advocacy tools
Research summarization systems
AI agents experimentation
🧪 Future Improvements
Add UI (Streamlit / React)
Support multiple LLM providers
Add fine-tuning support
Export to PDF / DOCX
Add SEO optimization
🤝 Contributing

Pull requests are welcome!
For major changes, open an issue first to discuss.


⭐ If you like this project

Give it a star ⭐ and share it!