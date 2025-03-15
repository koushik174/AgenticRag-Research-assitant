# AgenticRag-Research-assitant
# AgentRAG: Autonomous Research Assistant

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
![Python](https://img.shields.io/badge/python-v3.8+-success.svg)
![Torch](https://img.shields.io/badge/PyTorch-2.0+-red.svg)
[![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/yourusername/agent-rag/blob/main/AgentRAG_Colab.ipynb)

AgentRAG is a powerful autonomous research system that combines retrieval-augmented generation with agent-like behaviors to deliver comprehensive answers to complex questions.

## Features

- **Autonomous Web Research**: Dynamically searches for information relevant to user queries
- **Semantic Document Processing**: Chunks and embeds documents for accurate information retrieval
- **Multi-step Reasoning**: Breaks down complex questions into manageable research steps 
- **Follow-up Generation**: Automatically identifies and explores important follow-up questions
- **Comprehensive Synthesis**: Combines findings from multiple research paths into cohesive answers
- **Source Attribution**: Tracks and provides sources for all retrieved information

## Demo

![AgentRAG Demo](assets/agent-rag-demo.gif)

Try out AgentRAG directly in [Google Colab](https://colab.research.google.com/github/yourusername/agent-rag/blob/main/AgentRAG_Colab.ipynb).

## Installation

### Prerequisites

- Python 3.8+
- PyTorch 2.0+
- Transformers 4.30+
- A Serper API key (for web search)
- An OpenAI API key (for LLM capabilities)

### Setup

```bash
# Clone the repository
git clone https://github.com/yourusername/agent-rag.git
cd agent-rag

# Install dependencies
pip install -r requirements.txt

# Create .env file and add your API keys
cp .env.example .env
# Edit .env with your API keys
```

## Quick Start

```python
from agentrag import AgentRAG, AgentConfig

# Initialize the agent
agent = AgentRAG()

# Process a simple query
result = agent.process_query("What are the environmental impacts of electric vehicles?")
print(result["answer"])

# Perform deeper research with follow-up questions
research = agent.recursive_research("How does quantum computing affect cybersecurity?")
print(research["final_answer"])
```

## How It Works

AgentRAG operates through a 7-step process:

1. **Query Reception**: The system receives a user question
2. **Knowledge Check**: Searches existing knowledge in the vector store
3. **Web Research**: Retrieves relevant information from the web
4. **Contextualization**: Processes and indexes new information
5. **Answer Generation**: Produces an initial response
6. **Follow-up Research** (optional): Explores deeper aspects of the topic
7. **Synthesis**: Creates a comprehensive answer from all findings

## System Architecture

AgentRAG consists of four main components:

1. **Vector Store**: Manages document embeddings and semantic search
2. **Web Retriever**: Handles web search and content extraction
3. **LLM Interface**: Connects to language models for response generation
4. **Agent Orchestrator**: Coordinates the research and response process

## Example Use Cases

- Academic research assistance
- Complex topic exploration
- Technical documentation research
- Competitive analysis
- Legal and regulatory research
- Medical literature review

## Advanced Usage

### Custom Embedding Models

```python
config = AgentConfig(
    model_name="sentence-transformers/all-mpnet-base-v2",
    chunk_size=1024,
    chunk_overlap=100
)

agent = AgentRAG(config)
```

### Recursive Research with Custom Depth

```python
# Perform deeper research with more follow-up questions
deep_research = agent.recursive_research(
    "What are the latest advancements in quantum computing?",
    max_depth=4  # Default is 2
)
```

## Limitations

- Web content extraction may be imperfect due to site structures and anti-scraping measures
- Search API costs can accumulate with heavy usage
- Research quality depends on available information online
- Not suitable for real-time applications due to processing time

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Hugging Face](https://huggingface.co/) for the transformers library
- [OpenAI](https://openai.com/) for the LLM capabilities
- [Serper](https://serper.dev/) for the search API

## Contact

If you have any questions or feedback, please open an issue or contact the maintainers.
