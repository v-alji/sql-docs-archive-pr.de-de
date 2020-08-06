---
title: Erstellen einer Datenbank (Tutorial) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- tutorial creating a database
ms.assetid: e1e2c83f-dfad-4bb8-aa7a-09d3f69517ae
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 99d5439c289b5d4e71786d4c6734f158f6bba371
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619482"
---
# <a name="creating-a-database-tutorial"></a><span data-ttu-id="80fcf-102">Erstellen einer Datenbank (Lernprogramm)</span><span class="sxs-lookup"><span data-stu-id="80fcf-102">Creating a Database (Tutorial)</span></span>
  <span data-ttu-id="80fcf-103">Wie viele [!INCLUDE[tsql](../includes/tsql-md.md)] -Anweisungen verfügt auch die CREATE DATABASE-Anweisung über einen erforderlichen Parameter: den Namen der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="80fcf-103">Like many [!INCLUDE[tsql](../includes/tsql-md.md)] statements, the CREATE DATABASE statement has a required parameter: the name of the database.</span></span> <span data-ttu-id="80fcf-104">CREATE DATABASE verfügt auch über viele optionale Parameter wie den Speicherort auf dem Datenträger, an den Sie die Datenbankdateien kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="80fcf-104">CREATE DATABASE also has many optional parameters, such as the disk location where you want to put the database files.</span></span> <span data-ttu-id="80fcf-105">Wenn Sie CREATE DATABASE ohne optionale Parameter ausführen, werden von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Standardwerte für viele dieser Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="80fcf-105">When you execute CREATE DATABASE without the optional parameters, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] uses default values for many of these parameters.</span></span> <span data-ttu-id="80fcf-106">In diesem Lernprogramm werden nur wenige der optionalen Syntaxparameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="80fcf-106">This tutorial uses very few of the optional syntax parameters.</span></span>  
  
### <a name="to-create-a-database"></a><span data-ttu-id="80fcf-107">So erstellen Sie eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="80fcf-107">To create a database</span></span>  
  
1.  <span data-ttu-id="80fcf-108">Geben Sie in einem Fenster des Abfrage-Editors den folgenden Code ein, aber führen Sie ihn nicht aus:</span><span class="sxs-lookup"><span data-stu-id="80fcf-108">In a Query Editor window, type but do not execute the following code:</span></span>  
  
    ```  
    CREATE DATABASE TestData  
    GO  
    ```  
  
2.  <span data-ttu-id="80fcf-109">Verwenden Sie den Zeiger, um die Wörter `CREATE DATABASE`auszuwählen, und drücken Sie dann **F1**.</span><span class="sxs-lookup"><span data-stu-id="80fcf-109">Use the pointer to select the words `CREATE DATABASE`, and then press **F1**.</span></span> <span data-ttu-id="80fcf-110">Das CREATE DATABASE-Thema in der SQL Server-Onlinedokumentation sollte geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="80fcf-110">The CREATE DATABASE topic in SQL Server Books Online should open.</span></span> <span data-ttu-id="80fcf-111">Sie können dieses Verfahren verwenden, um die vollständige Syntax für CREATE DATABASE und für die anderen in diesem Lernprogramm verwendeten Anweisungen zu finden.</span><span class="sxs-lookup"><span data-stu-id="80fcf-111">You can use this technique to find the complete syntax for CREATE DATABASE and for the other statements that are used in this tutorial.</span></span>  
  
3.  <span data-ttu-id="80fcf-112">Drücken Sie im Abfrage-Editor **F5** , um die Anweisung auszuführen und eine Datenbank mit Namen `TestData`zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="80fcf-112">In Query Editor, press **F5** to execute the statement and create a database named `TestData`.</span></span>  
  
 <span data-ttu-id="80fcf-113">Wenn Sie eine Datenbank erstellen, wird von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] eine Kopie der **model** -Datenbank erstellt und die Kopie in den Namen der Datenbank umbenannt.</span><span class="sxs-lookup"><span data-stu-id="80fcf-113">When you create a database, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] makes a copy of the **model** database, and renames the copy to the database name.</span></span> <span data-ttu-id="80fcf-114">Dieser Vorgang dauert nur einige Sekunden, es sei denn, Sie geben eine große Anfangsgröße der Datenbank als optionalen Parameter an.</span><span class="sxs-lookup"><span data-stu-id="80fcf-114">This operation should only take several seconds, unless you specify a large initial size of the database as an optional parameter.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="80fcf-115">Das GO-Schlüsselwort trennt Anweisungen, wenn mehrere Anweisungen in einem einzelnen Batch gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="80fcf-115">The keyword GO separates statements when more than one statement is submitted in a single batch.</span></span> <span data-ttu-id="80fcf-116">GO ist optional, wenn der Batch nur eine Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="80fcf-116">GO is optional when the batch contains only one statement.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="80fcf-117">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="80fcf-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="80fcf-118">Erstellen einer Tabelle &#40;Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="80fcf-118">Creating a Table &#40;Tutorial&#41;</span></span>](lesson-1-2-creating-a-table.md)  
  
## <a name="see-also"></a><span data-ttu-id="80fcf-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="80fcf-119">See Also</span></span>  
 [<span data-ttu-id="80fcf-120">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="80fcf-120">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
  
