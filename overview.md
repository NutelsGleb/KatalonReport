# Azure Devops Katalon HTML Report

## About

This Azure DevOps extension provides task for Publishing Katalon HTML Reports into built into Azure Storage.

It base on Maciej Maciejewski Postman Report extension (https://marketplace.visualstudio.com/items?itemName=MaciejMaciejewski.postman-report&ssr=false#overview)

Reports can be viewed as a tab in Build and Release result page. Each Tab contains embeded reports as well as direct download links.

## Configuration

In order to use this extension first add `Upload Katalon HTML Report` task to your pipeline. In your Katalon execution task add `htmlextra` reporter that will generate `HTML` reports.

This tasks takes two parameters - required `cwd` which is path to the location whereKatalon HTML reports are stored and also optional `tabName` which is the name of the tab displayed within Azure DevOps report.

```YAML
steps:
- task: UploadKatalonHtmlReport@1
  displayName: 'Upload Katalon Html Report'
  inputs:
    cwd: '$(System.DefaultWorkingDirectory)'
    tabName: 'Katalon Test'
```
