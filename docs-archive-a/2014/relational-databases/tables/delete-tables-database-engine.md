---
title: Löschen von Tabellen (Datenbank-Engine) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table deletions [SQL Server]
- deleting tables
- removing tables
- dropping tables
ms.assetid: ca6aa3e9-9885-44c3-bafc-aec441fd97ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1e361456534f565f854d348bbef5751c7d66c0f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722669"
---
# <a name="delete-tables-database-engine"></a><span data-ttu-id="4403a-102">Löschen von Tabellen (Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="4403a-102">Delete Tables (Database Engine)</span></span>
  <span data-ttu-id="4403a-103">Sie können mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eine Tabelle aus der Datenbank in [!INCLUDE[tsql](../../includes/tsql-md.md)]löschen (DROP).</span><span class="sxs-lookup"><span data-stu-id="4403a-103">You can delete (drop) a table from your database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="4403a-104">Das Löschen einer Tabelle muss sorgfältig durchdacht werden.</span><span class="sxs-lookup"><span data-stu-id="4403a-104">Think carefully before you delete a table.</span></span> <span data-ttu-id="4403a-105">Alle Abfragen, Sichten, benutzerdefinierten Funktionen, gespeicherten Prozeduren und Programme, die auf diese Tabelle verweisen, verlieren durch den Löschvorgang ihre Gültigkeit.</span><span class="sxs-lookup"><span data-stu-id="4403a-105">If existing queries, views, user-defined functions, stored procedures, or programs refer to that table, the deletion will make these objects invalid.</span></span>  
  
 <span data-ttu-id="4403a-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="4403a-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4403a-107">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="4403a-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4403a-108">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4403a-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4403a-109">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4403a-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4403a-110">**So löschen Sie eine Tabelle mit:**</span><span class="sxs-lookup"><span data-stu-id="4403a-110">**To Delete a Table, using:**</span></span>  
  
     [<span data-ttu-id="4403a-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4403a-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4403a-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4403a-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4403a-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="4403a-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4403a-114">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4403a-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="4403a-115">Sie können keine Tabelle löschen, auf die mit einer FOREIGN KEY-Einschränkung verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="4403a-115">You cannot drop a table that is referenced by a FOREIGN KEY constraint.</span></span> <span data-ttu-id="4403a-116">Die verweisende FOREIGN KEY-Einschränkung oder die verweisende Tabelle muss zuerst gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="4403a-116">The referencing FOREIGN KEY constraint or the referencing table must first be dropped.</span></span> <span data-ttu-id="4403a-117">Wenn sowohl die verweisende Tabelle als auch die Tabelle mit dem Primärschlüssel in derselben DROP TABLE-Anweisung gelöscht werden, muss die verweisende Tabelle zuerst aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="4403a-117">If both the referencing table and the table that holds the primary key are being dropped in the same DROP TABLE statement, the referencing table must be listed first.</span></span>  
  
-   <span data-ttu-id="4403a-118">Wird eine Tabelle gelöscht, werden alle Bindungen von Regeln und Standardwerten zur Tabelle entfernt, und alle der Tabelle zugeordneten Einschränkungen und Trigger werden automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="4403a-118">When a table is dropped, rules or defaults on the table lose their binding, and any constraints or triggers associated with the table are automatically dropped.</span></span> <span data-ttu-id="4403a-119">Wenn Sie die Tabelle neu erstellen, müssen Sie auch die entsprechenden Regeln und Standardwerte neu binden, die Trigger neu erstellen und alle erforderlichen Einschränkungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4403a-119">If you re-create a table, you must rebind the appropriate rules and defaults, re-create any triggers, and add all required constraints.</span></span>  
  
-   <span data-ttu-id="4403a-120">Wenn Sie eine Tabelle löschen, die eine `varbinary (max)`-Spalte mit dem FILESTREAM-Attribut enthält, werden die im Dateisystem gespeicherten Daten nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="4403a-120">If you drop a table that contains a `varbinary (max)` column with the FILESTREAM attribute, any data stored in the file system will not be removed.</span></span>  
  
-   <span data-ttu-id="4403a-121">DROP TABLE und CREATE TABLE dürfen nicht in der gleichen Tabelle im gleichen Batch ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4403a-121">DROP TABLE and CREATE TABLE should not be executed on the same table in the same batch.</span></span> <span data-ttu-id="4403a-122">Andernfalls tritt möglicherweise ein unerwarteter Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="4403a-122">Otherwise an unexpected error may occur.</span></span>  
  
-   <span data-ttu-id="4403a-123">Jede Sicht oder gespeicherte Prozedur, die auf die gelöschte Tabelle verweist, muss explizit gelöscht oder bearbeitet werden,, um den Verweis auf die Tabelle zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="4403a-123">Any view or stored procedure that references the dropped table must be explicitly deleted or modified to remove the reference to the table.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4403a-124">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4403a-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4403a-125">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4403a-125">Permissions</span></span>  
 <span data-ttu-id="4403a-126">Erfordert die ALTER-Berechtigung für das Schema, zu dem die Tabelle gehört, die CONTROL-Berechtigung für die Tabelle oder die Mitgliedschaft in der festen Datenbankrolle **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="4403a-126">Requires ALTER permission on the schema to which the table belongs, CONTROL permission on the table, or membership in the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4403a-127">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4403a-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-table-from-the-database"></a><span data-ttu-id="4403a-128">So entfernen Sie eine Tabelle aus der Datenbank</span><span class="sxs-lookup"><span data-stu-id="4403a-128">To delete a table from the database</span></span>  
  
1.  <span data-ttu-id="4403a-129">Wählen Sie im Objekt-Explorer die zu löschende Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="4403a-129">In Object Explorer, select the table you want to delete.</span></span>  
  
2.  <span data-ttu-id="4403a-130">Klicken Sie mit der rechten Maustaste auf die Tabelle, und wählen Sie im Kontextmenü die Option **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="4403a-130">Right-click the table and choose **Delete** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="4403a-131">In einem Meldungsfeld werden Sie zum Bestätigen des Löschvorgangs aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="4403a-131">A message box prompts you to confirm the deletion.</span></span> <span data-ttu-id="4403a-132">Klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="4403a-132">Click **Yes**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4403a-133">Beim Löschen einer Tabelle werden automatisch alle Beziehungen zu der Tabelle entfernt.</span><span class="sxs-lookup"><span data-stu-id="4403a-133">Deleting a table automatically removes any relationships to it.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4403a-134">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4403a-134">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-table-in-query-editor"></a><span data-ttu-id="4403a-135">So löschen Sie eine Tabelle im Abfrage-Editor</span><span class="sxs-lookup"><span data-stu-id="4403a-135">To delete a table in Query Editor</span></span>  
  
1.  <span data-ttu-id="4403a-136">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="4403a-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4403a-137">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="4403a-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4403a-138">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="4403a-138">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    DROP TABLE dbo.PurchaseOrderDetail;  
  
    ```  
  
 <span data-ttu-id="4403a-139">Weitere Informationen finden Sie unter [DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4403a-139">For more information, see [DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql)</span></span>  
  
  
