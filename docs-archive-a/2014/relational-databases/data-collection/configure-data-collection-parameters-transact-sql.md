---
title: Konfigurieren von Parametern für die Datensammlung (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collection [SQL Server]
ms.assetid: 850905b6-35d2-4ed1-ab51-de64daa832b2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a8333b47612b4fbd933ef132e886b8125ffb58a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718262"
---
# <a name="configure-data-collection-parameters-transact-sql"></a><span data-ttu-id="fd292-102">Konfigurieren von Parametern für die Datensammlung (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fd292-102">Configure Data Collection Parameters (Transact-SQL)</span></span>
  <span data-ttu-id="fd292-103">Bevor Sie einen benutzerdefinierten Sammlungssatz erstellen, müssen Sie zuerst Datensammlungsparameter konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fd292-103">Before you create a custom collection set, you must first configure data collection parameters.</span></span> <span data-ttu-id="fd292-104">Hierfür können Sie die gespeicherten Prozeduren verwenden, die mit dem Datensammler bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="fd292-104">You can do this by using the stored procedures that are provided with the data collector.</span></span> <span data-ttu-id="fd292-105">Um diese Aufgabe auszuführen, müssen Sie mit dem Abfrage-Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] den folgenden Vorgang durchführen.</span><span class="sxs-lookup"><span data-stu-id="fd292-105">Accomplishing this task involves using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to carry out the following procedure.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fd292-106">Parameter für die Datensammlung können nur einmal konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="fd292-106">You only configure data collection parameters once.</span></span> <span data-ttu-id="fd292-107">Nach der Konfiguration werden diese Parameter für alle zusätzlichen Sammlungssätze verwendet, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="fd292-107">After configuration, these parameters are used for any additional collection sets that you create.</span></span>  
  
### <a name="configure-data-collection-parameters"></a><span data-ttu-id="fd292-108">Konfigurieren von Parametern für die Datensammlung</span><span class="sxs-lookup"><span data-stu-id="fd292-108">Configure data collection parameters</span></span>  
  
1.  <span data-ttu-id="fd292-109">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung mit der Datenbank her, in der Sie einen benutzerdefinierten Sammlungssatz erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="fd292-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the database where you want to create a custom collection set.</span></span>  
  
2.  <span data-ttu-id="fd292-110">Führen Sie im Abfrage-Editor die folgenden Anweisungen aus.</span><span class="sxs-lookup"><span data-stu-id="fd292-110">In Query Editor, issue the following statements.</span></span>  
  
    ```sql  
    USE msdb;  
    EXEC sp_syscollector_set_warehouse_instance_name N'INSTANCE_NAME';-- where instance name is the name of the SQL Server instance  
    EXEC sp_syscollector_set_warehouse_database_name N'MDW';  
    EXEC sp_syscollector_set_cache_directory N'D:\tempdata';  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fd292-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fd292-111">See Also</span></span>  
 <span data-ttu-id="fd292-112">[Datensammlung](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="fd292-112">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="fd292-113">Gespeicherte Prozeduren für den Datensammler &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fd292-113">Data Collector Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql)  
  
  
