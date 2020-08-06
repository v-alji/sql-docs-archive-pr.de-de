---
title: MSSQLSERVER_21899 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21899 (Database Engine error)
ms.assetid: 32b87a7c-5380-4638-b147-dd78618f6625
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cb1af04b56685d0e1b5a703b812d08d88909b693
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699650"
---
# <a name="mssqlserver_21899"></a><span data-ttu-id="af5aa-102">MSSQLSERVER_21899</span><span class="sxs-lookup"><span data-stu-id="af5aa-102">MSSQLSERVER_21899</span></span>
    
## <a name="details"></a><span data-ttu-id="af5aa-103">Details</span><span class="sxs-lookup"><span data-stu-id="af5aa-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="af5aa-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="af5aa-104">Product Name</span></span>|<span data-ttu-id="af5aa-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="af5aa-105">SQL Server</span></span>|  
|<span data-ttu-id="af5aa-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="af5aa-106">Event ID</span></span>|<span data-ttu-id="af5aa-107">21899</span><span class="sxs-lookup"><span data-stu-id="af5aa-107">21899</span></span>|  
|<span data-ttu-id="af5aa-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="af5aa-108">Event Source</span></span>|<span data-ttu-id="af5aa-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="af5aa-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="af5aa-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="af5aa-110">Component</span></span>|<span data-ttu-id="af5aa-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="af5aa-111">SQLEngine</span></span>|  
|<span data-ttu-id="af5aa-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="af5aa-112">Symbolic Name</span></span>|<span data-ttu-id="af5aa-113">SQLErrorNum21899</span><span class="sxs-lookup"><span data-stu-id="af5aa-113">SQLErrorNum21899</span></span>|  
|<span data-ttu-id="af5aa-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="af5aa-114">Message Text</span></span>|<span data-ttu-id="af5aa-115">Die Abfrage beim umgeleiteten Verleger '%s' zur Bestimmung, ob sysserver-Einträge für die Abonnenten des ursprünglichen Verlegers '%s' vorliegen, ist mit dem Fehler '%d', Fehlermeldung '%s', fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="af5aa-115">The query at the redirected publisher '%s' to determine whether there were sysserver entries for the subscribers of the original publisher '%s' failed with error '%d', error message '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="af5aa-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="af5aa-116">Explanation</span></span>  
 <span data-ttu-id="af5aa-117">`sp_validate_redirected_publisher` fragt die Abonnementmetadatentabellen von der Verlegerdatenbank beim Remoteserver ab, um seine zugeordneten Abonnenten zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="af5aa-117">`sp_validate_redirected_publisher` queries the subscription metadata tables of the publisher database at the remote server to determine its associated subscribers.</span></span> <span data-ttu-id="af5aa-118">Fehler 21899 wird zurückgegeben, wenn diese Abfrage fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="af5aa-118">Error 21899 is returned if this query fails.</span></span> <span data-ttu-id="af5aa-119">Die Überprüfungsabfrage erfordert Zugriff auf die veröffentlichte Datenbank beim umgeleiteten Verleger.</span><span class="sxs-lookup"><span data-stu-id="af5aa-119">The validation query requires access to the published database at the redirected publisher.</span></span> <span data-ttu-id="af5aa-120">Wenn die Anmeldung, die beim Aufruf von `sp_adddistpublisher` für den ursprünglichen Verleger angegeben wurde, nicht berechtigt ist, beim umgeleiteten Verleger auf die veröffentlichte Datenbank zuzugreifen, wird Fehler 21899 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="af5aa-120">If the login specified when `sp_adddistpublisher` is called for the original publisher is not authorized to access the published database at the redirected publisher, error 21899 is returned.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="af5aa-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="af5aa-121">User Action</span></span>  
 <span data-ttu-id="af5aa-122">Überprüfen Sie die erwähnte Fehlermeldung, um die Fehlerursache zu bestimmen und entsprechende Korrekturmaßnahmen zu ergreifen</span><span class="sxs-lookup"><span data-stu-id="af5aa-122">Review the cited error message to determine the cause of the failure and take appropriate corrective action</span></span>  
  
  
