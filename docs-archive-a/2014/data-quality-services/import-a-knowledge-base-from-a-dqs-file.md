---
title: Importieren einer Wissensdatenbank aus einer DQS-Datei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 9b9786fe-9e80-429a-afcb-dc3b3dd6f0b0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 522c5f6d8f962cef77e215c21133927e8da4d04f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701991"
---
# <a name="import-a-knowledge-base-from-a-dqs-file"></a><span data-ttu-id="e1b4d-102">Importieren einer Wissensdatenbank aus einer DQS-Datei</span><span class="sxs-lookup"><span data-stu-id="e1b4d-102">Import a Knowledge Base from a .dqs File</span></span>
  <span data-ttu-id="e1b4d-103">In diesem Thema wird beschrieben, wie eine gesamte Wissensdatenbank aus einer DQS-Datendatei in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) importiert wird.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-103">This topic describes how to import an entire knowledge base from a .dqs data file in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="e1b4d-104">Sie erstellen die Datendatei, indem Sie eine vorhandene Wissensdatenbank innerhalb der Anwendung exportieren [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] (siehe [Exportieren einer Wissensdatenbank in eine DQS-Date](../../2014/data-quality-services/export-a-knowledge-base-to-a-dqs-file.md)).</span><span class="sxs-lookup"><span data-stu-id="e1b4d-104">You create the data file by exporting an existing knowledge base from within the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] application (see [Export a Knowledge Base to a .dqs File](../../2014/data-quality-services/export-a-knowledge-base-to-a-dqs-file.md)).</span></span>  
  
 <span data-ttu-id="e1b4d-105">Durch Verwendung einer DQS-Datendatei zum Exportieren des Inhalts einer Wissensdatenbank und Importieren des Inhalts in eine andere Wissensdatenbank auf dem gleichen [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] oder einem anderen [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] wird der Wissensgenerierungsprozess vereinfacht, Zeit gespart und der Aufwand verringert.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-105">Using a .dqs data file to export the contents of a knowledge base and then import the contents into another knowledge base on the same [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] or a different [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] simplifies the knowledge generation process, saving time and effort.</span></span> <span data-ttu-id="e1b4d-106">Auf diese Weise haben Sie die Möglichkeit, eine Wissensdatenbank und ihr Wissen zusammen mit anderen zu nutzen und somit Zeit zu sparen.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-106">It enables you to share a knowledge base and its knowledge with others, saving them time.</span></span> <span data-ttu-id="e1b4d-107">Die DQS-Datei enthält alle Informationen aus der Wissensdatenbank, einschließlich Domänen und der Abgleichsrichtlinie, aber keine Informationen über angefügte Verweisdaten.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-107">The .dqs file will contain all knowledge base information, including domains and the matching policy, except for the attached reference data information.</span></span> <span data-ttu-id="e1b4d-108">Veröffentlichte und unveröffentlichte Daten werden importiert.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-108">Published and unpublished data will be imported.</span></span>  
  
 <span data-ttu-id="e1b4d-109">Eine DQS-Datendatei wird verschlüsselt und kann nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-109">A .dqs data file is encrypted, so cannot be viewed.</span></span>  
  
 <span data-ttu-id="e1b4d-110">Wenn Sie eine Wissensdatenbank importieren, können Sie den gleichen Namen verwenden, sofern der Wissensdatenbankname nicht bereits in der Clientanwendung vorhanden ist. In diesem Fall müssen Sie die Wissensdatenbank umbenennen.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-110">When you import a knowledge base, you can use the same name, unless the knowledge base name already exists in the client application, in which case you must rename it.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e1b4d-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="e1b4d-111">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="e1b4d-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e1b4d-112">Prerequisites</span></span>  
 <span data-ttu-id="e1b4d-113">Um eine Wissensdatenbank aus einer DQS-Datei importieren zu können, müssen Sie diese zuvor in eine DQS-Datei exportiert haben.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-113">To import a knowledge base from a .dqs file, you must have already exported the knowledge base into the .dqs file.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e1b4d-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e1b4d-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e1b4d-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e1b4d-115">Permissions</span></span>  
 <span data-ttu-id="e1b4d-116">Sie müssen über die Rolle „dqs_kb_editor“ oder „dqs_administrator“ in der DQS_MAIN-Datenbank verfügen, um eine Wissensdatenbank aus einer DQS-Datei zu importieren.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-116">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to import a knowledge base from a .dqs data file.</span></span>  
  
##  <a name="import-a-knowledge-base-from-a-dqs-file"></a><a name="Import"></a><span data-ttu-id="e1b4d-117">Importieren einer Wissensdatenbank aus einer DQS-Datei</span><span class="sxs-lookup"><span data-stu-id="e1b4d-117">Import a knowledge base from a .dqs file</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="e1b4d-118">[Führen Sie die Data Quality-Client Anwendung](../../2014/data-quality-services/run-the-data-quality-client-application.md)aus.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-118">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="e1b4d-119">Klicken Sie auf dem [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Startbildschirm auf **Neue Wissensdatenbank**.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-119">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **New knowledge base**.</span></span>  
  
3.  <span data-ttu-id="e1b4d-120">Geben Sie einen Namen für die Wissensdatenbank ein.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-120">Enter a name for the knowledge base.</span></span>  
  
4.  <span data-ttu-id="e1b4d-121">Klicken Sie auf den Abwärtspfeil für **Wissensdatenbank erstellen aus**, und wählen Sie dann **Aus DQS-Datei importieren**aus.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-121">Click the down arrow for **Create knowledge base from**, and then select **Import from DQS file**.</span></span>  
  
5.  <span data-ttu-id="e1b4d-122">Klicken Sie für **Datendatei auswählen**auf **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-122">For **Select data file**, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="e1b4d-123">Wechseln Sie im Dialogfeld **Aus Datendatei importieren** zum Ordner, in dem die zu importierende DQS-Datei gespeichert ist, und klicken Sie dann auf den Namen der Datei.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-123">In the **Import from Data File** dialog box, move to the folder that contains the .dqs file that you want to import, and then click the name of the file.</span></span> <span data-ttu-id="e1b4d-124">Klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-124">Click **Open**.</span></span>  
  
7.  <span data-ttu-id="e1b4d-125">Überprüfen Sie, ob in der Liste **Domäne** die richtige Wissensdatenbank und Domänen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-125">Verify that the correct knowledge base and domains are displayed in the **Domain** list.</span></span>  
  
8.  <span data-ttu-id="e1b4d-126">Wählen Sie die auszuführende Aktivität aus, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-126">Select the activity that you want to perform, and then click **Create**.</span></span>  
  
9. <span data-ttu-id="e1b4d-127">Überprüfen Sie im Dialogfeld **Wissensdatenbank importieren** , ob in der Statuszeile angegeben ist, dass der Importvorgang abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-127">In the **Import Knowledge Base** dialog box, verify that the status line indicates that the import completed.</span></span> <span data-ttu-id="e1b4d-128">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-128">Click **OK**.</span></span>  
  
10. <span data-ttu-id="e1b4d-129">Schließen Sie die erforderliche Wissensermittlung, Domänenverwaltung oder Abgleichsrichtlinientasks ab, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-129">Complete the knowledge discovery, domain management, or matching policy tasks that you need to perform, and then click **Finish**.</span></span>  
  
11. <span data-ttu-id="e1b4d-130">Klicken Sie auf **Veröffentlichen** , um das Wissen in der Wissensdatenbank zu veröffentlichen, oder klicken Sie auf **Nein** , wenn dieses nicht veröffentlicht werden soll.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-130">Click **Publish** to publish the knowledge in the knowledge base, or **No** not to.</span></span>  
  
12. <span data-ttu-id="e1b4d-131">Wenn Sie die Wissensdatenbank veröffentlichten, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-131">If you published the knowledge base, click **OK**.</span></span>  
  
13. <span data-ttu-id="e1b4d-132">Überprüfen Sie auf der Startseite von Data Quality Services, dass die Wissensdatenbank unter **Zuletzt verwendete Wissensdatenbank**aufgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-132">In the Data Quality Services home page, verify that the knowledge base is listed under **Recent knowledge bases**.</span></span>  
  
##  <a name="follow-up-after-importing-a-knowledge-base-from-a-dqs-file"></a><a name="FollowUp"></a><span data-ttu-id="e1b4d-133">Nachverfolgung: nach dem Importieren einer Wissensdatenbank aus einer DQS-Datei</span><span class="sxs-lookup"><span data-stu-id="e1b4d-133">Follow Up: After Importing a Knowledge Base from a .dqs File</span></span>  
 <span data-ttu-id="e1b4d-134">Nachdem Sie eine Wissensdatenbank aus einer DQS-Datei importiert haben, können Sie der Wissensdatenbank Wissen hinzufügen oder die Wissensdatenbank in einem Bereinigungs- oder Abgleichsprojekt verwenden - je nach Inhalt der Wissensdatenbank.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-134">After you import a knowledge base from a .dqs file, you can add knowledge to the knowledge base or use the knowledge base in a cleansing or matching project, depending on the contents of the knowledge base.</span></span> <span data-ttu-id="e1b4d-135">Weitere Informationen finden Sie unter [Durchführen der Wissensermittlung](../../2014/data-quality-services/perform-knowledge-discovery.md), [Verwalten einer Domäne](../../2014/data-quality-services/managing-a-domain.md), [Verwalten einer Verbunddomäne](../../2014/data-quality-services/managing-a-composite-domain.md), [Erstellen einer Abgleichsrichtlinie](../../2014/data-quality-services/create-a-matching-policy.md), [Datenbereinigung](../../2014/data-quality-services/data-cleansing.md) oder [Datenabgleich](../../2014/data-quality-services/data-matching.md).</span><span class="sxs-lookup"><span data-stu-id="e1b4d-135">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), [Managing a Composite Domain](../../2014/data-quality-services/managing-a-composite-domain.md), [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md), [Data Cleansing](../../2014/data-quality-services/data-cleansing.md), or [Data Matching](../../2014/data-quality-services/data-matching.md).</span></span>  
  
  
