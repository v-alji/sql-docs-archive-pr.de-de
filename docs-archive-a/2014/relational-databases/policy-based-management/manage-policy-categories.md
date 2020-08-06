---
title: Richtlinienkategorien verwalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.policycategories.f1
ms.assetid: d188a819-731f-4029-98aa-780d3299a0ce
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 168d05dd88286263da1dca5456a2c6072e946786
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616003"
---
# <a name="manage-policy-categories"></a><span data-ttu-id="35fb2-102">Richtlinienkategorien verwalten</span><span class="sxs-lookup"><span data-stu-id="35fb2-102">Manage Policy Categories</span></span>
  <span data-ttu-id="35fb2-103">In diesem Thema wird beschrieben, wie einzelne oder alle verfügbaren Richtlinien in einer Kategorie unter Verwendung von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] auf die gesamte Instanz von [!INCLUDE[tsql](../../includes/tsql-md.md)]angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="35fb2-103">This topic describes how to apply any or all available policies in a category to the whole instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="35fb2-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="35fb2-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="35fb2-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="35fb2-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="35fb2-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="35fb2-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="35fb2-107">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="35fb2-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="35fb2-108">**Anwenden von Kategorierichtlinien auf eine SQL Server-Instanz mit:**</span><span class="sxs-lookup"><span data-stu-id="35fb2-108">**To apply category policies to a SQL Server instance, using:**</span></span>  
  
     [<span data-ttu-id="35fb2-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="35fb2-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="35fb2-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="35fb2-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="35fb2-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="35fb2-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="35fb2-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="35fb2-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="35fb2-113">Wenn das Kontrollkästchen [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]Datenbankabonnements beauftragen **bei Verwendung von** nicht aktiviert ist, muss die Richtlinienkategorie einzeln auf jeden relevanten Bereich des Servers angewendet werden, wie z. B. auf eine oder mehrere Datenbanken oder Tabellen.</span><span class="sxs-lookup"><span data-stu-id="35fb2-113">When using [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], if the **Mandate Database Subscriptions** check box is not selected, the policy category must be individually applied to each relevant portion of the server, such as one or more databases or tables.</span></span>  
  
-   <span data-ttu-id="35fb2-114">Wenn Sie eine Richtlinienkategorie angeben, die nicht vorhanden ist, wird eine neue Richtlinienkategorie erstellt. Das Abonnement wird für alle Datenbanken beauftragt, wenn Sie die gespeicherte Prozedur ausführen.</span><span class="sxs-lookup"><span data-stu-id="35fb2-114">If you specify a policy category that does not exist, a new policy category is created and the subscription is mandated for all databases when you execute the stored procedure.</span></span> <span data-ttu-id="35fb2-115">Wenn Sie dann das beauftragte Abonnement für die neue Kategorie löschen, ist das Abonnement nur für die Datenbank gültig, die Sie als *target_object*angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="35fb2-115">If you then clear the mandated subscription for the new category, the subscription will only apply for the database that you specified as the *target_object*.</span></span> <span data-ttu-id="35fb2-116">Weitere Informationen zum Ändern der Einstellung eines beauftragten Abonnements finden Sie unter [sp_syspolicy_update_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-update-policy-category-subscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="35fb2-116">For more information about how to change a mandated subscription setting, see [sp_syspolicy_update_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-update-policy-category-subscription-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="35fb2-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="35fb2-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="35fb2-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="35fb2-118">Permissions</span></span>  
 <span data-ttu-id="35fb2-119">Diese gespeicherte Prozedur wird im Kontext des aktuellen Besitzers der gespeicherten Prozedur ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="35fb2-119">This stored procedure runs in the context of the current owner of the stored procedure.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="35fb2-120">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="35fb2-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-apply-category-policies-to-a-sql-server-instance"></a><span data-ttu-id="35fb2-121">So wenden Sie Kategorierichtlinien auf eine SQL Server-Instanz an</span><span class="sxs-lookup"><span data-stu-id="35fb2-121">To apply category policies to a SQL Server instance</span></span>  
  
1.  <span data-ttu-id="35fb2-122">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, auf dem Sie die Kategorierichtlinien anwenden.</span><span class="sxs-lookup"><span data-stu-id="35fb2-122">In **Object Explorer**, click the plus sign to expand the server where you will apply category policies.</span></span>  
  
2.  <span data-ttu-id="35fb2-123">Klicken Sie auf das Pluszeichen, um den Ordner **Verwaltung** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="35fb2-123">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="35fb2-124">Klicken Sie mit der rechten Maustaste auf **Richtlinienverwaltung** , und wählen Sie **Kategorien verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="35fb2-124">Right-click **Policy Management** and select **Manage Categories**.</span></span>  
  
     <span data-ttu-id="35fb2-125">Die folgenden Informationen sind im Dialogfeld **Richtlinienkategorien verwalten** verfügbar:</span><span class="sxs-lookup"><span data-stu-id="35fb2-125">The following information is available in the **Manage Policy Categories** dialog box:</span></span>  
  
     <span data-ttu-id="35fb2-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="35fb2-126">**Name**</span></span>  
     <span data-ttu-id="35fb2-127">Der Name der Richtlinienkategorie.</span><span class="sxs-lookup"><span data-stu-id="35fb2-127">The name of the policy category.</span></span>  
  
     <span data-ttu-id="35fb2-128">**bei Verwendung von**</span><span class="sxs-lookup"><span data-stu-id="35fb2-128">**Mandate Database Subscriptions**</span></span>  
     <span data-ttu-id="35fb2-129">Zwingt alle Datenbanken in der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , Richtlinien in der Richtlinienkategorie durchzusetzen.</span><span class="sxs-lookup"><span data-stu-id="35fb2-129">Forces all databases on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to enforce policies in the policy category.</span></span>  
  
4.  <span data-ttu-id="35fb2-130">Aktivieren oder deaktivieren Sie einzelne oder alle Kontrollkästchen unter **Datenbankabonnements beauftragen** , um diese Richtlinienkategorie auf die SQL Server-Instanz anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="35fb2-130">Select or clear any or all check boxes under **Mandate Database Subscriptions** to apply that policy category to the SQL Server instance.</span></span>  
  
5.  <span data-ttu-id="35fb2-131">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="35fb2-131">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="35fb2-132">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="35fb2-132">Using Transact-SQL</span></span>  
  
#### <a name="to-apply-category-policies-to-a-sql-server-instance"></a><span data-ttu-id="35fb2-133">So wenden Sie Kategorierichtlinien auf eine SQL Server-Instanz an</span><span class="sxs-lookup"><span data-stu-id="35fb2-133">To apply category policies to a SQL Server instance</span></span>  
  
1.  <span data-ttu-id="35fb2-134">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="35fb2-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="35fb2-135">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="35fb2-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="35fb2-136">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="35fb2-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb;  
    GO  
    -- configures the specified database to subscribe to a policy category that is named 'Table Naming Policies'.  
    EXEC dbo.sp_syspolicy_add_policy_category_subscription @target_type = N'DATABASE'  
    , @target_object = N'AdventureWorks2012'  
    , @policy_category = N'Table Naming Policies';  
    GO  
    ```  
  
 <span data-ttu-id="35fb2-137">Weitere Informationen finden Sie unter [sp_syspolicy_add_policy_category_subscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-add-policy-category-subscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="35fb2-137">For more information, see [sp_syspolicy_add_policy_category_subscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-add-policy-category-subscription-transact-sql).</span></span>  
  
  
