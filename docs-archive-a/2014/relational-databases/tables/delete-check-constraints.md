---
title: Löschen von CHECK-Einschränkungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing constraints
- CHECK constraints, deleting
- constraints [SQL Server], deleting
- constraints [SQL Server], check
- deleting constraints
ms.assetid: 5f86c1a6-f5fa-4e77-a892-f6ae96fc0ab3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 28a7f72993cbf2ed0a8cc76534380090ef0d0a55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617876"
---
# <a name="delete-check-constraints"></a><span data-ttu-id="92010-102">Löschen von CHECK-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="92010-102">Delete Check Constraints</span></span>
  <span data-ttu-id="92010-103">Sie können mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eine CHECK-Einschränkung in [!INCLUDE[tsql](../../includes/tsql-md.md)]löschen.</span><span class="sxs-lookup"><span data-stu-id="92010-103">You can delete a check constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="92010-104">Durch das Löschen von CHECK-Einschränkungen werden die Beschränkungen für die Datenwerte entfernt, die in der Spalte oder den Spalten im Einschränkungsausdruck zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="92010-104">Deleting check constraints removes the limitations on data values that are accepted in the column or columns included in the constraint expression.</span></span>  
  
 <span data-ttu-id="92010-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="92010-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="92010-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="92010-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="92010-107">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="92010-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="92010-108">**So löschen Sie eine CHECK-Einschränkung mit:**</span><span class="sxs-lookup"><span data-stu-id="92010-108">**To delete a check constraint, using:**</span></span>  
  
     [<span data-ttu-id="92010-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="92010-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="92010-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="92010-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="92010-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="92010-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="92010-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="92010-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="92010-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="92010-113">Permissions</span></span>  
 <span data-ttu-id="92010-114">Erfordert die ALTER-Berechtigung für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="92010-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="92010-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="92010-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-check-constraint"></a><span data-ttu-id="92010-116">So löschen Sie eine CHECK-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="92010-116">To delete a check constraint</span></span>  
  
1.  <span data-ttu-id="92010-117">Erweitern Sie im **Objekt-Explorer**die Tabelle mit der CHECK-Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="92010-117">In **Object Explorer**, expand the table with the check constraint.</span></span>  
  
2.  <span data-ttu-id="92010-118">Erweitern Sie  **Einschränkungen**.</span><span class="sxs-lookup"><span data-stu-id="92010-118">Expand  **Constraints**.</span></span>  
  
3.  <span data-ttu-id="92010-119">Klicken Sie mit der rechten Maustaste auf die Einschränkung, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="92010-119">Right-click the constraint and click **Delete**.</span></span>  
  
4.  <span data-ttu-id="92010-120">Klicken Sie im Dialogfeld **Objekt löschen** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="92010-120">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="92010-121">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="92010-121">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-check-constraint"></a><span data-ttu-id="92010-122">So löschen Sie eine CHECK-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="92010-122">To delete a check constraint</span></span>  
  
1.  <span data-ttu-id="92010-123">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="92010-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="92010-124">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="92010-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="92010-125">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="92010-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER TABLE dbo.DocExc   
    DROP CONSTRAINT CHK_ColumnD_DocExc;  
    GO  
    ```  
  
 <span data-ttu-id="92010-126">Weitere Informationen finden Sie unter [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="92010-126">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
  
