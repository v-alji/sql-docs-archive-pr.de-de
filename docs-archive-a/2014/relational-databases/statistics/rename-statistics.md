---
title: Umbenennen von Statistiken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- renaming statistics
- statistics [SQL Server], renaming
ms.assetid: a3bed7b7-3dc5-4b33-b1c6-67c27f573764
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1528dcec50a662524531065d597b004fe7f59e5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621412"
---
# <a name="rename-statistics"></a><span data-ttu-id="113de-102">Umbenennen von Statistiken</span><span class="sxs-lookup"><span data-stu-id="113de-102">Rename Statistics</span></span>
  <span data-ttu-id="113de-103">Sie können ein Statistikobjekt in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="113de-103">You can rename a statistics object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="113de-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="113de-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="113de-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="113de-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="113de-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="113de-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="113de-107">Security</span><span class="sxs-lookup"><span data-stu-id="113de-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="113de-108">**So benennen Sie ein Statistikobjekt um mit:**</span><span class="sxs-lookup"><span data-stu-id="113de-108">**To rename a statistics object, using:**</span></span>  
  
     [<span data-ttu-id="113de-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="113de-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="113de-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="113de-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="113de-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="113de-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="113de-112">Standardmäßig wird beim Erstellen eines Indexes eine Statistik für die Schlüsselspalten dieses Indexes erstellt.</span><span class="sxs-lookup"><span data-stu-id="113de-112">By default, creating an index creates a statistic on the key columns of that index.</span></span> <span data-ttu-id="113de-113">Daher wird beim Umbenennen des Indexes automatisch auch das Statistikobjekt umbenannt (und umgekehrt).</span><span class="sxs-lookup"><span data-stu-id="113de-113">Therefore, renaming the index automatically renames the statistics object, and vice versa.</span></span>  
  
 <span data-ttu-id="113de-114">Wenn Sie Teile eines Objektnamens ändern, können Skripts und gespeicherte Prozeduren funktionsunfähig werden.</span><span class="sxs-lookup"><span data-stu-id="113de-114">Changing any part of an object name can break scripts and stored procedures.</span></span> <span data-ttu-id="113de-115">Anstelle der Umbenennung ist das Löschen des Statistikobjekts und die Neuerstellung unter einem neuen Namen zu empfehlen.</span><span class="sxs-lookup"><span data-stu-id="113de-115">Instead of renaming, we recommend that you drop the statistics object and re-create it with the new name.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="113de-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="113de-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="113de-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="113de-117">Permissions</span></span>  
 <span data-ttu-id="113de-118">Erfordert die ALTER-Berechtigung in der Tabelle oder Sicht.</span><span class="sxs-lookup"><span data-stu-id="113de-118">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="113de-119">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="113de-119">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-statistics-object"></a><span data-ttu-id="113de-120">So benennen Sie ein Statistikobjekt um</span><span class="sxs-lookup"><span data-stu-id="113de-120">To rename a statistics object</span></span>  
  
1.  <span data-ttu-id="113de-121">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="113de-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="113de-122">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="113de-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="113de-123">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="113de-123">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_rename N'AK_Employee_LoginID', N'AK_Emp_Login', N'STATISTICS';   
    GO  
    ```  
  
 <span data-ttu-id="113de-124">Weitere Informationen finden Sie unter [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="113de-124">For more information, see [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
