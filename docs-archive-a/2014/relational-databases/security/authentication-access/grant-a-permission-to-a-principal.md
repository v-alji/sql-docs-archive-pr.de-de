---
title: Erteilen einer Berechtigung für einen Prinzipal | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Grant permission to a principal
ms.assetid: 4107389d-05b6-4aa3-9fa8-95b40cdf05dc
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 4256d62bdeac2d79c51e5f3792c991e0e3b15096
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725414"
---
# <a name="grant-a-permission-to-a-principal"></a><span data-ttu-id="18a4e-102">Erteilen einer Berechtigung für einen Prinzipal</span><span class="sxs-lookup"><span data-stu-id="18a4e-102">Grant a Permission to a Principal</span></span>
  <span data-ttu-id="18a4e-103">In diesem Thema wird beschrieben, wie Sie mit [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Berechtigungen für einen Prinzipal in [!INCLUDE[tsql](../../../includes/tsql-md.md)]gewähren können.</span><span class="sxs-lookup"><span data-stu-id="18a4e-103">This topic describes how to grant permission to a principal in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="18a4e-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="18a4e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="18a4e-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="18a4e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="18a4e-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="18a4e-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="18a4e-107">Security</span><span class="sxs-lookup"><span data-stu-id="18a4e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="18a4e-108">**So erteilen Sie eine Berechtigung für einen Prinzipal mit**</span><span class="sxs-lookup"><span data-stu-id="18a4e-108">**To grant permission to a principal, using:**</span></span>  
  
     [<span data-ttu-id="18a4e-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="18a4e-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="18a4e-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="18a4e-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="18a4e-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="18a4e-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="18a4e-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="18a4e-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="18a4e-113">Mit den folgenden Best Practices wird die Verwaltung von Berechtigungen erleichtert.</span><span class="sxs-lookup"><span data-stu-id="18a4e-113">Consider the following best practices that can make managing permissions easier.</span></span>  
  
-   <span data-ttu-id="18a4e-114">Erteilen von Berechtigungen für Rollen statt einzelner Anmeldenamen oder Benutzer.</span><span class="sxs-lookup"><span data-stu-id="18a4e-114">Grant permission to roles, instead of individual logins or users.</span></span> <span data-ttu-id="18a4e-115">Wenn eine Einzelperson durch eine andere ersetzt wird, kann fortgehende Einzelperson aus der Rolle entfernt und die neue Person der Rolle hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="18a4e-115">When one individual is replaced by another, remove the departing individual from the role and add the new individual to the role.</span></span> <span data-ttu-id="18a4e-116">Die vielen Berechtigungen, die der Rolle möglicherweise zugeordnet sind, sind für die neue Einzelperson automatisch verfügbar.</span><span class="sxs-lookup"><span data-stu-id="18a4e-116">The many permissions that might be associated with the role will automatically be available to the new individual.</span></span> <span data-ttu-id="18a4e-117">Wenn mehrere Personen in einer Organisation die gleichen Berechtigungen benötigen, können Sie diese der Rolle hinzufügen und ihnen so die gleichen Berechtigungen gewähren.</span><span class="sxs-lookup"><span data-stu-id="18a4e-117">If several people in an organization require the same permissions, adding each of them to the role will grant them the same permissions.</span></span>  
  
-   <span data-ttu-id="18a4e-118">Konfigurieren Sie ähnliche sicherungsfähige Elemente (Tabellen, Sichten und Prozeduren) als im Besitz eines Schemas befindlich, und gewähren Sie dem Schema anschließend Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="18a4e-118">Configure similar securables (tables, views, and procedures) to be owned by a schema, then grant permissions to the schema.</span></span> <span data-ttu-id="18a4e-119">Beispielsweise kann das Lohnlistenschema mehrere Tabellen, Sichten und gespeicherte Prozeduren besitzen.</span><span class="sxs-lookup"><span data-stu-id="18a4e-119">For example, the payroll schema might own several tables, views, and stored procedures.</span></span> <span data-ttu-id="18a4e-120">Durch Gewähren des Zugriffs für das Schema können alle zum Ausführen der Lohnlistenfunktion erforderlichen Berechtigungen gleichzeitig erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="18a4e-120">By granting access to the schema, all the necessary permissions to perform the payroll function can be granted at the same time.</span></span> <span data-ttu-id="18a4e-121">Weitere Informationen zu den sicherungsfähigen Elementen, denen Berechtigungen gewährt werden können, finden Sie unter [Securables](../securables.md).</span><span class="sxs-lookup"><span data-stu-id="18a4e-121">For more information about what securables can be granted permissions, see [Securables](../securables.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="18a4e-122">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="18a4e-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="18a4e-123">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="18a4e-123">Permissions</span></span>  
 <span data-ttu-id="18a4e-124">Der Berechtigende (oder der mit der AS-Option angegebene Prinzipal) muss entweder über die Berechtigung selbst mit GRANT OPTION oder über eine höhere Berechtigung verfügen, in der die erteilte Berechtigung impliziert ist.</span><span class="sxs-lookup"><span data-stu-id="18a4e-124">The grantor (or the principal specified with the AS option) must have either the permission itself with GRANT OPTION or a higher permission that implies the permission being granted.</span></span> <span data-ttu-id="18a4e-125">Mitglieder der festen Serverrolle **sysadmin** können beliebige Berechtigungen erteilen.</span><span class="sxs-lookup"><span data-stu-id="18a4e-125">Members of the **sysadmin** fixed server role can grant any permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="18a4e-126">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="18a4e-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-grant-permission-to-a-principal"></a><span data-ttu-id="18a4e-127">So erteilen Sie eine Berechtigung für einen Prinzipal</span><span class="sxs-lookup"><span data-stu-id="18a4e-127">To grant permission to a principal</span></span>  
  
1.  <span data-ttu-id="18a4e-128">Erweitern Sie im Objekt-Explorer die Datenbank, die das Objekt enthält, dem Sie Berechtigungen gewähren möchten.</span><span class="sxs-lookup"><span data-stu-id="18a4e-128">In Object Explorer, expand the database that contains the object to which you want to grant permissions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="18a4e-129">In diesen Schritten geht es ausdrücklich um das Gewähren von Berechtigungen für eine gespeicherte Prozedur. Sie können jedoch auch ähnliche Schritte vollziehen, um Tabellen, Sichten, Funktionen, Assemblys sowie anderen sicherungsfähigen Elementen Berechtigungen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="18a4e-129">These steps deal specifically with granting permissions to a stored procedure, but you can use similar steps to add permissions to tables, views, functions, and assemblies, as well as other securables.</span></span> <span data-ttu-id="18a4e-130">Weitere Informationen finden Sie unter [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="18a4e-130">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql)</span></span>  
  
2.  <span data-ttu-id="18a4e-131">Erweitern Sie den Ordner **Programmierbarkeit** .</span><span class="sxs-lookup"><span data-stu-id="18a4e-131">Expand the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="18a4e-132">Erweitern Sie den Ordner **Gespeicherte Prozeduren** .</span><span class="sxs-lookup"><span data-stu-id="18a4e-132">Expand the **Stored Procedures** folder.</span></span>  
  
4.  <span data-ttu-id="18a4e-133">Klicken Sie mit der rechten Maustaste auf eine gespeicherte Prozedur, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="18a4e-133">Right-click a stored procedure and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="18a4e-134">Wählen Sie im Dialogfeld **Eigenschaften der gespeicherten Prozedur**_stored_procedure_name_ Unterseite auswählen die Option **Berechtigungen**aus.</span><span class="sxs-lookup"><span data-stu-id="18a4e-134">In the **Stored Procedure Properties -**_stored_procedure_name_ dialog box, under select a page, select **Permissions**.</span></span> <span data-ttu-id="18a4e-135">Verwenden Sie diese Seite, um der gespeicherten Prozedur Benutzer oder Rollen hinzuzufügen und um die Berechtigungen anzugeben, die diese Benutzer oder Rollen haben.</span><span class="sxs-lookup"><span data-stu-id="18a4e-135">Use this page to add users or roles to the stored procedure and specify the permissions those users or roles have.</span></span>  
  
6.  <span data-ttu-id="18a4e-136">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="18a4e-136">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="18a4e-137">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="18a4e-137">Using Transact-SQL</span></span>  
  
#### <a name="to-grant-permission-to-a-principal"></a><span data-ttu-id="18a4e-138">So erteilen Sie eine Berechtigung für einen Prinzipal</span><span class="sxs-lookup"><span data-stu-id="18a4e-138">To grant permission to a principal</span></span>  
  
1.  <span data-ttu-id="18a4e-139">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="18a4e-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="18a4e-140">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="18a4e-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="18a4e-141">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="18a4e-141">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Grants EXECUTE permission on stored procedure HumanResources.uspUpdateEmployeeHireInfo to an application role called Recruiting11.   
    USE AdventureWorks2012;  
    GO  
    GRANT EXECUTE ON OBJECT::HumanResources.uspUpdateEmployeeHireInfo  
        TO Recruiting11;  
    GO  
    ```  
  
 <span data-ttu-id="18a4e-142">Weitere Informationen finden Sie unter [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) und [GRANT (Objektberechtigungen)&#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="18a4e-142">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) and [GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18a4e-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="18a4e-143">See Also</span></span>  
 [<span data-ttu-id="18a4e-144">Prinzipale &#40;Datenbank-Engine&#41;</span><span class="sxs-lookup"><span data-stu-id="18a4e-144">Principals &#40;Database Engine&#41;</span></span>](principals-database-engine.md)  
  
  
