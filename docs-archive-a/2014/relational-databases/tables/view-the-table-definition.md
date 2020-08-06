---
title: Anzeigen der Tabellendefinition | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- showing table properties
- displaying table properties
- tables [SQL Server], properties
- viewing table properties
ms.assetid: 1865fb7c-f480-4100-9007-df5364cd002a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 53170a78a104bfce4b4e4177015461f2eb9093e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630581"
---
# <a name="view-the-table-definition"></a><span data-ttu-id="7264f-102">Anzeigen der Tabellendefinition</span><span class="sxs-lookup"><span data-stu-id="7264f-102">View the Table Definition</span></span>
  <span data-ttu-id="7264f-103">Sie können die Eigenschaften einer Tabelle in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7264f-103">You can display properties for a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7264f-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="7264f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7264f-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="7264f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7264f-106">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7264f-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7264f-107">**So zeigen Sie Tabelleneigenschaften an mit:**</span><span class="sxs-lookup"><span data-stu-id="7264f-107">**To display table properties, using:**</span></span>  
  
     [<span data-ttu-id="7264f-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7264f-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7264f-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7264f-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7264f-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="7264f-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7264f-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7264f-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7264f-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7264f-112">Permissions</span></span>  
 <span data-ttu-id="7264f-113">Sie können nur Eigenschaften in einer Tabelle sehen, wenn Sie entweder die Tabelle besitzen oder Ihnen Berechtigungen für diese Tabelle gewährt wurden.</span><span class="sxs-lookup"><span data-stu-id="7264f-113">You can only see properties in a table if you either own the table or have been granted permissions to that table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7264f-114">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7264f-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-show-table-properties-in-the-properties-window"></a><span data-ttu-id="7264f-115">So zeigen Sie Tabelleneigenschaften im Eigenschaftenfenster an</span><span class="sxs-lookup"><span data-stu-id="7264f-115">To show table properties in the Properties window</span></span>  
  
1.  <span data-ttu-id="7264f-116">Wählen Sie im Objekt-Explorer die Tabelle aus, deren Eigenschaften Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="7264f-116">In Object Explorer, select the table for which you want to show properties.</span></span>  
  
2.  <span data-ttu-id="7264f-117">Klicken Sie mit der rechten Maustaste auf die Tabelle, und wählen Sie im Kontextmenü die Option **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="7264f-117">Right-click the table and choose **Properties** from the shortcut menu.</span></span> <span data-ttu-id="7264f-118">Weitere Informationen finden Sie unter [Table Properties](table-properties-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="7264f-118">For more information, see [Table Properties](table-properties-ssms.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7264f-119">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7264f-119">Using Transact-SQL</span></span>  
  
#### <a name="to-show-table-properties"></a><span data-ttu-id="7264f-120">So zeigen Sie Tabelleneigenschaften an</span><span class="sxs-lookup"><span data-stu-id="7264f-120">To show table properties</span></span>  
  
1.  <span data-ttu-id="7264f-121">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="7264f-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7264f-122">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="7264f-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7264f-123">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7264f-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="7264f-124">In diesem Beispiel werden alle Spalten der `sys.tables` -Katalogsicht für das angegebene Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7264f-124">The example returns all columns from the `sys.tables` catalog view for the specified object.</span></span>  
  
    ```  
    SELECT * FROM sys.tables  
    WHERE object_id = 1973582069;  
  
    ```  
  
 <span data-ttu-id="7264f-125">Weitere Informationen finden Sie unter [sys.tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7264f-125">For more information, see [sys.tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
