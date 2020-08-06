---
title: Erstellen einer neuen Bedingung der richtlinienbasierten Verwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, creating policy conditions
ms.assetid: 8a612f7e-6c70-49db-a4de-48431e097cc5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e4fe206c9a82b69101508f6f0a760ca9c1bc423d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618674"
---
# <a name="create-a-new-policy-based-management-condition"></a><span data-ttu-id="a431a-102">Erstellen einer neuen Bedingung der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="a431a-102">Create a New Policy-Based Management Condition</span></span>
  <span data-ttu-id="a431a-103">In diesem Thema wird beschrieben, wie Sie eine Bedingung der richtlinienbasierte Verwaltung in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]erstellen.</span><span class="sxs-lookup"><span data-stu-id="a431a-103">This topic describes how to create a Policy-based Management condition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="a431a-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="a431a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a431a-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="a431a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a431a-106">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a431a-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a431a-107">**Erstellen einer Bedingung mit:**</span><span class="sxs-lookup"><span data-stu-id="a431a-107">**To create a condition, using:**</span></span>  
  
     [<span data-ttu-id="a431a-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a431a-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a431a-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="a431a-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a431a-110">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a431a-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a431a-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a431a-111">Permissions</span></span>  
 <span data-ttu-id="a431a-112">Erfordert die Mitgliedschaft in der PolicyAdministratorRole-Rolle in der msdb-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="a431a-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a431a-113">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a431a-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-condition"></a><span data-ttu-id="a431a-114">So erstellen Sie eine Bedingung</span><span class="sxs-lookup"><span data-stu-id="a431a-114">To create a condition</span></span>  
  
1.  <span data-ttu-id="a431a-115">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, auf dem Sie die Bedingung der richtlinenbasierten Verwaltung erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="a431a-115">In **Object Explorer**, click the plus sign to expand the server where you want to create a Policy-based Management condition.</span></span>  
  
2.  <span data-ttu-id="a431a-116">Klicken Sie auf das Pluszeichen, um den Ordner **Verwaltung** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="a431a-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="a431a-117">Klicken Sie auf das Pluszeichen, um **Richtlinienverwaltung**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="a431a-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="a431a-118">Klicken Sie auf das Pluszeichen, um den Ordner **Facets** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="a431a-118">Click the plus sign to expand the **Facets** folder.</span></span>  
  
5.  <span data-ttu-id="a431a-119">Klicken Sie mit der rechten Maustaste auf das Facet, in dem Sie eine neue Bedingung erstellen möchten, und wählen Sie **Neue Bedingung**aus.</span><span class="sxs-lookup"><span data-stu-id="a431a-119">Right-click the facet in which you want to create a new condition and select **New Condition**.</span></span>  
  
6.  <span data-ttu-id="a431a-120">Geben Sie im Dialogfeld **Neue Bedingung erstellen** im Feld **Name** den Namen der neuen Bedingung ein.</span><span class="sxs-lookup"><span data-stu-id="a431a-120">In the **Create New Condition** dialog box, in the **Name** box, type the name of the new condition.</span></span>  
  
7.  <span data-ttu-id="a431a-121">Bestätigen Sie das richtige Facet in der Liste **Facet** , oder wählen Sie ein anderes Facet aus.</span><span class="sxs-lookup"><span data-stu-id="a431a-121">Confirm the correct facet in the **Facet** list, or select a different facet.</span></span>  
  
8.  <span data-ttu-id="a431a-122">Erstellen Sie unter **Ausdruck**Bedingungsausdrücke, indem Sie eine Faceteigenschaft im Feld **Feld** zusammen mit dem dazugehörigen Operator und Wert auswählen.</span><span class="sxs-lookup"><span data-stu-id="a431a-122">Under **Expression**, construct condition expressions by selecting a facet property in the **Field** box, together with its associated operator and value.</span></span> <span data-ttu-id="a431a-123">Wenn Sie mehrere Ausdrücke hinzufügen, können die Ausdrücke mit **Und** oder **Oder**verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="a431a-123">When you add multiple expressions, the expressions can be joined by using **And** or **Or**.</span></span> <span data-ttu-id="a431a-124">Weitere Informationen zu den Optionen in diesem Dialogfeld finden Sie unter [Dialogfeld 'Neue Bedingung erstellen' oder 'Bedingung öffnen', Seite 'Allgemein'](../../integration-services/general-page-of-integration-services-designers-options.md), [Dialogfeld 'Neue Bedingung erstellen' oder 'Bedingung öffnen', Seite 'Beschreibung'](create-new-condition-or-open-condition-dialog-box-description-page.md) und [Dialogfeld 'Erweiterte Bearbeitung &#40;Bedingung&#41;'](advanced-edit-condition-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="a431a-124">For more information on the available options in this dialog box, see [Create New Condition or Open Condition Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md), [Create New Condition or Open Condition Dialog Box, Description Page](create-new-condition-or-open-condition-dialog-box-description-page.md), and [Advanced Edit &#40;Condition&#41; Dialog Box](advanced-edit-condition-dialog-box.md).</span></span>  
  
9. <span data-ttu-id="a431a-125">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a431a-125">When finished, click **OK**.</span></span>  
  
  
