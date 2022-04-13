### Publish Docker Image to GitHub Container Registry


##### In here, the following workflow can use to publish the docker image to GitHub Container Registry (GCR) using GitHub Action. This GitHub action will be triggered every time a new Git tag is pushed to the GitHub repository.


#### Create Environment Variables

1.Create <a href="https://docs.github.com/en/packages/guides/enabling-improved-container-support">GitHub Personal Access Token</a> in your <a href="https://github.com/settings/tokens">profile developer settings</a> page. Select following scopes:<br><br>

<li>repo</li>
<li>read:packages</li>
<li>write:packages</li><br>

2.Go to your GitHub repositorie's <a href="https://github.com/{your_username}/{your_repository_name}/settings/secrets/actions">Settings => Secrets => Actins</a> and create New Repsitory Secret. Name it <b>GHCR_PAT</b> and set the value to your created <b>YOUR ACCESS TOKEN</b>.

#### Publish new Docker Image with version number

As usual, stage your changes and then commit them. Then, run the folowing commands:

```
git tag <your_tag> 
```

Then run the following command to push changes to GitHub repository:

```
git push origin <tag_name>
```

The following workflow is designed to be triggered when a new Git tag is pushed project repository. Using the workflow, you can perform pushes to the repository (git push) without triggering this workflow. For example, when updating the project’s README file, you can run the following command:

```
git push <branch_name>
```



