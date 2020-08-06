---
title: Auflisten von Informationen zu Auftragskategorien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 0fc668d4-6244-4fef-b90e-62d2c776cd7c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 924e2b064980b2ea7068230610414262995da1a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720809"
---
# <a name="list-job-category-information"></a><span data-ttu-id="02775-102">Auflisten von Informationen zu Auftragskategorien</span><span class="sxs-lookup"><span data-stu-id="02775-102">List Job Category Information</span></span>
  <span data-ttu-id="02775-103">Auflisten von Informationen zu Auftrags Kategorien in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[tsql](../../includes/tsql-md.md)] oder SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="02775-103">How to list job category information in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  

  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="02775-104">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="02775-104">Security</span></span>  
 <span data-ttu-id="02775-105">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="02775-105">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  

  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="02775-106">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="02775-106">Using Transact-SQL</span></span>  
  
#### <a name="to-list-job-category-information"></a><span data-ttu-id="02775-107">So listen Sie Informationen zu Auftragskategorien auf</span><span class="sxs-lookup"><span data-stu-id="02775-107">To list job category information</span></span>  
  
1.  <span data-ttu-id="02775-108">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="02775-108">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="02775-109">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="02775-109">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="02775-110">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="02775-110">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- returns information about jobs that are administered locally  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_category  
        @type = N'LOCAL' ;  
    GO  
    ```  
  
 <span data-ttu-id="02775-111">Weitere Informationen finden Sie unter [sp_help_category &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-help-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="02775-111">For more information, see [sp_help_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-category-transact-sql).</span></span>  
  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="02775-112">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="02775-112">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="02775-113">**So listen Sie Informationen zu Auftragskategorien auf**</span><span class="sxs-lookup"><span data-stu-id="02775-113">**To list job category information**</span></span>  
  
 <span data-ttu-id="02775-114">Verwenden Sie die `JobCategory`-Klasse in einer von Ihnen ausgewählten Programmiersprache, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02775-114">Use the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell..</span></span> <span data-ttu-id="02775-115">Weitere Informationen finden Sie unter [SQL Server Management Objects &#40;SMO&#41;-Programmier Handbuch](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md).</span><span class="sxs-lookup"><span data-stu-id="02775-115">For more information, see [SQL Server Management Objects &#40;SMO&#41; Programming Guide](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md).</span></span>  
