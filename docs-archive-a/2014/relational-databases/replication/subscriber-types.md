---
title: Abonnententypen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.subscribertypes.f1
ms.assetid: a70656cb-21c9-4489-be77-ccd396747e3b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4d356377dec1f5307fa136c94ea682c0824479a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622035"
---
# <a name="subscriber-types"></a><span data-ttu-id="554ea-102">Abonnententypen</span><span class="sxs-lookup"><span data-stu-id="554ea-102">Subscriber Types</span></span>
  <span data-ttu-id="554ea-103">Mithilfe der Mergereplikation können Sie die Typen der Abonnenten angeben, die eine Veröffentlichung unterstützen muss.</span><span class="sxs-lookup"><span data-stu-id="554ea-103">Merge replication allows you to specify the types of Subscribers that a publication must support.</span></span> <span data-ttu-id="554ea-104">Die Auswahl der Abonnententypen legt den *Veröffentlichungskompatibilitätsgrad*fest, der bestimmt, welche Funktionen von einer Veröffentlichung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="554ea-104">Selecting Subscriber types sets the *publication compatibility level*, which determines which features can be used by a publication.</span></span>  
  
 <span data-ttu-id="554ea-105">Nachdem eine Veröffentlichungsmomentaufnahme erstellt wurde, kann der Veröffentlichungskompatibilitätsgrad im Dialogfeld **Veröffentlichungseigenschaften** auf der Seite **Allgemein** gesteigert (restriktiver gemacht) werden. Der Veröffentlichungskompatibilitätsgrad kann nicht gesenkt werden.</span><span class="sxs-lookup"><span data-stu-id="554ea-105">After a publication snapshot is created, the publication compatibility level can be increased (made more restrictive) on the **General** page of the **Publication Properties** dialog box; the compatibility level cannot be decreased.</span></span>  
  
## <a name="options"></a><span data-ttu-id="554ea-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="554ea-106">Options</span></span>  
 <span data-ttu-id="554ea-107">Wählen Sie jeden Abonnententypen aus, der von der Veröffentlichung unterstützt werden muss.</span><span class="sxs-lookup"><span data-stu-id="554ea-107">Select each Subscriber type that this publication must support.</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]  
 <span data-ttu-id="554ea-108">Die Veröffentlichung kann alle Funktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="554ea-108">The publication can use all features.</span></span>  
  
 [!INCLUDE[ssEW](../../includes/ssew-md.md)]  
 <span data-ttu-id="554ea-109">Momentaufnahmedateien für die Veröffentlichung müssen ein Zeichenformat aufweisen (dies wird automatisch vom Momentaufnahme-Agent gehandhabt).</span><span class="sxs-lookup"><span data-stu-id="554ea-109">The publication requires snapshot files to be in character format (this is handled automatically by the Snapshot Agent).</span></span> <span data-ttu-id="554ea-110">Für[!INCLUDE[ssEW](../../includes/ssew-md.md)] gilt auch eine Reihe von Einschränkungen ohne Bezug zum Kompatibilitätsgrad.</span><span class="sxs-lookup"><span data-stu-id="554ea-110">[!INCLUDE[ssEW](../../includes/ssew-md.md)] also has a number of restrictions not related to compatibility level.</span></span>  
  
 <span data-ttu-id="554ea-111">Wenn diese Option ausgewählt ist, dann ist die Option zur Websynchronisierung für die Veröffentlichung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="554ea-111">If this option is selected, the Web synchronization option is enabled for the publication.</span></span> <span data-ttu-id="554ea-112">Weitere Informationen zur Websynchronisierung finden Sie unter [Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md).</span><span class="sxs-lookup"><span data-stu-id="554ea-112">For more information about Web synchronization, see [Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="554ea-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="554ea-113">See Also</span></span>  
 <span data-ttu-id="554ea-114">[Veröffentlichen von Daten und Datenbankobjekten](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="554ea-114">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 <span data-ttu-id="554ea-115">[Create a Publication](publish/create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="554ea-115">[Create a Publication](publish/create-a-publication.md) </span></span>  
 [<span data-ttu-id="554ea-116">Anzeigen und Ändern der Verteiler- und Verlegereigenschaften</span><span class="sxs-lookup"><span data-stu-id="554ea-116">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)   

  
