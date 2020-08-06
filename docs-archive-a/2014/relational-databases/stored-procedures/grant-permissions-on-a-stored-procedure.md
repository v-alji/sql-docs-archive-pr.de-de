---
title: Erteilen von Berechtigungen für eine gespeicherte Prozedur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], permissions
ms.assetid: a7d15816-a788-4099-ad91-dc4b26618299
author: stevestein
ms.author: sstein
ms.openlocfilehash: 23ea130b9d2033128adc99413c053d66936e3ccc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618568"
---
# <a name="grant-permissions-on-a-stored-procedure"></a><span data-ttu-id="10c75-102">Erteilen von Berechtigungen für eine gespeicherte Prozedur</span><span class="sxs-lookup"><span data-stu-id="10c75-102">Grant Permissions on a Stored Procedure</span></span>
  <span data-ttu-id="10c75-103">In diesem Thema wird beschrieben, wie Sie Berechtigungen für eine gespeicherte Prozedur in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]erteilen.</span><span class="sxs-lookup"><span data-stu-id="10c75-103">This topic describes how to grant permissions on a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="10c75-104">Berechtigungen können einem vorhandenen Benutzer, einer Datenbankrolle oder einer Anwendungsrolle in der Datenbank erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="10c75-104">Permissions can be granted to an existing user, database role, or application role in the database.</span></span>  
  
 <span data-ttu-id="10c75-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="10c75-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="10c75-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="10c75-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="10c75-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="10c75-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="10c75-108">Security</span><span class="sxs-lookup"><span data-stu-id="10c75-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="10c75-109">**Erteilen von Berechtigungen für eine gespeicherte Prozedur mit:**</span><span class="sxs-lookup"><span data-stu-id="10c75-109">**To grant permissions on a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="10c75-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="10c75-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="10c75-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="10c75-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="10c75-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="10c75-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="10c75-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="10c75-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="10c75-114">[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] kann nicht verwendet werden, um Berechtigungen für Systemprozeduren oder Systemfunktionen zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="10c75-114">You cannot use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to grant permissions on system procedures or system functions.</span></span> <span data-ttu-id="10c75-115">Verwenden Sie stattdessen [GRANT-Objektberechtigungen](/sql/t-sql/statements/grant-object-permissions-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="10c75-115">Use [GRANT Object Permissions](/sql/t-sql/statements/grant-object-permissions-transact-sql) instead.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="10c75-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="10c75-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="10c75-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="10c75-117">Permissions</span></span>  
 <span data-ttu-id="10c75-118">Der Berechtigende (oder der mit der AS-Option angegebene Prinzipal) benötigt entweder die Berechtigung selbst mit GRANT OPTION oder eine höhere Berechtigung, die die erteilte Berechtigung impliziert.</span><span class="sxs-lookup"><span data-stu-id="10c75-118">The grantor (or the principal specified with the AS option) must have either the permission itself with GRANT OPTION, or a higher permission that implies the permission being granted.</span></span> <span data-ttu-id="10c75-119">Erfordert die ALTER-Berechtigung im Schema, zu der die Prozedur gehört, oder die CONTROL-Berechtigung für die Prozedur.</span><span class="sxs-lookup"><span data-stu-id="10c75-119">Requires ALTER permission on the schema to which the procedure belongs, or CONTROL permission on the procedure.</span></span> <span data-ttu-id="10c75-120">Weitere Informationen finden Sie unter [GRANT (Objektberechtigungen) &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql)erteilen.</span><span class="sxs-lookup"><span data-stu-id="10c75-120">For more information, see [GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="10c75-121">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="10c75-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-grant-permissions-on-a-stored-procedure"></a><span data-ttu-id="10c75-122">So erteilen Sie Berechtigungen für eine gespeicherte Prozedur</span><span class="sxs-lookup"><span data-stu-id="10c75-122">To grant permissions on a stored procedure</span></span>  
  
1.  <span data-ttu-id="10c75-123">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../../includes/ssde-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="10c75-123">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="10c75-124">Erweitern Sie **Datenbanken**, erweitern Sie die Datenbank, zu der die Prozedur gehört, und erweitern Sie dann **Programmierbarkeit**.</span><span class="sxs-lookup"><span data-stu-id="10c75-124">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="10c75-125">Erweitern Sie **Gespeicherte Prozeduren**, klicken Sie mit der rechten Maustaste auf die Prozedur, für die Sie Berechtigungen erteilen möchten, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="10c75-125">Expand **Stored Procedures**, right-click the procedure to grant permissions on, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="10c75-126">Wählen Sie in **Eigenschaften der gespeicherten Prozedur**die Seite **Berechtigungen** aus.</span><span class="sxs-lookup"><span data-stu-id="10c75-126">From **Stored Procedure Properties**, select the **Permissions** page.</span></span>  
  
5.  <span data-ttu-id="10c75-127">Klicken Sie auf **Suchen**, um einem Benutzer, einer Datenbankrolle oder einer Anwendungsrolle Berechtigungen zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="10c75-127">To grant permissions to a user, database role, or application role, click **Search**.</span></span>  
  
6.  <span data-ttu-id="10c75-128">Klicken Sie in **Benutzer oder Rollen auswählen**auf **Objekttypen** , um die gewünschten Benutzer und Rollen hinzuzufügen bzw. zu löschen.</span><span class="sxs-lookup"><span data-stu-id="10c75-128">In **Select Users or Roles**, click **Object Types** to add or clear the users and roles you want.</span></span>  
  
7.  <span data-ttu-id="10c75-129">Klicken Sie auf **Durchsuchen** , um die Liste der Benutzer oder Rollen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="10c75-129">Click **Browse** to display the list of users or roles.</span></span> <span data-ttu-id="10c75-130">Wählen Sie die Benutzer bzw. Rollen aus, denen Berechtigungen gewährt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="10c75-130">Select the users or roles to whom permissions should be granted.</span></span>  
  
8.  <span data-ttu-id="10c75-131">Wählen Sie im Raster **Explizite Berechtigungen** die Berechtigungen aus, die Sie dem angegebenen Benutzer bzw. der angegebenen Rolle erteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="10c75-131">In the **Explicit Permissions** grid, select the permissions to grant to the specified user or role.</span></span> <span data-ttu-id="10c75-132">Eine Beschreibung der Berechtigungen finden Sie unter [Berechtigungen &#40;Datenbank-Engine&#41;](../security/permissions-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="10c75-132">For a description of the permissions, see [Permissions &#40;Database Engine&#41;](../security/permissions-database-engine.md).</span></span>  
  
 <span data-ttu-id="10c75-133">Durch Auswahl von **Erteilen** wird angegeben, dass der Empfänger die angegebene Berechtigung erhält.</span><span class="sxs-lookup"><span data-stu-id="10c75-133">Selecting **Grant** indicates the grantee will be given the specified permission.</span></span> <span data-ttu-id="10c75-134">Durch Auswahl von **Mit Erteilung** wird angegeben, dass der Empfänger außerdem die angegebene Berechtigung anderen Prinzipalen erteilen kann.</span><span class="sxs-lookup"><span data-stu-id="10c75-134">Selecting **Grant With** indicates that the grantee will also be able to grant the specified permission to other principals.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="10c75-135">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="10c75-135">Using Transact-SQL</span></span>  
  
#### <a name="to-grant-permissions-on-a-stored-procedure"></a><span data-ttu-id="10c75-136">So erteilen Sie Berechtigungen für eine gespeicherte Prozedur</span><span class="sxs-lookup"><span data-stu-id="10c75-136">To grant permissions on a stored procedure</span></span>  
  
1.  <span data-ttu-id="10c75-137">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="10c75-137">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="10c75-138">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="10c75-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="10c75-139">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="10c75-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="10c75-140">Im folgenden Beispiel wird die `EXECUTE` -Berechtigung für die gespeicherte Prozedur `HumanResources.uspUpdateEmployeeHireInfo` einer Anwendungsrolle mit dem Namen `Recruiting11`erteilt.</span><span class="sxs-lookup"><span data-stu-id="10c75-140">This example grants `EXECUTE` permission on the stored procedure `HumanResources.uspUpdateEmployeeHireInfo` to an application role named `Recruiting11`.</span></span>  
  
```sql  
USE AdventureWorks2012;   
GRANT EXECUTE ON OBJECT::HumanResources.uspUpdateEmployeeHireInfo  
    TO Recruiting11;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="10c75-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="10c75-141">See Also</span></span>  
 <span data-ttu-id="10c75-142">[sys.fn_builtin_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="10c75-142">[sys.fn_builtin_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) </span></span>  
 <span data-ttu-id="10c75-143">[GRANT (Objektberechtigungen) &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="10c75-143">[GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span></span>  
 <span data-ttu-id="10c75-144">[Erstellen einer gespeicherten Prozedur](../stored-procedures/create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="10c75-144">[Create a Stored Procedure](../stored-procedures/create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="10c75-145">[Ändern einer gespeicherten Prozedur](modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="10c75-145">[Modify a Stored Procedure](modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="10c75-146">[Löschen einer gespeicherten Prozedur](../stored-procedures/delete-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="10c75-146">[Delete a Stored Procedure](../stored-procedures/delete-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="10c75-147">Umbenennen einer gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="10c75-147">Rename a Stored Procedure</span></span>](rename-a-stored-procedure.md)  
  
  
