---
title: Anzeigen oder Ändern der Eigenschaften einer Bedingung der richtlinienbasierten Verwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, view policy conditions
- Policy-Based Management, modify policy conditions
ms.assetid: 890d7384-8444-4767-bb6f-f5debb155747
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 08baec48bd13445ef56ea6a29520d23ebaf683b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615981"
---
# <a name="view-or-modify-the-properties-of-a-policy-based-management-condition"></a><span data-ttu-id="8c0bf-102">Anzeigen oder Ändern der Eigenschaften einer Bedingung der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="8c0bf-102">View or Modify the Properties of a Policy-Based Management Condition</span></span>
  <span data-ttu-id="8c0bf-103">In diesem Thema wird beschrieben, wie Sie die Eigenschaften einer Bedingung der richtlinienbasierten Verwaltung mithilfe von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] in [!INCLUDE[tsql](../../includes/tsql-md.md)]ändern.</span><span class="sxs-lookup"><span data-stu-id="8c0bf-103">This topic describes how to view or modify the properties of a Policy-Based Management condition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8c0bf-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="8c0bf-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8c0bf-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="8c0bf-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8c0bf-106">Security</span><span class="sxs-lookup"><span data-stu-id="8c0bf-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8c0bf-107">**Anzeigen oder Ändern der Eigenschaften einer Bedingung mit:**</span><span class="sxs-lookup"><span data-stu-id="8c0bf-107">**To view or modify a condition's properties, using:**</span></span>  
  
     [<span data-ttu-id="8c0bf-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8c0bf-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8c0bf-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8c0bf-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8c0bf-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="8c0bf-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8c0bf-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8c0bf-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8c0bf-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8c0bf-112">Permissions</span></span>  
 <span data-ttu-id="8c0bf-113">Erfordert die Mitgliedschaft in der PolicyAdministratorRole-Rolle in der msdb-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="8c0bf-113">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8c0bf-114">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8c0bf-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-modify-a-conditions-properties"></a><span data-ttu-id="8c0bf-115">So zeigen Sie die Eigenschaften einer Bedingung an bzw. ändern sie</span><span class="sxs-lookup"><span data-stu-id="8c0bf-115">To view or modify a condition's properties</span></span>  
  
1.  <span data-ttu-id="8c0bf-116">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, der die Bedingungen enthält, die Sie anzeigen oder ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="8c0bf-116">In **Object Explorer**, click the plus sign to expand the server that contains the condition that you want to view or modify.</span></span>  
  
2.  <span data-ttu-id="8c0bf-117">Klicken Sie auf das Pluszeichen, um den Ordner **Verwaltung** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="8c0bf-117">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="8c0bf-118">Klicken Sie auf das Pluszeichen, um **Richtlinienverwaltung**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="8c0bf-118">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="8c0bf-119">Klicken Sie auf das Pluszeichen, um den Ordner **Bedingungen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="8c0bf-119">Click the plus sign to expand the **Conditions** folder.</span></span>  
  
5.  <span data-ttu-id="8c0bf-120">Klicken Sie mit der rechten Maustaste auf die Bedingung, die Sie anzeigen oder bearbeiten möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="8c0bf-120">Right-click the condition that you want to view or edit and select **Properties**.</span></span> <span data-ttu-id="8c0bf-121">Weitere Informationen zu den verfügbaren Optionen im Dialog **Feld Bedingung öffnen**_condition_name_ finden Sie im Dialog [Feld neue Bedingung erstellen oder Bedingung öffnen, Seite Allgemein](../../integration-services/general-page-of-integration-services-designers-options.md), [Dialogfeld ' Bedingung öffnen ', Seite ' Abhängige Richtlinien](open-condition-dialog-box-dependent-policies-page.md)', Dialogfeld ' [neue Bedingung erstellen ' oder ' Bedingung öffnen ', Seite ' Beschreibung](create-new-condition-or-open-condition-dialog-box-description-page.md)' und Dialogfeld ' [&#40;Bedingung bearbeiten '&#41; Dialogfeld](advanced-edit-condition-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="8c0bf-121">For more information on the available options in the **Open Condition -**_condition_name_ dialog box, see [Create New Condition or Open Condition Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md), [Open Condition Dialog Box, Dependent Policies Page](open-condition-dialog-box-dependent-policies-page.md), [Create New Condition or Open Condition Dialog Box, Description Page](create-new-condition-or-open-condition-dialog-box-description-page.md), and [Advanced Edit &#40;Condition&#41; Dialog Box](advanced-edit-condition-dialog-box.md).</span></span>  
  
6.  <span data-ttu-id="8c0bf-122">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c0bf-122">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8c0bf-123">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8c0bf-123">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-conditions-properties"></a><span data-ttu-id="8c0bf-124">So zeigen Sie die Eigenschaften einer Bedingung an</span><span class="sxs-lookup"><span data-stu-id="8c0bf-124">To view a condition's properties</span></span>  
  
1.  <span data-ttu-id="8c0bf-125">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="8c0bf-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8c0bf-126">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="8c0bf-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8c0bf-127">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="8c0bf-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb;  
    GO  
    SELECT name,  
       description,  
       facet,  
       expression,  
       is_name_condition,  
       obj_name  
    FROM syspolicy_conditions;  
    GO  
  
    ```  
  
 <span data-ttu-id="8c0bf-128">Weitere Informationen finden Sie unter [yspolicy_conditions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-conditions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8c0bf-128">For more information, see [syspolicy_conditions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-conditions-transact-sql).</span></span>  
  
  
