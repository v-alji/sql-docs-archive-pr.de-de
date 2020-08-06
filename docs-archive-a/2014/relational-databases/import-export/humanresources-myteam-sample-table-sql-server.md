---
title: HumanResources.myTeam-Beispieltabelle (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- myTeam sample table [SQL Server]
- bulk importing [SQL Server], examples
- bulk exporting [SQL Server], examples
ms.assetid: 27da45a0-c1f4-4bf4-ab24-6196e80d3834
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7d4e0cbbf42c2bdd25e3dd7c9577e4d0ec44549a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620382"
---
# <a name="humanresourcesmyteam-sample-table-sql-server"></a><span data-ttu-id="b0371-102">HumanResources.myTeam-Beispieltabelle (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b0371-102">HumanResources.myTeam Sample Table (SQL Server)</span></span>
  <span data-ttu-id="b0371-103">Viele der Codebeispiele in [Importieren und Exportieren von Massendaten](bulk-import-and-export-of-data-sql-server.md) erfordern eine besondere Testtabelle namens **myTeam**.</span><span class="sxs-lookup"><span data-stu-id="b0371-103">Many of the code examples in [Importing and Exporting Bulk Data](bulk-import-and-export-of-data-sql-server.md) require a special-purpose test table named **myTeam**.</span></span> <span data-ttu-id="b0371-104">Bevor Sie die Beispiele ausführen können, müssen Sie die **myTeam** -Tabelle im **HumanResources** -Schema der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank erstellen.</span><span class="sxs-lookup"><span data-stu-id="b0371-104">Before you can run the examples, you must create the **myTeam** table in the **HumanResources** schema of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] <span data-ttu-id="b0371-105">ist eine der Beispieldatenbanken in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0371-105">is one of the sample databases in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="b0371-106">Die **myTeam** -Tabelle enthält die folgenden Spalten.</span><span class="sxs-lookup"><span data-stu-id="b0371-106">The **myTeam** table is contains the following columns.</span></span>  
  
|<span data-ttu-id="b0371-107">Column</span><span class="sxs-lookup"><span data-stu-id="b0371-107">Column</span></span>|<span data-ttu-id="b0371-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="b0371-108">Data type</span></span>|<span data-ttu-id="b0371-109">NULL-Zulässigkeit</span><span class="sxs-lookup"><span data-stu-id="b0371-109">Nullability</span></span>|<span data-ttu-id="b0371-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b0371-110">Description</span></span>|  
|------------|---------------|-----------------|-----------------|  
|<span data-ttu-id="b0371-111">**EmployeeID**</span><span class="sxs-lookup"><span data-stu-id="b0371-111">**EmployeeID**</span></span>|`smallint`|<span data-ttu-id="b0371-112">Nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b0371-112">Not null</span></span>|<span data-ttu-id="b0371-113">Primärschlüssel für die Zeilen.</span><span class="sxs-lookup"><span data-stu-id="b0371-113">Primary key for the rows.</span></span> <span data-ttu-id="b0371-114">Mitarbeiter-ID eines Mitglieds meines Teams.</span><span class="sxs-lookup"><span data-stu-id="b0371-114">Employee ID of a member of my team.</span></span>|  
|<span data-ttu-id="b0371-115">**Name**</span><span class="sxs-lookup"><span data-stu-id="b0371-115">**Name**</span></span>|`nvarchar(50)`|<span data-ttu-id="b0371-116">Nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b0371-116">Not null</span></span>|<span data-ttu-id="b0371-117">Name eines Mitglieds meines Teams.</span><span class="sxs-lookup"><span data-stu-id="b0371-117">Name of a member of my team.</span></span>|  
|<span data-ttu-id="b0371-118">**Titel**</span><span class="sxs-lookup"><span data-stu-id="b0371-118">**Title**</span></span>|`nvarchar(50)`|<span data-ttu-id="b0371-119">Nullable</span><span class="sxs-lookup"><span data-stu-id="b0371-119">Nullable</span></span>|<span data-ttu-id="b0371-120">Titel des Mitarbeiters in meinem Team.</span><span class="sxs-lookup"><span data-stu-id="b0371-120">Title the employee performs on my team.</span></span>|  
|<span data-ttu-id="b0371-121">**Hintergrund**</span><span class="sxs-lookup"><span data-stu-id="b0371-121">**Background**</span></span>|`nvarchar(50)`|<span data-ttu-id="b0371-122">Nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b0371-122">Not null</span></span>|<span data-ttu-id="b0371-123">Datum und Uhrzeit des letzten Updates der Zeile.</span><span class="sxs-lookup"><span data-stu-id="b0371-123">Date and time the row was last updated.</span></span> <span data-ttu-id="b0371-124">(Standardwert)</span><span class="sxs-lookup"><span data-stu-id="b0371-124">(Default)</span></span>|  
  
 <span data-ttu-id="b0371-125">**So erstellen Sie HumanResources.myTeam**</span><span class="sxs-lookup"><span data-stu-id="b0371-125">**To create HumanResources.myTeam**</span></span>  
  
-   <span data-ttu-id="b0371-126">Verwenden Sie die folgende [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="b0371-126">Use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    --Create HumanResources.MyTeam:   
    USE AdventureWorks;  
    GO  
    CREATE TABLE HumanResources.myTeam   
    (EmployeeID smallint NOT NULL,  
    Name nvarchar(50) NOT NULL,  
    Title nvarchar(50) NULL,  
    Background nvarchar(50) NOT NULL DEFAULT ''  
    );  
    GO  
    ```  
  
 <span data-ttu-id="b0371-127">**So füllen Sie HumanResources.myTeam auf**</span><span class="sxs-lookup"><span data-stu-id="b0371-127">**To populate HumanResources.myTeam**</span></span>  
  
-   <span data-ttu-id="b0371-128">Führen Sie die folgenden `INSERT` -Anweisungen zum Auffüllen der Tabelle mit zwei Zeilen aus:</span><span class="sxs-lookup"><span data-stu-id="b0371-128">Execute following `INSERT` statements to populate the table with two rows:</span></span>  
  
    ```  
    USE AdventureWorks;  
    GO  
    INSERT INTO HumanResources.myTeam(EmployeeID,Name,Title,Background)  
       VALUES(77,'Mia Doppleganger','Administrative Assistant','Microsoft Office');  
    GO  
    INSERT INTO HumanResources.myTeam(EmployeeID,Name,Title,Background)  
       VALUES(49,'Hirum Mollicat','I.T. Specialist','Report Writing and Data Mining');  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="b0371-129">Bei diesen Anweisungen wird die vierte Spalte ( `Background`) ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="b0371-129">These statements skip the fourth column, `Background`.</span></span> <span data-ttu-id="b0371-130">Diese besitzt einen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="b0371-130">This has a default value.</span></span> <span data-ttu-id="b0371-131">Das Auslassen dieser Spalte bewirkt, dass diese Spalte bei der `INSERT` -Anweisung leer bleibt.</span><span class="sxs-lookup"><span data-stu-id="b0371-131">Skipping this column causes this `INSERT` statement to leave this column blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0371-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b0371-132">See Also</span></span>  
 [<span data-ttu-id="b0371-133">Massenimport und -export von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b0371-133">Bulk Import and Export of Data &#40;SQL Server&#41;</span></span>](bulk-import-and-export-of-data-sql-server.md)  
  
  
