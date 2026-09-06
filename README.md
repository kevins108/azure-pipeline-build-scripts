# Azure Pipeline Build Scripts

Sample Azure DevOps YAML pipeline templates for building .NET applications and deploying an Azure Functions app.

## Files

- `function-app-build-pipeline.yml` builds a .NET Function App, archives the published output, publishes it as a pipeline artifact, and deploys it to an Azure Function App.
- `net-core-build-pipeline.yml` restores, builds, publishes, and publishes build artifacts for an ASP.NET Core project targeting the full .NET Framework.

## Usage

1. Copy the pipeline template into the repository that contains the application source code.
2. Replace the sample values and project paths in the YAML file:
	- `FUNCTION_APP_NAME` and the Azure subscription/service connection in the Function App pipeline.
	- `PROJECT_NAME.csproj` in the .NET pipeline.
	- The sample Azure Artifacts feed identifier (`xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`) where applicable.
3. Review the agent image, SDK version, build configuration, artifact paths, and deployment environment.
4. In Azure DevOps, create a pipeline from the existing YAML file and authorize the referenced service connection and feed.

Both files use the `.yml` extension, which is supported for Azure DevOps YAML pipelines. They trigger on pushes to the `main` branch unless the `trigger` section is changed.

These are starting templates rather than drop-in pipelines. Validate project paths, service connections, permissions, framework versions, and task arguments for the target application before using them. In particular, review the sample `Relase` build argument and the empty `configuration` input in the .NET pipeline.
