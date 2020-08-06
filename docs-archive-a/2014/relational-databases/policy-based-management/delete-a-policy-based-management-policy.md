---
title: Löschen einer Richtlinie der richtlinienbasierten Verwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, delete policies
ms.assetid: 488f0305-190c-4223-aa5c-e9bd43b520eb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c43bc3cdf4a7a5b5d9268bbd7e68506616d1f0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695570"
---
# <a name="delete-a-policy-based-management-policy"></a><span data-ttu-id="919bc-102">Löschen einer Richtlinie der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="919bc-102">Delete a Policy-Based Management Policy</span></span>
  <span data-ttu-id="919bc-103">In diesem Thema wird beschrieben, wie Sie eine Richtlinie der richtlinienbasierten Verwaltung mithilfe von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] in [!INCLUDE[tsql](../../includes/tsql-md.md)]löschen.</span><span class="sxs-lookup"><span data-stu-id="919bc-103">This topic describes how to delete a Policy-Based Management policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="919bc-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="919bc-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="919bc-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="919bc-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="919bc-106">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="919bc-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="919bc-107">**Löschen einer Richtlinie mit:**</span><span class="sxs-lookup"><span data-stu-id="919bc-107">**To delete a policy, using:**</span></span>  
  
     [<span data-ttu-id="919bc-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="919bc-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="919bc-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="919bc-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="919bc-110">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="919bc-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="919bc-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="919bc-111">Permissions</span></span>  
 <span data-ttu-id="919bc-112">Erfordert die Mitgliedschaft in der PolicyAdministratorRole-Rolle in der msdb-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="919bc-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="919bc-113">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="919bc-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-policy"></a><span data-ttu-id="919bc-114">So löschen Sie eine Richtlinie</span><span class="sxs-lookup"><span data-stu-id="919bc-114">To delete a policy</span></span>  
  
1.  <span data-ttu-id="919bc-115">Klicken Sie im Objekt-Explorer auf das Pluszeichen, um den Server zu erweitern, in dem die zu löschende Richtlinie der richtlinienbasierten Verwaltung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="919bc-115">In Object Explorer, click the plus sign to expand the server that contains the Policy-Based Management policy that you want to delete.</span></span>  
  
2.  <span data-ttu-id="919bc-116">Klicken Sie auf das Pluszeichen, um den Ordner **Verwaltung** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="919bc-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="919bc-117">Klicken Sie auf das Pluszeichen, um **Richtlinienverwaltung**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="919bc-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="919bc-118">Klicken Sie auf das Pluszeichen, um den Ordner **Richtlinien** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="919bc-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="919bc-119">Klicken Sie mit der rechten Maustaste auf die zu löschende Richtlinie, und klicken Sie anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="919bc-119">Right-click the policy that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="919bc-120">Stellen Sie im Dialogfeld **Objekt löschen** sicher, dass die richtige Bedingung ausgewählt ist, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="919bc-120">In the **Delete Object** dialog box, ensure that the correct condition is selected and then click **OK**.</span></span>  
  
  
