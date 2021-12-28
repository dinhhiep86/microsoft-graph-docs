---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := msgraphsdk.NewContactFolder()
parentFolderId := "AQMkADIxYjJiYgEzLTFmNjYALTRjYTMtODA1NC0wZDkxZGNmOTcxNTQALgAAA8RJzXYaLKZPlmn0ge0edZkBADa3qi2IMXRNg6RwQSHe_F8AAAIBDgAAAA=="
requestBody.SetParentFolderId(&parentFolderId)
displayName := "Important contacts"
requestBody.SetDisplayName(&displayName)
options := &msgraphsdk.ContactFoldersRequestBuilderPostOptions{
	Body: requestBody,
}
result, err := graphClient.Me().ContactFolders().Post(options)


```