---
title: Wartungsplan (Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.maintplanproperties.server.f1
- sql12.swb.maint.servers.f1
ms.assetid: ac24d1a8-dd2f-4162-b804-c0df1fc1e61d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c971edc9b641846068313f47ca410715ec552014
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616525"
---
# <a name="maintenance-plan-servers"></a><span data-ttu-id="1c0fd-102">Wartungsplan (Server)</span><span class="sxs-lookup"><span data-stu-id="1c0fd-102">Maintenance Plan (Servers)</span></span>
  <span data-ttu-id="1c0fd-103">Mithilfe des Dialogfelds **Server** können Sie die Server auswählen, auf denen der Wartungsplan ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1c0fd-103">Use the **Servers** dialog box to select the servers where you want to run the maintenance plan.</span></span>  
  
 <span data-ttu-id="1c0fd-104">Es muss eine Multiserverumgebung mit einem Masterserver und mindestens einem Zielserver konfiguriert sein, um einen Multiserver-Wartungsplan erstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="1c0fd-104">A multiserver environment containing one master server and one or more target servers must be configured to create a multiserver maintenance plan.</span></span> <span data-ttu-id="1c0fd-105">Für Multiserver-Wartungspläne sollte der lokale Server als Masterserver konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1c0fd-105">For multiserver maintenance plans, the local server should be configured as a master server.</span></span> <span data-ttu-id="1c0fd-106">Bei Multiserverumgebungen werden in diesem Dialogfeld der **(lokale)** Masterserver und alle entsprechenden Zielserver angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1c0fd-106">In multiserver environments, this dialog box displays the **(local)** master server and all corresponding target servers.</span></span> <span data-ttu-id="1c0fd-107">Für den lokalen Server wird ein Auftrag des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents erstellt.</span><span class="sxs-lookup"><span data-stu-id="1c0fd-107">One [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job is created for the local server.</span></span> <span data-ttu-id="1c0fd-108">Er wird aktiviert oder deaktiviert, je nachdem, ob Sie den **(lokalen)** Server auswählen.</span><span class="sxs-lookup"><span data-stu-id="1c0fd-108">It is enabled or disabled depending on whether you select the **(local)** server.</span></span> <span data-ttu-id="1c0fd-109">Wenn Zielserver ausgewählt sind, wird für jeden ausgewählten Zielserver ein Multiserverauftrag erstellt und auf diesen heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="1c0fd-109">If target servers are selected, a multiserver job is created and downloaded to each of the selected target servers.</span></span> <span data-ttu-id="1c0fd-110">Wenn keine Zielserver ausgewählt sind, wird der Multiserverauftrag gelöscht.</span><span class="sxs-lookup"><span data-stu-id="1c0fd-110">If no target servers are selected, the multiserver job is deleted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c0fd-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1c0fd-111">See Also</span></span>  
 <span data-ttu-id="1c0fd-112">[Wartungspläne](maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="1c0fd-112">[Maintenance Plans](maintenance-plans.md) </span></span>  
 <span data-ttu-id="1c0fd-113">[Erstellen einer Multiserverumgebung](../../ssms/agent/create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="1c0fd-113">[Create a Multiserver Environment](../../ssms/agent/create-a-multiserver-environment.md) </span></span>  
 <span data-ttu-id="1c0fd-114">[Einrichten eines Masterservers](../../ssms/agent/make-a-master-server.md) </span><span class="sxs-lookup"><span data-stu-id="1c0fd-114">[Make a Master Server](../../ssms/agent/make-a-master-server.md) </span></span>  
 [<span data-ttu-id="1c0fd-115">Erstellen eines Zielservers</span><span class="sxs-lookup"><span data-stu-id="1c0fd-115">Make a Target Server</span></span>](../../ssms/agent/make-a-target-server.md)  
  
  
