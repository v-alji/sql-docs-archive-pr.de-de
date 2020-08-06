---
title: Anzeigen oder Ändern der Eigenschaften einer Richtlinie der richtlinienbasierten Verwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, modify policies
- Policy-Based Management, view policies
ms.assetid: ba805504-5db5-4731-a8da-a0e89cb20c37
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: da2226d3049a84098eb8e561635161f73b71ab10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615982"
---
# <a name="view-or-modify-the-properties-of-a-policy-based-management-policy"></a><span data-ttu-id="2b3c7-102">Anzeigen oder Ändern der Eigenschaften einer Richtlinie der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="2b3c7-102">View or Modify the Properties of a Policy-Based Management Policy</span></span>
  <span data-ttu-id="2b3c7-103">In diesem Thema wird beschrieben, wie Sie die Eigenschaften einer Richtlinie der richtlinienbasierten Verwaltung mithilfe von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] in [!INCLUDE[tsql](../../includes/tsql-md.md)]ändern.</span><span class="sxs-lookup"><span data-stu-id="2b3c7-103">This topic describes how to view or modify a Policy-Based Management policy's properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2b3c7-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="2b3c7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2b3c7-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="2b3c7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2b3c7-106">Security</span><span class="sxs-lookup"><span data-stu-id="2b3c7-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2b3c7-107">**Anzeigen oder Ändern der Eigenschaften einer Richtlinie mit:**</span><span class="sxs-lookup"><span data-stu-id="2b3c7-107">**To view or modify a policy's properties, using:**</span></span>  
  
     [<span data-ttu-id="2b3c7-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2b3c7-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2b3c7-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2b3c7-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2b3c7-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="2b3c7-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2b3c7-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="2b3c7-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2b3c7-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="2b3c7-112">Permissions</span></span>  
 <span data-ttu-id="2b3c7-113">Erfordert die Mitgliedschaft in der PolicyAdministratorRole-Rolle in der msdb-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2b3c7-113">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2b3c7-114">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2b3c7-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-of-all-policies-on-an-object"></a><span data-ttu-id="2b3c7-115">So zeigen Sie die Eigenschaften aller Richtlinien für ein Objekt an</span><span class="sxs-lookup"><span data-stu-id="2b3c7-115">To view the properties of all policies on an object</span></span>  
  
1.  <span data-ttu-id="2b3c7-116">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, ein Serverobjekt, eine Datenbank oder ein Datenbankobjekt, zeigen Sie auf **Richtlinien** , und wählen Sie dann **Anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="2b3c7-116">In Object Explorer, right-click a server, server object, database, or database object, point to **Policies** and select **View**.</span></span> <span data-ttu-id="2b3c7-117">Weitere Informationen zu den verfügbaren Optionen im Dialogfeld \*\*Richtlinien anzeigen – \*\*_Objektname_ finden Sie unter [Dialogfeld „Richtlinien anzeigen“](view-policies-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="2b3c7-117">For more information on the available options in the **View Policies -**_object_name_ dialog box, see [View Policies Dialog Box](view-policies-dialog-box.md).</span></span>  
  
2.  <span data-ttu-id="2b3c7-118">Wenn Sie fertig sind, klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="2b3c7-118">When finished, click **Close**.</span></span>  
  
#### <a name="to-view-or-modify-a-specific-policys-properties"></a><span data-ttu-id="2b3c7-119">So zeigen Sie die Eigenschaften einer bestimmten Richtlinie an bzw. ändern sie</span><span class="sxs-lookup"><span data-stu-id="2b3c7-119">To view or modify a specific policy's properties</span></span>  
  
1.  <span data-ttu-id="2b3c7-120">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, der die Richtlinie der richtlinienbasierten Verwaltung enthält, die Sie anzeigen oder ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="2b3c7-120">In **Object Explorer**, click the plus sign to expand the server that contains the Policy-Based Management policy that you want to view or modify.</span></span>  
  
2.  <span data-ttu-id="2b3c7-121">Klicken Sie auf das Pluszeichen, um den Ordner **Verwaltung** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="2b3c7-121">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="2b3c7-122">Klicken Sie auf das Pluszeichen, um **Richtlinienverwaltung**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="2b3c7-122">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="2b3c7-123">Klicken Sie auf das Pluszeichen, um den Ordner **Richtlinien** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="2b3c7-123">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="2b3c7-124">Klicken Sie mit der rechten Maustaste auf die Richtlinie, die Sie anzeigen oder ändern möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="2b3c7-124">Right-click the policy that you want to view or modify and select **Properties**.</span></span> <span data-ttu-id="2b3c7-125">Weitere Informationen zu den verfügbaren Optionen im Dialogfeld \*\*Richtlinie öffnen – \*\*_Richtlinienname_ finden Sie unter [Dialogfeld „Neue Richtlinie erstellen“ oder „Richtlinie öffnen“, Seite „Allgemein“](../../integration-services/general-page-of-integration-services-designers-options.md) oder [Dialogfeld „Neue Richtlinie erstellen“ oder „Richtlinie öffnen“, Seite „Beschreibung“](create-new-policy-or-open-policy-dialog-box-description-page.md).</span><span class="sxs-lookup"><span data-stu-id="2b3c7-125">For more information on the available options in the **Open Policy -**_policy_name_ dialog box, see [Create New Policy or Open Policy Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md) and [Create New Policy or Open Policy Dialog Box, Description Page](create-new-policy-or-open-policy-dialog-box-description-page.md).</span></span>  
  
6.  <span data-ttu-id="2b3c7-126">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b3c7-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2b3c7-127">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2b3c7-127">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-policys-properties"></a><span data-ttu-id="2b3c7-128">So zeigen Sie die Eigenschaften einer Richtlinie an</span><span class="sxs-lookup"><span data-stu-id="2b3c7-128">To view a policy's properties</span></span>  
  
1.  <span data-ttu-id="2b3c7-129">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="2b3c7-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2b3c7-130">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="2b3c7-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2b3c7-131">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="2b3c7-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb;  
    GO  
    SELECT name,  
       execution_mode,  
       description,  
       is_enabled,  
       job_id  
    FROM syspolicy_policies;  
    GO  
    ```  
  
 <span data-ttu-id="2b3c7-132">Weitere Informationen finden Sie unter [syspolicy_policies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-policies-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2b3c7-132">For more information, see [syspolicy_policies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-policies-transact-sql).</span></span>  
  
  
