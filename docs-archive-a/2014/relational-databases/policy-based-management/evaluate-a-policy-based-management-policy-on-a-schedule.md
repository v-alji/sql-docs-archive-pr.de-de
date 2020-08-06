---
title: Auswerten einer Richtlinie der richtlinienbasierten Verwaltung nach einem Zeitplan | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, evaluate policy
ms.assetid: bea09522-ff47-4037-ab55-a98ea7c10099
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f1c6b1a7d13d14c02f4b4e537c2dbdb2df39d02c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699459"
---
# <a name="evaluate-a-policy-based-management-policy-on-a-schedule"></a><span data-ttu-id="e370b-102">Auswerten einer Richtlinie der richtlinienbasierten Verwaltung nach einem Zeitplan</span><span class="sxs-lookup"><span data-stu-id="e370b-102">Evaluate a Policy-Based Management Policy on a Schedule</span></span>
  <span data-ttu-id="e370b-103">In diesem Thema wird beschrieben, wie Sie eine Richtlinie der richtlinienbasierten Verwaltung mithilfe von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] nach einem Zeitplan in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]auswerten.</span><span class="sxs-lookup"><span data-stu-id="e370b-103">This topic describes how to evaluate a Policy-Based Management policy on a schedule in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="e370b-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="e370b-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e370b-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="e370b-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e370b-106">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e370b-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e370b-107">**Auswerten einer Richtlinie nach einem Zeitplan mit:**</span><span class="sxs-lookup"><span data-stu-id="e370b-107">**To evaluate a policy on a schedule, using:**</span></span>  
  
     [<span data-ttu-id="e370b-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e370b-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e370b-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="e370b-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e370b-110">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e370b-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e370b-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e370b-111">Permissions</span></span>  
 <span data-ttu-id="e370b-112">Erfordert die Mitgliedschaft in der PolicyAdministratorRole-Rolle in der msdb-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="e370b-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e370b-113">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e370b-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-evaluate-a-policy-on-a-schedule"></a><span data-ttu-id="e370b-114">So werten Sie eine Richtlinie nach einem Zeitplan aus</span><span class="sxs-lookup"><span data-stu-id="e370b-114">To evaluate a policy on a schedule</span></span>  
  
1.  <span data-ttu-id="e370b-115">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, in dem der auszuwertende Richtlinienzeitplan enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="e370b-115">In **Object Explorer**, click the plus sign to expand the server that contains the policy schedule that you want to evaluate.</span></span>  
  
2.  <span data-ttu-id="e370b-116">Klicken Sie auf das Pluszeichen, um den Ordner **Verwaltung** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="e370b-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="e370b-117">Klicken Sie auf das Pluszeichen, um **Richtlinienverwaltung**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="e370b-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="e370b-118">Klicken Sie auf das Pluszeichen, um den Ordner **Richtlinien** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="e370b-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="e370b-119">Klicken Sie mit der rechten Maustaste auf die Richtlinie, deren Zeitplan Sie auswerten möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="e370b-119">Right-click the policy whose schedule you what to evaluate and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="e370b-120">Klicken Sie im Dialogfeld **Richtlinie öffnen**_Richtlinienname_ in der Liste **Auswertungsmodus** auf die Option **Nach Zeitplan**.</span><span class="sxs-lookup"><span data-stu-id="e370b-120">On the **Open Policy -**_policy_name_ dialog box, in the **Evaluation Mode** list, select **On schedule**.</span></span>  
  
7.  <span data-ttu-id="e370b-121">Klicken Sie unter **Zeitplan**auf **Auswählen** , um einen vorhandenen Zeitplan anzugeben, oder klicken Sie auf **Neu** , um einen neuen Zeitplan zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e370b-121">Under **Schedule**, click either **Pick** to specify an existing schedule or **New** to create a new schedule.</span></span>  
  
8.  <span data-ttu-id="e370b-122">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e370b-122">When finished, click **OK**.</span></span>  
  
  
