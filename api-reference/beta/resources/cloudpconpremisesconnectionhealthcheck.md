---
title: "cloudPcOnPremisesConnectionHealthCheck resource type"
description: "The result of a cloud PC on-premises connection health check."
author: "AshleyYangSZ"
ms.localizationpriority: medium
ms.prod: "cloud-pc"
doc_type: resourcePageType
---

# cloudPcOnPremisesConnectionHealthCheck resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

The result of a cloud PC on-premises connection health check.

## Methods

|Method|Return type|Description|
|:---|:---|:---|
|[RunHealthChecks of cloudPcOnPremisesConnection](../api/cloudpconpremisesconnection-runhealthcheck.md)|None|Run the health checks of a [cloudPcOnPremisesConnection](../resources/cloudpconpremisesconnection.md).|

## Properties

|Property|Type|Description|
|:---|:---|:---|
|displayName|String|The display name for this health check item.|
|status|[cloudPcOnPremisesConnectionStatus](../resources/cloudpconpremisesconnection.md#cloudpconpremisesconnectionstatus-values)|The status of the health check item. Possible values are: `pending`, `running`, `passed`, `failed`, `unknownFutureValue`. Read-only.|
|startDateTime|DateTimeOffset|The start time of the health check item. Read-only.|
|endDateTime|DateTimeOffset|The end time of the health check item. Read-only.|
|errorType|[cloudPcOnPremisesConnectionHealthCheckErrorType](#cloudpconpremisesconnectionhealthcheckerrortype-values)|The type of error that occurred during this health check.|
|recommendedAction|String|The recommended action to fix the corresponding error.|
|additionalDetails|String|Additional details about the health check or the recommended action.|

### cloudPcOnPremisesConnectionHealthCheckErrorType values

|Member|Description|
|:---|:---|
|dnsCheckFqdnNotFound|The DNS resolution failed for the domain name. Possible error causes: 1. The specified Azure vNet's DNS server can't resolve the domain name. Please update the vNet with an appropriate DNS server; 2. The domain name provided doesn't exist or isn't correct. Please update the on-premises network connection with the correct domain name. Please make sure that the vNet defined in the on-premises network connection can resolve the domain name.|
|dnsCheckUnknownError|The DNS resolution failed for the domain name. Possible error causes: 1. The specified Azure vNet's DNS server can't resolve the domain name. Please update the vNet with an appropriate DNS server; 2. The domain name provided doesn't exist or isn't correct. Please update the on-premises network connection with the correct domain name. Please make sure that the vNet defined in the on-premises network connection can resolve the domain name.|
|adJoinCheckFqdnNotFound|The domain join check failed because the domain name couldn't be found. Please make sure a domain controller for the domain name can be contacted by the vNet defined in the on-premises network connection.|
|adJoinCheckIncorrectCredentials|The domain join check failed because the credentials provided for the domain aren't correct. Please update the on-premises network connection with correct credentials.|
|adJoinCheckOrganizationalUnitNotFound|The domain join check failed because the organizational unit (OU) can't be found. Please provide an OU in the domain. The OU must be in distinguished name format. Example format: “OU=OU1,OU=OU2,OU=OU3,DC=DC1”.|
|adJoinCheckOrganizationalUnitIncorrectFormat|The domain join check failed because the organizational unit (OU) can't be found. Please provide an OU in the domain. The OU must be in distinguished name format. Example format: “OU=OU1,OU=OU2,OU=OU3,DC=DC1”.|
|adJoinCheckComputerObjectAlreadyExists|The computer account can't be found in the organizational unit (OU) provided in the on-premises network connection but the computer name already exists in the domain. This often occurs after the computer object was moved out of the OU configured in the on-premises network connection. Please move the computer object back to the target OU.|
|adJoinCheckAccessDenied|The domain join check failed because the user account provided doesn't have sufficient permissions to join the domain. Please make sure that the account provided has sufficient permissions or change the user account defined in the on-premises network connection properties. Permissions needed: *Create computer objects* and *Delete computer objects*.|
|adJoinCheckCredentialsExpired|The domain join check failed because the password of the domain join user has expired. Please, first update the password and then update the on-premises network connection with the new credentials.|
|adJoinCheckAccountLockedOrDisabled|The domain join check failed because the domain join user account is currently locked out or disabled. Please ensure the domain join user account is unlocked, active, and able to authenticate to the domain.|
|adJoinCheckAccountQuotaExceeded|The domain join check failed because the domain join user has exceeded maximum domain joins. Please make sure the domain join is allowed and the **ms-DS-MachineAccountQuota** Active Directory property allows sufficient domain joins.|
|adJoinCheckUnknownError|The domain join check failed due to an unknown error. Please make sure that the on-premises network connection can successfully join the domain using the details provided.|
|endpointConnectivityCheckCloudPcUrlNotAllowListed|During provisioning, one or more required URLs couldn't be contacted. Please make sure that all of the required URLs are allowed through the firewalls and proxies.|
|endpointConnectivityCheckWVDUrlNotAllowListed|During provisioning, one or more required WVD URLs couldn't be contacted. Please make sure that all of the required URLs are allowed through the firewalls and proxies.|
|endpointConnectivityCheckIntuneUrlNotAllowListed|During provisioning, one or more required Intune URLs couldn’t be contacted. Please make sure that all of the required URLs are allowed through the firewalls and proxies.|
|endpointConnectivityCheckUnknownError|During provisioning, one or more required URLs couldn't be contacted. Please make sure that all of the required URLs are allowed through the firewalls and proxies.|
|azureAdDeviceSyncCheckDeviceNotFound|The cloud PC computer object can't be found in Azure Active Directory (Azure AD). Please make sure that Azure AD connect works and syncs frequently so that the cloud PC computer objects are synced to Azure AD. Azure AD device sync must be enabled and synced within the last 60 minutes.|
|azureAdDeviceSyncCheckLongSyncCircle|The check whether the cloud PC computer object has been synced to Azure Active Directory (Azure AD) has timed out. Please make sure that Azure AD connect works and syncs frequently so that the cloud PC computer objects are synced to Azure AD. Azure AD device sync must be enabled and synced within the last 60 minutes.|
|azureAdDeviceSyncCheckConnectDisabled|The Azure Active Directory (Azure AD) device sync check failed because the Azure AD Connect is disabled. Please make sure the Azure AD Connect is enabled and it syncs frequently. If the Azure AD Connect doesn't sync the computer within 60 minutes, then the check will fail.|
|azureAdDeviceSyncCheckDurationExceeded|The Azure Active Directory (Azure AD) device sync check failed because the Azure AD Connect sync didn't sync within 60 minutes. Please make sure the Azure AD Connect is enabled and it syncs frequently. If the Azure AD Connect doesn't sync the computer within 60 minutes, then the check will fail.|
|azureAdDeviceSyncCheckTransientServiceError|The Azure Active Directory (Azure AD) device sync check failed due to a transient error. Please try it again. If the issue persists, please contact customer support.|
|azureAdDeviceSyncCheckUnknownError|Hybrid Azure Active Directory (Azure AD) connectivity check failed. Please make sure that Azure AD connect works and syncs frequently so that the cloud PC computer objects are synced to Azure AD. Azure AD device sync must be enabled and synced within the last 60 minutes.|
|resourceAvailabilityCheckNoSubnetIP|The subnet provided doesn't have IP addresses available. Please make sure that the subnet provided in the on-premises network connection has sufficient IP addresses available. Please expand the current selected subnet or select a different subnet to be used for provisioning.|
|resourceAvailabilityCheckSubscriptionDisabled|The Azure subscription provided is disabled. Please make sure that the Azure subscription is enabled and available for provisioning.|
|resourceAvailabilityCheckAzurePolicyViolation|The Azure subscription provided can't be found. Please ensure that the Azure subscription is available for provisioning.|
|resourceAvailabilityCheckSubscriptionNotFound|The Azure subscription provided can't be accessed. Please ensure that the Azure subscription is available for provisioning.|
|resourceAvailabilityCheckSubscriptionTransferred|The Azure subscription provided can't be accessed. Please ensure that the Azure subscription is available for provisioning.|
|resourceAvailabilityCheckGeneralSubscriptionError|An Azure policy is restricting the creation of resources. Please ensure that there is no Azure policy that restricts creating resources in the subscription and/or resource group.|
|resourceAvailabilityCheckUnsupportedVNetRegion|The selected vNet is located in an unsupported region. Please ensure that the selected vNet is located in a supported region.|
|resourceAvailabilityCheckResourceGroupInvalid|The selected Azure resource group is invalid or not found. Please make sure the selected Azure resource group is available to provision resources. Alternatively, update this on-premises network connection with another resource group.|
|resourceAvailabilityCheckVNetInvalid|The selected Azure virtual network is invalid. Please make sure the selected virtual network is available and healthy. Alternatively, update this on-premises network connection with another virtual network.|
|resourceAvailabilityCheckSubnetInvalid|The selected Azure subnet is invalid. Please make sure the selected subnet is available and healthy. Alternatively, update this on-premises network connection with another subnet.|
|resourceAvailabilityCheckResourceGroupBeingDeleted|The selected Azure resource group is being deleted. Please make sure the selected Azure resource group is available to provision resources. Alternatively, update this on-premises network connection with another resource group.|
|resourceAvailabilityCheckVNetBeingMoved|The selected Azure virtual network is being moved. Please ensure your virtual network isn't changing or being moved and try again. Alternatively, update this on-premises network connection with another vNet.|
|resourceAvailabilityCheckSubnetDelegationFailed|The selected Azure virtual network has subnet delegation which blocks the creation of a network interface (Nic). Please ask your Azure virtual network owner to modify their subnet delegation policy to allow provisioning to succeed.|
|resourceAvailabilityCheckSubnetWithExternalResources|The selected subnet can't be used because it contains external resources. Please remove any resources that could cause conflicts and try again. Alternatively, update this on-premises network connection with another subnet.|
|resourceAvailabilityCheckResourceGroupLockedForReadonly|The selected resource group is locked and can't be modified for provisioning. Please remove this lock to allow provisioning to succeed.|
|resourceAvailabilityCheckResourceGroupLockedForDelete|The selected resource group or its parent scope has been locked for delete actions. It may be because the IP addresses are used up. Please remove the lock and try again.|
|resourceAvailabilityCheckTransientServiceError|The resource availability check failed due to a transient error. Please try it again. If the issue persists, please contact customer support.|
|resourceAvailabilityCheckUnknownError|The resource availability check for Azure resources failed due to an unknown error. Please ensure that all Azure resources meet the prerequisites.|
|permissionCheckNoSubscriptionReaderRole|The cloud PC service principal doesn't have sufficient permissions on the Azure subscription. Please make sure that the cloud PC service principal has the *Reader* permissions on the subscription.|
|permissionCheckNoResourceGroupOwnerRole|The cloud PC service principal doesn't have sufficient permissions on the Azure resource group. Please make sure that the cloud PC service principal has the *Owner* permissions on the resource group. |
|permissionCheckNoVNetContributorRole|The cloud PC service principal doesn't have sufficient permissions on the Azure vNet. Please make sure that the cloud PC service has the *Network contributor* permissions on the vNet.|
|permissionCheckNoResourceGroupNetworkContributorRole|Cloud PC service principal doesn't have sufficient permissions on the Azure resource group. Please make sure that the  application has Network contributor permissions on the resource group.|
|permissionCheckTransientServiceError|The first-party app permission check failed due to a transient error. Please try it again. If the issue persists, please contact customer support.|
|permissionCheckUnknownError|The cloud PC service principal doesn't have sufficient permissions. Please make sure that the cloud PC service principal is granted sufficient Azure permissions.|
|internalServerErrorDeploymentCanceled|The deployment was canceled. Please try again later. If the problem persists, please contact support.|
|internalServerErrorAllocateResourceFailed|The allocation of resources failed. Please try again later. If the problem persists, please contact support.|
|internalServerErrorVMDeploymentTimeout|The virtual machine deployment timed out. Please try again later. If the problem persists, please contact support.|
|internalServerErrorUnableToRunDscScript|During provisioning, some PowerShell DSC scripts are executed on the cloud PC. Unable to either download these DSC scripts or execute them during the health check. Please ensure vNet has unrestricted access to the required endpoints, and PowerShell isn't blocked in the environment or Group Policy.|
|internalServerUnknownError|The provisioning has failed due to an internal error. Please contact customer support.|
|unknownFutureValue|Evolvable enumeration sentinel value. Do not use.|

## Relationships

None.

## JSON representation

The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.cloudPcOnPremisesConnectionHealthCheck"
}
-->

``` json
{
  "@odata.type": "#microsoft.graph.cloudPcOnPremisesConnectionHealthCheck",
  "displayName": "String",
  "status": "String",
  "startDateTime": "String (timestamp)",
  "endDateTime": "String (timestamp)",
  "errorType": "String",
  "recommendedAction": "String",
  "additionalDetails": "String"
}
```