---
title: Anzeigen der Eigenschaften eines Facets der richtlinienbasierten Verwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, view facet properties
ms.assetid: 022a244c-c2e7-4467-b9a2-c7a27859be22
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea24ff2768ecaeec426a8689455912d848b54813
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615977"
---
# <a name="view-the-properties-of-a-policy-based-management-facet"></a><span data-ttu-id="44712-102">Anzeigen der Eigenschaften eines Facets der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="44712-102">View the Properties of a Policy-Based Management Facet</span></span>
  <span data-ttu-id="44712-103">In diesem Thema wird beschrieben, wie Sie die Eigenschaften eines Facets der richtlinienbasierten Verwaltung i mithilfe von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]anzeigen.</span><span class="sxs-lookup"><span data-stu-id="44712-103">This topic describes how to view the properties of a Policy-Based Management facet in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="44712-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="44712-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="44712-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="44712-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="44712-106">Security</span><span class="sxs-lookup"><span data-stu-id="44712-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="44712-107">**Anzeigen der Eigenschaften eines Facets mit:**</span><span class="sxs-lookup"><span data-stu-id="44712-107">**To view the properties of a facet, using:**</span></span>  
  
     [<span data-ttu-id="44712-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="44712-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="44712-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="44712-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="44712-110">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="44712-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="44712-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="44712-111">Permissions</span></span>  
 <span data-ttu-id="44712-112">Erfordert die Mitgliedschaft in der PolicyAdministratorRole-Rolle in der msdb-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="44712-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="44712-113">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="44712-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-of-a-facet"></a><span data-ttu-id="44712-114">So zeigen Sie die Eigenschaften eines Facets an</span><span class="sxs-lookup"><span data-stu-id="44712-114">To view the properties of a facet</span></span>  
  
1.  <span data-ttu-id="44712-115">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, in dem das Facet mit den anzuzeigenden Eigenschaften enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="44712-115">In **Object Explorer**, click the plus sign to expand the server that contains the facet whose properties you want to view.</span></span>  
  
2.  <span data-ttu-id="44712-116">Klicken Sie auf das Pluszeichen, um den Ordner **Verwaltung** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="44712-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="44712-117">Klicken Sie auf das Pluszeichen, um **Richtlinienverwaltung**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="44712-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="44712-118">Klicken Sie auf das Pluszeichen, um den Ordner **Facets** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="44712-118">Click the plus sign to expand the **Facets** folder.</span></span>  
  
5.  <span data-ttu-id="44712-119">Klicken Sie mit der rechten Maustaste auf das Facet, dessen Eigenschaften Sie anzeigen möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="44712-119">Right-click the facet whose properties you want to view and select **Properties**.</span></span> <span data-ttu-id="44712-120">Weitere Informationen über die verfügbaren Optionen im Dialogfeld \*\*Facet-Eigenschaften – \*\*_Facet-Name_ finden Sie unter Dialogfeld [„Facet-Eigenschaften“, Seite „Allgemein“](../../integration-services/general-page-of-integration-services-designers-options.md), [Dialogfeld „Facet-Eigenschaften“, Seite „Abhängige Richtlinien“](facet-properties-dialog-box-dependent-policies-page.md) und [Dialogfeld „Facet-Eigenschaften“, Seite „Abhängige Bedingungen“](facet-properties-dialog-box-dependent-conditions-page.md).</span><span class="sxs-lookup"><span data-stu-id="44712-120">For more information on the available options in the **Facet Properties -**_facet_name_ dialog box, see [Facet Properties Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md), [Facet Properties Dialog Box, Dependent Policies Page](facet-properties-dialog-box-dependent-policies-page.md), and [Facet Properties Dialog Box, Dependent Conditions Page](facet-properties-dialog-box-dependent-conditions-page.md).</span></span>  
  
6.  <span data-ttu-id="44712-121">Wenn Sie fertig sind, klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="44712-121">When finished, click **Close**.</span></span>  
  
  
