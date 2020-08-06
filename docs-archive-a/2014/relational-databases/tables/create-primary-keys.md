---
title: Erstellen von Primärschlüsseln | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- primary keys [SQL Server], creating
ms.assetid: 85c623ca-4656-4d70-a9db-ee4d897cd214
author: stevestein
ms.author: sstein
ms.openlocfilehash: c515ef8f978b41225ff45e87646b0aa7a9706a34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630597"
---
# <a name="create-primary-keys"></a><span data-ttu-id="5bcd6-102">Erstellen von Primärschlüsseln</span><span class="sxs-lookup"><span data-stu-id="5bcd6-102">Create Primary Keys</span></span>
  <span data-ttu-id="5bcd6-103">Sie können mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] einen Primärschlüssel in [!INCLUDE[tsql](../../includes/tsql-md.md)]definieren.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-103">You can define a primary key in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5bcd6-104">Beim Erstellen eines Primärschlüssels wird automatisch ein zugehöriger eindeutiger, gruppierter oder nicht gruppierter Index erstellt.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-104">Creating a primary key automatically creates a corresponding unique, clustered or nonclustered index.</span></span>  
  
 <span data-ttu-id="5bcd6-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="5bcd6-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5bcd6-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="5bcd6-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5bcd6-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="5bcd6-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5bcd6-108">Security</span><span class="sxs-lookup"><span data-stu-id="5bcd6-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5bcd6-109">**So erstellen Sie einen Primärschlüssel mit:**</span><span class="sxs-lookup"><span data-stu-id="5bcd6-109">**To create a primary key, using:**</span></span>  
  
     [<span data-ttu-id="5bcd6-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5bcd6-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5bcd6-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5bcd6-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5bcd6-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="5bcd6-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5bcd6-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="5bcd6-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5bcd6-114">Eine Tabelle kann nur eine PRIMARY KEY-Einschränkung enthalten.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-114">A table can contain only one PRIMARY KEY constraint.</span></span>  
  
-   <span data-ttu-id="5bcd6-115">Alle Spalten, für die eine PRIMARY KEY-Einschränkung definiert wurde, müssen als NOT NULL definiert sein.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-115">All columns defined within a PRIMARY KEY constraint must be defined as NOT NULL.</span></span> <span data-ttu-id="5bcd6-116">Falls weder NULL noch NOT NULL angegeben ist, wird für alle Spalten, auf die eine PRIMARY KEY-Einschränkung angewendet wird, die NULL-Zulässigkeit auf NOT NULL festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-116">If nullability is not specified, all columns participating in a PRIMARY KEY constraint have their nullability set to NOT NULL.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5bcd6-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5bcd6-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5bcd6-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="5bcd6-118">Permissions</span></span>  
 <span data-ttu-id="5bcd6-119">Zum Erstellen einer neuen Tabelle mit einem primären Schlüssel sind die CREATE TABLE-Berechtigung für die Datenbank und die ALTER-Berechtigung für das Schema erforderlich, in dem die Tabelle erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-119">Creating a new table with a primary key requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span>  
  
 <span data-ttu-id="5bcd6-120">Zum Erstellen eines Primärschlüssels für eine vorhandene Tabelle ist die ALTER-Berechtigung für die Tabelle erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-120">Creating a primary key in an existing table requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5bcd6-121">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5bcd6-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-primary-key"></a><span data-ttu-id="5bcd6-122">So erstellen Sie einen Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="5bcd6-122">To create a primary key</span></span>  
  
1.  <span data-ttu-id="5bcd6-123">Klicken Sie in Objekt-Explorer mit der rechten Maustaste auf die Tabelle, der Sie eine Unique-Einschränkung hinzufügen möchten, und klicken Sie dann auf **entwerfen**.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-123">In Object Explorer, right-click the table to which you want to add a unique constraint, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="5bcd6-124">Klicken Sie im **Tabellen-Designer**auf den Zeilenselektor für die Datenbankspalte, die Sie als Primärschlüssel definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-124">In **Table Designer**, click the row selector for the database column you want to define as the primary key.</span></span> <span data-ttu-id="5bcd6-125">Wenn Sie mehrere Spalten auswählen möchten, halten Sie STRG gedrückt, und klicken Sie auf die Zeilenselektoren für die anderen Spalten.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-125">If you want to select multiple columns, hold down the CTRL key while you click the row selectors for the other columns.</span></span>  
  
3.  <span data-ttu-id="5bcd6-126">Klicken Sie mit der rechten Maustaste auf den Zeilenselektor für die Spalte, und wählen Sie **Primärschlüssel festlegen**aus.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-126">Right-click the row selector for the column and select **Set Primary Key**.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="5bcd6-127">Wenn Sie den Primärschlüssel neu definieren möchten, müssen Sie zunächst alle Beziehungen mit dem vorhandenen Primärschlüssel löschen, da erst dann der neue Primärschlüssel erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-127">If you want to redefine the primary key, any relationships to the existing primary key must be deleted before the new primary key can be created.</span></span> <span data-ttu-id="5bcd6-128">In einer Warnmeldung werden Sie informiert, dass vorhandene Beziehungen bei diesem Prozess automatisch gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-128">A message will warn you that existing relationships will be automatically deleted as part of this process.</span></span>  
  
 <span data-ttu-id="5bcd6-129">Sie können eine Primärschlüsselspalte am Primärschlüsselsymbol erkennen, das im Zeilenselektor angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-129">A primary key column is identified by a primary key symbol in its row selector.</span></span>  
  
 <span data-ttu-id="5bcd6-130">Wenn ein Primärschlüssel aus mehreren Spalten besteht, können Werte in einer Spalte doppelt vorkommen. Die Kombination der Werte in allen Spalten des Primärschlüssels muss jedoch eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-130">If a primary key consists of more than one column, duplicate values are allowed in one column, but each combination of values from all the columns in the primary key must be unique.</span></span>  
  
 <span data-ttu-id="5bcd6-131">Wenn Sie einen Verbundschlüssel definieren, stimmt die Spaltenreihenfolge im Primärschlüssel mit der Spaltenreihenfolge überein, die in der Tabelle angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-131">If you define a compound key, the order of columns in the primary key matches the order of columns as shown in the table.</span></span> <span data-ttu-id="5bcd6-132">Sie können die Spaltenreihenfolge jedoch nach Erstellen des Primärschlüssels ändern.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-132">However, you can change the order of columns after the primary key is created.</span></span> <span data-ttu-id="5bcd6-133">Weitere Informationen finden Sie unter [Ändern von Primärschlüsseln](modify-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="5bcd6-133">For more information, see [Modify Primary Keys](modify-primary-keys.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5bcd6-134">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5bcd6-134">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-primary-key-in-an-existing-table"></a><span data-ttu-id="5bcd6-135">So erstellen Sie einen Primärschlüssel in einer vorhandenen Tabelle</span><span class="sxs-lookup"><span data-stu-id="5bcd6-135">To create a primary key in an existing table</span></span>  
  
1.  <span data-ttu-id="5bcd6-136">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5bcd6-137">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5bcd6-138">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5bcd6-139">Im Beispiel wird ein Primärschlüssel für die Spalte `TransactionID`erstellt.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-139">The example creates a primary key on the column `TransactionID`.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Production.TransactionHistoryArchive   
    ADD CONSTRAINT PK_TransactionHistoryArchive_TransactionID PRIMARY KEY CLUSTERED (TransactionID);  
    GO  
  
    ```  
  
#### <a name="to-create-a-primary-key-in-a-new-table"></a><span data-ttu-id="5bcd6-140">So erstellen Sie einen Primärschlüssel in einer neuen Tabelle</span><span class="sxs-lookup"><span data-stu-id="5bcd6-140">To create a primary key in a new table</span></span>  
  
1.  <span data-ttu-id="5bcd6-141">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5bcd6-142">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-142">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5bcd6-143">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5bcd6-144">Im Beispiel wird eine Tabelle erstellt und ein Primärschlüssel für die Spalte `TransactionID`definiert.</span><span class="sxs-lookup"><span data-stu-id="5bcd6-144">The example creates a table and defines a primary key on the column `TransactionID`.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE Production.TransactionHistoryArchive1  
    (  
       TransactionID int NOT NULL,  
       CONSTRAINT PK_TransactionHistoryArchive_TransactionID PRIMARY KEY CLUSTERED (TransactionID)  
    );  
    GO  
  
    ```  
  
     <span data-ttu-id="5bcd6-145">Weitere Informationen finden Sie unter [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) und [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5bcd6-145">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql), and [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
