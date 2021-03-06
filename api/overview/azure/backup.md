---
title: Azure Backup libraries for .NET
description: Reference for Azure Backup libraries for .NET
keywords: Azure, .NET, SDK, API, Backup
author: camsoper
ms.author: casoper
manager: douge
ms.date: 07/24/2017
ms.topic: reference
ms.prod: azure
ms.technology: azure
ms.devlang: dotnet
ms.service: multiple
---

# Azure Backup libraries for .NET

## Overview

Azure Backup is the cloud service you can use to back up, protect, and restore your data.

Learn more about Azure Backup by reading [What is Azure Backup?](/azure/backup/backup-introduction-to-azure-backup).

## Management library

Use the backup management library to manage backups and set up Recovery Services vaults.

Install the [NuGet package](https://www.nuget.org/packages/Microsoft.Azure.Management.RecoveryServices.Backup) directly from the Visual Studio [Package Manager console][PackageManager] or with the [.NET Core CLI][DotNetCLI].

#### Visual Studio Package Manager

```powershell
Install-Package Microsoft.Azure.Management.RecoveryServices.Backup
```

```bash
dotnet add package Microsoft.Azure.Management.RecoveryServices.Backup
```

The following code example uses the management library to trigger a backup.

```csharp
RecoveryServicesBackupManagementClient client = new RecoveryServicesBackupManagementClient(credentials);
TriggerBackupRequest triggerBackupRequest = new TriggerBackupRequest();
BaseRecoveryServicesJobResponse resp =
    await client.Backups.TriggerBackupAsync(resourceGroupName, resourceName, null,
        fabricName, containerName, protectedItemName, triggerBackupRequest);
```

> [!div class="nextstepaction"]
> [Explore the management APIs](/dotnet/api/overview/azure/backup/management)

[PackageManager]: https://docs.microsoft.com/nuget/tools/package-manager-console
[DotNetCLI]: https://docs.microsoft.com/dotnet/core/tools/dotnet-add-package
