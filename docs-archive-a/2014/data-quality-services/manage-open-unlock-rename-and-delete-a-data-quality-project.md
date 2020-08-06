---
title: Verwalten (öffnen, entsperren, umbenennen und löschen) eines Data Quality-Projekts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.dqproject.opendqproject.f1
helpviewer_keywords:
- data quality project,delete
- data quality project,rename
- data quality project,unlock
- data quality project,open
ms.assetid: de8a2b04-4673-4beb-b4cf-96a28cdf3a93
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 216c95937676954c509890b879abdee8f55b778c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621673"
---
# <a name="manage-open-unlock-rename-and-delete-a-data-quality-project"></a><span data-ttu-id="59cdf-102">Verwalten von Data Quality-Projekten (Öffnen, Entsperren, Umbenennen, Löschen)</span><span class="sxs-lookup"><span data-stu-id="59cdf-102">Manage (Open, Unlock, Rename, and Delete) a Data Quality Project</span></span>
  <span data-ttu-id="59cdf-103">In diesem Thema wird beschrieben, wie ein Data Quality-Projekt mithilfe von [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] verwaltet wird, zum Beispiel das Öffnen, Entsperren, Umbenennen und Löschen eines Data Quality-Projekts.</span><span class="sxs-lookup"><span data-stu-id="59cdf-103">This topic describes how to manage a data quality project by using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] such as open, unlock, rename, and delete a data quality project.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="59cdf-104">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="59cdf-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="59cdf-105">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="59cdf-105">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="59cdf-106">Sie können kein gesperrtes Projekt öffnen, das von einem anderen Benutzer erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="59cdf-106">You cannot open a locked project that is created by another user.</span></span>  
  
-   <span data-ttu-id="59cdf-107">Sie können kein Data Quality-Projekt entsperren, umbenennen oder löschen, das von einem anderen Benutzer erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="59cdf-107">You cannot unlock, rename, or delete a data quality project that is created by another user.</span></span>  
  
-   <span data-ttu-id="59cdf-108">Sie können kein gesperrtes Data Quality-Projekt löschen.</span><span class="sxs-lookup"><span data-stu-id="59cdf-108">You cannot delete a locked data quality project.</span></span> <span data-ttu-id="59cdf-109">Zum Löschen müssen Sie es zunächst entsperren.</span><span class="sxs-lookup"><span data-stu-id="59cdf-109">You must first unlock it to delete.</span></span>  
  
-   <span data-ttu-id="59cdf-110">Sie können nur ein Data Quality-Projekt entsperren, das von Ihnen erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="59cdf-110">You can only unlock a data quality project that is created by you.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="59cdf-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="59cdf-111">Prerequisites</span></span>  
 <span data-ttu-id="59cdf-112">Sie müssen mindestens ein Data Quality-Projekt verwalten.</span><span class="sxs-lookup"><span data-stu-id="59cdf-112">You must have at least one data quality project to manage.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="59cdf-113">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="59cdf-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="59cdf-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="59cdf-114">Permissions</span></span>  
 <span data-ttu-id="59cdf-115">Sie müssen über die Rolle „dqs_kb_editor“ oder „dqs_kb_operator“ in der Datenbank DQS_MAIN verfügen, um ein Data Quality-Projekt zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="59cdf-115">You must have the dqs_kb_editor or dqs_kb_operator role on the DQS_MAIN database to manage a data quality project.</span></span>  
  
##  <a name="open-a-data-quality-project"></a><a name="Open"></a> <span data-ttu-id="59cdf-116">Öffnen eines Data Quality-Projekts</span><span class="sxs-lookup"><span data-stu-id="59cdf-116">Open a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="59cdf-117">[Führen Sie die Data Quality-Client Anwendung](../../2014/data-quality-services/run-the-data-quality-client-application.md)aus.</span><span class="sxs-lookup"><span data-stu-id="59cdf-117">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="59cdf-118">Klicken Sie im [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Startbildschirm auf **Data Quality-Projekt öffnen**.</span><span class="sxs-lookup"><span data-stu-id="59cdf-118">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="59cdf-119">Der Bildschirm **Projekt öffnen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="59cdf-119">The **Open project** screen appears.</span></span>  
  
     <span data-ttu-id="59cdf-120">Sie können ein unter **Zuletzt verwendetes Data Quality-Projekt** aufgelistetes Data Quality-Projekt auch direkt öffnen, indem Sie darauf klicken.</span><span class="sxs-lookup"><span data-stu-id="59cdf-120">Alternately, you can directly open a data quality project listed under **Recent data quality project** area by clicking it.</span></span>  
  
3.  <span data-ttu-id="59cdf-121">Wählen Sie auf dem Bildschirm **Projekt öffnen** das zu öffnende Data Quality-Projekt durch Klicken aus, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="59cdf-121">In the **Open project** screen, click to select the data quality project that you want to open, and click **Next**.</span></span>  
  
4.  <span data-ttu-id="59cdf-122">Das Data Quality-Projekt wird mit demselben Aktivitätsstatus geöffnet, mit dem es zuletzt geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="59cdf-122">The data quality project opens at the same state of the activity where it was last closed.</span></span> <span data-ttu-id="59cdf-123">Ein Data Quality-Projekt hat die folgenden Status:</span><span class="sxs-lookup"><span data-stu-id="59cdf-123">A data quality project has the following states:</span></span>  
  
    -   <span data-ttu-id="59cdf-124">Für die Bereinigungs **Aktivität kann** ein Data Quality-Projekt die folgenden Zustände aufweisen: **Bereinigung-** zuordnen, **Bereinigung-** bereinigen, **Bereinigung-Ergebnisse verwalten und anzeigen**und **Bereinigung-Export**.</span><span class="sxs-lookup"><span data-stu-id="59cdf-124">For the **Cleansing** activity, a data quality project can have the following states: **Cleansing - Map**, **Cleansing - Cleanse**, **Cleansing - Manage and View Results**, and **Cleansing - Export**.</span></span>  
  
    -   <span data-ttu-id="59cdf-125">Für die **Matching** abgleichsaktivität kann ein Data Quality-Projekt die folgenden Zustände aufweisen: " **Matching-Map**", " **Matching-Matching**", " **Matching-vorship**" und " **Matching-Export**".</span><span class="sxs-lookup"><span data-stu-id="59cdf-125">For the **Matching** activity, a data quality project can have the following states: **Matching - Map**, **Matching - Matching**, **Matching - Survivorship**, and **Matching - Export**.</span></span>  
  
##  <a name="unlock-a-data-quality-project"></a><a name="Unlock"></a> <span data-ttu-id="59cdf-126">Entsperren eines Data Quality-Projekts</span><span class="sxs-lookup"><span data-stu-id="59cdf-126">Unlock a Data Quality Project</span></span>  
 <span data-ttu-id="59cdf-127">Wenn Sie ein Data Quality-Projekt erstellen, ist es gesperrt, um zu verhindern, dass es von anderen Benutzern verwendet oder geändert wird.</span><span class="sxs-lookup"><span data-stu-id="59cdf-127">When you create a data quality project, it is in a locked state to prevent usage or modification by other users.</span></span> <span data-ttu-id="59cdf-128">Sie müssen das Data Quality-Projekt entsperren, nachdem Sie die Arbeit abgeschlossen haben, wenn Sie möchten, dass andere Benutzer am Data Quality-Projekt arbeiten können.</span><span class="sxs-lookup"><span data-stu-id="59cdf-128">You must unlock the data quality project after you have completed your work if you want other users to work on your data quality project.</span></span> <span data-ttu-id="59cdf-129">Ein Schlosssymbol wird für gesperrte Projekte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="59cdf-129">A lock symbol is displayed for projects that are locked.</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="59cdf-130">[Führen Sie die Data Quality-Client Anwendung](../../2014/data-quality-services/run-the-data-quality-client-application.md)aus.</span><span class="sxs-lookup"><span data-stu-id="59cdf-130">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="59cdf-131">Klicken Sie im [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Startbildschirm auf **Data Quality-Projekt öffnen**.</span><span class="sxs-lookup"><span data-stu-id="59cdf-131">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="59cdf-132">Der Bildschirm **Projekt öffnen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="59cdf-132">The **Open project** screen appears.</span></span>  
  
3.  <span data-ttu-id="59cdf-133">Klicken Sie auf dem Bildschirm **Projekt öffnen** mit der rechten Maustaste auf ein gesperrtes Data Quality-Projekt, das von Ihnen erstellt wurde, und klicken Sie dann im Kontextmenü auf **Entsperren** .</span><span class="sxs-lookup"><span data-stu-id="59cdf-133">In the **Open project** screen, right-click a locked data quality project that is created by you, and then click **Unlock** in the shortcut menu.</span></span> <span data-ttu-id="59cdf-134">Ein grünes Häkchen wird für das Projekt angezeigt, das angibt, dass es entsperrt wurde.</span><span class="sxs-lookup"><span data-stu-id="59cdf-134">A green check mark is displayed for the project indicating that it is unlocked.</span></span>  
  
##  <a name="rename-a-data-quality-project"></a><a name="Rename"></a><span data-ttu-id="59cdf-135">Umbenennen eines Data Quality-Projekts</span><span class="sxs-lookup"><span data-stu-id="59cdf-135">Rename a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="59cdf-136">[Führen Sie die Data Quality-Client Anwendung](../../2014/data-quality-services/run-the-data-quality-client-application.md)aus.</span><span class="sxs-lookup"><span data-stu-id="59cdf-136">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="59cdf-137">Klicken Sie im [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Startbildschirm auf **Data Quality-Projekt öffnen**.</span><span class="sxs-lookup"><span data-stu-id="59cdf-137">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="59cdf-138">Der Bildschirm **Projekt öffnen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="59cdf-138">The **Open project** screen appears.</span></span>  
  
3.  <span data-ttu-id="59cdf-139">Klicken Sie auf dem Bildschirm **Projekt öffnen** mit der rechten Maustaste auf ein Data Quality-Projekt, das von Ihnen erstellt wurde, und klicken Sie dann im Kontextmenü auf **Umbenennen** .</span><span class="sxs-lookup"><span data-stu-id="59cdf-139">In the **Open project** screen, right-click a data quality project that is created by you, and then click **Rename** in the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="59cdf-140">Der Name des Data Quality-Projekts kann in der Spalte **Name** bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="59cdf-140">The data quality project name becomes editable in the **Name** column.</span></span> <span data-ttu-id="59cdf-141">Heben Sie einen neuen Namen ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="59cdf-141">Type a new name, and then press Enter.</span></span>  
  
##  <a name="delete-a-data-quality-project"></a><a name="Delete"></a><span data-ttu-id="59cdf-142">Löschen eines Data Quality-Projekts</span><span class="sxs-lookup"><span data-stu-id="59cdf-142">Delete a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="59cdf-143">[Führen Sie die Data Quality-Client Anwendung](../../2014/data-quality-services/run-the-data-quality-client-application.md)aus.</span><span class="sxs-lookup"><span data-stu-id="59cdf-143">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="59cdf-144">Klicken Sie im [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Startbildschirm auf **Data Quality-Projekt öffnen**.</span><span class="sxs-lookup"><span data-stu-id="59cdf-144">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="59cdf-145">Der Bildschirm **Projekt öffnen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="59cdf-145">The **Open project** screen appears.</span></span>  
  
3.  <span data-ttu-id="59cdf-146">Klicken Sie auf dem Bildschirm **Projekt öffnen** mit der rechten Maustaste auf ein entsperrtes Data Quality-Projekt, das von Ihnen erstellt wurde, und klicken Sie dann im Kontextmenü auf **Löschen** .</span><span class="sxs-lookup"><span data-stu-id="59cdf-146">In the **Open project** screen, right-click an unlocked data quality project that is created by you, and then click **Delete** in the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="59cdf-147">Eine Bestätigungsmeldung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="59cdf-147">A confirmation message appears.</span></span> <span data-ttu-id="59cdf-148">Klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="59cdf-148">Click **Yes**.</span></span>  
  
  
