---
title: Exportieren einer Wissensdatenbank in eine DQS-Datei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: a324ead5-c8aa-4e26-abe3-ef415add00f8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 81dfc8e7f20fae9dacd521595d101be3117a6794
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610051"
---
# <a name="export-a-knowledge-base-to-a-dqs-file"></a><span data-ttu-id="2d24e-102">Exportieren einer Wissensdatenbank in eine DQS-Datei</span><span class="sxs-lookup"><span data-stu-id="2d24e-102">Export a Knowledge Base to a .dqs File</span></span>
  <span data-ttu-id="2d24e-103">In diesem Thema wird beschrieben, wie eine gesamte Wissensdatenbank in eine DQS-Datendatei in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) exportiert wird.</span><span class="sxs-lookup"><span data-stu-id="2d24e-103">This topic describes how to export an entire knowledge base to a .dqs data file in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="2d24e-104">Sie können eine Domäne oder eine ganze Wissensdatenbank in eine Datendatei exportieren.</span><span class="sxs-lookup"><span data-stu-id="2d24e-104">You can export a domain or an entire knowledge base to a data file.</span></span> <span data-ttu-id="2d24e-105">Weitere Informationen zum Exportieren einer Domäne finden Sie unter [Exportieren einer Domäne in eine DQS-Datei](../../2014/data-quality-services/export-a-domain-to-a-dqs-file.md).</span><span class="sxs-lookup"><span data-stu-id="2d24e-105">For information about exporting a domain, see [Export a Domain to a .dqs File](../../2014/data-quality-services/export-a-domain-to-a-dqs-file.md).</span></span>  
  
 <span data-ttu-id="2d24e-106">Indem Sie eine Wissensdatenbank in eine DQS-Datei exportieren und diese dann als weitere Wissensdatenbank importieren, wird der Wissensgenerierungsprozess vereinfacht, Zeit gespart und der Aufwand verringert.</span><span class="sxs-lookup"><span data-stu-id="2d24e-106">Exporting a knowledge base to a .dqs file, and then importing it as another knowledge base simplifies the knowledge generation process, saving time and effort.</span></span> <span data-ttu-id="2d24e-107">Auf diese Weise haben Sie die Möglichkeit, eine Wissensdatenbank und ihr Wissen zusammen mit anderen zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="2d24e-107">It enables you to share a knowledge base and its knowledge with others.</span></span> <span data-ttu-id="2d24e-108">Die DQS-Datei enthält alle Informationen aus der Wissensdatenbank, einschließlich Domänen und der Abgleichsrichtlinie, aber keine Informationen über angefügte Verweisdaten.</span><span class="sxs-lookup"><span data-stu-id="2d24e-108">The .dqs file will contain all knowledge base information, including domains and the matching policy, except for the attached reference data information.</span></span> <span data-ttu-id="2d24e-109">Nachdem Sie die DQS-Datei importiert haben, müssen Sie die erforderlichen Domänen ggf. erneut an die entsprechenden Verweisdatendienste anfügen.</span><span class="sxs-lookup"><span data-stu-id="2d24e-109">You must attach the required domains to appropriate reference data services again, if required, after importing the .dqs file.</span></span> <span data-ttu-id="2d24e-110">Sowohl veröffentlichte als auch nicht veröffentlichte Daten in einer Wissensdatenbank werden exportiert.</span><span class="sxs-lookup"><span data-stu-id="2d24e-110">Both published and unpublished data in a knowledge base is exported.</span></span>  
  
 <span data-ttu-id="2d24e-111">Die durch den Exportvorgang erstellte DQS-Datendatei wird verschlüsselt, damit der Inhalt nicht angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2d24e-111">The .dqs data file created by the export process is encrypted, so the contents cannot be viewed.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2d24e-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="2d24e-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="2d24e-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2d24e-113">Prerequisites</span></span>  
 <span data-ttu-id="2d24e-114">Um eine Wissensdatenbank in eine DQS-Datendatei zu exportieren, müssen Sie zuvor eine Wissensdatenbank erstellt und geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="2d24e-114">To export a knowledge base to a .dqs data file, you must have created and opened a knowledge base.</span></span> <span data-ttu-id="2d24e-115">Sie benötigen für den Export keine DQS-Datei. Eine DQS-Datei wird für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="2d24e-115">You do not need to have a .dqs file to export into; one will be created for you.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2d24e-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="2d24e-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2d24e-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="2d24e-117">Permissions</span></span>  
 <span data-ttu-id="2d24e-118">Sie müssen über die Rolle „dqs_kb_editor“ oder „dqs_administrator“ in der DQS_MAIN-Datenbank verfügen, um eine Wissensdatenbank in eine DQS-Datendatei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="2d24e-118">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to export a knowledge base to a .dqs data file.</span></span>  
  
##  <a name="export-a-knowledge-base-to-a-dqs-file"></a><a name="Export"></a><span data-ttu-id="2d24e-119">Exportieren einer Wissensdatenbank in eine DQS-Datei</span><span class="sxs-lookup"><span data-stu-id="2d24e-119">Export a knowledge base to a .dqs file</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="2d24e-120">[Führen Sie die Data Quality-Client Anwendung](../../2014/data-quality-services/run-the-data-quality-client-application.md)aus.</span><span class="sxs-lookup"><span data-stu-id="2d24e-120">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="2d24e-121">Öffnen Sie im [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Startbildschirm in der Domänenverwaltungsaktivität eine Wissensdatenbank.</span><span class="sxs-lookup"><span data-stu-id="2d24e-121">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, open a knowledge base in the Domain Management activity.</span></span>  
  
3.  <span data-ttu-id="2d24e-122">Klicken Sie auf der Seite „Domänenverwaltung“ (bei Auswahl einer beliebigen Registerkarte) oberhalb der Domänenliste auf das Symbol **Daten der Wissensdatenbank exportieren** , und klicken Sie dann auf **Wissensdatenbank exportieren**.</span><span class="sxs-lookup"><span data-stu-id="2d24e-122">In the Domain Management page (with any tab selected), click the **Export Knowledge Base data** icon above the Domain list, and then click **Export Knowledge Base**.</span></span> <span data-ttu-id="2d24e-123">Sie können alternativ auch mit der rechten Maustaste in der Liste **Domäne** klicken, auf **Exportieren**zeigen und dann auf **Wissensdatenbank exportieren**klicken.</span><span class="sxs-lookup"><span data-stu-id="2d24e-123">Alternatively, you can also right-click in the **Domain** list, hover over **Export**, and then click **Export Knowledge Base**.</span></span>  
  
4.  <span data-ttu-id="2d24e-124">Wechseln Sie im Dialogfeld **In Datendatei exportieren** zu dem Ordner, in dem Sie die Datei speichern möchten, benennen Sie die Datei, oder behalten Sie den Namen der Wissensdatenbank bei, übernehmen Sie **DQS-Datendateien (\*.dqs)** als Dateityp unter **Speichern unter**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="2d24e-124">In the **Export to Data File** dialog box, move to the folder that you want to save the file in, name the file or keep the knowledge base name, keep **DQS Data Files (\*.dqs)** as the **Save as** type, and then click **Save**.</span></span>  
  
5.  <span data-ttu-id="2d24e-125">Überprüfen Sie im Dialogfeld **Wissensdatenbank exportieren** , ob die Statuszeile angibt, dass der Exportvorgang abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="2d24e-125">In the **Export Knowledge Base** dialog box, verify that the status line indicates that the export completed.</span></span> <span data-ttu-id="2d24e-126">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d24e-126">Click **OK**.</span></span>  
  
##  <a name="follow-up-after-exporting-a-domain-to-a-dqs-file"></a><a name="FollowUp"></a> <span data-ttu-id="2d24e-127">Nachverfolgung: Nach dem Exportieren einer Domäne in eine DQS-Datei</span><span class="sxs-lookup"><span data-stu-id="2d24e-127">Follow Up: After Exporting a Domain to a .dqs File</span></span>  
 <span data-ttu-id="2d24e-128">Nachdem Sie eine Wissensdatenbank in eine DQS-Datei exportiert haben, können Sie die Wissensdatenbank in den gleichen [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] (unter einem neuen Namen) oder in einen anderen [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)]importieren.</span><span class="sxs-lookup"><span data-stu-id="2d24e-128">After you export a knowledge base to a .dqs file, you can import the knowledge base into the same [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] (with a new name) or into a different [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
  
