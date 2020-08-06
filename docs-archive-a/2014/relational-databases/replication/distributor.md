---
title: Verteiler | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replicationutilities.selectdistributor.f1
ms.assetid: 787f0e9c-09dd-438a-bc04-5b8f99c127b8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c601a540088b5cd9d7a2033510a5cf9b83c3170e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609112"
---
# <a name="distributor"></a><span data-ttu-id="be2f5-102">Verteiler</span><span class="sxs-lookup"><span data-stu-id="be2f5-102">Distributor</span></span>
  <span data-ttu-id="be2f5-103">Die Seite **Verteiler** wird im Verteilungskonfigurations-Assistenten und im Assistenten für neue Veröffentlichung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="be2f5-103">The **Distributor** page appears in the Configure Distribution Wizard and in the New Publication Wizard.</span></span> <span data-ttu-id="be2f5-104">Beim Verteiler handelt es sich um einen Server, der die Verteilungsdatenbank beinhaltet und auf dem die Metadaten und Verlaufsdaten für alle Replikationstypen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="be2f5-104">The Distributor is a server that contains the distribution database and stores metadata and history data for all types of replication.</span></span> <span data-ttu-id="be2f5-105">Darüber hinaus werden auf dem Verteiler Transaktionen für die Transaktionsreplikation gespeichert.</span><span class="sxs-lookup"><span data-stu-id="be2f5-105">The Distributor also stores transactions for transactional replication.</span></span> <span data-ttu-id="be2f5-106">Beim Verteiler kann es sich um denselben Server, der als Verleger (lokaler Verteiler) verwendet wird, oder um einen anderen Server als den Verleger (Remoteverteiler) handeln.</span><span class="sxs-lookup"><span data-stu-id="be2f5-106">The Distributor can be the same server as the Publisher (a local Distributor) or it can be a separate server from the Publisher (a remote Distributor).</span></span> <span data-ttu-id="be2f5-107">Die Rolle des Verteilers variiert je nach implementiertem Replikationstyp.</span><span class="sxs-lookup"><span data-stu-id="be2f5-107">The role of the Distributor varies, depending on which type of replication you implement.</span></span> <span data-ttu-id="be2f5-108">Im Allgemeinen spielt er bei der Transaktionsreplikation eine größere Rolle als bei der Merge- oder Momentaufnahmereplikation.</span><span class="sxs-lookup"><span data-stu-id="be2f5-108">In general, its role is much greater for transactional replication than it is for merge replication and snapshot replication.</span></span> <span data-ttu-id="be2f5-109">Bei der Merge- und Momentaufnahmereplikation wird normalerweise ein lokaler Verteiler verwendet, allerdings kann sich die Verwendung eines Remoteverteilers bei ausgelasteten Systemen positiv auf die Transaktionsreplikation auswirken.</span><span class="sxs-lookup"><span data-stu-id="be2f5-109">Merge and snapshot replication typically use a local Distributor, but transactional replication on a very busy system can benefit from using a remote Distributor.</span></span>  
  
 <span data-ttu-id="be2f5-110">Der Verteiler verwendet die folgenden zusätzlichen Ressourcen auf dem Server, auf dem er sich befindet:</span><span class="sxs-lookup"><span data-stu-id="be2f5-110">The Distributor uses these additional resources on the server where it is located:</span></span>  
  
-   <span data-ttu-id="be2f5-111">Zusätzlichen Speicherplatz, falls die Momentaufnahmedateien für die Veröffentlichung darin gespeichert werden (was normalerweise der Fall ist).</span><span class="sxs-lookup"><span data-stu-id="be2f5-111">Additional disk space if the snapshot files for the publication are stored on it (which they typically are).</span></span>  
  
-   <span data-ttu-id="be2f5-112">Zusätzlichen Speicherplatz zum Speichern der Verteilungsdatenbank.</span><span class="sxs-lookup"><span data-stu-id="be2f5-112">Additional disk space to store the distribution database.</span></span>  
  
-   <span data-ttu-id="be2f5-113">Zusätzliche Prozessornutzung durch Replikations-Agents für auf dem Verteiler ausgeführte Pushabonnements.</span><span class="sxs-lookup"><span data-stu-id="be2f5-113">Additional processor usage by replication agents for push subscriptions running on the Distributor.</span></span>  
  
 <span data-ttu-id="be2f5-114">Der Server, den Sie als Verteiler auswählen, sollte ausreichend Speicherplatz und Prozessorleistung für die Replikation und sonstige Aktivitäten, die auf diesem Server basieren, aufweisen.</span><span class="sxs-lookup"><span data-stu-id="be2f5-114">The server you select as the Distributor should have adequate disk space and processor power to support replication and any other activities on that server.</span></span>  
  
## <a name="options"></a><span data-ttu-id="be2f5-115">Tastatur</span><span class="sxs-lookup"><span data-stu-id="be2f5-115">Options</span></span>  
 <span data-ttu-id="be2f5-116">**"\<ServerName>" agiert als sein eigener Verteiler. SQL Server erstellt eine Verteilungsdatenbank und ein Protokoll**</span><span class="sxs-lookup"><span data-stu-id="be2f5-116">**'\<ServerName>' will act as its own Distributor; SQL Server will create a distribution database and log**</span></span>  
 <span data-ttu-id="be2f5-117">Wählen Sie diese Option aus, um den Server zu konfigurieren, mit dem Sie als Verteiler verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="be2f5-117">Select this option to configure the server you are connected to as a Distributor.</span></span>  
  
 <span data-ttu-id="be2f5-118">**Folgenden Server als Verteiler verwenden (Hinweis: Der ausgewählte Server muss bereits als Verteiler konfiguriert sein)**</span><span class="sxs-lookup"><span data-stu-id="be2f5-118">**Use the following server as the Distributor (Note: the server you select must already be configured as a Distributor)**</span></span>  
 <span data-ttu-id="be2f5-119">Wählen Sie diese Option aus, und klicken Sie anschließend unten auf den Namen eines Servers, um einen anderen Server als Verteiler zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="be2f5-119">Select this option and then click on the name of a server below to configure another server as the Distributor.</span></span>  
  
 <span data-ttu-id="be2f5-120">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="be2f5-120">**Add**</span></span>  
 <span data-ttu-id="be2f5-121">Wenn der Server, den Sie als Verteiler verwenden möchten, nicht aufgelistet ist, klicken Sie auf **Hinzufügen** , um den Server zu identifizieren und der Liste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="be2f5-121">If the server you want to use as a Distributor is not listed, click **Add** to identify the server and add it to the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="be2f5-122">Um einen Remoteserver als Verteiler zu verwenden, muss der Remoteserver bereits als Verteiler konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="be2f5-122">To use a remote server as the Distributor, the remote server must already be configured as a Distributor.</span></span> <span data-ttu-id="be2f5-123">Der Server, für den der Assistent ausgeführt wird, muss auf diesem Verteiler als Verleger aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="be2f5-123">The server against which this wizard is running must be enabled as a Publisher on that Distributor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be2f5-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="be2f5-124">See Also</span></span>  
 <span data-ttu-id="be2f5-125">[Verteilung konfigurieren](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="be2f5-125">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="be2f5-126">Konfigurieren der Veröffentlichung und der Verteilung</span><span class="sxs-lookup"><span data-stu-id="be2f5-126">Configure Publishing and Distribution</span></span>](configure-publishing-and-distribution.md)  
  
  
