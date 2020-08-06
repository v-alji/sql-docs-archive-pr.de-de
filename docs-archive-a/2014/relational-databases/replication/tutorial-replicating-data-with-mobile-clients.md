---
title: 'Tutorial: Replizieren von Daten mit mobilen Clients | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: af673514-30c7-403a-9d18-d01e1a095115
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2cdf8be7cb0da11f0aa1022ba656d50c10826ad2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622527"
---
# <a name="tutorial-replicating-data-with-mobile-clients"></a><span data-ttu-id="45531-102">Lernprogramm: Replizieren von Daten mit mobilen Clients</span><span class="sxs-lookup"><span data-stu-id="45531-102">Tutorial: Replicating Data with Mobile Clients</span></span>
  <span data-ttu-id="45531-103">Die Replikation stellt eine geeignete Lösung für das Problem des Verschiebens von Daten zwischen einem zentralen Server und mobilen Clients dar, die nur gelegentlich miteinander verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="45531-103">Replication is a good solution to the problem of moving data between a central server and mobile clients that are only occasionally connected.</span></span> <span data-ttu-id="45531-104">Mithilfe von Replikations-Assistenten können Sie eine Replikationstopologie auf einfache Weise konfigurieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="45531-104">Using replication's wizards, you can easily configure and administer a replication topology.</span></span> <span data-ttu-id="45531-105">In diesem Lernprogramm wird die Konfiguration einer Replikationstopologie für mobile Clients erläutert.</span><span class="sxs-lookup"><span data-stu-id="45531-105">This tutorial shows you how to configure a replication topology for mobile clients.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="45531-106">Lernziele</span><span class="sxs-lookup"><span data-stu-id="45531-106">What You Will Learn</span></span>  
 <span data-ttu-id="45531-107">In diesem Lernprogramm werden mithilfe einer Mergereplikation Daten aus einer zentralen Datenbank für einen oder für mehrere mobile Benutzer veröffentlicht, sodass jeder Benutzer eine eindeutig gefilterte Teilmenge von Daten erhält.</span><span class="sxs-lookup"><span data-stu-id="45531-107">In this tutorial you will use merge replication to publish data from a central database to one or more mobile users so that each user gets a uniquely filtered subset of the data.</span></span> <span data-ttu-id="45531-108">In der ersten Lektion wird die Verwendung von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] zum Erstellen einer Veröffentlichung erläutert.</span><span class="sxs-lookup"><span data-stu-id="45531-108">The first lesson shows how to use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create a publication.</span></span> <span data-ttu-id="45531-109">In darauf folgenden Lektionen wird erläutert, wie ein Abonnement erstellt und synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="45531-109">Later lessons show how to create and synchronize a subscription.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45531-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="45531-110">Requirements</span></span>  
 <span data-ttu-id="45531-111">Dieses Lernprogramm ist für Benutzer vorgesehen, die mit grundlegenden Datenbankvorgängen vertraut sind, aber nur über begrenzte Kenntnisse in Bezug auf die Replikation verfügen.</span><span class="sxs-lookup"><span data-stu-id="45531-111">This tutorial is intended for users familiar with fundamental database operations, but who have limited experience with replication.</span></span> <span data-ttu-id="45531-112">Bevor Sie dieses Tutorial starten, müssen Sie das [Tutorial: Vorbereiten des Servers für die Replikation](tutorial-preparing-the-server-for-replication.md)abschließen.</span><span class="sxs-lookup"><span data-stu-id="45531-112">Before you start this tutorial, you must complete [Tutorial: Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
 <span data-ttu-id="45531-113">Ihr System muss die folgenden installierten Komponenten aufweisen, damit dieses Lernprogramm verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="45531-113">To use this tutorial, your system must have the following components installed:</span></span>  
  
-   <span data-ttu-id="45531-114">Auf dem Verlegerserver (Quelle):</span><span class="sxs-lookup"><span data-stu-id="45531-114">At the Publisher server (source):</span></span>  
  
    -   <span data-ttu-id="45531-115">Eine beliebige Edition von [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]mit Ausnahme von Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) und [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45531-115">Any edition of [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], except for Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) or [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> <span data-ttu-id="45531-116">Diese Editionen können nicht als Replikationsverleger fungieren.</span><span class="sxs-lookup"><span data-stu-id="45531-116">These editions cannot be a replication Publisher.</span></span>  
  
    -   <span data-ttu-id="45531-117">Die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Beispieldatenbank</span><span class="sxs-lookup"><span data-stu-id="45531-117">The [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="45531-118">Aus Sicherheitsgründen werden die Beispieldatenbanken standardmäßig nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="45531-118">To enhance security, the sample databases are not installed by default.</span></span>  
  
-   <span data-ttu-id="45531-119">Abonnentenserver (Ziel):</span><span class="sxs-lookup"><span data-stu-id="45531-119">Subscriber server (destination):</span></span>  
  
    -   <span data-ttu-id="45531-120">Eine beliebige Edition von [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]mit Ausnahme von [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45531-120">Any edition of [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], except for [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> [!INCLUDE[ssEW](../../includes/ssew-md.md)] <span data-ttu-id="45531-121">wird nicht von der in diesem Lernprogramm erstellten Veröffentlichung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="45531-121">is not supported by the publication created in this tutorial.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="45531-122">Die Replikation wird bei [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]nicht standardmäßig installiert.</span><span class="sxs-lookup"><span data-stu-id="45531-122">Replication is not installed by default on [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45531-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]muss eine Verbindung mit dem Verleger und dem Abonnenten hergestellt werden. Dazu wird ein Anmeldename verwendet, der Mitglied der festen Serverrolle sysadmin ist.</span><span class="sxs-lookup"><span data-stu-id="45531-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you must connect to the Publisher and Subscriber using a login that is a member of the sysadmin fixed server role.</span></span>  
  
 <span data-ttu-id="45531-124">**Geschätzte Zeit bis zum Abschluss dieses Tutorials: 30 Minuten.**</span><span class="sxs-lookup"><span data-stu-id="45531-124">**Estimated time to complete this tutorial: 30 minutes.**</span></span>  
  
## <a name="lessons-in-this-tutorial"></a><span data-ttu-id="45531-125">Lektionen in diesem Lernprogramm</span><span class="sxs-lookup"><span data-stu-id="45531-125">Lessons in This Tutorial</span></span>  
  
-   [<span data-ttu-id="45531-126">Lektion 1: Veröffentlichen von Daten mithilfe der Mergereplikation</span><span class="sxs-lookup"><span data-stu-id="45531-126">Lesson 1: Publishing Data Using Merge Replication</span></span>](lesson-1-publishing-data-using-merge-replication.md)  
  
-   [<span data-ttu-id="45531-127">Lektion 2: Erstellen eines Abonnements für die Mergeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="45531-127">Lesson 2: Creating a Subscription to the Merge Publication</span></span>](lesson-2-creating-a-subscription-to-the-merge-publication.md)  
  
 [<span data-ttu-id="45531-128">Lernprogramm starten</span><span class="sxs-lookup"><span data-stu-id="45531-128">Start the Tutorial</span></span>](merge/merge-replication.md)  
  
## <a name="see-also"></a><span data-ttu-id="45531-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="45531-129">See Also</span></span>  
 [<span data-ttu-id="45531-130">Konzepte für die Replikationsprogrammierung</span><span class="sxs-lookup"><span data-stu-id="45531-130">Replication Programming Concepts</span></span>](concepts/replication-programming-concepts.md)  
  
  
