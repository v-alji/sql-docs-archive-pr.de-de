---
title: Verwalten einer Wissensdatenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 27f306f4-d67c-47f5-b35c-4260cc5d36e3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cc5fdd87ddb3ea687db10a29d7001564fd8ff107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621686"
---
# <a name="manage-a-knowledge-base"></a><span data-ttu-id="8327f-102">Verwalten einer Wissensdatenbank</span><span class="sxs-lookup"><span data-stu-id="8327f-102">Manage a Knowledge Base</span></span>
  <span data-ttu-id="8327f-103">In diesem Thema wird beschrieben, wie Verwaltungsfunktionen für eine Wissensdatenbank in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8327f-103">This topic describes how to perform management functions on a knowledge base in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="8327f-104">Sie können eine Wissensdatenbank löschen, entsperren, umbenennen, vorgenommene Anpassungen verwerfen und die Eigenschaften der Wissensdatenbank anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8327f-104">You can delete a knowledge base, unlock it, discard your work on it, rename it, and display its properties.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8327f-105">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="8327f-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="8327f-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="8327f-106">Prerequisites</span></span>  
 <span data-ttu-id="8327f-107">Um eine Wissensdatenbank zu verwalten, muss die Wissensdatenbank bereits erstellt und entweder veröffentlicht (wenn sie eine andere Person erstellt hat) oder geschlossen (wenn Sie sie erstellt haben) worden sein.</span><span class="sxs-lookup"><span data-stu-id="8327f-107">To manage a knowledge base, the knowledge base must have already been created, and either published (if another person created it) or have been closed (if you created it).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8327f-108">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8327f-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8327f-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8327f-109">Permissions</span></span>  
 <span data-ttu-id="8327f-110">Sie müssen über die Rolle "dqs_kb_editor" oder "dqs_administrator" in der DQS_MAIN-Datenbank verfügen, um eine Wissensdatenbank zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8327f-110">You must have the dqs_kb_editor role or the dqs_administrator on the DQS_MAIN database to open a knowledge base.</span></span>  
  
##  <a name="manage-a-knowledge-base"></a><a name="Manage"></a><span data-ttu-id="8327f-111">Verwalten einer Wissensdatenbank</span><span class="sxs-lookup"><span data-stu-id="8327f-111">Manage a Knowledge Base</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="8327f-112">[Führen Sie die Data Quality-Client Anwendung](../../2014/data-quality-services/run-the-data-quality-client-application.md)aus.</span><span class="sxs-lookup"><span data-stu-id="8327f-112">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="8327f-113">Klicken Sie auf dem [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Startbildschirm auf **Wissensdatenbank öffnen**.</span><span class="sxs-lookup"><span data-stu-id="8327f-113">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open knowledge base**.</span></span>  
  
3.  <span data-ttu-id="8327f-114">Klicken Sie mit der rechten Maustaste auf eine Wissensdatenbank in der Wissensdatenbanktabelle.</span><span class="sxs-lookup"><span data-stu-id="8327f-114">Right-click a knowledge base in the knowledge base table.</span></span>  
  
4.  <span data-ttu-id="8327f-115">Im Kontextmenü können Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="8327f-115">In the context menu, you can do the following:</span></span>  
  
    1.  <span data-ttu-id="8327f-116">**Öffnen**: Klicken Sie auf diese Option, um die Wissensdatenbank in der Aktivität zu öffnen, die im Bereich **Aktivität auswählen** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="8327f-116">**Open**: Click to open the knowledge base in the activity selected in the **Select Activity** pane.</span></span>  
  
    2.  <span data-ttu-id="8327f-117">**Entsperren**: Sie können die Wissensdatenbank entsperren, wenn Sie die Wissensdatenbank im Rahmen der Domänenverwaltungs-, Wissensermittlungs- und Abgleichsrichtlinienaktivitäten bearbeitet und die Wissensdatenbank geschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="8327f-117">**Unlock**: You can unlock the knowledge base if you are the user who was working on the knowledge base in one of the steps of domain management, knowledge discovery, and the matching policy activity, and closed it.</span></span> <span data-ttu-id="8327f-118">Wenn Sie die Wissensdatenbank entsperren, kann sie von einer anderen Person geöffnet und bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="8327f-118">If you unload the knowledge base, another person will be able to open it and work on it.</span></span> <span data-ttu-id="8327f-119">Dieser Befehl ist nicht verfügbar, wenn sich die Wissensdatenbank nicht in einem Aktivitätszustand befindet.</span><span class="sxs-lookup"><span data-stu-id="8327f-119">This command is not available if the knowledge base is not in a state of an activity.</span></span> <span data-ttu-id="8327f-120">Weitere Informationen finden Sie unter [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="8327f-120">For more information, see [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
    3.  <span data-ttu-id="8327f-121">**Arbeit verwerfen**: Klicken Sie auf diese Option, wenn die Wissensdatenbank bearbeitet wird, wie durch einen Eintrag im Feld Status in der Tabelle angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8327f-121">**Discard work**: Click when the knowledge base is in a state of being worked on, as shown with an entry in the State field in the table.</span></span> <span data-ttu-id="8327f-122">Dieser Befehl ist nicht verfügbar, wenn sich die Wissensdatenbank nicht in einem Aktivitätszustand befindet oder wenn die Wissensdatenbank gesperrt ist.</span><span class="sxs-lookup"><span data-stu-id="8327f-122">This command is not available if the knowledge base is not in a state of an activity, and it is not available if the knowledge base is locked.</span></span> <span data-ttu-id="8327f-123">Weitere Informationen finden Sie unter [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="8327f-123">For more information, see [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
    4.  <span data-ttu-id="8327f-124">**Umbenennen**: Klicken Sie auf diese Option, um das Wissensdatenbankfeld der Tabelle für die Wissensdatenbank, auf die Sie mit der rechten Maustaste geklickt haben, bearbeiten zu können.</span><span class="sxs-lookup"><span data-stu-id="8327f-124">**Rename**: Click to make the Knowledge Base field of the table editable for the knowledge base that you right-clicked on.</span></span> <span data-ttu-id="8327f-125">Ändern Sie den Namen, und klicken Sie dann auf diese Wissensdatenbank und eine andere Wissensdatenbank in dem Feld, um die Namensänderung zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="8327f-125">Change the name, and then click on that knowledge base and another one in the field to accept the name change.</span></span>  
  
    5.  <span data-ttu-id="8327f-126">**Löschen**: Klicken Sie auf diese Option, um die Wissensdatenbank aus der DQS_MAIN-Datenbank auf dem [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)]zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="8327f-126">**Delete**: Click to remove the knowledge base from the DQS_MAIN database on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
    6.  <span data-ttu-id="8327f-127">**Eigenschaften**: Klicken Sie auf diese Option, um die Eigenschaften für die Datenbank im schreibgeschützten Modus anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8327f-127">**Properties**: Click to display properties for the database in a read-only display.</span></span>  
  
        1.  <span data-ttu-id="8327f-128">**Quell-Wissensdatenbank**: Wissensdatenbank, auf der diese Datenbank basiert.</span><span class="sxs-lookup"><span data-stu-id="8327f-128">**Source Knowledge Base**: the knowledge base that this database was based on.</span></span> <span data-ttu-id="8327f-129">Diese ist optional.</span><span class="sxs-lookup"><span data-stu-id="8327f-129">This is optional.</span></span>  
  
        2.  <span data-ttu-id="8327f-130">**Status**: Gibt an, ob sich die Wissensdatenbank **In Arbeit** und in einer bestimmten Wissensverwaltungsaktivität befindet. Dabei gilt der Status, als sie zum letzten Mal geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="8327f-130">**State**: Indicates if the knowledge base is **In Work** and if it is in a specific knowledge management activity, as determined when it was last closed.</span></span> <span data-ttu-id="8327f-131">Die Wissensdatenbank kann den Status **In Arbeit**haben – in dem Fall ist sie in einer Wissensverwaltungssitzung, jedoch nicht in einer bestimmten Aktivität geöffnet -, oder sie kann sich im Status **In Arbeit** sowie in einer Wissensverwaltungsaktivität befinden. In dem Fall ist die Wissensdatenbank in einer Wissensverwaltungssitzung und in einer bestimmten Aktivität geöffnet.</span><span class="sxs-lookup"><span data-stu-id="8327f-131">The state can be **In Work**, in which the knowledge base is opened in a knowledge management session, but not in a specific activity, or **In Work** plus a knowledge management activity, in which the knowledge base is opened in a knowledge management session, and in a specific activity.</span></span>  
  
        3.  <span data-ttu-id="8327f-132">**Ist Gesperrt**: Der Wert ist **True** , wenn die Wissensdatenbank gesperrt wurde, und **False** , wenn sie nicht gesperrt wurde.</span><span class="sxs-lookup"><span data-stu-id="8327f-132">**Is Locked**: **True** if the knowledge base was locked, **False** if not</span></span>  
  
        4.  <span data-ttu-id="8327f-133">**Enthält nicht veröffentlichten Inhalt**: Der Wert ist True, wenn die Wissensdatenbank Inhalt enthält, der nicht durch eine Veröffentlichung gespeichert wurde, und False, wenn dies nicht der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="8327f-133">**Contains unpublished content**: True if the knowledge base contains content that has not been saved by publishing, False if not</span></span>  
  
        5.  <span data-ttu-id="8327f-134">**Gesperrt von**: Name des Benutzers, der die Wissensdatenbank geschlossen und dabei gesperrt hat.</span><span class="sxs-lookup"><span data-stu-id="8327f-134">**Locked By**: the name of the user who closed the knowledge base, locking it</span></span>  
  
        6.  <span data-ttu-id="8327f-135">**Sperrdatum**: Datum der Sperrung.</span><span class="sxs-lookup"><span data-stu-id="8327f-135">**Locked Date**: date when locked</span></span>  
  
        7.  <span data-ttu-id="8327f-136">**Erstellt von**: Name des Benutzers, der die Wissensdatenbank erstellt hat, und das entsprechende Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="8327f-136">**Created By**: the name of the user who created the knowledge base, with the network that he or she belongs to</span></span>  
  
        8.  <span data-ttu-id="8327f-137">**Erstellungsdatum**: Datum der Erstellung.</span><span class="sxs-lookup"><span data-stu-id="8327f-137">**Created Date**: date when created</span></span>  
  
##  <a name="follow-up-after-managing-a-knowledge-base"></a><a name="FollowUp"></a><span data-ttu-id="8327f-138">Nachverfolgung: nach dem Verwalten einer Wissensdatenbank</span><span class="sxs-lookup"><span data-stu-id="8327f-138">Follow Up: After Managing a Knowledge Base</span></span>  
 <span data-ttu-id="8327f-139">Der nächste Schritt nach dem Verwalten einer Wissensdatenbank hängt davon ab, welche Aktion Sie für die Wissensdatenbank durchgeführt haben:</span><span class="sxs-lookup"><span data-stu-id="8327f-139">After you manage a knowledge base, your next step depends upon the action you took on the knowledge base:</span></span>  
  
-   <span data-ttu-id="8327f-140">Wenn Sie die Wissensdatenbank geöffnet haben, fahren Sie mit der Aktivität fort, die Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="8327f-140">If you opened the knowledge base, you will continue in the activity that you selected.</span></span>  
  
-   <span data-ttu-id="8327f-141">Wenn Sie die Wissensdatenbank entsperrt haben, kann diese von einer anderen Person im angegebenen Status geöffnet und bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="8327f-141">If you unlocked it, it will be available for another person to open and work on, in the state indicated.</span></span>  
  
-   <span data-ttu-id="8327f-142">Wenn Sie die Anpassungen der Wissensdatenbank verworfen haben, ist sie im zuletzt veröffentlichten Status verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8327f-142">If you discarded the work on it, the knowledge base will be available in its last published state.</span></span>  
  
-   <span data-ttu-id="8327f-143">Wenn Sie die Wissensdatenbank umbenannt haben, müssen Sie die Wissensdatenbank mit dem neuen Namen öffnen, um sie zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="8327f-143">If you renamed it, you will have to open the renamed knowledge base to work on it.</span></span>  
  
-   <span data-ttu-id="8327f-144">Wenn Sie sie löschen, müssen Sie eine andere Wissensdatenbank für die Bearbeitung auswählen oder eine neue erstellen.</span><span class="sxs-lookup"><span data-stu-id="8327f-144">If you delete it, you will have to select another knowledge base to work on, or create a new one.</span></span>  
  
  
