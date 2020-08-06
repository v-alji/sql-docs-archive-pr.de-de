---
title: Erstellen einer Richtlinie der richtlinienbasierten Verwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, creating policies
ms.assetid: b28bf963-89f9-4941-b6c1-6004fec347f1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e76b4dce17e00bae5e8ca4fcf071868c0641c786
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618669"
---
# <a name="create-a-policy-based-management-policy"></a><span data-ttu-id="091d5-102">Erstellen einer Richtlinie der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="091d5-102">Create a Policy-Based Management Policy</span></span>
  <span data-ttu-id="091d5-103">In diesem Thema wird beschrieben, wie Sie eine Richtlinie der richtlinienbasierten Verwaltung mithilfe von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]erstellen.</span><span class="sxs-lookup"><span data-stu-id="091d5-103">This topic describes how to create a Policy-Based Management policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="091d5-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="091d5-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="091d5-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="091d5-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="091d5-106">Security</span><span class="sxs-lookup"><span data-stu-id="091d5-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="091d5-107">**Erstellen einer Richtlinie mit:**</span><span class="sxs-lookup"><span data-stu-id="091d5-107">**To create a policy, using:**</span></span>  
  
     [<span data-ttu-id="091d5-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="091d5-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="091d5-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="091d5-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="091d5-110">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="091d5-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="091d5-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="091d5-111">Permissions</span></span>  
 <span data-ttu-id="091d5-112">Erfordert die Mitgliedschaft in der PolicyAdministratorRole-Rolle in der msdb-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="091d5-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="091d5-113">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="091d5-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-policy"></a><span data-ttu-id="091d5-114">So erstellen Sie eine Richtlinie</span><span class="sxs-lookup"><span data-stu-id="091d5-114">To create a policy</span></span>  
  
1.  <span data-ttu-id="091d5-115">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, auf dem Sie eine neue Richtlinie der richtlinienbasierten Verwaltung erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="091d5-115">In **Object Explorer**, click the plus sign to expand the server where you want to create a new a Policy-Based Management policy.</span></span>  
  
2.  <span data-ttu-id="091d5-116">Klicken Sie auf das Pluszeichen, um den Ordner **Verwaltung** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="091d5-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="091d5-117">Klicken Sie auf das Pluszeichen, um **Richtlinienverwaltung**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="091d5-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="091d5-118">Klicken Sie mit der rechten Maustaste auf den Ordner **Richtlinien** , und wählen Sie **Neue Richtlinie**aus.</span><span class="sxs-lookup"><span data-stu-id="091d5-118">Right-click the **Policies** folder and select **New Policy**.</span></span>  
  
5.  <span data-ttu-id="091d5-119">Geben Sie im Dialogfeld **Neue Richtlinie erstellen** im Feld **Name** den Namen der neuen Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="091d5-119">In the **Create New Policy** dialog box, in the **Name** box, type the name of the new policy.</span></span>  
  
6.  <span data-ttu-id="091d5-120">Wenn die Richtlinie sofort nach dem Erstellen aktiviert werden soll, aktivieren Sie das Kontrollkästchen **Aktiviert** .</span><span class="sxs-lookup"><span data-stu-id="091d5-120">If you want the policy to be enabled as soon as it is created, select the **Enabled** check box.</span></span> <span data-ttu-id="091d5-121">Wenn der Auswertungsmodus **Bedarfsgesteuert**lautet, ist das Kontrollkästchen **Aktiviert** nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="091d5-121">If the evaluation mode is **On demand**, the **Enabled** check box is not available.</span></span>  
  
7.  <span data-ttu-id="091d5-122">Wählen Sie in der Liste **Bedingung überprüfen** eine der vorhandenen Bedingungen aus, oder wählen Sie **Neue Bedingung**aus.</span><span class="sxs-lookup"><span data-stu-id="091d5-122">In the **Check condition** list, select one of the existing conditions, or select **New Condition**.</span></span> <span data-ttu-id="091d5-123">Zum Bearbeiten einer Bedingung wählen Sie die Bedingung aus und klicken dann auf die Schaltfläche mit den Auslassungspunkten ( **...** ). Weitere Informationen finden Sie unter [Erstellen einer neuen Bedingung der richtlinienbasierten Verwaltung](create-a-new-policy-based-management-condition.md) oder [Anzeigen oder Ändern der Eigenschaften einer Bedingung der richtlinienbasierten Verwaltung](view-or-modify-the-properties-of-a-policy-based-management-condition.md).</span><span class="sxs-lookup"><span data-stu-id="091d5-123">To edit a condition, select the condition and then click the ellipsis (**...**). For more information, see [Create a New Policy-Based Management Condition](create-a-new-policy-based-management-condition.md) or [View or Modify the Properties of a Policy-Based Management Condition](view-or-modify-the-properties-of-a-policy-based-management-condition.md).</span></span>  
  
8.  <span data-ttu-id="091d5-124">Wählen Sie im Feld **Für Ziele** einen oder mehrere Zieltypen für diese Richtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="091d5-124">In the **Against targets** box, select one or more target types for this policy.</span></span> <span data-ttu-id="091d5-125">Einige Bedingungen und Facets können nur auf bestimmte Zieltypen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="091d5-125">Some conditions and facets can only be applied to certain types of targets.</span></span> <span data-ttu-id="091d5-126">Die verfügbaren Zielsätze werden im zugeordneten Feld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="091d5-126">The available target sets appear in the associated box.</span></span> <span data-ttu-id="091d5-127">Erweitern Sie **Alle** , um eine Filterbedingung für bestimmte Zieltypen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="091d5-127">Expand **Every** to select a filtering condition for some types of the targets.</span></span> <span data-ttu-id="091d5-128">Wenn keine Ziele in diesem Feld angezeigt werden, wird die Prüfungsbedingung auf Serverebene bewertet.</span><span class="sxs-lookup"><span data-stu-id="091d5-128">If no targets appear in this box, the check condition is scoped at the server level.</span></span>  
  
9. <span data-ttu-id="091d5-129">Legen Sie im Feld **Auswertungsmodus** fest, wie sich diese Richtlinie verhalten soll.</span><span class="sxs-lookup"><span data-stu-id="091d5-129">In the **Evaluation Mode** box, select how this policy will behave.</span></span> <span data-ttu-id="091d5-130">Verschiedene Bedingungen können verschiedene gültige Auswertungsmodi haben.</span><span class="sxs-lookup"><span data-stu-id="091d5-130">Different conditions can have different valid evaluation modes.</span></span> <span data-ttu-id="091d5-131">Weitere Informationen darüber, welche Auswertungsmodi gültig sind, finden Sie unter [Verwalten von Servern mit der richtlinienbasierten Verwaltung](administer-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="091d5-131">For more information about which evaluation modes are valid, see [Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md).</span></span>  
  
10. <span data-ttu-id="091d5-132">Wenn die Richtlinie nach einem Zeitplan ausgewertet werden soll, legen Sie den Auswertungsmodus auf **Nach Zeitplan**fest, und klicken Sie dann auf **Auswählen** , um einen Zeitplan auszuwählen, oder auf **Neu** , um einen neuen Zeitplan zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="091d5-132">If the policy will be evaluated on a schedule, set the evaluation mode to **On schedule**, and then click **Pick** to select a schedule, or click **New** to create a new schedule.</span></span>  
  
11. <span data-ttu-id="091d5-133">Zur Beschränkung der Richtlinie auf eine Teilmenge der Zieltypen treffen Sie im Feld **Serverbeschränkung** eine Auswahl aus den beschränkenden Bedingungen, oder erstellen Sie eine neue Bedingung.</span><span class="sxs-lookup"><span data-stu-id="091d5-133">To limit the policy to subset of the target types, in the **Server restriction** box, select from limiting conditions or create a new condition.</span></span>  
  
     <span data-ttu-id="091d5-134">Weitere Informationen zu den Optionen im Dialogfeld **Neue Richtlinie erstellen** finden Sie unter [Dialogfeld 'Neue Richtlinie erstellen' oder 'Richtlinie öffnen', Seite 'Allgemein'](../../integration-services/general-page-of-integration-services-designers-options.md) oder [Dialogfeld 'Neue Richtlinie erstellen' oder 'Richtlinie öffnen', Seite 'Beschreibung'](create-new-policy-or-open-policy-dialog-box-description-page.md).</span><span class="sxs-lookup"><span data-stu-id="091d5-134">For more information on the available options in the **Create New Policy** dialog box, see [Create New Policy or Open Policy Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md) or [Create New Policy or Open Policy Dialog Box, Description Page](create-new-policy-or-open-policy-dialog-box-description-page.md).</span></span>  
  
12. <span data-ttu-id="091d5-135">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="091d5-135">When finished click **OK**.</span></span>  
  
  
