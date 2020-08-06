---
title: MSSQLSERVER_17053 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17053 (Database Engine error)
ms.assetid: e0a01f3d-d0aa-4c38-8bcc-82e59de50512
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 11137ba334b66f20c7d9a6caaaf7d1ef42c15dec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607805"
---
# <a name="mssqlserver_17053"></a><span data-ttu-id="c5284-102">MSSQLSERVER_17053</span><span class="sxs-lookup"><span data-stu-id="c5284-102">MSSQLSERVER_17053</span></span>
    
## <a name="details"></a><span data-ttu-id="c5284-103">Details</span><span class="sxs-lookup"><span data-stu-id="c5284-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c5284-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="c5284-104">Product Name</span></span>|<span data-ttu-id="c5284-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c5284-105">SQL Server</span></span>|  
|<span data-ttu-id="c5284-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c5284-106">Event ID</span></span>|<span data-ttu-id="c5284-107">17053</span><span class="sxs-lookup"><span data-stu-id="c5284-107">17053</span></span>|  
|<span data-ttu-id="c5284-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="c5284-108">Event Source</span></span>|<span data-ttu-id="c5284-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c5284-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c5284-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="c5284-110">Component</span></span>|<span data-ttu-id="c5284-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c5284-111">SQLEngine</span></span>|  
|<span data-ttu-id="c5284-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="c5284-112">Symbolic Name</span></span>|<span data-ttu-id="c5284-113">OS_ERROR</span><span class="sxs-lookup"><span data-stu-id="c5284-113">OS_ERROR</span></span>|  
|<span data-ttu-id="c5284-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="c5284-114">Message Text</span></span>|<span data-ttu-id="c5284-115">%ls: Betriebssystemfehler %ls.</span><span class="sxs-lookup"><span data-stu-id="c5284-115">%ls: Operating system error %ls encountered.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c5284-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="c5284-116">Explanation</span></span>  
 <span data-ttu-id="c5284-117">Ein allgemeiner Betriebssystemfehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c5284-117">Generic operating system error occurred.</span></span>  <span data-ttu-id="c5284-118">Der resultierende Status ist unbekannt.</span><span class="sxs-lookup"><span data-stu-id="c5284-118">Not clear what the resulting state is.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c5284-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="c5284-119">User Action</span></span>  
 <span data-ttu-id="c5284-120">Normalerweise tritt dies in Verbindung mit einem anderen Fehler auf und sollte dazu verwendet werden, eine Diagnose für diesen Fehler zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c5284-120">Usually this is in conjunction with some other error and should be used to help diagnose that failure.</span></span> <span data-ttu-id="c5284-121">Zu den Beispielen gehören fehlerhafte Lese- oder Schreibvorgänge für Daten und Protokolldateien, Lese-/Schreibvorgänge für die Registrierung oder unerwartete Win32API-Fehler.</span><span class="sxs-lookup"><span data-stu-id="c5284-121">Examples would include reads or writes to data or log files that fail, registry read/write operations, or other unexpected Win32API failures.</span></span>  
  
  
