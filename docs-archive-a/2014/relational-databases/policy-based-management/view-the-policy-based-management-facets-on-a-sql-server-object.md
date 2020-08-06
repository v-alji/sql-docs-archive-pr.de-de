---
title: Anzeigen der Facets der richtlinienbasierten Verwaltung für ein SQL Server-Objekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, view facets
ms.assetid: 5f423b9f-a6c4-41a7-9d8d-8f4926ce1fb4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9137971a79e9e5a18e0ef5d901184133a4c3eff3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615978"
---
# <a name="view-the-policy-based-management-facets-on-a-sql-server-object"></a><span data-ttu-id="3fde9-102">Anzeigen der Facets der richtlinienbasierten Verwaltung für ein SQL Server-Objekt</span><span class="sxs-lookup"><span data-stu-id="3fde9-102">View the Policy-Based Management Facets on a SQL Server Object</span></span>
  <span data-ttu-id="3fde9-103">In diesem Thema wird beschrieben, wie Sie alle Facets der richtlinienbasierten Verwaltung, die auf ein bestimmtes SQL Server-Objekt in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] angewendet wurden, mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3fde9-103">This topic describes how to view all of the Policy-Based Management facets applied to a specific SQL Server object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="3fde9-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="3fde9-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3fde9-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="3fde9-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3fde9-106">Security</span><span class="sxs-lookup"><span data-stu-id="3fde9-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3fde9-107">**Anzeigen aller Facets in einem Objekt mit:**</span><span class="sxs-lookup"><span data-stu-id="3fde9-107">**To view all of the facets in an object, using:**</span></span>  
  
     [<span data-ttu-id="3fde9-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3fde9-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3fde9-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="3fde9-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3fde9-110">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3fde9-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3fde9-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="3fde9-111">Permissions</span></span>  
 <span data-ttu-id="3fde9-112">Erfordert die Mitgliedschaft in der PolicyAdministratorRole-Rolle in der msdb-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="3fde9-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3fde9-113">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3fde9-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-all-of-the-facets-in-an-object"></a><span data-ttu-id="3fde9-114">So zeigen Sie alle Facets in einem Objekt an</span><span class="sxs-lookup"><span data-stu-id="3fde9-114">To view all of the facets in an object</span></span>  
  
1.  <span data-ttu-id="3fde9-115">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ein Instanzobjekt, eine Datenbank oder ein Datenbankobjekt, und klicken Sie dann auf **Facets**.</span><span class="sxs-lookup"><span data-stu-id="3fde9-115">In Object Explorer, right-click an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], instance object, database, or database object, and then click **Facets**.</span></span>  
  
2.  <span data-ttu-id="3fde9-116">Wählen Sie im Dialogfeld **Facetten anzeigen-**_object_name_ in der **Facetten** Liste eine Facette aus, um die zugehörigen Eigenschaften anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3fde9-116">In the **View Facets -**_object_name_ dialog box, in the **Facet** list, select a facet to view its properties.</span></span> <span data-ttu-id="3fde9-117">Weitere Informationen zu den Optionen in diesem Dialogfeld finden Sie unter [View Facets Dialog Box](view-facets-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="3fde9-117">For more information on the available options in this dialog box, see [View Facets Dialog Box](view-facets-dialog-box.md).</span></span>  
  
3.  <span data-ttu-id="3fde9-118">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3fde9-118">When finished, click **OK**.</span></span>  
  
  
