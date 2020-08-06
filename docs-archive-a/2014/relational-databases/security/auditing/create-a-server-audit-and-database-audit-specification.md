---
title: Erstellen einer Server- und Datenbank-Überwachungsspezifikation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqlaudit.dbaudit.general.f1
helpviewer_keywords:
- audits [SQL Server], creating database specification
- database audit [SQL Server]
ms.assetid: 26ee85de-6e97-4318-b526-900924d96e62
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 0cad01eae45d534f0f74911ce8f57827858cc920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700965"
---
# <a name="create-a-server-audit-and-database-audit-specification"></a><span data-ttu-id="4b903-102">Erstellen einer Server- und Datenbank-Überwachungsspezifikation</span><span class="sxs-lookup"><span data-stu-id="4b903-102">Create a Server Audit and Database Audit Specification</span></span>
  <span data-ttu-id="4b903-103">In diesem Thema wird beschrieben, wie eine Serverüberwachung und Datenbanküberwachungsspezifikation in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../../includes/tsql-md.md)]erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="4b903-103">This topic describes how to create a server audit and database audit specification in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4b903-104">Bei der*Überwachung* einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] oder einer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Datenbank werden Ereignisse im System verfolgt und protokolliert.</span><span class="sxs-lookup"><span data-stu-id="4b903-104">*Auditing* an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database involves tracking and logging events that occur on the system.</span></span> <span data-ttu-id="4b903-105">Das *SQL Server Audit* -Objekt listet eine einzelne Instanz an Aktionen oder Aktionsgruppen auf Server- oder Datenbankebene auf, die überwacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="4b903-105">The *SQL Server Audit* object collects a single instance of server- or database-level actions and groups of actions to monitor.</span></span> <span data-ttu-id="4b903-106">Die Überwachung wird auf [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Instanzebene ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4b903-106">The audit is at the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance level.</span></span> <span data-ttu-id="4b903-107">Es können mehrere Überwachungen pro [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Instanz vorliegen.</span><span class="sxs-lookup"><span data-stu-id="4b903-107">You can have multiple audits per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="4b903-108">Das Objekt für die *Überwachungsspezifikation auf Datenbankebene* gehört ebenfalls zu einer Überwachung.</span><span class="sxs-lookup"><span data-stu-id="4b903-108">The *Database-Level Audit Specification* object belongs to an audit.</span></span> <span data-ttu-id="4b903-109">Sie können eine Datenbank-Überwachungsspezifikation pro SQL Server-Datenbank und pro Überwachung erstellen.</span><span class="sxs-lookup"><span data-stu-id="4b903-109">You can create one database audit specification per SQL Server database per audit.</span></span> <span data-ttu-id="4b903-110">Weitere Informationen finden Sie unter [SQL Server Audit &#40;Datenbank-Engine&#41;](sql-server-audit-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="4b903-110">For more information, see [SQL Server Audit &#40;Database Engine&#41;](sql-server-audit-database-engine.md).</span></span>  
  
 <span data-ttu-id="4b903-111">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="4b903-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4b903-112">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="4b903-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4b903-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4b903-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4b903-114">Security</span><span class="sxs-lookup"><span data-stu-id="4b903-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4b903-115">**So erstellen Sie eine Server- und Datenbank-Überwachungsspezifikation mit**</span><span class="sxs-lookup"><span data-stu-id="4b903-115">**To create a server audit and database audit specification, using:**</span></span>  
  
     [<span data-ttu-id="4b903-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4b903-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4b903-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4b903-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4b903-118">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="4b903-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4b903-119">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4b903-119">Limitations and Restrictions</span></span>  
 <span data-ttu-id="4b903-120">Datenbank-Überwachungsspezifikationen sind nicht sicherungsfähige Objekte, die sich in einer gegebenen Datenbank befinden.</span><span class="sxs-lookup"><span data-stu-id="4b903-120">Database audit specifications are non-securable objects that reside in a given database.</span></span> <span data-ttu-id="4b903-121">Wenn eine Datenbank-Überwachungsspezifikation erstellt wird, befindet sich diese in einem deaktivierten Zustand.</span><span class="sxs-lookup"><span data-stu-id="4b903-121">When a database audit specification is created, it is in a disabled state.</span></span>  
  
 <span data-ttu-id="4b903-122">Wenn Sie in einer Benutzerdatenbank eine Datenbank-Überwachungsspezifikation erstellen oder ändern, sollten Sie keine Überwachungsaktionen für Serverbereichsobjekte einschließen, z. B. die Systemsichten.</span><span class="sxs-lookup"><span data-stu-id="4b903-122">When you are creating or modifying a database audit specification in a user database, do not include audit actions on server-scope objects, such as the system views.</span></span> <span data-ttu-id="4b903-123">Wenn Objekte mit Serverbereich eingeschlossen sind, wird die Überwachung zwar erstellt.</span><span class="sxs-lookup"><span data-stu-id="4b903-123">If server-scoped objects are included, the audit will be created.</span></span> <span data-ttu-id="4b903-124">Die Objekte mit Serverbereich sind jedoch nicht enthalten, und es wird kein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4b903-124">However, the server-scoped objects will not be included, and no error will be returned.</span></span> <span data-ttu-id="4b903-125">Verwenden Sie eine Datenbank-Überwachungsspezifikation in der master-Datenbank, um Objekte mit Serverbereich zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="4b903-125">To audit server-scope objects, use a database audit specification in the master database.</span></span>  
  
 <span data-ttu-id="4b903-126">Die Datenbank-Überwachungsspezifikationen befinden sich in der Datenbank, in der sie erstellt werden, mit Ausnahme der Systemdatenbank `tempdb`.</span><span class="sxs-lookup"><span data-stu-id="4b903-126">Database audit specifications reside in the database where they are created, with the exception of the `tempdb` system database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4b903-127">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4b903-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4b903-128">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4b903-128">Permissions</span></span>  
  
-   <span data-ttu-id="4b903-129">Benutzer mit der ALTER ANY DATABASE AUDIT-Berechtigung können Datenbank-Überwachungsspezifikationen erstellen und sie an eine beliebige Überwachung binden.</span><span class="sxs-lookup"><span data-stu-id="4b903-129">Users with the ALTER ANY DATABASE AUDIT permission can create database audit specifications and bind them to any audit.</span></span>  
  
-   <span data-ttu-id="4b903-130">Nachdem eine Datenbank-Überwachungsspezifikation erstellt wurde, kann diese von Prinzipalen mit den Berechtigungen CONTROL SERVER und ALTER ANY DATABASE AUDIT oder von Prinzipalen mit Zugriff auf das sysadmin-Konto angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4b903-130">After a database audit specification is created, it can be viewed by principals with the CONTROL SERVER,  ALTER ANY DATABASE AUDIT permissions, or the sysadmin account.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4b903-131">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4b903-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="4b903-132">So erstellen Sie eine Serverüberwachung</span><span class="sxs-lookup"><span data-stu-id="4b903-132">To create a server audit</span></span>  
  
1.  <span data-ttu-id="4b903-133">Erweitern Sie im Objekt-Explorer den Ordner **Sicherheit** .</span><span class="sxs-lookup"><span data-stu-id="4b903-133">In Object Explorer, expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="4b903-134">Klicken Sie **mit der rechten** Maustaste auf den Ordner Überwachungen, und wählen Sie neue über **Prüfung**aus. Weitere Informationen finden Sie unter [Create a Server Audit and Server Audit Specification](create-a-server-audit-and-server-audit-specification.md).</span><span class="sxs-lookup"><span data-stu-id="4b903-134">Right-click the **Audits** folder and select **New Audit...**. For more information, see [Create a Server Audit and Server Audit Specification](create-a-server-audit-and-server-audit-specification.md).</span></span>  
  
3.  <span data-ttu-id="4b903-135">Nachdem Sie alle Optionen ausgewählt haben, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4b903-135">When you are finished selecting options, click **OK**.</span></span>  
  
#### <a name="to-create-a-database-level-audit-specification"></a><span data-ttu-id="4b903-136">So erstellen Sie eine Überwachungsspezifikation auf Datenbankebene</span><span class="sxs-lookup"><span data-stu-id="4b903-136">To create a database-level audit specification</span></span>  
  
1.  <span data-ttu-id="4b903-137">Erweitern Sie im Objekt-Explorer die Datenbank, in der Sie eine Überwachungsspezifikation erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="4b903-137">In Object Explorer, expand the database where you want to create an audit specification.</span></span>  
  
2.  <span data-ttu-id="4b903-138">Erweitern Sie den Ordner **Sicherheit** .</span><span class="sxs-lookup"><span data-stu-id="4b903-138">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="4b903-139">Klicken Sie mit der rechten Maustaste auf den Ordner Datenbank-Überwachungs **Spezifikationen** , und wählen Sie **neue Datenbank**-Überwachungs Spezifikation aus.</span><span class="sxs-lookup"><span data-stu-id="4b903-139">Right-click the **Database Audit Specifications** folder and select **New Database Audit Specification...**.</span></span>  
  
     <span data-ttu-id="4b903-140">Die folgenden Optionen sind im Dialogfeld **Datenbank-Überwachungsspezifikation erstellen** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4b903-140">The following options are available on the **Create Database Audit Specification** dialog box.</span></span>  
  
     <span data-ttu-id="4b903-141">**Name**</span><span class="sxs-lookup"><span data-stu-id="4b903-141">**Name**</span></span>  
     <span data-ttu-id="4b903-142">Der Name der Datenbank-Überwachungsspezifikation.</span><span class="sxs-lookup"><span data-stu-id="4b903-142">The name of the database audit specification.</span></span> <span data-ttu-id="4b903-143">Er wird automatisch generiert, wenn Sie eine neue Serverüberwachungsspezifikation erstellen, er kann jedoch bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="4b903-143">This is generated automatically when you create a new server audit specification but is editable.</span></span>  
  
     <span data-ttu-id="4b903-144">**Überwachung**</span><span class="sxs-lookup"><span data-stu-id="4b903-144">**Audit**</span></span>  
     <span data-ttu-id="4b903-145">Der Name einer vorhandenen Datenbanküberwachung.</span><span class="sxs-lookup"><span data-stu-id="4b903-145">The name of an existing database audit.</span></span> <span data-ttu-id="4b903-146">Geben Sie den Namen der Überwachung ein, oder wählen Sie ihn aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="4b903-146">Either type in the name of the audit or select it from the list.</span></span>  
  
     <span data-ttu-id="4b903-147">**Überwachungsaktionstyp**</span><span class="sxs-lookup"><span data-stu-id="4b903-147">**Audit Action Type**</span></span>  
     <span data-ttu-id="4b903-148">Gibt die aufzuzeichnenden Überwachungsaktionsgruppen auf Datenbankebene und Überwachungsaktionen an.</span><span class="sxs-lookup"><span data-stu-id="4b903-148">Specifies the database-level audit action groups and audit actions to capture.</span></span> <span data-ttu-id="4b903-149">Eine Liste der Überwachungsaktionsgruppen auf Datenbankebene und Überwachungsaktionen sowie eine Beschreibung der darin enthaltenen Ereignisse finden Sie unter [SQL Server Audit-Aktionsgruppen und -Aktionen](sql-server-audit-action-groups-and-actions.md).</span><span class="sxs-lookup"><span data-stu-id="4b903-149">For the list of database-level audit action groups and audit actions and a description of the events they contain, see [SQL Server Audit Action Groups and Actions](sql-server-audit-action-groups-and-actions.md).</span></span>  
  
     <span data-ttu-id="4b903-150">**Objektschema**</span><span class="sxs-lookup"><span data-stu-id="4b903-150">**Object Schema**</span></span>  
     <span data-ttu-id="4b903-151">Zeigt das Schema für den angegebenen **Objektnamen**an.</span><span class="sxs-lookup"><span data-stu-id="4b903-151">Displays the schema for the specified **Object Name**.</span></span>  
  
     <span data-ttu-id="4b903-152">**Objektnamen**</span><span class="sxs-lookup"><span data-stu-id="4b903-152">**Object Name**</span></span>  
     <span data-ttu-id="4b903-153">Der Name des zu überwachenden Objekts.</span><span class="sxs-lookup"><span data-stu-id="4b903-153">The name of the object to audit.</span></span> <span data-ttu-id="4b903-154">Das Objekt ist nur für Überwachungsaktionen verfügbar, es gilt nicht für Überwachungsgruppen.</span><span class="sxs-lookup"><span data-stu-id="4b903-154">This is only available for audit actions; it does not apply to audit groups.</span></span>  
  
     <span data-ttu-id="4b903-155">**Auslassungspunkte (…)**</span><span class="sxs-lookup"><span data-stu-id="4b903-155">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="4b903-156">Öffnet das Dialogfeld **Objekte auswählen** , in dem Sie anhand des angegebenen **Überwachungsaktionstyps**nach einem verfügbaren Objekt suchen und es auswählen können.</span><span class="sxs-lookup"><span data-stu-id="4b903-156">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Audit Action Type**.</span></span>  
  
     <span data-ttu-id="4b903-157">**Prinzipalname**</span><span class="sxs-lookup"><span data-stu-id="4b903-157">**Principal Name**</span></span>  
     <span data-ttu-id="4b903-158">Das Konto, anhand dessen die Überwachung für das zu überwachende Objekt gefiltert wird.</span><span class="sxs-lookup"><span data-stu-id="4b903-158">The account to filter the audit by for the object being audited.</span></span>  
  
     <span data-ttu-id="4b903-159">**Auslassungspunkte (…)**</span><span class="sxs-lookup"><span data-stu-id="4b903-159">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="4b903-160">Öffnet das Dialogfeld **Objekte auswählen** , in dem Sie nach einem verfügbaren Objekt anhand des angegebenen **Objektnamens**suchen und es auswählen können.</span><span class="sxs-lookup"><span data-stu-id="4b903-160">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Object Name**.</span></span>  
  
4.  <span data-ttu-id="4b903-161">Nachdem Sie alle Optionen ausgewählt haben, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4b903-161">When you are finished selecting option, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4b903-162">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4b903-162">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="4b903-163">So erstellen Sie eine Serverüberwachung</span><span class="sxs-lookup"><span data-stu-id="4b903-163">To create a server audit</span></span>  
  
1.  <span data-ttu-id="4b903-164">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="4b903-164">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4b903-165">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="4b903-165">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4b903-166">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="4b903-166">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE master ;  
    GO  
    -- Create the server audit.   
    CREATE SERVER AUDIT Payrole_Security_Audit  
        TO FILE ( FILEPATH =   
    'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA' ) ;   
    GO  
    -- Enable the server audit.   
    ALTER SERVER AUDIT Payrole_Security_Audit   
    WITH (STATE = ON) ;  
    ```  
  
#### <a name="to-create-a-database-level-audit-specification"></a><span data-ttu-id="4b903-167">So erstellen Sie eine Überwachungsspezifikation auf Datenbankebene</span><span class="sxs-lookup"><span data-stu-id="4b903-167">To create a database-level audit specification</span></span>  
  
1.  <span data-ttu-id="4b903-168">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="4b903-168">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4b903-169">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="4b903-169">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4b903-170">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="4b903-170">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4b903-171">Im folgenden Beispiel wird die Serverüberwachung mit dem Namen `Audit_Pay_Tables` , in der die SELECT- und INSERT-Anweisungen des `dbo` -Benutzers überwacht werden, für die `HumanResources.EmployeePayHistory` -Tabelle anhand der obigen Serverüberwachung erstellt.</span><span class="sxs-lookup"><span data-stu-id="4b903-171">The example creates a database audit specification called `Audit_Pay_Tables` that audits SELECT and INSERT statements by the `dbo` user, for the `HumanResources.EmployeePayHistory` table based on the server audit defined above.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;   
    GO  
    -- Create the database audit specification.   
    CREATE DATABASE AUDIT SPECIFICATION Audit_Pay_Tables  
    FOR SERVER AUDIT Payrole_Security_Audit  
    ADD (SELECT , INSERT  
         ON HumanResources.EmployeePayHistory BY dbo )   
    WITH (STATE = ON) ;   
    GO  
  
    ```  
  
 <span data-ttu-id="4b903-172">Weitere Informationen finden Sie unter [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql) und [CREATE DATABASE AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-database-audit-specification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4b903-172">For more information, see [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql) and [CREATE DATABASE AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-database-audit-specification-transact-sql).</span></span>  
  
  
