---
title: MSSQLSERVER_21893 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21893 (Database Engine error)
ms.assetid: 1ab1195a-fe2a-4e06-b871-b177b6bea1fe
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 92479d7727ac2300d6a60d02492667d99a69b022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620436"
---
# <a name="mssqlserver_21893"></a><span data-ttu-id="a5676-102">MSSQLSERVER_21893</span><span class="sxs-lookup"><span data-stu-id="a5676-102">MSSQLSERVER_21893</span></span>
    
## <a name="details"></a><span data-ttu-id="a5676-103">Details</span><span class="sxs-lookup"><span data-stu-id="a5676-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a5676-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="a5676-104">Product Name</span></span>|<span data-ttu-id="a5676-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a5676-105">SQL Server</span></span>|  
|<span data-ttu-id="a5676-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a5676-106">Event ID</span></span>|<span data-ttu-id="a5676-107">21893</span><span class="sxs-lookup"><span data-stu-id="a5676-107">21893</span></span>|  
|<span data-ttu-id="a5676-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="a5676-108">Event Source</span></span>|<span data-ttu-id="a5676-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a5676-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a5676-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="a5676-110">Component</span></span>|<span data-ttu-id="a5676-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a5676-111">SQLEngine</span></span>|  
|<span data-ttu-id="a5676-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="a5676-112">Symbolic Name</span></span>|<span data-ttu-id="a5676-113">SQLErrorNum21893</span><span class="sxs-lookup"><span data-stu-id="a5676-113">SQLErrorNum21893</span></span>|  
|<span data-ttu-id="a5676-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="a5676-114">Message Text</span></span>|<span data-ttu-id="a5676-115">Die Abonnenten (%s) des ursprünglichen Verlegers '%s' werden bei dem umgeleitetem Verleger '%s' nicht als Remoteserver angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a5676-115">The subscribers ( %s ) of original publisher '%s' do not appear as remote servers at redirected publisher '%s'.</span></span> <span data-ttu-id="a5676-116">Führen `sp_addlinkedserver` Sie auf dem umgeleiteten Verleger aus, um diese Abonnenten als Remote Server hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a5676-116">Run `sp_addlinkedserver` at the redirected publisher to add these subscribers as remote servers .</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a5676-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="a5676-117">Explanation</span></span>  
 <span data-ttu-id="a5676-118">`sp_validate_redirected_publisher` verwendet die Abonnementmetadatentabellen von der Verlegerdatenbank beim Remoteserver, um seine zugeordneten Abonnenten zu identifizieren, und überprüft, ob für die Abonnenten zugehörige Einträge in master.dbo.sysservers vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a5676-118">`sp_validate_redirected_publisher` uses the subscription metadata tables of the publisher database at the remote server to identify its associated subscribers and verifies that there are associated entries in master.dbo.sysservers for the subscribers.</span></span> <span data-ttu-id="a5676-119">Dieser Fehler wird zurückgegeben, wenn einer der identifizierten Abonnenten nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a5676-119">This error is returned if any of the identified subscribers are not present.</span></span>  
  
 <span data-ttu-id="a5676-120">Dies wird jedoch nicht als schwerwiegender Fehler angesehen.</span><span class="sxs-lookup"><span data-stu-id="a5676-120">This error is not considered a fatal error.</span></span> <span data-ttu-id="a5676-121">Agents, in denen dieser Fehler auftritt, protokollieren den Fehler als Information, werden aber nicht beendet, da sich das Nichtvorhandensein entsprechender Abonnenteneinträge beim neuen Verleger nur beschränkt auf die Replikation auswirkt.</span><span class="sxs-lookup"><span data-stu-id="a5676-121">Agents encountering this error will log the error as informational but will not terminate, since a failure to have appropriate subscriber entries at the new publisher has limited impact on replication.</span></span> <span data-ttu-id="a5676-122">Ohne einen entsprechenden Eintrag für einen Abonnenten in „sysservers“ schlagen einige Abonnementverwaltungsaktivitäten möglicherweise fehl, wenn sie über [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a5676-122">Without an appropriate entry for a subscriber in sysservers, some subscription management activities may fail when executed through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="a5676-123">Diese gleichen Aktivitäten können jedoch erfolgreich ausgeführt werden, indem die gespeicherten Verwaltungsprozeduren explizit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a5676-123">However, these same activities can be successfully performed by executing the management stored procedures explicitly.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a5676-124">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="a5676-124">User Action</span></span>  
 <span data-ttu-id="a5676-125">Führen Sie `sp_addlinkedserver` für jeden identifizierten Abonnenten auf dem umgeleiteten Verleger aus, um diese Abonnenten als Remoteserver hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a5676-125">Run `sp_addlinkedserver` at the redirected publisher for each of the identified subscribers to add them as remote servers.</span></span> <span data-ttu-id="a5676-126">Führen Sie dann `sp_serveroption` aus, um das Abonnentenbit für den Server festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a5676-126">Then, run `sp_serveroption` to set the subscriber bit for the server.</span></span>  
  
  
