# demo-pyapp-repo
Demo Python Flask app configured for Azure DevOps CI/CD.

## Files
- `app.py` - Simple Flask app.
- `requirements.txt` - Python dependencies.
- `azure-pipelines.yml` - Azure Pipelines YAML (CI + CD to Azure App Service).

## Quickstart (Local)
1. Create a virtualenv: `python -m venv .venv && source .venv/bin/activate`
2. Install deps: `pip install -r requirements.txt`
3. Run: `python app.py`
4. Visit http://localhost:8080/

## Deploy with Azure DevOps
1. Create an Azure DevOps project and repo, then push this repository to it.
2. Create a Service Connection (Project settings → Service connections → Azure Resource Manager).
   - Name it `AzureConnection` or update the YAML with your service connection name.
3. Create an Azure App Service (Linux) and note the app name.
4. Update `azure-pipelines.yml` replacing `your-app-service-name` with your App Service name.
5. Create a Pipeline in Azure DevOps using existing YAML in the repo.
6. Push to `main` branch to trigger the pipeline.

## Notes
- The pipeline archives the repo and deploys the ZIP to App Service.
- For production, add tests and secure secrets via variable groups or Azure Key Vault.
