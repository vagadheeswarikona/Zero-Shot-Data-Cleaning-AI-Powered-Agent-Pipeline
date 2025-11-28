# Zero-Shot-Data-Cleaning-AI-Powered-Agent-Pipeline
Autonomous multi-agent AI pipeline for zero-shot data cleaning. Leverages LLMs &amp; Pydantic to intelligently profile, plan, execute, and verify cleaning operations with minimal human input. Transforms messy data into ML-ready datasets, accelerating insights &amp; boosting AI/ML reliability. A resilient, adaptive solution for the 'dirty data' bottleneck.

# 🚀 Project Overview
  In the age of big data, pervasive "dirty" data—marked by missing values, inconsistencies, and redundancies—cripples analytical efforts, consuming up to 80% of data scientists' time, delaying insights, degrading model performance, and posing insurmountable scalability challenges.
  The Zero-Shot Data Cleaning Pipeline is an innovative, autonomous multi-agent AI system designed to fundamentally transform this bottleneck. It intelligently profiles, plans, executes, and verifies data cleaning operations with minimal human input, leveraging Large Language Models (LLMs) to dynamically generate tailored cleaning plans for novel datasets in a "zero-shot" manner. This ensures ML-ready data, accelerates insights, and significantly enhances AI/ML model reliability, delivering a resilient, adaptive, and trustworthy automated process.

# ✨ Solution Highlights
1. **Autonomous & Zero-Shot:** Automatically generates cleaning plans for new datasets without prior examples or extensive configuration.
2. **Multi-Agent Architecture:** A modular system with specialized agents handling distinct stages of data preparation.
3. **LLM-Powered Intelligence:** Utilizes LLMs for dynamic, context-aware plan generation.
4. **Robust & Transparent:** Features a static fallback plan for operational resilience and provides detailed verification reports with confidence scores.

# 🏛️ Architecture: Multi-Agent System Design
The pipeline functions as a sophisticated Multi-Agent System, featuring distinct, specialized agents that ensure modularity, scalability, and robust error handling throughout the data cleaning lifecycle.
1. **Loader Agent (Ingester):** Handles raw data ingestion from sources like Kaggle, performing initial sanitization (e.g., converting diverse missing value strings to $np.nan$).
2. **Profiler Agent (Observer):** Analyzes data to identify quality issues, generating a comprehensive statistical summary that forms the "context compaction."
3. **Planner Agent (LLM-Powered / Decision Maker):** The core "brain." Dynamically reasons using an LLM to formulate executable CleaningAction objects (zero-shot planning). Includes a robust fallback to a pre-defined static plan if the LLM is unavailable or its output invalid.
4. **Executor Agent(Doer):** Executes cleaning actions from the CleaningPlan against the DataFrame using a library of atomic cleaning tools (e.g., deduplicate, impute).
5. **Verifier Agent (Quality Assurance):** Assesses cleaning effectiveness, comparing raw and cleaned data, calculating a confidence score based on key metrics (e.g., nulls reduced, rows dropped), and generating a VerificationReport with actionable flags and a recommendation for data usage.
*Inter-Agent Communication:* Governed by a strict A2A (Agent-to-Agent) Protocol, implemented using Pydantic data models to guarantee unambiguous, machine-readable instructions and reports between all agents.

# 💰 Value Proposition
1. **Maximize Strategic Productivity:** Frees highly skilled data scientists from up to 80% of mundane cleaning tasks, allowing them to focus on complex modeling, advanced analytics, and high-value strategic insights.
2. **Accelerate Business Outcomes:** Dramatically reduces the time from raw data ingestion to actionable insights, driving significantly faster decision-making and enabling agile responses to market opportunities.
3. **Enhance AI/ML Model Reliability:** Ensures a consistent supply of clean, high-quality, and validated data, leading to the development of more accurate, robust, and trustworthy AI/ML models.
4. **Future-Proof Data Operations:** Provides a scalable and adaptable multi-agent framework that seamlessly handles diverse and evolving datasets, minimizing the need for constant manual re-engineering and reducing technical debt.

# 🛠️ Essential Tools and Utilities
The pipeline leverages a curated set of robust Python libraries, each playing a critical role in the multi-agent system's functionality:
1. **Pandas:** The core library for all DataFrame manipulation, data processing, and analytical operations performed by the Executor Agent and during profiling.
2. **NumPy:** Essential for efficient numerical operations and the consistent handling of $np.nan$ values for missing data across the system.
3. **Pydantic:** Crucial for defining and enforcing the strict JSON schema of the A2A communication protocol. This schema is what guides the LLM's plan generation and ensures reliable parsing and validation of all cleaning plans and reports.
4. **kagglehub:** Specifically utilized by the Loader Agent for programmatically downloading datasets directly from Kaggle, enabling dynamic data ingestion.
5. **glob & os:** Standard Python modules that provide robust file system interaction, used for locating, managing, and resolving data file paths within the system.
6. **json:** Employed for serializing and deserializing structured data—from the Profiler's summaries to the Planner's cleaning plans—facilitating inter-agent communication.

# 🚀 Getting Started
This project is best experienced directly on Kaggle, where all dependencies are pre-configured and the environment is ready to run.
Open the Kaggle Notebook: 
1. Click here to access and run the notebook directly on Kaggle
2. Run on Kaggle: Once on the Kaggle page, click "Copy & Edit" to create your own editable version. Then, simply run all cells (or "Run All" / "Commit") to execute the pipeline.
3. Configure Dataset (Optional): Within the notebook, locate the "Global Constants & Setup" section. You can easily adjust KAGGLE_DATASET_ID and CSV_FILE_NAME if you wish to apply the pipeline to a different Kaggle dataset.

# ✅ Conclusion
The Zero-Shot Data Transformation Pipeline represents a significant leap towards truly autonomous data preparation. By intelligently combining specialized AI agents with a powerful LLM and a robust static fallback, it offers an adaptive, efficient, and reliable solution for transforming raw, messy data into high-quality, ML-ready datasets. This system fundamentally minimizes manual data wrangling, accelerates the data-to-insight cycle, and significantly enhances the trustworthiness of all downstream analytical and machine learning applications, thus directly overcoming the pervasive 'dirty data' bottleneck that cripples modern analytics.
