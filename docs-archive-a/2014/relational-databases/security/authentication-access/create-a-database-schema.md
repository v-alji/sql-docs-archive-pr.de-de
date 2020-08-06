---
title: Erstellen eines Datenbankschemas | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.schemas.general.f1
helpviewer_keywords:
- creating schemas with Management Studio
- CREATE SCHEMA [Management Studio]
- database schemas
- schemas [SQL Server], creating
ms.assetid: ed2a5522-f4d2-4111-95a4-d3e1e5081739
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 3ac0c00768db6501c7d786c35758c1a9d75a5a7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697772"
---
# <a name="create-a-database-schema"></a><span data-ttu-id="b0598-102">Erstellen eines Datenbankschemas</span><span class="sxs-lookup"><span data-stu-id="b0598-102">Create a Database Schema</span></span>
  <span data-ttu-id="b0598-103">In diesem Thema wird beschrieben, wie ein Schema in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../../includes/tsql-md.md)]erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="b0598-103">This topic describes how to create a schema in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b0598-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="b0598-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b0598-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="b0598-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b0598-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b0598-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b0598-107">Security</span><span class="sxs-lookup"><span data-stu-id="b0598-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b0598-108">**So erstellen Sie ein Schema mit**</span><span class="sxs-lookup"><span data-stu-id="b0598-108">**To create a schema, using:**</span></span>  
  
     [<span data-ttu-id="b0598-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b0598-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b0598-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b0598-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b0598-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="b0598-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b0598-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b0598-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b0598-113">Das neue Schema ist im Besitz einer der folgenden Prinzipale auf Datenbankebene: Datenbankbenutzer, Datenbankrolle oder Anwendungsrolle.</span><span class="sxs-lookup"><span data-stu-id="b0598-113">The new schema is owned by one of the following database-level principals: database user, database role, or application role.</span></span> <span data-ttu-id="b0598-114">Objekte, die innerhalb eines Schemas erstellt werden, gehören dem Besitzer des Schemas und haben für **principal_id** in **sys.objects** einen NULL-Wert.</span><span class="sxs-lookup"><span data-stu-id="b0598-114">Objects created within a schema are owned by the owner of the schema, and have a NULL **principal_id** in **sys.objects**.</span></span> <span data-ttu-id="b0598-115">Der Besitz von Objekten, die Schemas als Bereich aufweisen, kann an jeden Prinzipal auf Datenbankebene übertragen werden, aber der Schemabesitzer behält immer die CONTROL-Berechtigung für Objekte innerhalb des Schemas.</span><span class="sxs-lookup"><span data-stu-id="b0598-115">Ownership of schema-contained objects can be transferred to any database-level principal, but the schema owner always retains CONTROL permission on objects within the schema.</span></span>  
  
-   <span data-ttu-id="b0598-116">Wenn Sie beim Erstellen eines Datenbankobjekts einen gültigen Domänenprinzipal als Objektbesitzer (Benutzer oder Gruppe) angeben, wird der Domänenprinzipal der Datenbank als Schema hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b0598-116">When creating a database object, if you specify a valid domain principal (user or group) as the object owner, the domain principal will be added to the database as a schema.</span></span> <span data-ttu-id="b0598-117">Das neue Schema befindet sich im Besitz des Domänenprinzipals.</span><span class="sxs-lookup"><span data-stu-id="b0598-117">The new schema will be owned by that domain principal.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b0598-118">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b0598-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b0598-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b0598-119">Permissions</span></span>  
  
-   <span data-ttu-id="b0598-120">Erfordert die CREATE SCHEMA-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="b0598-120">Requires CREATE SCHEMA permission on the database.</span></span>  
  
-   <span data-ttu-id="b0598-121">Um einen anderen Benutzer als den Besitzer des zu erstellenden Schemas anzugeben, benötigt der Aufrufer die IMPERSONATE-Berechtigung für diesen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b0598-121">To specify another user as the owner of the schema being created, the caller must have IMPERSONATE permission on that user.</span></span> <span data-ttu-id="b0598-122">Wenn eine Datenbankrolle als Besitzer angegeben wird, muss der Aufrufer entweder über eine Mitgliedschaft in der Rolle oder die ALTER-Berechtigung für die Rolle verfügen.</span><span class="sxs-lookup"><span data-stu-id="b0598-122">If a database role is specified as the owner, the caller must have one of the following: membership in the role or ALTER permission on the role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b0598-123">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b0598-123">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-a-schema"></a><span data-ttu-id="b0598-124">So erstellen Sie ein Schema</span><span class="sxs-lookup"><span data-stu-id="b0598-124">To create a schema</span></span>  
  
1.  <span data-ttu-id="b0598-125">Erweitern Sie im Objekt-Explorer den Ordner **Datenbanken** .</span><span class="sxs-lookup"><span data-stu-id="b0598-125">In Object Explorer, expand the **Databases** folder.</span></span>  
  
2.  <span data-ttu-id="b0598-126">Erweitern Sie die Datenbank, in der das neue Datenbankschema erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b0598-126">Expand the database in which to create the new database schema.</span></span>  
  
3.  <span data-ttu-id="b0598-127">Klicken Sie mit der rechten Maustaste auf den Ordner **Sicherheit** , zeigen Sie auf **Neu**, und wählen Sie **Schema**aus.</span><span class="sxs-lookup"><span data-stu-id="b0598-127">Right-click the **Security** folder, point to **New**, and select **Schema**.</span></span>  
  
4.  <span data-ttu-id="b0598-128">Geben Sie im Dialogfeld **Schema - Neu** auf der Seite **Allgemein** im Feld **Schemaname** einen Namen für das neue Schema ein.</span><span class="sxs-lookup"><span data-stu-id="b0598-128">In the **Schema - New** dialog box, on the **General** page, enter a name for the new schema in the **Schema name** box.</span></span>  
  
5.  <span data-ttu-id="b0598-129">Geben Sie im Feld **Schemabesitzer** den Namen eines Datenbankbenutzers oder einer Rolle ein, der bzw. die über das Schema verfügen soll.</span><span class="sxs-lookup"><span data-stu-id="b0598-129">In the **Schema owner** box, enter the name of a database user or role to own the schema.</span></span> <span data-ttu-id="b0598-130">Klicken Sie alternativ auf **Suchen** , um das Dialogfeld **Rollen und Benutzer suchen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b0598-130">Alternately, click **Search** to open the **Search Roles and Users** dialog box.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="b0598-131">Zusätzliche Optionen</span><span class="sxs-lookup"><span data-stu-id="b0598-131">Additional Options</span></span>  
 <span data-ttu-id="b0598-132">Im Dialogfeld **Schema – Neu** sind auch Optionen auf zwei zusätzlichen Seiten verfügbar: **Berechtigungen** und **Erweiterte Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b0598-132">The **Schema- New** dialog box also offers options on two additional pages: **Permissions** and **Extended Properties**.</span></span>  
  
-   <span data-ttu-id="b0598-133">Auf der Seite **Berechtigungen** werden alle möglichen sicherungsfähigen Elemente und die Berechtigungen für diese sicherungsfähigen Elemente aufgelistet, die für die Anmeldung gewährt werden können.</span><span class="sxs-lookup"><span data-stu-id="b0598-133">The **Permissions** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span>  
  
-   <span data-ttu-id="b0598-134">Mithilfe der Seite **Erweiterte Eigenschaften** können Sie Datenbankbenutzern benutzerdefinierte Eigenschaften hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b0598-134">The **Extended properties** page allows you to add custom properties to database users.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b0598-135">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b0598-135">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-schema"></a><span data-ttu-id="b0598-136">So erstellen Sie ein Schema</span><span class="sxs-lookup"><span data-stu-id="b0598-136">To create a schema</span></span>  
  
1.  <span data-ttu-id="b0598-137">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="b0598-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b0598-138">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="b0598-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b0598-139">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b0598-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Creates the schema Sprockets owned by Annik that contains table NineProngs.   
    -- The statement grants SELECT to Mandar and denies SELECT to Prasanna.  
  
    CREATE SCHEMA Sprockets AUTHORIZATION Annik  
        CREATE TABLE NineProngs (source int, cost int, partnumber int)  
        GRANT SELECT ON SCHEMA::Sprockets TO Mandar  
        DENY SELECT ON SCHEMA::Sprockets TO Prasanna;  
    GO  
    ```  
  
 <span data-ttu-id="b0598-140">Weitere Informationen finden Sie unter [CREATE SCHEMA &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-schema-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b0598-140">For more information, see [CREATE SCHEMA &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-schema-transact-sql).</span></span>  
  
  
