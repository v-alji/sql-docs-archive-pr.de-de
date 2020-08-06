---
title: MSSQL_ENG021330 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021330 error
ms.assetid: e2bb2e21-62a7-4689-b68b-bdfba3fdd985
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4338756a641b23bfc6f52da6b3de296bb6415756
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697941"
---
# <a name="mssql_eng021330"></a><span data-ttu-id="bf309-102">MSSQL_ENG021330</span><span class="sxs-lookup"><span data-stu-id="bf309-102">MSSQL_ENG021330</span></span>
    
## <a name="message-details"></a><span data-ttu-id="bf309-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="bf309-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bf309-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="bf309-104">Product Name</span></span>|<span data-ttu-id="bf309-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bf309-105">SQL Server</span></span>|  
|<span data-ttu-id="bf309-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="bf309-106">Event ID</span></span>|<span data-ttu-id="bf309-107">21330</span><span class="sxs-lookup"><span data-stu-id="bf309-107">21330</span></span>|  
|<span data-ttu-id="bf309-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="bf309-108">Event Source</span></span>|<span data-ttu-id="bf309-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bf309-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bf309-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="bf309-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="bf309-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="bf309-111">Symbolic Name</span></span>||  
|<span data-ttu-id="bf309-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="bf309-112">Message Text</span></span>|<span data-ttu-id="bf309-113">Fehler beim Erstellen eines Unterverzeichnisses unter dem Replikationsarbeitsverzeichnis. (%1!s!)</span><span class="sxs-lookup"><span data-stu-id="bf309-113">Failed to create a sub-directory under the replication working directory.(%ls)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bf309-114">Erklärung</span><span class="sxs-lookup"><span data-stu-id="bf309-114">Explanation</span></span>  
 <span data-ttu-id="bf309-115">Dieser Fehler kann auftreten, wenn ein Abonnement manuell initialisiert wird und es beim Erstellen des Verzeichnisses, in dem die Replikationsskripts gespeichert werden, zu einem Problem kommt.</span><span class="sxs-lookup"><span data-stu-id="bf309-115">This error can occur when a subscription is initialized manually, and there is a problem creating the directory in which replication scripts are stored.</span></span> <span data-ttu-id="bf309-116">Ursache für den Fehler kann ein Problem mit den Berechtigungen sein: Wenn ein Abonnement ohne Verwendung einer Momentaufnahme initialisiert wird, muss das Konto, über dass der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst auf dem Verleger ausgeführt wird, Schreibberechtigungen für den Momentaufnahmeordner auf dem Verleger besitzen.</span><span class="sxs-lookup"><span data-stu-id="bf309-116">The error can be caused by a permissions issue: when a subscription is initialized without using a snapshot, the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs at the Publisher must have write permissions on the snapshot folder at the Distributor.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bf309-117">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="bf309-117">User Action</span></span>  
 <span data-ttu-id="bf309-118">Stellen Sie sicher, dass der richtige Pfad für den Momentaufnahmeordner angegeben wird und dass das Konto, über das der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst auf dem Verleger ausgeführt wird, über ausreichende Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="bf309-118">Ensure that the correct path has been specified for the snapshot folder and that the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs at the Publisher has sufficient permissions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf309-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bf309-119">See Also</span></span>  
 <span data-ttu-id="bf309-120">[Angeben des standardmäßigen Momentaufnahme Speicher Orts](snapshot-options.md#snapshot-folder-locations) </span><span class="sxs-lookup"><span data-stu-id="bf309-120">[Specify the Default Snapshot Location](snapshot-options.md#snapshot-folder-locations) </span></span>  
 <span data-ttu-id="bf309-121">[Fehler- und Ereignisreferenz &#40;Replikation&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="bf309-121">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="bf309-122">Initialisieren eines Transaktionsabonnements ohne Momentaufnahme</span><span class="sxs-lookup"><span data-stu-id="bf309-122">Initialize a Transactional Subscription Without a Snapshot</span></span>](initialize-a-transactional-subscription-without-a-snapshot.md)  
  
  
