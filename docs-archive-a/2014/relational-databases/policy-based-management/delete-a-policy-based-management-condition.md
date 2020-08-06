---
title: Löschen einer Bedingung der richtlinienbasierten Verwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, delete policy conditions
ms.assetid: e04148b8-f6dd-4c50-a5ef-c650b71dbf4d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f02a5294ecb53db4d8baa4f3dae0a232d9551a13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608594"
---
# <a name="delete-a-policy-based-management-condition"></a><span data-ttu-id="c3807-102">Löschen einer Bedingung der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="c3807-102">Delete a Policy-Based Management Condition</span></span>
  <span data-ttu-id="c3807-103">In diesem Thema wird beschrieben, wie Sie eine Bedingung der richtlinienbasierten Verwaltung mithilfe von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]ändern.</span><span class="sxs-lookup"><span data-stu-id="c3807-103">This topic describes how to delete a Policy-based Management condition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="c3807-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="c3807-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c3807-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="c3807-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c3807-106">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c3807-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c3807-107">**Löschen einer Bedingung mit:**</span><span class="sxs-lookup"><span data-stu-id="c3807-107">**To delete a condition, using:**</span></span>  
  
     [<span data-ttu-id="c3807-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c3807-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c3807-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="c3807-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c3807-110">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c3807-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c3807-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c3807-111">Permissions</span></span>  
 <span data-ttu-id="c3807-112">Erfordert die Mitgliedschaft in der PolicyAdministratorRole-Rolle in der msdb-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="c3807-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c3807-113">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c3807-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-condition"></a><span data-ttu-id="c3807-114">So löschen Sie eine Bedingung</span><span class="sxs-lookup"><span data-stu-id="c3807-114">To delete a condition</span></span>  
  
1.  <span data-ttu-id="c3807-115">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, in dem die zu löschende Bedingung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="c3807-115">In **Object Explorer**, click the plus sign to expand the server that contains the condition that you want to delete.</span></span>  
  
2.  <span data-ttu-id="c3807-116">Klicken Sie auf das Pluszeichen, um den Ordner **Verwaltung** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="c3807-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="c3807-117">Klicken Sie auf das Pluszeichen, um **Richtlinienverwaltung**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="c3807-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="c3807-118">Klicken Sie auf das Pluszeichen, um den Ordner **Bedingungen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="c3807-118">Click the plus sign to expand the **Conditions** folder.</span></span>  
  
5.  <span data-ttu-id="c3807-119">Klicken Sie mit der rechten Maustaste auf die Bedingung, die Sie löschen möchten, und wählen Sie **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="c3807-119">Right-click the condition that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="c3807-120">Stellen Sie im Dialogfeld **Objekt löschen** sicher, dass die richtige Bedingung ausgewählt ist, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3807-120">In the **Delete Object** dialog box, ensure that the correct condition is selected and then click **OK**.</span></span>  
  
  
