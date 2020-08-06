---
title: Erstellen einer Anwendungsrolle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.approle.general.f1
helpviewer_keywords:
- application roles [SQL Server], creating
ms.assetid: 6b8da1f5-3d8e-4f88-b111-b915788b06f1
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 51272dad57558cdb771f9b98a2f5e5b3da7609cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620782"
---
# <a name="create-an-application-role"></a><span data-ttu-id="f3265-102">Erstellen einer Anwendungsrolle</span><span class="sxs-lookup"><span data-stu-id="f3265-102">Create an Application Role</span></span>
  <span data-ttu-id="f3265-103">In diesem Thema wird beschrieben, wie Sie eine Anwendungsrolle in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../../includes/tsql-md.md)]erstellen können.</span><span class="sxs-lookup"><span data-stu-id="f3265-103">This topic describes how to create an application role in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f3265-104">Mit Anwendungsrollen wird der Benutzerzugriff auf eine Datenbank bis auf Zugriffe über bestimmte Anwendungen eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="f3265-104">Application roles restrict user access to a database except through specific applications.</span></span> <span data-ttu-id="f3265-105">Anwendungsrollen verfügen nicht über Benutzer, daher wird die Liste **Rollenmitglieder** nicht angezeigt, wenn **Anwendungsrolle** ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="f3265-105">Application roles have no users, so the **Role Members** list is not displayed when **Application role** is selected.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f3265-106">Beim Festlegen von Kennwörtern für Anwendungsrollen wird die Kennwortkomplexität überprüft.</span><span class="sxs-lookup"><span data-stu-id="f3265-106">Password complexity is checked when application role passwords are set.</span></span> <span data-ttu-id="f3265-107">Anwendungen, die Anwendungsrollen aufrufen, müssen ihre Kennwörter speichern.</span><span class="sxs-lookup"><span data-stu-id="f3265-107">Applications that invoke application roles must store their passwords.</span></span> <span data-ttu-id="f3265-108">Kennwörter für Anwendungsrollen sollten immer verschlüsselt gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="f3265-108">Application role passwords should always be stored encrypted.</span></span>  
  
 <span data-ttu-id="f3265-109">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="f3265-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f3265-110">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="f3265-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f3265-111">Security</span><span class="sxs-lookup"><span data-stu-id="f3265-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f3265-112">**So erstellen Sie eine Anwendungsrolle mit**</span><span class="sxs-lookup"><span data-stu-id="f3265-112">**To create an application role, using:**</span></span>  
  
     [<span data-ttu-id="f3265-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f3265-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f3265-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f3265-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f3265-115">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="f3265-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f3265-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f3265-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f3265-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f3265-117">Permissions</span></span>  
 <span data-ttu-id="f3265-118">Erfordert die ALTER ANY APPLICATION ROLE-Berechtigung in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f3265-118">Requires ALTER ANY APPLICATION ROLE permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f3265-119">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f3265-119">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-an-application-role"></a><span data-ttu-id="f3265-120">So erstellen Sie eine Anwendungsrolle</span><span class="sxs-lookup"><span data-stu-id="f3265-120">To create an application role</span></span>  
  
1.  <span data-ttu-id="f3265-121">Erweitern Sie im Objekt-Explorer die Datenbank, in der Sie eine Anwendungsrolle erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="f3265-121">In Object Explorer, expand the database where you want to create an application role.</span></span>  
  
2.  <span data-ttu-id="f3265-122">Erweitern Sie den Ordner **Sicherheit** .</span><span class="sxs-lookup"><span data-stu-id="f3265-122">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="f3265-123">Erweitern Sie den Ordner **Rollen** .</span><span class="sxs-lookup"><span data-stu-id="f3265-123">Expand the **Roles** folder.</span></span>  
  
4.  <span data-ttu-id="f3265-124">Klicken Sie mit der rechten Maustaste auf den Ordner **Anwendungsrollen**, und klicken Sie dann auf **Neue Anwendungsrolle...** .</span><span class="sxs-lookup"><span data-stu-id="f3265-124">Right-click the **Application Roles** folder and select **New Application Role...**.</span></span>  
  
5.  <span data-ttu-id="f3265-125">Geben Sie in das Dialogfeld **Anwendungsrolle – Neu** auf der Seite **Allgemein** den Namen der neuen Anwendungsrolle in das Feld **Rollenname** ein.</span><span class="sxs-lookup"><span data-stu-id="f3265-125">In the **Application Role - New** dialog box, on the **General Page**, enter the new name of the new application role in the **Role name** box.</span></span>  
  
6.  <span data-ttu-id="f3265-126">Geben Sie im Feld **Standardschema** das Schema an, das Objekte besitzen soll, die von dieser Rolle durch Eingabe der Objektnamen erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f3265-126">In the **Default Schema** box, specify the schema that will own objects created by this role by entering the object names.</span></span> <span data-ttu-id="f3265-127">Klicken Sie alternativ auf die Auslassungspunkte **(...)** , um das Dialogfeld **Schema suchen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f3265-127">Alternately, click the ellipsis **(...)** to open the **Locate Schema** dialog box.</span></span>  
  
7.  <span data-ttu-id="f3265-128">Geben Sie im Feld **Kennwort** ein Kennwort für die neue Rolle ein.</span><span class="sxs-lookup"><span data-stu-id="f3265-128">In the **Password** box, enter a password for the new role.</span></span> <span data-ttu-id="f3265-129">Geben Sie dieses Kennwort erneut im Feld **Kennwort bestätigen** ein.</span><span class="sxs-lookup"><span data-stu-id="f3265-129">Enter that password again into the **Confirm Password** box.</span></span>  
  
8.  <span data-ttu-id="f3265-130">Wählen Sie unter **Schemas im Besitz dieser Rolle**die Schemas aus, die diese Rolle besitzen soll, oder zeigen Sie sie an.</span><span class="sxs-lookup"><span data-stu-id="f3265-130">Under **Schemas owned by this role**, select or view schemas that will be owned by this role.</span></span> <span data-ttu-id="f3265-131">Jedes Schema kann immer nur im Besitz eines einzelnen Schemas oder einer einzelnen Rolle sein.</span><span class="sxs-lookup"><span data-stu-id="f3265-131">A schema can be owned by only one schema or role.</span></span>  
  
9. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="f3265-132">Zusätzliche Optionen</span><span class="sxs-lookup"><span data-stu-id="f3265-132">Additional Options</span></span>  
 <span data-ttu-id="f3265-133">Im Dialogfeld **Anwendungsrolle – Neu** sind auch Optionen auf zwei zusätzlichen Seiten verfügbar: **Sicherungsfähige Elemente** und **Erweiterte Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="f3265-133">The **Application Role - New** dialog box also offers options on two additional pages: **Securables** and **Extended Properties**.</span></span>  
  
-   <span data-ttu-id="f3265-134">Auf der Seite **Sicherungsfähige Elemente** werden alle möglichen sicherungsfähigen Elemente und die Berechtigungen für diese sicherungsfähigen Elemente aufgelistet, die für die Anmeldung gewährt werden können.</span><span class="sxs-lookup"><span data-stu-id="f3265-134">The **Securables** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span>  
  
-   <span data-ttu-id="f3265-135">Mithilfe der Seite **Erweiterte Eigenschaften** können Sie Datenbankbenutzern benutzerdefinierte Eigenschaften hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f3265-135">The **Extended properties** page allows you to add custom properties to database users.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f3265-136">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f3265-136">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-application-role"></a><span data-ttu-id="f3265-137">So erstellen Sie eine Anwendungsrolle</span><span class="sxs-lookup"><span data-stu-id="f3265-137">To create an application role</span></span>  
  
1.  <span data-ttu-id="f3265-138">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="f3265-138">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f3265-139">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="f3265-139">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f3265-140">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f3265-140">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates an application role called "weekly_receipts" that has the password "987Gbv876sPYY5m23" and "Sales" as its default schema.  
  
    CREATE APPLICATION ROLE weekly_receipts   
        WITH PASSWORD = '987G^bv876sPY)Y5m23'   
        , DEFAULT_SCHEMA = Sales;  
    GO  
    ```  
  
 <span data-ttu-id="f3265-141">Weitere Informationen finden Sie unter [CREATE APPLICATION ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-application-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f3265-141">For more information, see [CREATE APPLICATION ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-application-role-transact-sql).</span></span>  
  
  
