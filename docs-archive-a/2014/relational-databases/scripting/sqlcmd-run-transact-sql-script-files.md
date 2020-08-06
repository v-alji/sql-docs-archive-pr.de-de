---
title: Ausführen von Transact-SQL-Skriptdateien mithilfe von sqlcmd
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- transact sql scripts
ms.assetid: 90067eb8-ca3e-44e8-bb1a-bf7d1a359423
author: rothja
ms.author: jroth
ms.openlocfilehash: cd34b089fc4e971cac9e5713cbe303192a7a48c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609788"
---
# <a name="run-transact-sql-script-files-using-sqlcmd"></a><span data-ttu-id="081da-102">Ausführen von Transact-SQL-Skriptdateien mithilfe von sqlcmd</span><span class="sxs-lookup"><span data-stu-id="081da-102">Run Transact-SQL Script Files Using sqlcmd</span></span>
  <span data-ttu-id="081da-103">Sie können `sqlcmd` verwenden, um eine [!INCLUDE[tsql](../../includes/tsql-md.md)]-Skriptdatei auszuführen.</span><span class="sxs-lookup"><span data-stu-id="081da-103">You can use `sqlcmd` to run a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="081da-104">Eine [!INCLUDE[tsql](../../includes/tsql-md.md)]-Skriptdatei ist eine Textdatei, die eine Kombination aus [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen, `sqlcmd`-Befehlen und Skriptvariablen enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="081da-104">A [!INCLUDE[tsql](../../includes/tsql-md.md)] script file is a text file that can contain a combination of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, `sqlcmd` commands, and scripting variables.</span></span>  
  
 <span data-ttu-id="081da-105">Führen Sie die folgenden Schritte aus, um eine einfache [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skriptdatei mithilfe des Editors zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="081da-105">To create a simple [!INCLUDE[tsql](../../includes/tsql-md.md)] script file by using Notepad, follow these steps:</span></span>  
  
1.  <span data-ttu-id="081da-106">Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, zeigen Sie auf **Zubehör**, und klicken Sie dann auf **Editor**.</span><span class="sxs-lookup"><span data-stu-id="081da-106">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Notepad**.</span></span>  
  
2.  <span data-ttu-id="081da-107">Kopieren Sie den folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] -Code, und fügen Sie ihn im Editor ein:</span><span class="sxs-lookup"><span data-stu-id="081da-107">Copy and paste the following [!INCLUDE[tsql](../../includes/tsql-md.md)] code into Notepad:</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT p.FirstName + ' ' + p.LastName AS 'Employee Name',  
    a.AddressLine1, a.AddressLine2 , a.City, a.PostalCode   
    FROM Person.Person AS p   
       INNER JOIN HumanResources.Employee AS e   
            ON p.BusinessEntityID = e.BusinessEntityID  
        INNER JOIN Person.BusinessEntityAddress bea   
            ON bea.BusinessEntityID = e.BusinessEntityID  
        INNER JOIN Person.Address AS a   
            ON a.AddressID = bea.AddressID;  
    GO  
    ```  
  
3.  <span data-ttu-id="081da-108">Speichern Sie die Datei auf dem Laufwerk C unter dem Namen **myScript.sql** .</span><span class="sxs-lookup"><span data-stu-id="081da-108">Save the file as **myScript.sql** in the C drive.</span></span>  
  
### <a name="to-run-the-script-file"></a><span data-ttu-id="081da-109">So führen Sie die Skriptdatei aus</span><span class="sxs-lookup"><span data-stu-id="081da-109">To run the script file</span></span>  
  
1.  <span data-ttu-id="081da-110">Öffnen Sie ein Eingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="081da-110">Open a command prompt window.</span></span>  
  
2.  <span data-ttu-id="081da-111">Geben Sie im Fenster "Eingabeaufforderung" Folgendes ein: `sqlcmd -S myServer\instanceName -i C:\myScript.sql`</span><span class="sxs-lookup"><span data-stu-id="081da-111">In the Command Prompt window, type: `sqlcmd -S myServer\instanceName -i C:\myScript.sql`</span></span>  
  
3.  <span data-ttu-id="081da-112">Drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="081da-112">Press ENTER.</span></span>  
  
 <span data-ttu-id="081da-113">Eine Liste mit Namen und Adressen von Mitarbeitern aus [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] wird in das Eingabeaufforderungsfenster geschrieben.</span><span class="sxs-lookup"><span data-stu-id="081da-113">A list of [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] employee names and addresses is written to the command prompt window.</span></span>  
  
### <a name="to-save-this-output-to-a-text-file"></a><span data-ttu-id="081da-114">So speichern Sie diese Ausgabe in einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="081da-114">To save this output to a text file</span></span>  
  
1.  <span data-ttu-id="081da-115">Öffnen Sie ein Eingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="081da-115">Open a command prompt window.</span></span>  
  
2.  <span data-ttu-id="081da-116">Geben Sie im Fenster "Eingabeaufforderung" Folgendes ein: `sqlcmd -S myServer\instanceName -i C:\myScript.sql -o C:\EmpAdds.txt`</span><span class="sxs-lookup"><span data-stu-id="081da-116">In the Command Prompt window, type: `sqlcmd -S myServer\instanceName -i C:\myScript.sql -o C:\EmpAdds.txt`</span></span>  
  
3.  <span data-ttu-id="081da-117">Drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="081da-117">Press ENTER.</span></span>  
  
 <span data-ttu-id="081da-118">In diesem Fall erfolgt keine Ausgabe im Eingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="081da-118">No output is returned in the Command Prompt window.</span></span> <span data-ttu-id="081da-119">Stattdessen erfolgt die Ausgabe in die Datei EmpAdds.txt.</span><span class="sxs-lookup"><span data-stu-id="081da-119">Instead, the output is sent to the EmpAdds.txt file.</span></span> <span data-ttu-id="081da-120">Sie können diese Ausgabe prüfen, indem Sie die Datei EmpAdds.txt öffnen.</span><span class="sxs-lookup"><span data-stu-id="081da-120">You can verify this output by opening the EmpAdds.txt file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="081da-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="081da-121">See Also</span></span>  
 <span data-ttu-id="081da-122">[Starten des Hilfsprogramms „sqlcmd“](sqlcmd-start-the-utility.md) </span><span class="sxs-lookup"><span data-stu-id="081da-122">[Start the sqlcmd Utility](sqlcmd-start-the-utility.md) </span></span>  
 [<span data-ttu-id="081da-123">SQLCMD-Hilfsprogramm</span><span class="sxs-lookup"><span data-stu-id="081da-123">sqlcmd Utility</span></span>](../../tools/sqlcmd-utility.md)  
  
  
