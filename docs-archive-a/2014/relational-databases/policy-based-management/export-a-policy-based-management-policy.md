---
title: Exportieren einer Richtlinie der richtlinienbasierten Verwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, export policy
ms.assetid: f0001b33-9078-4432-8460-496736fb325a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 15f554aeeebfd47c3fa1ea13b100fbe6bcfcc055
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618667"
---
# <a name="export-a-policy-based-management-policy"></a><span data-ttu-id="3e2c9-102">Exportieren einer Richtlinie der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="3e2c9-102">Export a Policy-Based Management Policy</span></span>
  <span data-ttu-id="3e2c9-103">In diesem Thema wird beschrieben, wie Sie eine Richtlinie der richtlinienbasierten Verwaltung mithilfe von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]exportieren.</span><span class="sxs-lookup"><span data-stu-id="3e2c9-103">This topic describes how to export a Policy-Based Management policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="3e2c9-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="3e2c9-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3e2c9-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="3e2c9-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3e2c9-106">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3e2c9-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3e2c9-107">**Exportieren einer Richtlinie mit:**</span><span class="sxs-lookup"><span data-stu-id="3e2c9-107">**To export a policy, using:**</span></span>  
  
     [<span data-ttu-id="3e2c9-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3e2c9-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3e2c9-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="3e2c9-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3e2c9-110">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3e2c9-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3e2c9-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="3e2c9-111">Permissions</span></span>  
 <span data-ttu-id="3e2c9-112">Erfordert die Mitgliedschaft in der PolicyAdministratorRole-Rolle in der msdb-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="3e2c9-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3e2c9-113">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3e2c9-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-export-a-policy"></a><span data-ttu-id="3e2c9-114">So exportieren Sie eine Richtlinie</span><span class="sxs-lookup"><span data-stu-id="3e2c9-114">To export a policy</span></span>  
  
1.  <span data-ttu-id="3e2c9-115">Klicken Sie im Objekt-Explorer auf das Pluszeichen, um den Server zu erweitern, in dem die zu exportierende Richtlinie der richtlinienbasierten Verwaltung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="3e2c9-115">In Object Explorer, click the plus sign to expand the server that contains the Policy-Based Management policy that you want to export.</span></span>  
  
2.  <span data-ttu-id="3e2c9-116">Klicken Sie auf das Pluszeichen, um den Ordner **Verwaltung** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="3e2c9-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="3e2c9-117">Klicken Sie auf das Pluszeichen, um **Richtlinienverwaltung**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="3e2c9-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="3e2c9-118">Klicken Sie auf das Pluszeichen, um den Ordner **Richtlinien** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="3e2c9-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="3e2c9-119">Klicken Sie mit der rechten Maustaste auf die zu exportierende Richtlinie, und wählen Sie **Richtlinie exportieren**aus.</span><span class="sxs-lookup"><span data-stu-id="3e2c9-119">Right-click the policy that you want to export and select **Export Policy**.</span></span>  
  
6.  <span data-ttu-id="3e2c9-120">Geben Sie im Dialogfeld **Richtlinie exportieren** den Pfad und den Namen der Datei in der Adressleiste ein.</span><span class="sxs-lookup"><span data-stu-id="3e2c9-120">In the **Export Policy** dialog box, type the path and name of the file in the address bar.</span></span> <span data-ttu-id="3e2c9-121">Suchen Sie alternativ im Navigationsbereich des Dialogfelds einen geeigneten Speicherort für die Datei, und geben Sie den Namen der XML-Datei in das Feld **Dateiname** ein.</span><span class="sxs-lookup"><span data-stu-id="3e2c9-121">Alternately, find a suitable location for the file in the dialog box's navigation pane, and then type the name of the XML file in the **File Name** box.</span></span>  
  
7.  <span data-ttu-id="3e2c9-122">Klicken Sie abschließend auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="3e2c9-122">When finished, click **Save**.</span></span>  
  
  
