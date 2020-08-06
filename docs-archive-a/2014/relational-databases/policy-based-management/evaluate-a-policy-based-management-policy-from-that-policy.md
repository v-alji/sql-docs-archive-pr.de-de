---
title: Auswerten einer Richtlinie der richtlinienbasierten Verwaltung von der Richtlinie aus | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, evaluate policy
ms.assetid: 0b3214bd-d0ab-45ab-9281-3d95507abe54
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 207c86f1465c49238fc9b50ee75489b43d956caf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619775"
---
# <a name="evaluate-a-policy-based-management-policy-from-that-policy"></a><span data-ttu-id="0a6ab-102">Auswerten einer Richtlinie der richtlinienbasierten Verwaltung von der Richtlinie aus</span><span class="sxs-lookup"><span data-stu-id="0a6ab-102">Evaluate a Policy-Based Management Policy from That Policy</span></span>
  <span data-ttu-id="0a6ab-103">In diesem Thema wird beschrieben, wie Sie eine Richtlinie auswerten, indem diese Richtlinie in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0a6ab-103">This topic describes how to evaluate a policy using that policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="0a6ab-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="0a6ab-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0a6ab-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="0a6ab-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0a6ab-106">Security</span><span class="sxs-lookup"><span data-stu-id="0a6ab-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0a6ab-107">**Auswerten einer Richtlinie mit:**</span><span class="sxs-lookup"><span data-stu-id="0a6ab-107">**To evaluate a policy, using:**</span></span>  
  
     [<span data-ttu-id="0a6ab-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0a6ab-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0a6ab-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="0a6ab-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0a6ab-110">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="0a6ab-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0a6ab-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="0a6ab-111">Permissions</span></span>  
 <span data-ttu-id="0a6ab-112">Erfordert die Mitgliedschaft in der PolicyAdministratorRole-Rolle in der msdb-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="0a6ab-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0a6ab-113">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0a6ab-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-evaluate-a-policy"></a><span data-ttu-id="0a6ab-114">So werten Sie eine Richtlinie aus</span><span class="sxs-lookup"><span data-stu-id="0a6ab-114">To evaluate a policy</span></span>  
  
1.  <span data-ttu-id="0a6ab-115">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, in dem die auszuwertende Richtlinie enthalten ist</span><span class="sxs-lookup"><span data-stu-id="0a6ab-115">In **Object Explorer**, click the plus sign to expand the server that contains the policy that you want to evaluate.</span></span>  
  
2.  <span data-ttu-id="0a6ab-116">Klicken Sie auf das Pluszeichen, um den Ordner **Verwaltung** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="0a6ab-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="0a6ab-117">Klicken Sie auf das Pluszeichen, um **Richtlinienverwaltung**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="0a6ab-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="0a6ab-118">Klicken Sie auf das Pluszeichen, um den Ordner **Richtlinien** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="0a6ab-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="0a6ab-119">Klicken Sie mit der rechten Maustaste auf die Richtlinie, die Sie auswerten möchten, und wählen Sie **Auswerten**aus.</span><span class="sxs-lookup"><span data-stu-id="0a6ab-119">Right-click the policy that you want to evaluate and select **Evaluate**.</span></span>  
  
6.  <span data-ttu-id="0a6ab-120">Im Dialogfeld **Ergebnisse auswerten**  werden die Ergebnisse der Richtlinienauswertung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0a6ab-120">In the **Evaluate Results**  dialog box, you see the results of the policy evaluation.</span></span> <span data-ttu-id="0a6ab-121">Für Ziele, die mit der Richtlinie nicht übereinstimmen und die Eigenschaften besitzen, die von der richtlinienbasierten Verwaltung neu konfiguriert werden können, erzwingen Sie die Einhaltung, indem Sie auf **Anwenden**klicken.</span><span class="sxs-lookup"><span data-stu-id="0a6ab-121">For targets that do not comply with the policy and have properties that can be reconfigured by Policy-Based Management, you can enforce compliance by clicking **Apply**.</span></span> <span data-ttu-id="0a6ab-122">Weitere Informationen zu den Optionen im Dialogfeld **Richtlinien auswerten** finden Sie unter [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md) und [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md).</span><span class="sxs-lookup"><span data-stu-id="0a6ab-122">For more information on the available options in the **Evaluate Policies** dialog box, see [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md) and [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md).</span></span>  
  
7.  <span data-ttu-id="0a6ab-123">Wenn Sie fertig sind, klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="0a6ab-123">When finished, click **Close**.</span></span>  
  
  
