---
title: Erstellen einer Wissensdatenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.kb.selectkb.f1
- sql12.dqs.kb.newkb.f1
ms.assetid: 2733a284-975f-4650-abcc-cc2aad074cab
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 281fa663362cc4462cd4e32839c1eaf6908394e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609468"
---
# <a name="create-a-knowledge-base"></a><span data-ttu-id="ef1fa-102">Erstellen einer Wissensdatenbank</span><span class="sxs-lookup"><span data-stu-id="ef1fa-102">Create a Knowledge Base</span></span>
  <span data-ttu-id="ef1fa-103">In diesem Thema wird beschrieben, wie eine Wissensdatenbank in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) erstellt und auf die Domänenverwaltung, die Wissensermittlung und das Hinzufügen einer Abgleichsrichtlinie vorbereitet wird.</span><span class="sxs-lookup"><span data-stu-id="ef1fa-103">This topic describes how to create a knowledge base in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS), and prepare it for domain management, knowledge discovery, or adding a matching policy.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ef1fa-104">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="ef1fa-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="ef1fa-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ef1fa-105">Prerequisites</span></span>  
 <span data-ttu-id="ef1fa-106">Um eine Wissensdatenbank zu erstellen, müssen Sie [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] und [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]installiert haben.</span><span class="sxs-lookup"><span data-stu-id="ef1fa-106">To create a knowledge base, you must have installed [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] and [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ef1fa-107">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ef1fa-107">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ef1fa-108">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ef1fa-108">Permissions</span></span>  
 <span data-ttu-id="ef1fa-109">Sie müssen über die dqs_kb_editor- oder dqs_administrator-Rolle in der DQS_MAIN-Datenbank verfügen, um eine Wissensdatenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ef1fa-109">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to create a knowledge base.</span></span>  
  
##  <a name="create-a-knowledge-base"></a><a name="Createaknowledgebase"></a><span data-ttu-id="ef1fa-110">Erstellen einer Wissensdatenbank</span><span class="sxs-lookup"><span data-stu-id="ef1fa-110">Create a knowledge base</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="ef1fa-111">[Führen Sie die Data Quality-Client Anwendung](../../2014/data-quality-services/run-the-data-quality-client-application.md)aus.</span><span class="sxs-lookup"><span data-stu-id="ef1fa-111">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="ef1fa-112">Klicken Sie auf dem [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Startbildschirm auf **Neue Wissensdatenbank**.</span><span class="sxs-lookup"><span data-stu-id="ef1fa-112">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **New knowledge base**.</span></span>  
  
3.  <span data-ttu-id="ef1fa-113">Geben Sie einen Namen und eine Beschreibung für die neue Wissensdatenbank ein.</span><span class="sxs-lookup"><span data-stu-id="ef1fa-113">Enter a name and description for the new knowledge base.</span></span>  
  
4.  <span data-ttu-id="ef1fa-114">Wählen Sie unter **Wissensdatenbank erstellen aus**aus, worauf die neue Wissensdatenbank basieren soll:</span><span class="sxs-lookup"><span data-stu-id="ef1fa-114">In **Create knowledge base from**, select what to base the knowledge base on:</span></span>  
  
    -   <span data-ttu-id="ef1fa-115">Wählen Sie **Keine** aus, wenn die neue Wissensdatenbank nicht auf einer vorhandenen Wissensdatenbank oder Datendatei basieren soll.</span><span class="sxs-lookup"><span data-stu-id="ef1fa-115">Select **None** if you do not want to base the new knowledge base on an existing knowledge base or data file.</span></span>  
  
    -   <span data-ttu-id="ef1fa-116">Wählen Sie **Vorhandene Wissensdatenbank** aus, um eine Wissensdatenbank, die bereits auf [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)]erstellt wurde, oder die Standardwissensdatenbank als Grundlage für die neue Wissensdatenbank zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ef1fa-116">Select **Existing Knowledge Base** to base the new knowledge base on a knowledge base that has already been created on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], or on the default knowledge base.</span></span> <span data-ttu-id="ef1fa-117">Wählen Sie die Wissensdatenbank aus der Dropdownliste **Wissensdatenbank auswählen** aus, oder klicken Sie auf **Durchsuchen** , um das Dialogfeld **Wissensdatenbank auswählen** anzuzeigen, wählen Sie eine vorhandene Wissensdatenbank als Grundlage für die neue Wissensdatenbank aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef1fa-117">Select the knowledge base from the **Select Knowledge Base** drop-down list, or click **Browse** to display the **Select a Knowledge Base** dialog box, select an existing knowledge base to base the new knowledge base on, and then click **OK**.</span></span> <span data-ttu-id="ef1fa-118">Wenn Sie eine Wissensdatenbank aus dem Tablett auswählen, werden die Domänen und Abgleichsregeln in der Wissensdatenbank im rechten Bereich des Dialogfelds angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ef1fa-118">When you select a knowledge base from the tablet, the domains and matching rules in the knowledge base will be displayed in the right-hand pane of the dialog box.</span></span> <span data-ttu-id="ef1fa-119">Sie können auch die Wissensdatenbank **DQS-Daten** auswählen. Das ist die Standardwissensdatenbank, die allgemeine Standarddomänen und auf US-amerikanische Unternehmens-, Adressen- und Parteidaten bezogenes Wissen enthält.</span><span class="sxs-lookup"><span data-stu-id="ef1fa-119">You can also select the **DQS Data** knowledge base, which is the default knowledge base that contains common out-of-the-box domains and knowledge related to U.S. company, address, and party data.</span></span>  
  
    -   <span data-ttu-id="ef1fa-120">Wählen Sie **Aus DQS-Datei importieren** aus, um die neue Wissensdatenbank auf eine DQS-Datei auf dem [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)]zu basieren.</span><span class="sxs-lookup"><span data-stu-id="ef1fa-120">Select **Import from DQS File** to base the new knowledge base on a DQS file on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span> <span data-ttu-id="ef1fa-121">Klicken Sie auf **Durchsuchen**, wählen Sie eine DQS-Datendatei mit der Erweiterung ".dqs" aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef1fa-121">Click **Browse**, select a DQS data file with an extension of .dqs, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="ef1fa-122">Wählen Sie unter **Aktivität auswählen**die Aktivität aus, die Sie für die neue Wissensdatenbank ausführen möchten:</span><span class="sxs-lookup"><span data-stu-id="ef1fa-122">In **Select Activity**, select the activity that you want to perform on the new knowledge base:</span></span>  
  
    -   <span data-ttu-id="ef1fa-123">Wählen Sie **Domänenverwaltung** aus, um die Wissensdatenbank zu erstellen, und öffnen Sie dann die Bildschirme, in denen Sie die Domänen in der Wissensdatenbank ändern.</span><span class="sxs-lookup"><span data-stu-id="ef1fa-123">Select **Domain Management** to create the knowledge base and enter the screens that you use to modify the domains in the knowledge base.</span></span>  
  
    -   <span data-ttu-id="ef1fa-124">Wählen Sie **Wissensermittlung** aus, um die Wissensdatenbank zu erstellen und um den Assistenten zum Analysieren eines Datenbeispiels zu öffnen, und füllen Sie die Domänen der Wissensdatenbank mit den Ergebnissen auf.</span><span class="sxs-lookup"><span data-stu-id="ef1fa-124">Select **Knowledge Discovery** to create the knowledge base and enter the wizard that you use to analyze a data sample and populate the domains of the knowledge base with the results.</span></span>  
  
    -   <span data-ttu-id="ef1fa-125">Wählen Sie **Abgleichsrichtlinie** aus, um eine Abgleichsrichtlinie zu erstellen und sie der Wissensdatenbank hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ef1fa-125">Select **Matching Policy** to create a matching policy and add it to the knowledge base.</span></span>  
  
6.  <span data-ttu-id="ef1fa-126">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ef1fa-126">Click **Create**.</span></span>  
  
##  <a name="follow-up-after-creating-a-knowledge-base"></a><a name="FollowUp"></a> <span data-ttu-id="ef1fa-127">Nachverfolgung: Nach dem Erstellen einer Wissensdatenbank</span><span class="sxs-lookup"><span data-stu-id="ef1fa-127">Follow Up: After Creating a Knowledge Base</span></span>  
 <span data-ttu-id="ef1fa-128">Nachdem Sie eine Wissensdatenbank erstellt haben, werden ein Assistent für die Wissensermittlung, ein Assistent zum Erstellen einer Abgleichsrichtlinie oder Seiten für die Domänenverwaltung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ef1fa-128">After you create a knowledge base, you are presented with a wizard that you can use to perform knowledge discovery, a wizard to create a matching policy, or pages to perform domain management.</span></span> <span data-ttu-id="ef1fa-129">Weitere Informationen zu Wissensermittlung, Domänenverwaltung oder Abgleichsrichtlinien finden Sie unter [Durchführen der Wissensermittlung](../../2014/data-quality-services/perform-knowledge-discovery.md), [Verwalten einer Domäne](../../2014/data-quality-services/managing-a-domain.md) oder [Erstellen einer Abgleichsrichtlinie](../../2014/data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="ef1fa-129">For more information about the knowledge discovery, domain management, or matching policy, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), or [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md).</span></span>  
  
  
