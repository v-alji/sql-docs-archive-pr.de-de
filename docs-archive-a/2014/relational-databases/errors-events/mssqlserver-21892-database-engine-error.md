---
title: MSSQLSERVER_21892 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21892 (Database Engine error)
ms.assetid: 199818e8-28f4-440e-ad85-7bea88f51153
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5fd3bfa1213f0569293991d6bd759619c6e7b596
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723910"
---
# <a name="mssqlserver_21892"></a><span data-ttu-id="b36a4-102">MSSQLSERVER_21892</span><span class="sxs-lookup"><span data-stu-id="b36a4-102">MSSQLSERVER_21892</span></span>
    
## <a name="details"></a><span data-ttu-id="b36a4-103">Details</span><span class="sxs-lookup"><span data-stu-id="b36a4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b36a4-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="b36a4-104">Product Name</span></span>|<span data-ttu-id="b36a4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b36a4-105">SQL Server</span></span>|  
|<span data-ttu-id="b36a4-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b36a4-106">Event ID</span></span>|<span data-ttu-id="b36a4-107">21892</span><span class="sxs-lookup"><span data-stu-id="b36a4-107">21892</span></span>|  
|<span data-ttu-id="b36a4-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="b36a4-108">Event Source</span></span>|<span data-ttu-id="b36a4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b36a4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b36a4-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="b36a4-110">Component</span></span>|<span data-ttu-id="b36a4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b36a4-111">SQLEngine</span></span>|  
|<span data-ttu-id="b36a4-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="b36a4-112">Symbolic Name</span></span>|<span data-ttu-id="b36a4-113">SQLErrorNum21892</span><span class="sxs-lookup"><span data-stu-id="b36a4-113">SQLErrorNum21892</span></span>|  
|<span data-ttu-id="b36a4-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="b36a4-114">Message Text</span></span>|<span data-ttu-id="b36a4-115">„sys.availability_replicas“ kann beim primären Replikat der Verfügbarkeitsgruppe, das dem virtuellen Netzwerknamen '%s' für die Servernamen der Mitgliedsreplikate zugeordnet ist, nicht abgefragt werden: Fehler =%d, Fehlermeldung =% s.'</span><span class="sxs-lookup"><span data-stu-id="b36a4-115">Unable to query sys.availability_replicas at the availability group primary associated with virtual network name '%s' for the server names of the member replicas: error = %d, error message = %s.',</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b36a4-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="b36a4-116">Explanation</span></span>  
 <span data-ttu-id="b36a4-117">`sp_validate_replica_hosts_as_publishers` fragt das aktuelle Primäre der Verfügbarkeitsgruppe ab, das dem umgeleiteten Verleger zugeordnet ist, um die Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zu bestimmen, welche die Mitgliedsreplikate hosten.</span><span class="sxs-lookup"><span data-stu-id="b36a4-117">`sp_validate_replica_hosts_as_publishers` queries the current primary of the availability group associated with the redirected publisher, to determine the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that host the member replicas.</span></span>  <span data-ttu-id="b36a4-118">Wenn diese Abfrage fehlschlägt, wird Fehler 21892 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b36a4-118">When this query fails, error 21892 is returned.</span></span>  
  
 <span data-ttu-id="b36a4-119">In dem `sp_validate_replica_hosts_as_publishers`Aufruf wird der temporäre Verbindungsserver in der Regel zum ersten Mal verwendet. Wenn Verbindungsprobleme vorliegen, ist es daher wahrscheinlich, dass diese zuerst beim Aufruf von `sp_validate_replica_hosts_as_publishers` augenscheinlich werden.</span><span class="sxs-lookup"><span data-stu-id="b36a4-119">`sp_validate_replica_hosts_as_publishers` is typically on of the first use of the temporary linked server, so if there are connectivity problems they are likely to appear first with `sp_validate_replica_hosts_as_publishers`.</span></span> <span data-ttu-id="b36a4-120">Im Gegensatz zu `sp_validate_redirected_publisher` verwendet der von `sp_validate_replica_hosts_as_publishers` verwendete Verbindungsserver beim Herstellen einer Verbindung mit Replikathost der Verfügbarkeitsgruppen immer die Anmeldeinformationen des Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="b36a4-120">Unlike `sp_validate_redirected_publisher`, the linked server used by `sp_validate_replica_hosts_as_publishers` always uses the credentials of the caller when connecting to any of the availability group replica hosts.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b36a4-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="b36a4-121">User Action</span></span>  
 <span data-ttu-id="b36a4-122">Stellen Sie beim Ausführen dieser gespeicherten Prozedur sicher, dass Sie eine Anmeldung verwenden, die bei allen Replikaten gültig ist.</span><span class="sxs-lookup"><span data-stu-id="b36a4-122">When running this stored procedure, made certain that you run from a login that is valid on all of the replicas.</span></span> <span data-ttu-id="b36a4-123">Die Anmeldung muss dazu autorisiert sein, Verfügbarkeitsgruppenmetadatentabellen abzufragen sowie die Abonnementmetadatentabellen im Verlegerdatenbankreplikat abzufragen.</span><span class="sxs-lookup"><span data-stu-id="b36a4-123">The login will require sufficient authorization to query availability group metadata tables as well as to query the subscription metadata tables in the publisher database replica.</span></span>  
  
 <span data-ttu-id="b36a4-124">Überprüfen Sie ursprünglich angegebene Fehlermeldung, um die Fehlerursache zu bestimmen und entsprechende Korrekturmaßnahmen zu ergreifen.</span><span class="sxs-lookup"><span data-stu-id="b36a4-124">Examine the original referenced error to determine the cause of the failure and appropriate corrective action.</span></span>  
  
  
