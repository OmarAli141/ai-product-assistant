# AI Product Procurement Assistant

An intelligent multi-agent system built with CrewAI that automates product search, comparison, and procurement report generation.

## 🚀 Features

- **Smart Search Query Generation**: AI-powered agent generates optimized search queries for product discovery
- **Web Search Integration**: Uses Tavily API to search across multiple e-commerce platforms
- **Product Scraping**: Extracts detailed product information including prices, specs, and images
- **Automated Report Generation**: Creates professional HTML procurement reports with analysis and recommendations
- **Multi-Agent Architecture**: Specialized AI agents work together sequentially to complete the procurement workflow

## 🛠️ Tech Stack

- **CrewAI**: Multi-agent orchestration framework
- **Google Gemini 2.5 Pro**: LLM for agent reasoning
- **Tavily**: Search engine API
- **Scrapegraph**: Web scraping service
- **AgentOps**: Agent monitoring and observability

## 📋 Prerequisites

- Python 3.11.x
- API Keys for:
  - Google Gemini (GOOGLE_API_KEY)
  - Tavily (TAVILY_API_KEY)
  - Scrapegraph (SCRAPEGRAPH_API_KEY)
  - AgentOps (AGENTOPS_API_KEY) - optional

## ⚙️ Installation

1. Clone the repository:
```bash
git clone <your-repo-url>
cd ai-agent
```

2. Create and activate a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Create a `.env` file in the root directory:
```env
GOOGLE_API_KEY=your_google_api_key
TAVILY_API_KEY=your_tavily_api_key
SCRAPEGRAPH_API_KEY=your_scrapegraph_api_key
AGENTOPS_API_KEY=your_agentops_api_key
```

## 🎯 Usage

1. Update the input parameters in `coffe_machine.py`:
```python
crew_results = rankyx_crew.kickoff(
    inputs={
        "product_name": "your product name",
        "websites_list": ["website1.com", "website2.com"],
        "country_name": "Country",
        "no_keywords": 10,
        "language": "English",
        "score_th": 0.10,
        "top_recommendations_no": 10
    }
)
```

2. Run the script:
```bash
python coffe_machine.py
```

3. Check the output in the `ai-agent-output/` directory:
   - `search_queries.json`: Generated search queries
   - `step_2_search_results.json`: Search results
   - `step_3_extracted_products.json`: Scraped product data
   - `step_4_procurement_report.html`: Final procurement report

## 📁 Project Structure

```
ai-agent/
├── coffe_machine.py      # Main script with agent definitions
├── requirements.txt      # Python dependencies
├── .env                  # Environment variables (not in repo)
├── .gitignore           # Git ignore rules
└── ai-agent-output/     # Generated outputs
```

## 🔧 Configuration

The system uses four specialized agents:

1. **Search Queries Recommendation Agent**: Generates optimized search queries
2. **Search Engine Agent**: Searches for products using Tavily
3. **Scraping Agent**: Extracts detailed product information
4. **Procurement Report Author Agent**: Creates the final HTML report

