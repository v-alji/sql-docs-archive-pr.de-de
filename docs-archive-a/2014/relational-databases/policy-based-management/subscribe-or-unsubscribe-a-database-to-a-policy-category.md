---
title: Abonnieren einer Richtlinienkategorie für eine Datenbank bzw. Kündigen des Abonnements | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.groupsubscription.f1
ms.assetid: d2c31769-7098-428e-ad9c-ef56541b7c52
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2b4ca6f804352b57b30b42012da93e0d031be8d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699453"
---
# <a name="subscribe-or-unsubscribe-a-database--to-a-policy-category"></a><span data-ttu-id="2e026-102">Abonnieren einer Richtlinienkategorie für eine Datenbank bzw. Kündigen des Abonnements</span><span class="sxs-lookup"><span data-stu-id="2e026-102">Subscribe or Unsubscribe a Database  to a Policy Category</span></span>
  <span data-ttu-id="2e026-103">In diesem Thema wird beschrieben, wie mithilfe von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eine Richtlinienkategorie für eine Datenbank in [!INCLUDE[tsql](../../includes/tsql-md.md)]abonniert bzw. das Abonnement gekündigt wird.</span><span class="sxs-lookup"><span data-stu-id="2e026-103">This topic describes how to subscribe or unsubscribe a database to a policy category.in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2e026-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="2e026-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2e026-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="2e026-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2e026-106">Security</span><span class="sxs-lookup"><span data-stu-id="2e026-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2e026-107">**Abonnieren einer Richtlinienkategorie für eine Datenbank bzw. Kündigen des Abonnements mit:**</span><span class="sxs-lookup"><span data-stu-id="2e026-107">**To subscribe or unsubscribe a database to a policy category., using:**</span></span>  
  
     [<span data-ttu-id="2e026-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2e026-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2e026-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2e026-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2e026-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="2e026-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2e026-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="2e026-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2e026-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="2e026-112">Permissions</span></span>  
 <span data-ttu-id="2e026-113">Erfordert die Mitgliedschaft in der festen Datenbankrolle "db_owner".</span><span class="sxs-lookup"><span data-stu-id="2e026-113">Requires membership in the db_owner fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2e026-114">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2e026-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-subscribe-or-unsubscribe-a-database-to-a-policy-category"></a><span data-ttu-id="2e026-115">So abonnieren Sie eine Richtlinienkategorie für eine Datenbank bzw. kündigen das Abonnement</span><span class="sxs-lookup"><span data-stu-id="2e026-115">To subscribe or unsubscribe a database to a policy category</span></span>  
  
1.  <span data-ttu-id="2e026-116">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, der die Datenbank enthält, in der Sie Kategorieabonnements verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="2e026-116">In **Object Explorer**, click the plus sign to expand the server that contains the database wherein you want to manage category subscriptions.</span></span>  
  
2.  <span data-ttu-id="2e026-117">Klicken Sie auf das Pluszeichen, um den Ordner **Datenbanken** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="2e026-117">Click the plus sign to expand the **Databases** folder.</span></span>  
  
3.  <span data-ttu-id="2e026-118">Klicken Sie mit der rechten Maustaste auf die Datenbank, in der Sie Kategorieabonnements verwalten möchten, zeigen Sie auf **Richtlinien**, und wählen Sie **Kategorien**aus.</span><span class="sxs-lookup"><span data-stu-id="2e026-118">Right-click the database wherein you want to manage category subscriptions, point to **Policies**, and select **Categories**</span></span>  
  
     <span data-ttu-id="2e026-119">Die folgenden Optionen sind im Dialogfeld **Kategorien** verfügbar:</span><span class="sxs-lookup"><span data-stu-id="2e026-119">The following options are available in the **Categories** dialog box:</span></span>  
  
     <span data-ttu-id="2e026-120">Spalte erweitern</span><span class="sxs-lookup"><span data-stu-id="2e026-120">Expand column</span></span>  
     <span data-ttu-id="2e026-121">Klicken Sie, um eine Richtlinienkategorie zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="2e026-121">Click to expand a policy category.</span></span> <span data-ttu-id="2e026-122">Dadurch werden alle in der Kategorie enthaltenen Richtlinien aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="2e026-122">This lists all the policies that are included in the category.</span></span>  
  
     <span data-ttu-id="2e026-123">**Name**</span><span class="sxs-lookup"><span data-stu-id="2e026-123">**Name**</span></span>  
     <span data-ttu-id="2e026-124">Der Name der Richtlinienkategorie.</span><span class="sxs-lookup"><span data-stu-id="2e026-124">The name of the policy category.</span></span>  
  
     <span data-ttu-id="2e026-125">**Zehnmal**</span><span class="sxs-lookup"><span data-stu-id="2e026-125">**Subscribed**</span></span>  
     <span data-ttu-id="2e026-126">Gibt an, ob das Ziel die Richtlinienkategorie abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="2e026-126">Indicates whether the target has subscribed to the policy category.</span></span> <span data-ttu-id="2e026-127">Wenn dieses Kontrollkästchen deaktiviert ist, wird die Richtlinienkategorie für **Datenbankabonnements beauftragen**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2e026-127">If this check box is disabled, the policy category is set for **Mandate Database Subscriptions**.</span></span> <span data-ttu-id="2e026-128">Dies bedeutet, dass die Richtlinienkategorie für alle Datenbanken auf dem Server gilt.</span><span class="sxs-lookup"><span data-stu-id="2e026-128">This means that the policy category applies to all databases on the server.</span></span>  
  
     <span data-ttu-id="2e026-129">**Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="2e026-129">**Policy**</span></span>  
     <span data-ttu-id="2e026-130">Wenn Richtliniengruppen erweitert werden, werden die Richtlinien in der Richtlinienkategorie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2e026-130">When policy groups are expanded, displays the policies in the policy category.</span></span>  
  
     <span data-ttu-id="2e026-131">**Aktiviert**</span><span class="sxs-lookup"><span data-stu-id="2e026-131">**Enabled**</span></span>  
     <span data-ttu-id="2e026-132">Gibt an, ob die Richtlinien aktiviert oder deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="2e026-132">Indicates whether the policies are enabled or disabled.</span></span>  
  
     <span data-ttu-id="2e026-133">**Ausführungsmodus**</span><span class="sxs-lookup"><span data-stu-id="2e026-133">**Execution Mode**</span></span>  
     <span data-ttu-id="2e026-134">Zeigt den Ausführungsmodus der Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="2e026-134">Displays the execution mode of the policy.</span></span>  
  
     <span data-ttu-id="2e026-135">**History**</span><span class="sxs-lookup"><span data-stu-id="2e026-135">**History**</span></span>  
     <span data-ttu-id="2e026-136">Klicken Sie auf den Link Verlauf anzeigen, um den Protokolldatei-Viewer zu öffnen und den Richtlinienverlauf anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2e026-136">Click the View History hyperlink to open the Log File Viewer to see the policy history.</span></span>  
  
4.  <span data-ttu-id="2e026-137">Um eine Kategorie der richtlinienbasierten Verwaltung zu abonnieren, aktivieren Sie das Kontrollkästchen der Kategorie unter der Spalte **Abonniert** .</span><span class="sxs-lookup"><span data-stu-id="2e026-137">To subscribe to a Policy-Based Management category, select the category's check box under the **Subscribed** column.</span></span> <span data-ttu-id="2e026-138">Um das Abonnement einer Kategorie zu kündigen, deaktivieren Sie das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="2e026-138">To unsubscribe from a category, clear the check box.</span></span>  
  
5.  <span data-ttu-id="2e026-139">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2e026-139">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2e026-140">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2e026-140">Using Transact-SQL</span></span>  
  
#### <a name="to-subscribe-a-database-to-a-policy-category"></a><span data-ttu-id="2e026-141">So abonnieren Sie eine Richtlinienkategorie für eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="2e026-141">To subscribe a database to a policy category</span></span>  
  
1.  <span data-ttu-id="2e026-142">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="2e026-142">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2e026-143">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="2e026-143">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2e026-144">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="2e026-144">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    -- Adds a subscription to the 'Finance' policy category for the AdventureWorks2012 database.  
    EXEC sys.sp_syspolicy_subscribe_to_policy_category @policy_category = N'Finance';  
    GO  
    ```  
  
 <span data-ttu-id="2e026-145">Weitere Informationen finden Sie unter [sp_syspolicy_subscribe_to_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-subscribe-to-policy-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2e026-145">For more information, see [sp_syspolicy_subscribe_to_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-subscribe-to-policy-category-transact-sql).</span></span>  
  
#### <a name="to-unsubscribe-a-database-to-a-policy-category"></a><span data-ttu-id="2e026-146">So kündigen Sie das Abonnement einer Richtlinienkategorie für eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="2e026-146">To unsubscribe a database to a policy category</span></span>  
  
1.  <span data-ttu-id="2e026-147">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="2e026-147">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2e026-148">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="2e026-148">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2e026-149">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="2e026-149">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    -- Deletes a subscription to the 'Finance' policy category for the AdventureWorks2012 database.  
    EXEC sys.sp_syspolicy_unsubscribe_from_policy_category @policy_category = N'Finance';  
    GO  
    ```  
  
 <span data-ttu-id="2e026-150">Weitere Informationen finden Sie unter [sp_syspolicy_unsubscribe_from_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-unsubscribe-from-policy-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2e026-150">For more information, see [sp_syspolicy_unsubscribe_from_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-unsubscribe-from-policy-category-transact-sql).</span></span>  
  
  
