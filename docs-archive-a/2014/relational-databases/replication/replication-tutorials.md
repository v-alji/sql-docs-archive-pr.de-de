---
title: Tutorials zur Replikation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- tutorials [SQL Server replication]
- walkthroughs [SQL Server replication]
- replication [SQL Server], tutorials
ms.assetid: 19fbd10e-5b59-4cd0-a988-52d5d9206242
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f4d70abd6c58b3eb0fa4a53e2806ab1b3fbe9245
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608522"
---
# <a name="replication-tutorials"></a><span data-ttu-id="5bd39-102">Lernprogramme zur Replikation</span><span class="sxs-lookup"><span data-stu-id="5bd39-102">Replication Tutorials</span></span>
  <span data-ttu-id="5bd39-103">Zur Replikation stehen Lernprogramme zur Verfügung, in denen Sie lernen können, wie Replikationstopologien mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eingerichtet und ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5bd39-103">Replication includes tutorials that you can use to learn how to set up and run replication topologies using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="5bd39-104">In den Lernprogrammen zur Replikation bezieht sich "Verleger" auf den Server, der die zu replizierenden Quelldaten enthält, und "Abonnent" bezieht sich auf den Zielserver.</span><span class="sxs-lookup"><span data-stu-id="5bd39-104">In the replication tutorials, "Publisher" refers to the server that contains that source data being replicated and "Subscriber" refers to the destination server.</span></span> <span data-ttu-id="5bd39-105">Verleger und Abonnent können dieselbe Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]gemeinsam verwenden; dies ist jedoch keine Anforderung.</span><span class="sxs-lookup"><span data-stu-id="5bd39-105">The Publisher and Subscriber may share the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but it is not a requirement.</span></span> <span data-ttu-id="5bd39-106">Weitere Informationen finden Sie unter [Das Replikationsveröffentlichungsmodell (Übersicht)](publish/replication-publishing-model-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5bd39-106">For more information, see [Replication Publishing Model Overview](publish/replication-publishing-model-overview.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5bd39-107">Die meisten der in diesen Lernprogrammen vorgestellten Aufgaben können programmgesteuert ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5bd39-107">Most of the tasks shown in these tutorials can be performed programmatically.</span></span> <span data-ttu-id="5bd39-108">Weitere Informationen finden Sie [im Entwicklerhandbuch &#40;Replikations&#41;](concepts/replication-developer-documentation.md).</span><span class="sxs-lookup"><span data-stu-id="5bd39-108">For more information, see [Developer's Guide &#40;Replication&#41;](concepts/replication-developer-documentation.md).</span></span>  
  
## <a name="replication-tutorials"></a><span data-ttu-id="5bd39-109">Lernprogramme zur Replikation</span><span class="sxs-lookup"><span data-stu-id="5bd39-109">Replication Tutorials</span></span>  
 [<span data-ttu-id="5bd39-110">Vorbereiten des Servers für die Replikation</span><span class="sxs-lookup"><span data-stu-id="5bd39-110">Preparing the Server for Replication</span></span>](tutorial-preparing-the-server-for-replication.md)  
 <span data-ttu-id="5bd39-111">Hier erfahren Sie, wie Server so vorbereitet werden, dass die Replikation mit geringsten Benutzerrechten ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5bd39-111">Learn how to prepare servers so that replication can be run with least privileges.</span></span> <span data-ttu-id="5bd39-112">Es ist erforderlich, dieses Lernprogramm vor den anderen Lernprogrammen zur Replikation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="5bd39-112">You must complete this tutorial before the other replication tutorials.</span></span>  
  
 [<span data-ttu-id="5bd39-113">Replizieren von Daten zwischen Servern mit kontinuierlicher Verbindung</span><span class="sxs-lookup"><span data-stu-id="5bd39-113">Replicating Data Between Continuously Connected Servers</span></span>](tutorial-replicating-data-between-continuously-connected-servers.md)  
 <span data-ttu-id="5bd39-114">Hier erfahren Sie, wie Daten mithilfe der Transaktionsreplikation zwischen vollständig verbundenen Servern repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="5bd39-114">Learn how to use transactional replication to replicate data between fully connected servers.</span></span>  
  
 [<span data-ttu-id="5bd39-115">Replizieren von Daten mit mobilen Clients</span><span class="sxs-lookup"><span data-stu-id="5bd39-115">Replicating Data with Mobile Clients</span></span>](tutorial-replicating-data-with-mobile-clients.md)  
 <span data-ttu-id="5bd39-116">Hier erfahren Sie, wie Daten mithilfe der Mergereplikation zwischen einem Server und einem oder mehreren Clients ausgetauscht werden, die nur gelegentlich verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="5bd39-116">Learn how to use merge replication to exchange data between a server and one or more clients that are only occasionally connected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bd39-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5bd39-117">See Also</span></span>  
 [<span data-ttu-id="5bd39-118">SQL Server-Replikation Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5bd39-118">SQL Server Replication Security</span></span>](security/view-and-modify-replication-security-settings.md)  
  
  
