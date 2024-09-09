# Airlines Data Incremental Processing with CI/CD

## Project Overview
This project showcases an end-to-end **incremental data processing** solution for airlines data using **Azure Data Factory** (ADF), **Azure Synapse**, and **Azure DevOps** for continuous integration and deployment (CI/CD). The project processes data from **Azure Data Lake Storage (ADLS)**, utilizes **Azure Synapse** as the destination, and is fully automated with a release pipeline in **Azure DevOps**.

## Key Features
- **Data Processing Pipeline**: Setup a data pipeline in **Azure Data Factory (ADF)** that pulls data from ADLS containers and processes it using a defined data flow.
- **CI/CD Integration**: The entire deployment process is automated using **Azure DevOps**, with changes tracked in **Azure Repos** and deployed using **ARM templates**.
- **Automated Releases**: Created an automated release pipeline in **Azure DevOps** that deploys updated ARM templates to the production environment based on changes pushed to the **adf_publish** branch.
- **Parameterized ARM Templates**: The pipeline deployment is configured using parameterized ARM templates, allowing for flexibility and reusability across environments.

## Architecture
1. **Azure Data Lake Storage (ADLS)**: The source data is stored in ADLS containers.
2. **Azure Data Factory (ADF)**: ADF is used for ingesting and transforming the data.
3. **Azure Synapse Analytics**: The processed data is stored in Synapse.
4. **Azure DevOps Pipelines**: Automated deployment and CI/CD integration using DevOps.
### ADF DataFlow
![image](https://github.com/user-attachments/assets/84500df6-3827-4957-8f2f-c3a648ee22e4)
### ADF Pipeline
![image](https://github.com/user-attachments/assets/a9b2a639-971c-479a-9b1f-82ad26baad5c)
### Azure Devops Repo
<img width="944" alt="image" src="https://github.com/user-attachments/assets/86df7ee2-f5cc-4c15-a62c-64cbd09dd4c1">

### CI-CD Release Pipeline

### Steps Involved
1. **Azure DevOps Setup**:
   - Created an organization and project in **Azure DevOps**.
   - Setup **Repository**, **Agent Pool**, and branching strategy.
2. **ADF and Synapse Integration**:
   - Developed a data ingestion pipeline in ADF that pulls from ADLS and processes the data in Synapse.
   - Used data flows for transformation and data joining.
3. **CI/CD Pipeline Setup**:
   - Integrated **Azure Repos** for version control.
   - Pushed changes to the collaboration branch and parameterized ARM templates to the **adf_publish** branch.
   - Created a release pipeline in Azure DevOps that triggers deployments automatically when new changes are pushed.
4. **Automated Deployment**:
   - Configured the release pipeline to deploy updated ARM templates to ADF production environment.
   - Parameterized ARM templates for flexibility.

## Technologies Used
- **Azure Data Factory (ADF)**
- **Azure Synapse Analytics**
- **Azure Data Lake Storage (ADLS)**
- **Azure DevOps** (Pipelines, Repos, Agent Pools)
- **GitHub**
- **ARM Templates**

## Repository Structure
- `/dataflow/`: Contains the data flow configurations.
- `/dataset/`: Stores dataset configurations.
- `/factory/`: ADF factory configurations.
- `/linkedService/`: Definitions for linked services used in ADF.
- `/pipeline/`: ADF pipelines for data ingestion and processing.
- `/adf_publish/`: Parameterized ARM templates for deploying to production.
