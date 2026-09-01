<!---
Copyright 2026 Sahíl Sharma. All rights reserved.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
-->

# Contribute to DataAgent

Everyone is welcome to contribute, and we value every contribution. Code contributions are not the only way to support the project. Improving AI agent behavior, BigQuery data analysis, MCP integration, Google Cloud deployment, performance, security, testing, or documentation are all valuable ways to contribute to **DataAgent**.

If you find this project helpful, consider sharing it with others, referencing it in your projects, discussing it with the community, or simply giving the repository a ⭐️ to support the project.

**However you choose to contribute, please be mindful and respect our [Code of Conduct](https://github.com/sahil-me/DataAgent/blob/main/CODE_OF_CONDUCT.md).**

## Ways to contribute

There are several ways you can contribute to **DataAgent**.

* **AI Agent Improvements**: Improve the agent's ability to understand analytical questions, reason over available data, and provide clear and useful responses.
* **BigQuery Improvements**: Improve data analysis workflows, SQL generation, query accuracy, schema exploration, and analytical reasoning.
* **MCP Integration**: Improve the integration with the BigQuery MCP Server and the use of available MCP tools.
* **Data Analysis**: Improve the agent's ability to investigate tables, understand schemas, identify dimensions, and perform meaningful aggregations and filtering.
* **Bug Fixes**: Identify and fix bugs or unexpected behavior in the agent or supporting configuration.
* **Performance Optimization**: Improve agent response time, query efficiency, resource usage, and overall application performance.
* **Security Improvements**: Help identify and address security issues related to authentication, Google Cloud access, MCP communication, configuration, or secrets.
* **Testing**: Add or improve tests for agent behavior, SQL generation, MCP tool usage, and data-analysis workflows.
* **Google Cloud Improvements**: Improve the use of Google ADK, Gemini, BigQuery, MCP, Cloud Run, or related Google Cloud services.
* **Documentation**: Improve the README, setup instructions, architecture documentation, troubleshooting guidance, and other project documentation.

> All contributions are equally valuable to the project and community. 🥰

## Submitting a bug-related issue or feature request

At any moment, feel free to open an issue, including relevant error logs, screenshots, Python version, dependency versions, or other useful information when it is related to a bug.

Please check the existing issues before creating a new one. This helps avoid duplicate reports and makes it easier to track existing problems.

### Did you find a bug?

**DataAgent** becomes more reliable through community feedback, issue reporting, and meaningful contributions.

Before reporting an issue, please make sure the bug has not already been reported under the repository's **Issues** section.

When submitting a bug report, please include the following information:

* Your **operating system** and version.
* Steps to reproduce the issue.
* A short description of the expected behavior and what actually happened.
* Relevant error messages or application logs.
* Python version and relevant dependency versions.
* Google Cloud configuration details when relevant.
* Screenshots or screen recordings, if applicable.
* Any other information that may help reproduce or understand the issue.

Please **do not include API keys, passwords, authentication tokens, service-account credentials, access tokens, or other sensitive information** in an issue.

### Do you want a new feature?

If there is a new feature you'd like to see in **DataAgent**, please open an issue and describe:

1. **Motivation**  
   Explain the problem, limitation, or use case that the feature would address.

2. **Feature Description**  
   Describe the proposed feature and how you would expect it to work.

3. **Agent Behavior**  
   Explain how the feature should influence the agent's reasoning, data analysis, tool usage, or responses.

4. **Data Analysis**  
   Describe how the feature would interact with BigQuery data, schemas, SQL queries, or analytical workflows.

5. **Implementation Details**  
   If you have an implementation idea, architecture suggestion, or code example, feel free to include it.

6. **Additional References**  
   If the feature is inspired by an external project, article, design, or technical reference, please include the relevant link.

A clear and well-written feature request makes it much easier to evaluate and discuss the proposal.

## Do you want to improve BigQuery or MCP integration?

BigQuery and the BigQuery MCP Server are important parts of **DataAgent**.

You can contribute by:

* Improving BigQuery schema exploration.
* Improving table and column discovery.
* Improving SQL generation.
* Improving SQL validation and query accuracy.
* Improving MCP tool selection and usage.
* Improving analytical reasoning over BigQuery data.
* Improving query filtering, aggregation, and dimension analysis.
* Improving error handling for BigQuery or MCP operations.
* Improving the agent's ability to work with available datasets.

When modifying the data-analysis workflow, ensure that the agent verifies the available schema and data rather than making unsupported assumptions.

## Do you want to improve AI agent behavior?

Contributions that improve the DataAgent's behavior are especially welcome.

Examples include:

* Improving agent instructions.
* Improving analytical reasoning.
* Improving schema investigation.
* Improving SQL generation.
* Improving query planning.
* Improving MCP tool usage.
* Reducing unsupported assumptions about data.
* Improving response accuracy and clarity.
* Improving error handling.
* Improving the agent's ability to explain analytical results.
* Adding additional safety or validation constraints.

Changes to agent behavior should be tested against representative analytical questions to ensure that the agent continues to inspect and verify available data before generating conclusions.

## Do you want to add documentation?

We're always looking for improvements that make **DataAgent** clearer and easier to understand.

You can contribute by:

* Fixing typos or grammatical errors.
* Improving setup instructions.
* Adding missing documentation.
* Improving Google Cloud configuration instructions.
* Improving local development instructions.
* Improving Cloud Run deployment documentation.
* Documenting the agent architecture.
* Documenting BigQuery MCP integration.
* Adding examples.
* Improving troubleshooting documentation.
* Documenting agent behavior and available tools.

Documentation contributions are highly appreciated, especially when they make it easier for new contributors to understand and run the project.

## Fixing outstanding issues

If you notice an existing issue and have a fix in mind, feel free to **[start contributing](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)** and open a Pull Request.

### Making code changes

<details>

1. **Fork the Repository**

   Go to the **DataAgent** repository on GitHub and click the **Fork** button.

2. **Clone your forked repository**

   ```bash
   git clone https://github.com/<username>/DataAgent.git
   ```

   Navigate into the project directory:

   ```bash
   cd DataAgent
   ```

3. **Create a New Branch**
   
   ```bash
   git checkout -b feature/your-feature-name
   ```

4. **Set Up the Python Environment**

   Make sure Python is installed and create a virtual environment:

   ```bash
   python -m venv .venv
   ```

   Activate the virtual environment.

   **Windows PowerShell:**
    
   ```bash
   .\.venv\Scripts\Activate.ps1
   ```
  
   **macOS / Linux:**
  
   ```bash
   source .venv/bin/activate
   ```

5. **Install Dependencies**

   Navigate to the application directory:

   ```bash
   source .venv/bin/activate
   ```

   Install the required Python packages:

   ```bash
   pip install -r requirements.txt
   ```

6. **Configure Google Cloud**

   DataAgent uses Google Cloud services for Gemini, BigQuery, MCP, and Cloud Run.

   Configure your Google Cloud project and required services according to the project's README and deployment instructions.

   Required configuration may include:
   - Google Cloud project
   - Cloud Run region
   - Gemini in Google Cloud
   - BigQuery
   - Required Google Cloud APIs
  
   > Never commit API keys, service-account credentials, access tokens, or other secrets to the repository.

7. **Configure Environment Variables**

    Configure the required Google Cloud environment variables before running the agent.

    Typical configuration includes:

    ```bash
    export GOOGLE_CLOUD_PROJECT="YOUR_PROJECT_ID"
    export GOOGLE_CLOUD_REGION="YOUR_REGION"
    export GOOGLE_GENAI_USE_ENTERPRISE="True"
    export GOOGLE_CLOUD_LOCATION="global"
    ```

    > Do not commit `.env` files, credentials, or other files containing sensitive information.
   
8. **Run the Agent Locally**

    From the project directory, use the ADK CLI to start the local development interface:

    ```bash
    From the project directory, use the ADK CLI to start the local development interface:
    ```

    Open the local ADK Web interface at:

    ```bash
    http://localhost:8080/
    ```

9. **Make Your Changes**

    - Develop the feature or fix.
    - Follow the existing project structure and coding conventions.
    - Keep changes focused and maintainable.
    - Avoid unnecessary changes to unrelated files.
    - Test your changes locally before submitting a Pull Request.

10. **Test AI and Data Analysis Behavior**

     If your changes affect the agent or BigQuery/MCP workflow, test representative scenarios such as:

     - Asking what data is available.
     - Asking about available tables and fields.
     - Questions requiring schema investigation.
     - Questions requiring SQL generation.
     - Questions requiring filtering or aggregation.
     - Questions requiring multiple MCP tool calls.
     - Analytical questions about the Citi Bike dataset.
     - Requests that require the agent to verify assumptions against the available data.

     Verify that the agent:

     - Investigates the available data before making assumptions.
     - Uses the appropriate BigQuery MCP tools.
     - Generates valid SQL.
     - Uses read-only data access appropriately.
     - Provides clear and relevant analytical responses.

11. **Commit Your Changes**

     ```bash
     git add .
     ```

     ```bash
     git commit -m "Add feature/bugfix description"
     ```

12. **Push to Your Fork**

     ```bash
     git push origin feature/your-feature-name
     ```

13. **Create a Pull Request**

     Go to the original **DataAgent** repository and open a **New Pull Request**

     In your Pull Request description:
     - Explain what you changed.
     - Explain why the change was needed.
     - Mention any relevant issue.
     - Describe changes to agent behavior.
     - Describe changes to BigQuery or MCP integration.
     - Mention any testing performed.
     - Include screenshots or logs when appropriate.

14. **Address Feedback**

     If maintainers leave comments or request changes, address the feedback and push the required updates to your branch.

</details>

## Contribution Guidelines

  To keep the project maintainable and welcoming:
  - Keep Pull Requests focused on a single feature, fix, or improvement whenever possible.
  - Avoid unnecessary changes to unrelated files.
  - Follow the existing coding style and project structure.
  - Test changes before submitting a Pull Request.
  - Test AI agent behavior when modifying agent instructions or logic.
  - Test BigQuery and MCP behavior when modifying data-access functionality.
  - Do not commit secrets, API keys, credentials, access tokens, .env files, or service-account files.
  - Do not make unsupported assumptions about the underlying data.
  - Keep SQL queries accurate, readable, and appropriately scoped.
  - Use read-only data access when working with the agent's analytical workflow.
  - Provide clear commit messages and Pull Request descriptions.
  - Include relevant screenshots, logs, or test results when appropriate.
  - Be respectful and constructive when reviewing or discussing contributions.

## I want to become a maintainer of the project. How do I get there?

  **DataAgent** is an AI-powered data analysis agent that uses Google Agent Development Kit (ADK), Gemini, BigQuery, and the BigQuery MCP Server to reason over structured data.

Contributors interested in improving AI agent behavior, BigQuery analysis, MCP integration, SQL generation, Google ADK integration, Gemini integration, Cloud Run deployment, performance, testing, security, or documentation are always welcome.

We are happy to welcome motivated contributors who want to take a deeper role in the project and help **DataAgent** evolve into a reliable and useful AI data-analysis application.

If you are interested in contributing at a deeper level, consistently submitting meaningful improvements, reviewing Pull Requests, improving documentation, or helping maintain the project, feel free to get involved and collaborate with the community.

Thank you for contributing to **DataAgent**! 📊🤖
  
