# download-artifact

The "Download artifact" GitHub Action is a wrapper around the official download-artifact action provided by GitHub. It includes additional functionality for extracting the artifact after download.

# Inputs

| Input    | Description                        | Required | Default |
|----------|------------------------------------|----------|---------|
| `name`   | The name of the artifact to download. | Yes      | -       |
| `path`   | The destination path for the downloaded artifact. | No       | `.`     |

# Action Workflow

The action consists of the following steps:

**Download Artifacts:**

- This step uses the actions/download-artifact@v3 action to download the specified artifact to the provided path.

**Extract Artifacts:**

- After downloading, this step extracts the contents of the .tar archive.

**Remove Archive:**

- Once extraction is complete, this step removes the .tar file to clean up the workspace.

# Usage

To use this action in your workflow, include it as a step in your **.yml** workflow file, providing the necessary inputs. The **name** input is required, while **path** is optional.

# Example

```yaml
steps:
- uses: echapmanFromBunnings/download-artifact@main
  with:
    name: 'artifact-name'
    path: './path/to/destination' # Optional
```
