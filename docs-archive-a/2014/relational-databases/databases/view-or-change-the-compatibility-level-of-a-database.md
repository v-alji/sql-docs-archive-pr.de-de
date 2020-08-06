---
title: Anzeigen oder Ändern des Kompatibilitätsgrads einer Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- compatibility levels [SQL Server], viewing
- compatibility [SQL Server], databases
- compatibility levels [SQL Server], changing
ms.assetid: 579867ec-57cb-4cb8-af35-9688c1e9e15d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35cf7af50eba333440c42a1bac428df1fff156b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724761"
---
# <a name="view-or-change-the-compatibility-level-of-a-database"></a><span data-ttu-id="a123d-102">Anzeigen oder Ändern des Kompatibilitätsgrads einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="a123d-102">View or Change the Compatibility Level of a Database</span></span>
  <span data-ttu-id="a123d-103">In diesem Thema wird die Vorgehensweise zum Anzeigen oder Ändern des Kompatibilitätsgrads einer Datenbank in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a123d-103">This topic describes how to view or change the compatibility level of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a123d-104">Vor dem Ändern des Kompatibilitätsgrads einer Datenbank sollten Sie wissen, wie sich die Änderung auf die Anwendungen auswirkt.</span><span class="sxs-lookup"><span data-stu-id="a123d-104">Before you change the compatibility level of a database, you should understand the impact of the change on your applications.</span></span> <span data-ttu-id="a123d-105">Weitere Informationen finden Sie unter [ALTER DATABASE-Kompatibilitätsgrad &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span><span class="sxs-lookup"><span data-stu-id="a123d-105">For more information, see [ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span></span>  
  
 <span data-ttu-id="a123d-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="a123d-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a123d-107">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="a123d-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a123d-108">Security</span><span class="sxs-lookup"><span data-stu-id="a123d-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a123d-109">**So zeigen Sie den Kompatibilitätsgrad einer Datenbank an oder ändern ihn mit:**</span><span class="sxs-lookup"><span data-stu-id="a123d-109">**To view or change the compatibility level of a database, using:**</span></span>  
  
     [<span data-ttu-id="a123d-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a123d-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a123d-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a123d-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a123d-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="a123d-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a123d-113">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a123d-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a123d-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a123d-114">Permissions</span></span>  
 <span data-ttu-id="a123d-115">Erfordert die ALTER-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="a123d-115">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a123d-116">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a123d-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-compatibility-level-of-a-database"></a><span data-ttu-id="a123d-117">So zeigen Sie den Kompatibilitätsgrad einer Datenbank an oder ändern ihn</span><span class="sxs-lookup"><span data-stu-id="a123d-117">To view or change the compatibility level of a database</span></span>  
  
1.  <span data-ttu-id="a123d-118">Stellen Sie eine Verbindung zur entsprechenden Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, und klicken Sie danach im Objekt-Explorer auf den Servernamen.</span><span class="sxs-lookup"><span data-stu-id="a123d-118">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name.</span></span>  
  
2.  <span data-ttu-id="a123d-119">Erweitern Sie **Datenbanken**, und wählen Sie je nach Datenbank eine Benutzerdatenbank aus, oder erweitern Sie **Systemdatenbanken** , und wählen Sie eine Systemdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="a123d-119">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="a123d-120">Klicken Sie mit der rechten Maustaste auf die Datenbank, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a123d-120">Right-click the database, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="a123d-121">Das Dialogfeld **Datenbankeigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a123d-121">The **Database Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="a123d-122">Klicken Sie auf der Seite **Seite auswählen** auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="a123d-122">In the **Select a page** pane, click **Options**.</span></span>  
  
     <span data-ttu-id="a123d-123">Der aktuelle Kompatibilitätsgrad wird im Listenfeld **Kompatibilitätsgrad** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a123d-123">The current compatibility level is displayed in the **Compatibility level** list box.</span></span>  
  
5.  <span data-ttu-id="a123d-124">Um den Kompatibilitätsgrad zu ändern, wählen Sie eine andere Option aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="a123d-124">To change the compatibility level, select a different option from the list.</span></span> <span data-ttu-id="a123d-125">Zur Auswahl stehen **SQL Server 2008 (100)**, **SQL Server 2012 (110)**, oder **SQL Server 2014 (120)**.</span><span class="sxs-lookup"><span data-stu-id="a123d-125">The choices are **SQL Server 2008 (100)**, **SQL Server 2012 (110)**, or **SQL Server 2014 (120)**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a123d-126">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a123d-126">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-compatibility-level-of-a-database"></a><span data-ttu-id="a123d-127">So zeigen Sie den Kompatibilitätsgrad einer Datenbank an</span><span class="sxs-lookup"><span data-stu-id="a123d-127">To view the compatibility level of a database</span></span>  
  
1.  <span data-ttu-id="a123d-128">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="a123d-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a123d-129">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="a123d-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a123d-130">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a123d-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="a123d-131">In diesem Beispiel wird der Kompatibilitätsgrad der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a123d-131">This example returns the compatibility level of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT compatibility_level  
FROM sys.databases WHERE name = 'AdventureWorks2012';  
GO  
  
```  
  
#### <a name="to-change-the-compatibility-level-of-a-database"></a><span data-ttu-id="a123d-132">So ändern Sie den Kompatibilitätsgrad einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="a123d-132">To change the compatibility level of a database</span></span>  
  
1.  <span data-ttu-id="a123d-133">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="a123d-133">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a123d-134">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="a123d-134">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a123d-135">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a123d-135">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="a123d-136">In diesem Beispiel wird der Kompatibilitäts Grad von geändert [!INCLUDE[ssSampleDBobject](../../includes/sssql14-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a123d-136">This example changes the compatibility level of the [!INCLUDE[ssSampleDBobject](../../includes/sssql14-md.md)].</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012  
SET COMPATIBILITY_LEVEL = 120;  
GO  
```  
  
  
