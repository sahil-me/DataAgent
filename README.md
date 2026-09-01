# 🤖 DataAgent 📊

https://github.com/user-attachments/assets/3b66184a-22de-4a2b-8d26-8f0f5c8836f5

> 🎥 Watch **DataAgent** in action!

---

## Table of Contents

- [Introduction](#introduction)
- [Architecture Diagram](#architecture-diagram)
- [Project Structure](#project-structure)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Application Workflow](#application-workflow)
- [Screenshots](#screenshots)
- [AI-Assisted Development](#ai-assisted-development)
- [Google Codelab Reference](#google-codelab-reference)
- [Future Enhancements](#future-enhancements)
- [Resources](#resources)
- [Disclaimer](#disclaimer)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

---

## Introduction

**DataAgent** is an AI-powered data analysis agent that allows users to ask natural-language questions about structured data and receive data-driven answers.

The application combines **Google Agent Development Kit (ADK)**, **Gemini**, and the **BigQuery MCP Server** to allow an AI agent to explore and analyze data stored in BigQuery.

Instead of requiring users to manually write SQL queries, the agent can understand a natural-language request, inspect the available dataset and schema, formulate an appropriate analysis plan, generate SQL queries, and retrieve relevant results through the BigQuery MCP tools.

The project uses the public **NYC Citi Bike dataset** available through BigQuery and demonstrates how an AI agent can interact with structured data through the **Model Context Protocol (MCP)**.

The application is deployed as a containerized agent on **Google Cloud Run**, providing a serverless environment for running the DataAgent.

---

## Architecture Diagram

The following diagram illustrates the high-level architecture of **DataAgent**, including the user's browser, Google Cloud Run, Google Agent Development Kit (ADK), Gemini, BigQuery MCP Server, and the BigQuery public dataset.

<img width="590" height="442" alt="Architecture Diagram" src="https://github.com/user-attachments/assets/35f1b56a-09db-46ee-8cce-b82d3433781b" />

### Architecture Overview

1. **User Browser**
   - Provides the web interface for interacting with DataAgent.
   - Allows users to ask natural-language questions about the available data.
   - Displays the agent's analysis and results.

2. **Google Cloud Run**
   - Hosts the deployed DataAgent application.
   - Provides the serverless runtime environment for the AI agent.
   - Runs the containerized agent application.

3. **Google Agent Development Kit (ADK)**
   - Provides the agent development and execution framework.
   - Manages the LLM agent and its available tools.
   - Connects the agent with the BigQuery MCP Server.

4. **Gemini**
   - Provides model inference for understanding user questions.
   - Helps the agent reason about the available data.
   - Generates analysis plans and SQL queries.

5. **BigQuery MCP Server**
   - Provides MCP-based access to BigQuery.
   - Exposes tools for dataset and table discovery.
   - Allows the agent to retrieve schema information and execute read-only SQL queries.

6. **BigQuery**
   - Provides the structured data source used by the agent.
   - Uses the public `bigquery-public-data.new_york_citibike` dataset.
   - Provides Citi Bike station and trip data for analysis.

---

## Project Structure

```text
DataAgent/
│
├── data_agent/
│   ├── data_agent/
│   │   ├── __init__.py
│   │   ├── agent.py
│   │   └── requirements.txt
│   └── env.sh
│
├── .gitignore
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── LICENSE
├── README.md
└── SECURITY.md
```

> The `data_agent/` directory contains the main ADK agent implementation, dependencies, and environment configuration used by the project.

---

## Features

  - **Natural-Language Data Analysis:** Ask questions about structured data using conversational language.
  - **Gemini-Powered Agent:** Uses Gemini for reasoning, planning, and response generation.
  - **Google ADK Integration:** Uses Google Agent Development Kit for agent development and runtime execution.
  - **BigQuery MCP Integration:** Connects the AI agent to BigQuery through the BigQuery MCP Server.
  - **Dataset Exploration:** Allows the agent to inspect available datasets and tables before performing analysis.
  - **Schema-Aware Analysis:** The agent examines table schemas and data dimensions before generating queries.
  - **Read-Only SQL Execution:** Uses the `execute_sql_readonly` MCP tool for querying data without modifying the underlying dataset.
  - **SQL Generation:** Generates BigQuery SQL based on the user's natural-language request.
  - **Data-Grounded Responses:** Uses retrieved BigQuery information to produce data-driven answers.
  - **MCP Toolset:** Integrates BigQuery MCP tools including dataset information, table discovery, schema inspection, and read-only SQL execution.
  - **ADK Web Interface:** Supports local interactive testing through the ADK web interface.
  - **Cloud Run Deployment:** Deploys the agent as a containerized service on Google Cloud Run.

---

## Tech Stack

| Technology                             | Purpose                                 |
| -------------------------------------- | --------------------------------------- |
| **Python**                             | Primary programming language            |
| **Google Agent Development Kit (ADK)** | Agent development and runtime framework |
| **Gemini**                             | LLM inference and agent reasoning       |
| **BigQuery MCP Server**                | MCP-based access to BigQuery            |
| **BigQuery**                           | Structured data storage and analysis    |
| **Model Context Protocol (MCP)**       | Agent-to-data tool integration          |
| **Google Cloud Run**                   | Serverless agent deployment             |
| **Docker**                             | Containerized deployment                |
| **Google Cloud**                       | Cloud infrastructure and services       |
| **Git**                                | Version control                         |
| **GitHub**                             | Source code hosting                     |

---

## Application Workflow

**DataAgent** follows a data-grounded agent workflow for analyzing structured BigQuery data.

1️⃣ **User Query**

  - The user opens the DataAgent interface and asks a natural-language question about the available data.
  - Example:
    - "We have budget for 3 coffee trucks. What are the best Citi Bike stations to place them?"

2️⃣ **Agent Understanding**

  - The **LlmAgent** interprets the user's question and determines what information is required to answer it.

3️⃣ **Dataset Exploration**

  - The agent uses BigQuery MCP tools to inspect the available dataset and tables.
  - It can use tools such as:
    - list_table_ids
    - get_dataset_info
    - get_table_info

4️⃣ **Schema Analysis**

  - The agent analyzes table schemas, column types, dimensions, and available values before constructing the query.
  - The workflow is designed to avoid making assumptions about the underlying data structure.

5️⃣ **Analysis Planning**

  - The agent formulates a plan for answering the user's question based on the available BigQuery data.

6️⃣ **SQL Generation**

  - The agent generates an appropriate BigQuery SQL query based on the user's request and the discovered schema.

7️⃣ **Read-Only Query Execution**

  - The generated SQL is executed through the BigQuery MCP Server using the `execute_sql_readonly` tool.
  - The workflow uses dry-run validation to verify SQL correctness before retrieving results.

8️⃣ **Data Analysis**

  - The agent analyzes the returned BigQuery results and uses them to formulate the response.

9️⃣ **Final Response**

  - The agent returns a natural-language answer containing the relevant findings and recommendations.

---

## Screenshots

### Google Cloud Run Services

<img width="1366" height="690" alt="Google Cloud Run Services" src="https://github.com/user-attachments/assets/64334b38-9472-47d6-ab91-2a35917c53da" />

### Project Source Code

<img width="1366" height="768" alt="Project Source Code" src="https://github.com/user-attachments/assets/2d835773-4cdb-4c24-97cd-0b2de01479bd" />

### Cloud Run Overview

<img width="1366" height="687" alt="Cloud Run Overview" src="https://github.com/user-attachments/assets/945f2058-07cb-425e-b698-0cf5e42c9993" />

### Cloud Run Service Logs

<img width="1366" height="644" alt="Cloud Run Service Logs" src="https://github.com/user-attachments/assets/c5601bbd-c031-48c2-8880-0e0cd9d8655f" />

### Cloud Run Metrics

<img width="1366" height="684" alt="Cloud Run Metrics-1" src="https://github.com/user-attachments/assets/e82c8386-ce10-469b-941e-6b6e37889eb9" />
<img width="1366" height="690" alt="Cloud Run Metrics-2" src="https://github.com/user-attachments/assets/6f696ed0-f3da-4f5e-afc3-992a9a6c8c89" />
<img width="1366" height="685" alt="Cloud Run Metrics-3" src="https://github.com/user-attachments/assets/f5d03109-e269-47d3-965d-b86a7f3e83fc" />
<img width="1365" height="681" alt="Cloud Run Metrics-4" src="https://github.com/user-attachments/assets/d75e2fc5-9de8-490e-b152-8c0c217b35f2" />
<img width="1366" height="678" alt="Cloud Run Metrics-5" src="https://github.com/user-attachments/assets/ca68eedb-b3c5-47d6-a064-c8e51f701c45" />
<img width="1366" height="689" alt="Cloud Run Metrics-6" src="https://github.com/user-attachments/assets/93a33af2-cf15-47b4-92ca-e7b9f3e2d087" />
<img width="1366" height="682" alt="Cloud Run Metrics-7" src="https://github.com/user-attachments/assets/3155cb88-5002-4cc8-9ecf-c430e84f5fca" />
<img width="1366" height="683" alt="Cloud Run Metrics-9" src="https://github.com/user-attachments/assets/e323a835-144a-40de-a877-e28f1bddcf28" />

---

## AI-Assisted Development

**DataAgent** was developed with the assistance of AI tools during the development process.

AI assistance was used to support areas such as:
- Agent development.
- Google ADK integration.
- BigQuery MCP integration.
- MCP tool configuration.
- Prompt and instruction design.
- SQL workflow design.
- Google Cloud deployment guidance.
- Debugging and troubleshooting.
- Documentation and development guidance.

AI-generated suggestions and code were reviewed, modified, integrated, tested, and adapted as part of the development process.

The final project reflects the implemented agent architecture, MCP workflow, BigQuery integration, and Google Cloud deployment configuration.

---

## Google Codelab Reference

This project was developed as an implementation and extension of Google's official hands-on codelab:

[Build and Deploy AI Agents with Gemini and BigQuery MCP server in Cloud Run](https://codelabs.developers.google.com/codelabs/cloud-run/cloud-run-adk-gemini-bq-mcp)

The official codelab demonstrates how to:
- Create an AI Agent using Google Agent Development Kit (ADK).
- Use Gemini in Agent Platform.
- Connect an AI agent to structured BigQuery data.
- Use the BigQuery MCP Server.
- Analyze the public NYC Citi Bike dataset.
- Deploy the agent to Google Cloud Run.

**DataAgent** follows the core concepts and workflow introduced in the codelab while the project implementation, configuration, experimentation, testing, deployment, and documentation were developed and adapted as part of this project.

---

## Future Enhancements

The following improvements could be considered in future iterations of **DataAgent**:

- Expanded Data Sources: Support additional BigQuery datasets and structured data sources.
- Advanced Analytics: Support more complex analytical questions and multi-step analysis.
- Data Visualization: Generate charts and visualizations from query results.
- Conversation Memory: Add improved contextual memory for longer analytical conversations.
- Multi-Dataset Support: Allow the agent to analyze multiple datasets and tables.
- Query Optimization: Improve generated SQL for performance and cost efficiency.
- Automated Evaluation: Add evaluation cases for SQL correctness, grounding, and analytical accuracy.
- Observability: Add improved logging, monitoring, and tracing for agent and MCP performance.
- Additional MCP Tools: Integrate additional MCP servers and tools for broader data access.

---

## Resources

[![Google ADK](https://img.shields.io/badge/Google%20ADK-Documentation-4285F4?logo=google)](https://google.github.io/adk-docs/)
[![Gemini](https://img.shields.io/badge/Gemini-Documentation-8E75B2?logo=google)](https://ai.google.dev/)
[![BigQuery](https://img.shields.io/badge/BigQuery-Documentation-4285F4?logo=googlecloud)](https://cloud.google.com/bigquery/docs)
[![Cloud Run](https://img.shields.io/badge/Google%20Cloud%20Run-Documentation-4285F4?logo=googlecloud)](https://cloud.google.com/run/docs)
[![Google Cloud](https://img.shields.io/badge/Google%20Cloud-Documentation-4285F4?logo=googlecloud)](https://cloud.google.com/docs)
[![Python](https://img.shields.io/badge/Python-Documentation-3776AB?logo=python)](https://docs.python.org/3/)
[![MCP](https://img.shields.io/badge/Model%20Context%20Protocol-Documentation-5C5CFF)](https://modelcontextprotocol.io/)
[![Google Codelabs](https://img.shields.io/badge/Google-Codelabs-4285F4?logo=google)](https://codelabs.developers.google.com/)

---

## Disclaimer

**DataAgent** is an AI-powered application developed for learning, experimentation, and demonstration purposes.

The project uses third-party services including **Google Cloud**, **Google Cloud Run**, **Google Agent Development Kit**, **Gemini**, **BigQuery**, and the **BigQuery MCP Server**. Their availability, functionality, usage limits, pricing, and applicable policies are subject to the respective providers' terms and documentation.

AI-generated responses and data analysis may contain errors or omissions. Results should be reviewed against the underlying BigQuery data before being used for business, operational, or other real-world decisions.

The project is provided "as is" without warranties of any kind, to the extent permitted by applicable law.

---

## Contributing

Contributions are welcome. Before submitting changes, please review:

- [Contributing Guide](./CONTRIBUTING.md)
- [Code of Conduct](./CODE_OF_CONDUCT.md)
- [Security Policy](./SECURITY.md)

---

## License

This project is licensed under the **Apache License 2.0**.

See the [**LICENSE**](./LICENSE) file for details.

---

## Author

[**Sahil Sharma**](https://github.com/sahil-me)

Thank you for exploring **DataAgent**. If you found the project useful, consider giving the repository a ⭐ to show your support.
