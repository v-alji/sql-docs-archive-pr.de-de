---
title: 'Tutorial: Vorbereiten des Servers für die Replikation | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: ce30a095-2975-4387-9377-94a461ac78ee
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1f036ff2a111ee6b5f97655b9bebaf34391a436
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622531"
---
# <a name="tutorial-preparing-the-server-for-replication"></a><span data-ttu-id="59b1c-102">Lernprogramm: Vorbereiten des Servers für die Replikation</span><span class="sxs-lookup"><span data-stu-id="59b1c-102">Tutorial: Preparing the Server for Replication</span></span>
  <span data-ttu-id="59b1c-103">Es ist wichtig, einen Sicherheitsplan zu erstellen, bevor Sie die Replikationstopologie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="59b1c-103">It is important to plan for security before you configure your replication topology.</span></span> <span data-ttu-id="59b1c-104">In diesem Lernprogramm erfahren Sie, wie Sie eine Replikationstopologie besser sichern und die Verteilung konfigurieren können. Dieser Vorgang stellt den ersten Schritt für die Replikation von Daten dar.</span><span class="sxs-lookup"><span data-stu-id="59b1c-104">This tutorial shows you how to better secure a replication topology as well as how to configure distribution, which is the first step in replicating data.</span></span> <span data-ttu-id="59b1c-105">Es ist erforderlich, dieses Lernprogramm vor allen anderen Lernprogrammen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="59b1c-105">You must complete this tutorial before any of the others.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59b1c-106">Für das sichere Replizieren von Daten zwischen Servern empfiehlt es sich, alle Empfehlungen unter [Bewährte Methoden für die Replikationssicherheit](security/replication-security-best-practices.md)zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="59b1c-106">To replicate data securely between servers, you should implement all of the recommendations in [Replication Security Best Practices](security/replication-security-best-practices.md).</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="59b1c-107">Lernziele</span><span class="sxs-lookup"><span data-stu-id="59b1c-107">What You Will Learn</span></span>  
 <span data-ttu-id="59b1c-108">In diesem Lernprogramm erfahren Sie, wie Sie einen Server vorbereiten, sodass die Replikation sicher und mit den geringsten Privilegien ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="59b1c-108">In this tutorial you will learn how to prepare a server so that replication can run securely with least privileges.</span></span> <span data-ttu-id="59b1c-109">In der ersten Lektion wird veranschaulicht, wie Sie die Windows-Dienstkonten erstellen können, die zur Ausführung von Replikations-Agents verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="59b1c-109">The first lesson shows how to create the Windows service accounts used to run replication agents.</span></span> <span data-ttu-id="59b1c-110">In der zweiten Lektion erfahren Sie, wie der Ordner konfiguriert wird, in dem Momentaufnahmeveröffentlichungen generiert und gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="59b1c-110">The second lesson shows how to configure the folder used to generate and store publication snapshots.</span></span> <span data-ttu-id="59b1c-111">In der dritten Lektion wird das Konfigurieren der Verteilung und das Festlegen der Berechtigungen erläutert.</span><span class="sxs-lookup"><span data-stu-id="59b1c-111">The third lesson shows how to configure distribution and set permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59b1c-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="59b1c-112">Requirements</span></span>  
 <span data-ttu-id="59b1c-113">Dieses Lernprogramm ist für Benutzer vorgesehen, die mit grundlegenden Datenbankvorgängen vertraut sind, aber nur über begrenzte Erfahrungen in Bezug auf die Replikation verfügen.</span><span class="sxs-lookup"><span data-stu-id="59b1c-113">This tutorial is intended for users familiar with fundamental database operations, but who have limited exposure to replication.</span></span>  
  
 <span data-ttu-id="59b1c-114">Ihr System muss die folgenden installierten Komponenten aufweisen, damit dieses Lernprogramm verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="59b1c-114">To use this tutorial, your system must have the following components installed:</span></span>  
  
-   [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] <span data-ttu-id="59b1c-115">mit der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="59b1c-115">with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="59b1c-116">Aus Sicherheitsgründen werden die Beispieldatenbanken standardmäßig nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="59b1c-116">To enhance security, the sample databases are not installed by default.</span></span>  
  
 <span data-ttu-id="59b1c-117">**Geschätzte Zeit bis zum Abschluss dieses Tutorials: 30 Minuten.**</span><span class="sxs-lookup"><span data-stu-id="59b1c-117">**Estimated time to complete this tutorial: 30 minutes.**</span></span>  
  
## <a name="lessons-in-this-tutorial"></a><span data-ttu-id="59b1c-118">Lektionen in diesem Lernprogramm</span><span class="sxs-lookup"><span data-stu-id="59b1c-118">Lessons in This Tutorial</span></span>  
  
-   [<span data-ttu-id="59b1c-119">Lektion 1: Erstellen von Windows-Konten für die Replikation</span><span class="sxs-lookup"><span data-stu-id="59b1c-119">Lesson 1: Creating Windows Accounts for Replication</span></span>](lesson-1-creating-windows-accounts-for-replication.md)  
  
-   [<span data-ttu-id="59b1c-120">Lektion 2: Vorbereiten des Momentaufnahmeordners</span><span class="sxs-lookup"><span data-stu-id="59b1c-120">Lesson 2: Preparing the Snapshot Folder</span></span>](lesson-2-preparing-the-snapshot-folder.md)  
  
-   [<span data-ttu-id="59b1c-121">Lektion 3: Konfigurieren der Verteilung</span><span class="sxs-lookup"><span data-stu-id="59b1c-121">Lesson 3: Configuring Distribution</span></span>](lesson-3-configuring-distribution.md)  
  
 [<span data-ttu-id="59b1c-122">Lernprogramm starten</span><span class="sxs-lookup"><span data-stu-id="59b1c-122">Start the Tutorial</span></span>](lesson-1-creating-windows-accounts-for-replication.md)  
  
## <a name="see-also"></a><span data-ttu-id="59b1c-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="59b1c-123">See Also</span></span>  
 <span data-ttu-id="59b1c-124">[Verteilung konfigurieren](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="59b1c-124">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="59b1c-125">SQL Server-Replikation Sicherheit</span><span class="sxs-lookup"><span data-stu-id="59b1c-125">SQL Server Replication Security</span></span>](security/view-and-modify-replication-security-settings.md)  
  
  
