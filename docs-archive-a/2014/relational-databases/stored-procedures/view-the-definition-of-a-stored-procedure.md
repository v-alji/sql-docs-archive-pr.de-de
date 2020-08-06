---
title: Anzeigen der Definition einer gespeicherten Prozedur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], viewing
- definition of stored procedure
- viewing stored procedures
- displaying stored procedures
ms.assetid: 93318587-a0c5-4788-946f-3b5dc8372ea9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4da455d38f984b08ee1f396f26cd4cc85411be92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617878"
---
# <a name="view-the-definition-of-a-stored-procedure"></a><span data-ttu-id="9b655-102">Anzeigen der Definition einer gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="9b655-102">View the Definition of a Stored Procedure</span></span>
    
##  <a name="you-can-view-the-definition-of-a-stored-procedure-in-ssmanstudiofull-using-object-explorer-menu-options-or-in-the-query-editor-using-tsql-this-topic-describes-how-to-view-the-definition-of-procedure-in-object-explorer-and-by-using-a-system-stored-procedure-system-function-and-object-catalog-view-in-the-query-editor"></a><a name="Top"></a> <span data-ttu-id="9b655-103">Sie können die Definition einer gespeicherten Prozedur in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] mit Objekt-Explorer-Menüoptionen oder im Abfrage-Editor mit [!INCLUDE[tsql](../../includes/tsql-md.md)]anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9b655-103">You can view the definition of a stored procedure in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] using Object Explorer menu options or in the Query Editor using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="9b655-104">In diesem Thema wird beschrieben, wie die Definition der Prozedur im Objekt-Explorer und mit einer gespeicherten Systemprozedur, Systemfunktion und der Objektkatalogsicht im Abfrage-Editor angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9b655-104">This topic describes how to view the definition of procedure in Object Explorer and by using a system stored procedure, system function, and object catalog view in the Query Editor.</span></span>  
  
-   <span data-ttu-id="9b655-105">**Vorbereitungen:**  [Sicherheit](#Security)</span><span class="sxs-lookup"><span data-stu-id="9b655-105">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="9b655-106">**Anzeigen der Definition einer Prozedur mit:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="9b655-106">**To view the definition of a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9b655-107">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="9b655-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9b655-108">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="9b655-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9b655-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9b655-109">Permissions</span></span>  
 <span data-ttu-id="9b655-110">Gespeicherte Systemprozedur: `sp_helptext`</span><span class="sxs-lookup"><span data-stu-id="9b655-110">System Stored Procedure: `sp_helptext`</span></span>  
 <span data-ttu-id="9b655-111">Erfordert die Mitgliedschaft in der **public** -Rolle.</span><span class="sxs-lookup"><span data-stu-id="9b655-111">Requires membership in the **public** role.</span></span> <span data-ttu-id="9b655-112">Definitionen von Systemobjekten sind öffentlich sichtbar.</span><span class="sxs-lookup"><span data-stu-id="9b655-112">System object definitions are publicly visible.</span></span> <span data-ttu-id="9b655-113">Die Definition von Benutzerobjekten ist für den Objektbesitzer sichtbar oder für Berechtigte, die über eine der folgenden Berechtigungen verfügen: ALTER, CONTROL, TAKE OWNERSHIP oder VIEW DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="9b655-113">The definition of user objects is visible to the object owner or grantees that have any one of the following permissions: ALTER, CONTROL, TAKE OWNERSHIP, or VIEW DEFINITION.</span></span>  
  
 <span data-ttu-id="9b655-114">Systemfunktion: `OBJECT_DEFINITION`</span><span class="sxs-lookup"><span data-stu-id="9b655-114">System Function: `OBJECT_DEFINITION`</span></span>  
 <span data-ttu-id="9b655-115">Definitionen von Systemobjekten sind öffentlich sichtbar.</span><span class="sxs-lookup"><span data-stu-id="9b655-115">System object definitions are publicly visible.</span></span> <span data-ttu-id="9b655-116">Die Definition von Benutzerobjekten ist für den Objektbesitzer sichtbar oder für Berechtigte, die über eine der folgenden Berechtigungen verfügen: ALTER, CONTROL, TAKE OWNERSHIP oder VIEW DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="9b655-116">The definition of user objects is visible to the object owner or grantees that have any one of the following permissions: ALTER, CONTROL, TAKE OWNERSHIP, or VIEW DEFINITION.</span></span> <span data-ttu-id="9b655-117">Über diese Berechtigungen verfügen implizit Mitglieder der festen Datenbankrollen **db_owner**, **db_ddladmin**und **db_securityadmin** .</span><span class="sxs-lookup"><span data-stu-id="9b655-117">These permissions are implicitly held by members of the **db_owner**, **db_ddladmin**, and **db_securityadmin** fixed database roles.</span></span>  
  
 <span data-ttu-id="9b655-118">Objektkatalogsicht: `sys.sql_modules`</span><span class="sxs-lookup"><span data-stu-id="9b655-118">Object Catalog View: `sys.sql_modules`</span></span>  
 <span data-ttu-id="9b655-119">Die Sichtbarkeit der Metadaten in Katalogsichten ist auf sicherungsfähige Elemente eingeschränkt, bei denen der Benutzer entweder der Besitzer ist oder für die dem Benutzer eine Berechtigung erteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="9b655-119">The visibility of the metadata in catalog views is limited to securables that a user either owns or on which the user has been granted some permission.</span></span> <span data-ttu-id="9b655-120">Weitere Informationen finden Sie unter [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="9b655-120">For more information, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
##  <a name="how-to-view-the-definition-of-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="9b655-121">Anzeigen der Definition einer gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="9b655-121">How to View the Definition of a Stored Procedure</span></span>  
 <span data-ttu-id="9b655-122">Sie können eine der folgenden Anwendungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="9b655-122">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="9b655-123">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9b655-123">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="9b655-124">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9b655-124">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9b655-125">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9b655-125">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="9b655-126">**So zeigen Sie die Definition einer Prozedur im Objekt-Explorer an**</span><span class="sxs-lookup"><span data-stu-id="9b655-126">**To view the definition a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="9b655-127">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="9b655-127">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="9b655-128">Erweitern Sie **Datenbanken**, erweitern Sie die Datenbank, zu der die Prozedur gehört, und erweitern Sie dann **Programmierbarkeit**.</span><span class="sxs-lookup"><span data-stu-id="9b655-128">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="9b655-129">Erweitern Sie **Gespeicherte Prozeduren**, klicken Sie mit der rechten Maustaste auf die Prozedur und anschließend auf **Skript für gespeicherte Prozedur als**, und klicken Sie dann auf eine der folgenden Optionen: **Erstellen in**, **Ändern in** oder **Löschen und erstellen in**.</span><span class="sxs-lookup"><span data-stu-id="9b655-129">Expand **Stored Procedures**, right-click the procedure and then click **Script Stored Procedure as**, and then click one of the following: **Create To**, **Alter To**, or **Drop and Create To**.</span></span>  
  
4.  <span data-ttu-id="9b655-130">Wählen Sie **Neues Abfrage-Editor-Fenster** aus.</span><span class="sxs-lookup"><span data-stu-id="9b655-130">Select **New Query Editor Window**.</span></span> <span data-ttu-id="9b655-131">Daraufhin wird die Prozedurdefinition angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9b655-131">This will display the procedure definition.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9b655-132">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9b655-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="9b655-133">**So zeigen Sie die Definition einer Prozedur im Abfrage-Editor an**</span><span class="sxs-lookup"><span data-stu-id="9b655-133">**To view the definition of a procedure in Query Editor**</span></span>  
  
 <span data-ttu-id="9b655-134">Gespeicherte Systemprozedur: `sp_helptext`</span><span class="sxs-lookup"><span data-stu-id="9b655-134">System Stored Procedure: `sp_helptext`</span></span>  
 1.  <span data-ttu-id="9b655-135">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="9b655-135">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9b655-136">Klicken Sie auf der Symbolleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="9b655-136">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9b655-137">Geben Sie im Abfragefenster die folgende Anweisung ein, die die gespeicherte Systemprozedur `sp_helptext` verwendet.</span><span class="sxs-lookup"><span data-stu-id="9b655-137">In the query window, enter the following statement that uses the `sp_helptext` system stored procedure.</span></span> <span data-ttu-id="9b655-138">Ändern Sie den Datenbanknamen und den Namen der gespeicherten Prozedur so, dass diese auf die gewünschte Datenbank und die gespeicherte Prozedur verweisen.</span><span class="sxs-lookup"><span data-stu-id="9b655-138">Change the database name and stored procedure name to reference the database and stored procedure that you want.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_helptext N'AdventureWorks2012.dbo.uspLogError';  
    ```  
  
 <span data-ttu-id="9b655-139">Systemfunktion: `OBJECT_DEFINITION`</span><span class="sxs-lookup"><span data-stu-id="9b655-139">System Function: `OBJECT_DEFINITION`</span></span>  
 1.  <span data-ttu-id="9b655-140">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="9b655-140">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9b655-141">Klicken Sie auf der Symbolleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="9b655-141">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9b655-142">Geben Sie im Abfragefenster die folgenden Anweisungen ein, die die `OBJECT_DEFINITION`-Systemfunktion verwenden:</span><span class="sxs-lookup"><span data-stu-id="9b655-142">In the query window, enter the following statements that use the `OBJECT_DEFINITION` system function.</span></span> <span data-ttu-id="9b655-143">Ändern Sie den Datenbanknamen und den Namen der gespeicherten Prozedur so, dass diese auf die gewünschte Datenbank und die gespeicherte Prozedur verweisen.</span><span class="sxs-lookup"><span data-stu-id="9b655-143">Change the database name and stored procedure name to reference the database and stored procedure that you want.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT OBJECT_DEFINITION (OBJECT_ID(N'AdventureWorks2012.dbo.uspLogError'));  
    ```  
  
 <span data-ttu-id="9b655-144">Objektkatalogsicht: `sys.sql_modules`</span><span class="sxs-lookup"><span data-stu-id="9b655-144">Object Catalog View: `sys.sql_modules`</span></span>  
 1.  <span data-ttu-id="9b655-145">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="9b655-145">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9b655-146">Klicken Sie auf der Symbolleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="9b655-146">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9b655-147">Geben Sie im Abfragefenster die folgenden Anweisungen ein, die die `sys.sql_modules`-Katalogsicht verwenden:</span><span class="sxs-lookup"><span data-stu-id="9b655-147">In the query window, enter the following statements that use the `sys.sql_modules` catalog view.</span></span> <span data-ttu-id="9b655-148">Ändern Sie den Datenbanknamen und den Namen der gespeicherten Prozedur so, dass diese auf die gewünschte Datenbank und die gespeicherte Prozedur verweisen.</span><span class="sxs-lookup"><span data-stu-id="9b655-148">Change the database name and stored procedure name to reference the database and stored procedure that you want.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT definition  
    FROM sys.sql_modules  
    WHERE object_id = (OBJECT_ID(N'AdventureWorks2012.dbo.uspLogError'));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9b655-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9b655-149">See Also</span></span>  
 <span data-ttu-id="9b655-150">[Erstellen einer gespeicherten Prozedur](create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="9b655-150">[Create a Stored Procedure](create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="9b655-151">[Ändern einer gespeicherten Prozedur](modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="9b655-151">[Modify a Stored Procedure](modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="9b655-152">[Löschen einer gespeicherten Prozedur](delete-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="9b655-152">[Delete a Stored Procedure](delete-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="9b655-153">[Umbenennen einer gespeicherten Prozedur](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="9b655-153">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="9b655-154">[OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b655-154">[OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql) </span></span>  
 <span data-ttu-id="9b655-155">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b655-155">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="9b655-156">[sp_helptext &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b655-156">[sp_helptext &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql) </span></span>  
 [<span data-ttu-id="9b655-157">OBJECT_ID &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9b655-157">OBJECT_ID &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/object-id-transact-sql)  
  
  
