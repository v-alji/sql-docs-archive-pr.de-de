---
title: 'Lektion 3: Schreiben einer vollständigen Datenbanksicherung in den Azure BLOB Storage-Dienst | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 454c8296-64e9-46ed-b141-5ebfbc8a4fe2
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 17e7e6b608d248a48cde52f1107bb910f06d64ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694881"
---
# <a name="lesson-3-write-a-full-database-backup-to-the-azure-blob-storage-service"></a><span data-ttu-id="4cffa-102">Lektion 3: Schreiben einer vollständigen Datenbanksicherung in den Azure Blob Storage-Dienst</span><span class="sxs-lookup"><span data-stu-id="4cffa-102">Lesson 3: Write a Full Database Backup to the Azure Blob Storage Service</span></span>
  <span data-ttu-id="4cffa-103">Diese Lektion veranschaulicht die Verwendung der TQL-Anweisung zum Ausführen einer vollständigen Datenbanksicherung im Azure-BLOB-Speicherdienst.</span><span class="sxs-lookup"><span data-stu-id="4cffa-103">This lesson demonstrates the use of tsql statement to perform a full database backup to Azure Blob storage service.</span></span>  
  
## <a name="perform-a-full-database-backup-to-the-azure-blob-storage-service"></a><span data-ttu-id="4cffa-104">Ausführen einer vollständigen Datenbanksicherung für den Azure BLOB Storage-Dienst</span><span class="sxs-lookup"><span data-stu-id="4cffa-104">Perform a Full Database Backup to the Azure Blob Storage Service</span></span>  
 <span data-ttu-id="4cffa-105">Führen Sie die folgenden Schritte aus, um eine vollständige Datenbanksicherung zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="4cffa-105">To create a full database backup, use the following steps:</span></span>  
  
1.  <span data-ttu-id="4cffa-106">Stellen Sie eine Verbindung mit [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="4cffa-106">Connect to [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="4cffa-107">Stellen Sie im **Objekt-Explorer**eine Verbindung mit der [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="4cffa-107">In the **Object Explorer**, connect to the instance of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
3.  <span data-ttu-id="4cffa-108">Klicken Sie auf der Standardmenüleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="4cffa-108">On the Standard menu bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="4cffa-109">Kopieren Sie das folgende Beispiel, und fügen Sie es in das Abfragefenster ein, ändern Sie das Beispiel ggf., und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="4cffa-109">Copy and paste the following example into the query window, modify as needed, and click **Execute**.</span></span>  
  
    ```  
    BACKUP DATABASE[AdventureWorks2012]   
    TO URL = 'https://mystorageaccount.blob.core.windows.net/privatecontainertest/AdventureWorks2012.bak'   
    /* URL includes the endpoint for the BLOB service, followed by the container name, and the name of the backup file*/   
    WITH CREDENTIAL = 'mycredential';  
    /* name of the credential you created in the previous step */   
    GO  
  
    ```  
  
5.  <span data-ttu-id="4cffa-110">Stellen Sie im Objekt-Explorer eine Verbindung mit dem Azure-Speicher her.</span><span class="sxs-lookup"><span data-stu-id="4cffa-110">In the object explorer, connect to Azure Storage.</span></span> <span data-ttu-id="4cffa-111">Navigieren Sie zum Container und den neu erstellten Sicherungsdateien.</span><span class="sxs-lookup"><span data-stu-id="4cffa-111">Browse to find the container and the newly created backup files.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="4cffa-112">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="4cffa-112">Next Lesson</span></span>  
 <span data-ttu-id="4cffa-113">[Lektion 4: Ausführen einer Wiederherstellung aus einer vollständigen Datenbanksicherung](../../2014/tutorials/lesson-4-perform-a-restore-from-a-full-database-backup.md)</span><span class="sxs-lookup"><span data-stu-id="4cffa-113">[Lesson 4: Perform a Restore From a Full Database Backup](../../2014/tutorials/lesson-4-perform-a-restore-from-a-full-database-backup.md).</span></span>  
  
  
