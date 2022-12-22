# Azure Devops Postman HTML Report

## About

This Azure DevOps extension provides task for Publishing Katalon HTML Reports into built into Azure Storage.

Reports can be viewed as a tab in Build and Release result pages.
Tab contains embeded reports as well as direct download links.

## Configuration

In order to use this extension first add `Upload Katalon HTML Report` task to your pipeline. In your Katalon execution task add `htmlextra` reporter that will generate `HTML` reports.

This tasks takes two parameters - required `cwd` which is path to the location where Katalon HTML reports are stored and also optional `tabName` which is the name of the tab displayed within Azure DevOps report.

```YAML
steps:
- task: UploadPostmanHtmlReport@1
  displayName: 'Upload Postman Html Report'
  inputs:
    cwd: '$(System.DefaultWorkingDirectory)'
    tabName: 'Katalon Test'
```

