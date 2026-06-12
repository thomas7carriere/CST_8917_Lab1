# CST_8917_Lab1

## Setup Instructions:

1. Install the required software: Python 3.12, Azure Functions Core Tools, and the Azure Functions VS Code extension.
2. Create a new python based Function project in a new folder (`func init --python`).
3. Replace the generated `local.settings.json` with

```{
  "IsEncrypted": false,
  "Values": {
    "FUNCTIONS_WORKER_RUNTIME": "python",
    "AzureWebJobsStorage": "UseDevelopmentStorage=true",
    "COSMOS_ENDPOINT": "<your-cosmos-db-endpoint>",
    "COSMOS_KEY": "<your-cosmos-db-primary-key>",
    "COSMOS_DATABASE": "LabDB",
    "COSMOS_CONTAINER": "AnalysisResults"
  }
}
```
Replace the values for the cosmos configuration with your own.

4. Replace the generated `function_app.py` and `requirements.txt` with the versions in this repository.
5. Start Azurite with the command Pallette using `Azurite: Start`
6. Start the function app with the CLI with `func start`
7. Endpoints can then be tested:

```
curl "http://localhost:7071/api/TextAnalyzer?text=test message1"
curl "http://localhost:7071/api/TextAnalyzer?text=test message2"
curl "http://localhost:7071/api/GetAnalysisHistory?limit=1"

```
