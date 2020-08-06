---
title: 'Lektion 4: Ausführen einer Wiederherstellung aus einer vollständigen Datenbanksicherung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 580f76e6-9802-4abc-9043-db6de592c733
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 9906ea14c2f76a49644a8f76fbd894adf8b9d500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616871"
---
# <a name="lesson-4-perform-a-restore-from-a-full-database-backup"></a><span data-ttu-id="b8162-102">Lektion 4: Ausführen einer Wiederherstellung aus einer vollständigen Datenbanksicherung</span><span class="sxs-lookup"><span data-stu-id="b8162-102">Lesson 4: Perform a Restore From a Full Database Backup</span></span>
  <span data-ttu-id="b8162-103">In dieser Lektion wird veranschaulicht, wie mithilfe einer T-SQL-Anweisung eine Wiederherstellung von einer vollständigen Datenbanksicherung ausgeführt wird, die in der vorherigen Lektion erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b8162-103">This lesson demonstrates the use of a tsql statement to perform a restore from a full database backup created in the previous lesson.</span></span>  
  
## <a name="perform-a-restore-of-a-database-backup"></a><span data-ttu-id="b8162-104">Ausführen einer Wiederherstellung von einer Datenbanksicherung</span><span class="sxs-lookup"><span data-stu-id="b8162-104">Perform a Restore of a Database Backup</span></span>  
 <span data-ttu-id="b8162-105">Führen Sie die folgenden Schritte aus, um eine vollständige Datenbanksicherung wiederherzustellen:</span><span class="sxs-lookup"><span data-stu-id="b8162-105">To restore a full database backup, use the following steps:</span></span>  
  
1.  <span data-ttu-id="b8162-106">Stellen Sie eine Verbindung mit [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="b8162-106">Connect to [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="b8162-107">Stellen Sie im **Objekt-Explorer**eine Verbindung mit der [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="b8162-107">In the **Object Explorer**, connect to the instance of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
3.  <span data-ttu-id="b8162-108">Klicken Sie auf der Standardmenüleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="b8162-108">On the Standard menu bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="b8162-109">Kopieren Sie das folgende Beispiel in das Abfragefenster, und ändern Sie es nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="b8162-109">Copy and paste the following example into the query window, modify as needed.</span></span>  
  
    ```  
    RESTORE DATABASE AdventureWorks2012   
    FROM URL = 'https://mystorageaccount.blob.core.windows.net/privatecontainertest/AdventureWorks2012.bak'   
    WITH CREDENTIAL = 'mycredential';  
    , STATS = 5 - use this to see monitor the progress  
    GO  
  
    ```  
  
5.  <span data-ttu-id="b8162-110">Überprüfen Sie die T-SQL-Anweisung, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b8162-110">Verify the T-SQL statement and click **Execute**</span></span>  
  
### <a name="return-to-tutorials-portal"></a><span data-ttu-id="b8162-111">Zurück zum Portal für die Lernprogramme</span><span class="sxs-lookup"><span data-stu-id="b8162-111">Return to Tutorials Portal</span></span>  
 <span data-ttu-id="b8162-112">[Tutorial: SQL Server sichern und Wiederherstellen Azure BLOB Storage Dienstanbieter](../relational-databases/tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="b8162-112">[Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service](../relational-databases/tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md).</span></span>  
  
  
