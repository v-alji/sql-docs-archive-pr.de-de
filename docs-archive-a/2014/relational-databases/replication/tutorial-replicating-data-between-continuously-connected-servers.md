---
title: 'Tutorial: Replizieren von Daten zwischen Servern mit kontinuierlicher Verbindung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- tutorials [SQL Server replication]
- replication [SQL Server], tutorials
- wizards [SQL Server replication]
ms.assetid: 7b18a04a-2c3d-4efe-a0bc-c3f92be72fd0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 415cac62112c1c1d2aa6c42ec189c2614ec03923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622529"
---
# <a name="tutorial-replicating-data-between-continuously-connected-servers"></a><span data-ttu-id="65b3b-102">Lernprogramm: Replizieren von Daten zwischen Servern mit kontinuierlicher Verbindung</span><span class="sxs-lookup"><span data-stu-id="65b3b-102">Tutorial: Replicating Data Between Continuously Connected Servers</span></span>
  <span data-ttu-id="65b3b-103">Die Replikation stellt eine bewährte Lösung für das Problem des Verschiebens von Daten zwischen Servern mit kontinuierlicher Verbindung dar.</span><span class="sxs-lookup"><span data-stu-id="65b3b-103">Replication is a good solution to the problem of moving data between continuously connected servers.</span></span> <span data-ttu-id="65b3b-104">Mithilfe von Replikations-Assistenten können Sie eine Replikationstopologie auf einfache Weise konfigurieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="65b3b-104">Using replication's wizards, you can easily configure and administer a replication topology.</span></span> <span data-ttu-id="65b3b-105">In diesem Lernprogramm wird die Konfiguration einer Replikationstopologie für Server mit kontinuierlicher Verbindung erläutert.</span><span class="sxs-lookup"><span data-stu-id="65b3b-105">This tutorial shows you how to configure a replication topology for continuously connected servers.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="65b3b-106">Lernziele</span><span class="sxs-lookup"><span data-stu-id="65b3b-106">What You Will Learn</span></span>  
 <span data-ttu-id="65b3b-107">In diesem Lernprogramm erfahren Sie, wie Sie Daten aus einer Datenbank mithilfe der Transaktionsreplikation in einer anderen Datenbank veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="65b3b-107">This tutorial will show you how to publish data from one database to another using transactional replication.</span></span> <span data-ttu-id="65b3b-108">In der ersten Lektion wird die Verwendung von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] zum Erstellen einer Veröffentlichung erläutert.</span><span class="sxs-lookup"><span data-stu-id="65b3b-108">The first lesson shows how to use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create a publication.</span></span> <span data-ttu-id="65b3b-109">In den darauf folgenden Lektionen wird erläutert, wie Sie ein Abonnement erstellen und überprüfen und wie Sie die Latenzzeit messen.</span><span class="sxs-lookup"><span data-stu-id="65b3b-109">Later lessons show how to create and validate a subscription and how to measure latency.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65b3b-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="65b3b-110">Requirements</span></span>  
 <span data-ttu-id="65b3b-111">Dieses Lernprogramm ist für Benutzer vorgesehen, die mit grundlegenden Datenbankvorgängen vertraut sind, aber nur über begrenzte Kenntnisse in Bezug auf die Replikation verfügen.</span><span class="sxs-lookup"><span data-stu-id="65b3b-111">This tutorial is intended for users who are familiar with basic database operations, but who have limited experience with replication.</span></span> <span data-ttu-id="65b3b-112">Für dieses Lernprogramm ist es erforderlich, dass Sie das vorherige Lernprogramm ( [Vorbereiten des Servers für die Replikation](tutorial-preparing-the-server-for-replication.md)) abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="65b3b-112">This tutorial requires that you have completed the previous tutorial, [Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
 <span data-ttu-id="65b3b-113">Auf Ihrem System müssen für die Verwendung dieses Lernprogramms folgende Komponenten installiert sein:</span><span class="sxs-lookup"><span data-stu-id="65b3b-113">To use this tutorial, your system must have the following components:</span></span>  
  
-   <span data-ttu-id="65b3b-114">Auf dem Verlegerserver (Quelle):</span><span class="sxs-lookup"><span data-stu-id="65b3b-114">At the Publisher server (source):</span></span>  
  
    -   <span data-ttu-id="65b3b-115">Eine beliebige Edition von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]mit Ausnahme von Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) und [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65b3b-115">Any edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], except Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) or [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> <span data-ttu-id="65b3b-116">Diese Editionen können nicht als Verleger für Replikationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="65b3b-116">These editions cannot be replication Publishers.</span></span>  
  
    -   [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] <span data-ttu-id="65b3b-117">-Beispieldatenbank</span><span class="sxs-lookup"><span data-stu-id="65b3b-117">sample database.</span></span> <span data-ttu-id="65b3b-118">Aus Sicherheitsgründen werden die Beispieldatenbanken standardmäßig nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="65b3b-118">To enhance security, the sample databases are not installed by default.</span></span>  
  
-   <span data-ttu-id="65b3b-119">Abonnentenserver (Ziel):</span><span class="sxs-lookup"><span data-stu-id="65b3b-119">Subscriber server (destination):</span></span>  
  
    -   <span data-ttu-id="65b3b-120">Eine beliebige Edition von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]mit Ausnahme von [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65b3b-120">Any edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], except [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> [!INCLUDE[ssEW](../../includes/ssew-md.md)] <span data-ttu-id="65b3b-121">kann nicht als Abonnent einer Transaktionsreplikation fungieren.</span><span class="sxs-lookup"><span data-stu-id="65b3b-121">cannot be a Subscriber in transactional replication.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="65b3b-122">Die Replikation wird in [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] nicht standardmäßig installiert.</span><span class="sxs-lookup"><span data-stu-id="65b3b-122">Replication is not installed on [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="65b3b-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] müssen Sie eine Verbindung mit dem Verleger und dem Abonnenten herstellen, indem Sie einen Anmelde Namen verwenden, der Mitglied der festen Server Rolle **sysadmin** ist.</span><span class="sxs-lookup"><span data-stu-id="65b3b-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you must connect to the Publisher and Subscriber using a login that is a member of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="65b3b-124">**Geschätzte Zeit bis zum Abschluss dieses Tutorials: 30 Minuten.**</span><span class="sxs-lookup"><span data-stu-id="65b3b-124">**Estimated time to complete this tutorial: 30 minutes.**</span></span>  
  
## <a name="lessons-in-this-tutorial"></a><span data-ttu-id="65b3b-125">Lektionen in diesem Lernprogramm</span><span class="sxs-lookup"><span data-stu-id="65b3b-125">Lessons in This Tutorial</span></span>  
  
-   [<span data-ttu-id="65b3b-126">Lektion 1: Veröffentlichen von Daten mithilfe der Transaktionsreplikation</span><span class="sxs-lookup"><span data-stu-id="65b3b-126">Lesson 1: Publishing Data Using Transactional Replication</span></span>](lesson-1-publishing-data-using-transactional-replication.md)  
  
-   [<span data-ttu-id="65b3b-127">Lektion 2: Erstellen eines Abonnements für die Transaktionsveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="65b3b-127">Lesson 2: Creating a Subscription to the Transactional Publication</span></span>](lesson-2-creating-a-subscription-to-the-transactional-publication.md)  
  
-   [<span data-ttu-id="65b3b-128">Lektion 3: Überprüfen des Abonnements und Messen der Latenzzeit</span><span class="sxs-lookup"><span data-stu-id="65b3b-128">Lesson 3: Validating the Subscription and Measuring Latency</span></span>](lesson-3-validating-the-subscription-and-measuring-latency.md)  
  
 [<span data-ttu-id="65b3b-129">Lernprogramm starten</span><span class="sxs-lookup"><span data-stu-id="65b3b-129">Start the Tutorial</span></span>](transactional/transactional-replication.md)  
  
## <a name="see-also"></a><span data-ttu-id="65b3b-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="65b3b-130">See Also</span></span>  
 [<span data-ttu-id="65b3b-131">Konzepte für die Replikationsprogrammierung</span><span class="sxs-lookup"><span data-stu-id="65b3b-131">Replication Programming Concepts</span></span>](concepts/replication-programming-concepts.md)  
  
  
