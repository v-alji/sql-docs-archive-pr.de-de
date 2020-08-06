---
title: MSSQLSERVER_21889 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21889 (Database Engine error)
ms.assetid: ae199540-7986-4cc2-b782-cd22793236d3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c152a542550d7b81af880545f526037baeb4644e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718181"
---
# <a name="mssqlserver_21889"></a><span data-ttu-id="541ed-102">MSSQLSERVER_21889</span><span class="sxs-lookup"><span data-stu-id="541ed-102">MSSQLSERVER_21889</span></span>
    
## <a name="details"></a><span data-ttu-id="541ed-103">Details</span><span class="sxs-lookup"><span data-stu-id="541ed-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="541ed-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="541ed-104">Product Name</span></span>|<span data-ttu-id="541ed-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="541ed-105">SQL Server</span></span>|  
|<span data-ttu-id="541ed-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="541ed-106">Event ID</span></span>|<span data-ttu-id="541ed-107">21889</span><span class="sxs-lookup"><span data-stu-id="541ed-107">21889</span></span>|  
|<span data-ttu-id="541ed-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="541ed-108">Event Source</span></span>|<span data-ttu-id="541ed-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="541ed-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="541ed-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="541ed-110">Component</span></span>|<span data-ttu-id="541ed-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="541ed-111">SQLEngine</span></span>|  
|<span data-ttu-id="541ed-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="541ed-112">Symbolic Name</span></span>|<span data-ttu-id="541ed-113">SQLErrorNum21889</span><span class="sxs-lookup"><span data-stu-id="541ed-113">SQLErrorNum21889</span></span>|  
|<span data-ttu-id="541ed-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="541ed-114">Message Text</span></span>|<span data-ttu-id="541ed-115">Die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz '%s' ist kein Replikationsverleger.</span><span class="sxs-lookup"><span data-stu-id="541ed-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance '%s' is not a replication publisher.</span></span> <span data-ttu-id="541ed-116">Führen Sie `sp_adddistributor` auf der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz '%s' mit dem Verteiler '%s' aus, um die Instanz als Host der Veröffentlichungsdatenbank '%s' zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="541ed-116">Run `sp_adddistributor` on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance '%s' with distributor '%s' in order to enable the instance to host the publishing database '%s'.</span></span> <span data-ttu-id="541ed-117">Stellen Sie sicher, dass Sie die gleiche Anmeldung und das gleiche Kennwort angeben, die für den ursprünglichen Verleger verwendet worden sind.</span><span class="sxs-lookup"><span data-stu-id="541ed-117">Make certain to specify the same login and password as that used for the original publisher.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="541ed-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="541ed-118">Explanation</span></span>  
 <span data-ttu-id="541ed-119">Um die Verlegerdatenbank hosten zu können, muss die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ein Replikationsverleger sein.</span><span class="sxs-lookup"><span data-stu-id="541ed-119">In order to host the publisher database, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be a replication publisher.</span></span> <span data-ttu-id="541ed-120">`sp_validate_redirected_publisher` ruft `sp_helpdistributor` beim Remoteserver auf, um zu bestimmen, ob der Server Replikationsverleger ist.</span><span class="sxs-lookup"><span data-stu-id="541ed-120">`sp_validate_redirected_publisher` calls `sp_helpdistributor` at the remote server to determine whether the server is a replication publisher.</span></span> <span data-ttu-id="541ed-121">Dieser Fehler wird zurückgegeben, wenn die Ausführung der gespeicherten Prozedur `sp_helpdistributor` ergibt, dass die Zielinstanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] kein Replikationsverleger ist.</span><span class="sxs-lookup"><span data-stu-id="541ed-121">This error is returned when execution of the stored procedure `sp_helpdistributor` indicates that the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not a replication publisher.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="541ed-122">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="541ed-122">User Action</span></span>  
 <span data-ttu-id="541ed-123">Führen Sie `sp_adddistributor` bei der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], die als Host der Verlegerdatenbank fungiert hat.</span><span class="sxs-lookup"><span data-stu-id="541ed-123">Execute `sp_adddistributor` at the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the publisher database.</span></span> <span data-ttu-id="541ed-124">Wenn Sie `sp_adddistributor` ausführen, geben Sie den richtigen Verteiler an.</span><span class="sxs-lookup"><span data-stu-id="541ed-124">When running `sp_adddistributor`, specify the correct distributor.</span></span> <span data-ttu-id="541ed-125">Verwenden Sie den gleichen Wert für den- *@password* Parameter, der verwendet wurde, als `sp_adddistributor` ursprünglich auf dem Verteiler ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="541ed-125">Use the same value for the *@password* parameter as that used when `sp_adddistributor` was initially run at the distributor.</span></span>  
  
  
