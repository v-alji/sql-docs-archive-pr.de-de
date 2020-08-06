---
title: MSSQLSERVER_9790 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9790 (Database Engine error)
ms.assetid: 83fd379f-5deb-4f97-8cb4-282e3d3fed94
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6d6d065d4a0e841da3b5ecb84f902df17dcfd60c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617033"
---
# <a name="mssqlserver_9790"></a><span data-ttu-id="c9ebd-102">MSSQLSERVER_9790</span><span class="sxs-lookup"><span data-stu-id="c9ebd-102">MSSQLSERVER_9790</span></span>
    
## <a name="details"></a><span data-ttu-id="c9ebd-103">Details</span><span class="sxs-lookup"><span data-stu-id="c9ebd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c9ebd-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="c9ebd-104">Product Name</span></span>|<span data-ttu-id="c9ebd-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c9ebd-105">SQL Server</span></span>|  
|<span data-ttu-id="c9ebd-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c9ebd-106">Event ID</span></span>|<span data-ttu-id="c9ebd-107">9790</span><span class="sxs-lookup"><span data-stu-id="c9ebd-107">9790</span></span>|  
|<span data-ttu-id="c9ebd-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="c9ebd-108">Event Source</span></span>|<span data-ttu-id="c9ebd-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c9ebd-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c9ebd-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="c9ebd-110">Component</span></span>|<span data-ttu-id="c9ebd-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c9ebd-111">SQLEngine</span></span>|  
|<span data-ttu-id="c9ebd-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="c9ebd-112">Symbolic Name</span></span>|<span data-ttu-id="c9ebd-113">SB3_XMIT_ERROR_ENTRANCE_BROKER_SINGLE_USER</span><span class="sxs-lookup"><span data-stu-id="c9ebd-113">SB3_XMIT_ERROR_ENTRANCE_BROKER_SINGLE_USER</span></span>|  
|<span data-ttu-id="c9ebd-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="c9ebd-114">Message Text</span></span>|<span data-ttu-id="c9ebd-115">Die eingehende Nachricht kann nicht geroutet werden.</span><span class="sxs-lookup"><span data-stu-id="c9ebd-115">Unable to route the incoming message.</span></span> <span data-ttu-id="c9ebd-116">Die MSDB-Systemdatenbank, die Routinginformationen enthält, befindet sich im Einzelbenutzermodus.</span><span class="sxs-lookup"><span data-stu-id="c9ebd-116">The system database MSDB containing routing information is in SINGLE USER mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c9ebd-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="c9ebd-117">Explanation</span></span>  
 <span data-ttu-id="c9ebd-118">Beim Klassifizieren einer empfangenen Nachricht ist ein Fehler aufgetreten, da die MSDB-Datenbank im SINGLE USER-Modus war.</span><span class="sxs-lookup"><span data-stu-id="c9ebd-118">An error occurred while trying to classify a message received off the wire because the MSDB database was in Single User mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c9ebd-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="c9ebd-119">User Action</span></span>  
 <span data-ttu-id="c9ebd-120">Ändern Sie die MSDB-Datenbank mit dem Befehl ALTER DATABASE auf den MULTI USER-Modus.</span><span class="sxs-lookup"><span data-stu-id="c9ebd-120">Change MSDB to be in MULTI USER mode with the ALTER DATABASE command.</span></span>  
  
  
