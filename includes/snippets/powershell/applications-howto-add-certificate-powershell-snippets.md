---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Applications

$params = @{
	KeyCredentials = @(
		@{
			EndDateTime = [System.DateTime]::Parse("2024-01-11T15:31:26Z")
			StartDateTime = [System.DateTime]::Parse("2023-01-12T15:31:26Z")
			Type = "AsymmetricX509Cert"
			Usage = "Verify"
			Key = [System.Text.Encoding]::ASCII.GetBytes("base64MIIDADCCAeigAwIBAgIQP6HEGDdZ65xJTcK4dCBvZzANBgkqhkiG9w0BAQsFADATMREwDwYDVQQDDAgyMDIzMDExMjAeFw0yMzAxMTIwODExNTZaFw0yNDAxMTIwODMxNTZaMBMxETAPBgNVBAMMCDIwMjMwMTEyMIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAseKf1weEacJ67D6/...laxQPUbuIL+DaXVkKRm1V3GgIpKTBqMzTf4tCpy7rpUZbhcwAFw6h9A==")
			DisplayName = "CN=20230112"
		}
	)
}

Update-MgApplication -ApplicationId $applicationId -BodyParameter $params

```