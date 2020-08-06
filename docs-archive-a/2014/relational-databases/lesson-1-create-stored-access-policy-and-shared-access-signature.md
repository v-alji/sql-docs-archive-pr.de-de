---
title: 'Lektion 2: Erstellen einer Richtlinie für einen Container und Generieren eines Shared Access Signature (SAS)-Schlüssels | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 41674d9d-8132-4bff-be4d-85a861419f3d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab209f08d53b25a4791ef675e6fb6b78cab115f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723849"
---
# <a name="lesson-2-create-a-policy-on-container-and-generate-a-shared-access-signature-sas-key"></a><span data-ttu-id="35c4c-103">Lektion 2:</span><span class="sxs-lookup"><span data-stu-id="35c4c-103">Lesson 2.</span></span> <span data-ttu-id="35c4c-104">Erstellen einer Richtlinie für einen Container und Generieren eines Shared Access Signature (SAS)-Schlüssels</span><span class="sxs-lookup"><span data-stu-id="35c4c-104">Create a policy on container and generate a Shared Access Signature (SAS) key</span></span>
  <span data-ttu-id="35c4c-105">In dieser Lektion erfahren Sie, wie Sie eine Richtlinie für den BLOB-Container erstellen und auch einen SAS-Schlüssel generieren.</span><span class="sxs-lookup"><span data-stu-id="35c4c-105">In this lesson, you will learn how to create a policy on the Blob container and also generate a SAS key.</span></span>  
  
 <span data-ttu-id="35c4c-106">Eine gespeicherte Zugriffsrichtlinie stellt eine zusätzliche Steuerungsebene für Shared Access Signatures auf Serverseite bereit.</span><span class="sxs-lookup"><span data-stu-id="35c4c-106">A stored access policy provides an additional level of control over shared access signatures on the server side.</span></span> <span data-ttu-id="35c4c-107">Eine Shared Access Signature ist ein URI, der eingeschränkte Zugriffsrechte für Container, BLOBs, Warteschlangen und Tabellen gewährt.</span><span class="sxs-lookup"><span data-stu-id="35c4c-107">A shared access signature is a URI that grants restricted access rights to containers, blobs, queues, and tables.</span></span> <span data-ttu-id="35c4c-108">Wenn Sie diese neue Erweiterung verwenden, müssen Sie eine Richtlinie für einen Container mit Lese-, Schreib- und Auflistungsrechten erstellen.</span><span class="sxs-lookup"><span data-stu-id="35c4c-108">When using this new enhancement, you need to create a policy on a container with read, write, and list rights.</span></span>  
  
 <span data-ttu-id="35c4c-109">Sie können eine Richtlinie und eine Shared Access Signature erstellen, indem Sie eine der folgenden Methoden verwenden:</span><span class="sxs-lookup"><span data-stu-id="35c4c-109">You can create a policy and a shared access signature by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="35c4c-110">Azure-Rest-API-Vorgänge: [Container erstellen](https://msdn.microsoft.com/library/azure/dd179468.aspx), [Container-ACL festlegen](https://msdn.microsoft.com/library/azure/dd179391.aspx)und [Container-ACL erhalten](https://msdn.microsoft.com/library/azure/dd179469.aspx).</span><span class="sxs-lookup"><span data-stu-id="35c4c-110">Azure REST API operations: [Create Container](https://msdn.microsoft.com/library/azure/dd179468.aspx), [Set Container ACL](https://msdn.microsoft.com/library/azure/dd179391.aspx), and [Get Container ACL](https://msdn.microsoft.com/library/azure/dd179469.aspx).</span></span>  
  
-   <span data-ttu-id="35c4c-111">[Cloudblobcontainer. getsharedaccesssignature-Methode](https://docs.microsoft.com/dotnet/api/microsoft.azure.storage.blob.cloudblobcontainer.getsharedaccesssignature) im Azure-SDK.</span><span class="sxs-lookup"><span data-stu-id="35c4c-111">[CloudBlobContainer.GetSharedAccessSignature Method](https://docs.microsoft.com/dotnet/api/microsoft.azure.storage.blob.cloudblobcontainer.getsharedaccesssignature) in the Azure SDK.</span></span>  
  
    ```  
  
       string signature = blob.GetSharedAccessSignature(new SharedAccessPolicy()   
        {   
            // Specify the expiration time for the signature.   
            SharedAccessExpiryTime = DateTime.Now.Years(1),   
            // Specify the permissions granted by the signature.    
            Permissions = SharedAccessPermissions.Write | SharedAccessPermissions.Read   
        });  
  
    ```  
  
-   <span data-ttu-id="35c4c-112">Ein Azure-Explorer-Tool von Drittanbietern, z. b. [Azure Storage-Explorer](https://azurestorageexplorer.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="35c4c-112">A third-party Azure explorer tool, such as [Azure Storage Explorer](https://azurestorageexplorer.codeplex.com/).</span></span>  
  
 <span data-ttu-id="35c4c-113">**Nächste Lektion:**</span><span class="sxs-lookup"><span data-stu-id="35c4c-113">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="35c4c-114">Lektion 3: Erstellen von SQL Server-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="35c4c-114">Lesson 3: Create a SQL Server Credential</span></span>](../relational-databases/lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)  
  
