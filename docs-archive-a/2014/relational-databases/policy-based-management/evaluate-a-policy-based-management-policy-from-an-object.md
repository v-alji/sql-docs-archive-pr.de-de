---
title: Auswerten einer Richtlinie der richtlinienbasierten Verwaltung von einem Objekt aus | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, evaluate policy
ms.assetid: b9e9d646-4894-4dee-a02a-0c71a8dc020e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f0de02092c87a727b723a5940805f34a75052e5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619773"
---
# <a name="evaluate-a-policy-based-management-policy-from-an-object"></a><span data-ttu-id="50867-102">Auswerten einer Richtlinie der richtlinienbasierten Verwaltung von einem Objekt aus</span><span class="sxs-lookup"><span data-stu-id="50867-102">Evaluate a Policy-Based Management Policy from an Object</span></span>
  <span data-ttu-id="50867-103">In diesem Thema wird beschrieben, wie eine Richtlinie aus einer Serverinstanz, Datenbank oder einem Datenbankobjekt in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="50867-103">This topic describes how to evaluate a policy from a server instance, database, or database object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="50867-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="50867-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="50867-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="50867-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="50867-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="50867-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="50867-107">Security</span><span class="sxs-lookup"><span data-stu-id="50867-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="50867-108">**Auswerten einer Richtlinie aus einem Objekt mit:**</span><span class="sxs-lookup"><span data-stu-id="50867-108">**To evaluate a policy from an object, using:**</span></span>  
  
     [<span data-ttu-id="50867-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="50867-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="50867-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="50867-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="50867-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="50867-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="50867-112">Der Ausführungsmodus wird als Teil der Richtlinie definiert und kann im Dialogfeld **Richtlinien auswerten** nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="50867-112">The execution mode is defined as part of the policy and cannot be changed in the **Evaluate Policies** dialog box.</span></span>  
  
-   <span data-ttu-id="50867-113">Das Dialogfeld **Richtlinien auswerten** zeigt nur Richtlinien an, die für das Datenbankobjekt geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="50867-113">The **Evaluate Policies** dialog box only shows policies appropriate for the database object.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="50867-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="50867-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="50867-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="50867-115">Permissions</span></span>  
 <span data-ttu-id="50867-116">Erfordert die Mitgliedschaft in der PolicyAdministratorRole-Rolle in der msdb-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="50867-116">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="50867-117">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="50867-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-evaluate-a-policy-from-an-object"></a><span data-ttu-id="50867-118">So werten Sie eine Richtlinie für ein Objekt aus</span><span class="sxs-lookup"><span data-stu-id="50867-118">To evaluate a policy from an object</span></span>  
  
1.  <span data-ttu-id="50867-119">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf eine Serverinstanz, eine Datenbank oder ein Datenbankobjekt, zeigen Sie auf **Richtlinien**, und wählen Sie dann **Auswerten**aus.</span><span class="sxs-lookup"><span data-stu-id="50867-119">In Object Explorer, right-click a server instance, a database, or a database object, point to **Policies**, and select **Evaluate**.</span></span>  
  
2.  <span data-ttu-id="50867-120">Wählen Sie im Dialogfeld **Richtlinien auswerten** eine oder mehrere Richtlinien aus, und klicken Sie auf **Auswerten** , um die Richtlinie im Auswertungsmodus auszuführen.</span><span class="sxs-lookup"><span data-stu-id="50867-120">In the **Evaluate Policies** dialog box, select one or more policies and click **Evaluate** to run the policy in evaluation mode.</span></span> <span data-ttu-id="50867-121">Dadurch wird ein Kompatibilitätsbericht für den Zielsatz generiert. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird jedoch nicht neu konfiguriert, und es wird auch keine zukünftige Kompatibilität durchgesetzt.</span><span class="sxs-lookup"><span data-stu-id="50867-121">This generates a compliance report for the target set but does not reconfigure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or enforce future compliance.</span></span> <span data-ttu-id="50867-122">Für Ziele, die mit den ausgewählten Richtlinien nicht übereinstimmen und Eigenschaften besitzen, die von der richtlinienbasierten Verwaltung neu konfiguriert werden können, erzwingen Sie die Richtlinieneinhaltung, indem Sie auf **Anwenden**klicken.</span><span class="sxs-lookup"><span data-stu-id="50867-122">For targets that do not comply with the selected policies and have properties that can be reconfigured by Policy-Based Management, you can enforce policy compliance by clicking **Apply**.</span></span> <span data-ttu-id="50867-123">Weitere Informationen zu den Optionen im Dialogfeld **Richtlinien auswerten** finden Sie unter [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md), [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md)und [Results Detailed View Dialog Box](results-detailed-view-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="50867-123">For more information on the available options in the **Evaluate Policies** dialog box, see [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md), [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md), and [Results Detailed View Dialog Box](results-detailed-view-dialog-box.md).</span></span>  
  
3.  <span data-ttu-id="50867-124">Wenn Sie fertig sind, klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="50867-124">When finished, click **Close**.</span></span>  
  
  
