---
title: MSSQLSERVER_17130 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17130 (Database Engine error)
ms.assetid: 7ce6afca-221d-402f-89df-da7e74a339a8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b63be325273e4df33d837ec1548ed46701323977
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699704"
---
# <a name="mssqlserver_17130"></a><span data-ttu-id="cd2a2-102">MSSQLSERVER_17130</span><span class="sxs-lookup"><span data-stu-id="cd2a2-102">MSSQLSERVER_17130</span></span>
    
## <a name="details"></a><span data-ttu-id="cd2a2-103">Details</span><span class="sxs-lookup"><span data-stu-id="cd2a2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cd2a2-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="cd2a2-104">Product Name</span></span>|<span data-ttu-id="cd2a2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cd2a2-105">SQL Server</span></span>|  
|<span data-ttu-id="cd2a2-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="cd2a2-106">Event ID</span></span>|<span data-ttu-id="cd2a2-107">17130</span><span class="sxs-lookup"><span data-stu-id="cd2a2-107">17130</span></span>|  
|<span data-ttu-id="cd2a2-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="cd2a2-108">Event Source</span></span>|<span data-ttu-id="cd2a2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cd2a2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cd2a2-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="cd2a2-110">Component</span></span>|<span data-ttu-id="cd2a2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cd2a2-111">SQLEngine</span></span>|  
|<span data-ttu-id="cd2a2-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="cd2a2-112">Symbolic Name</span></span>|<span data-ttu-id="cd2a2-113">INIT_NOLOCKSPACE</span><span class="sxs-lookup"><span data-stu-id="cd2a2-113">INIT_NOLOCKSPACE</span></span>|  
|<span data-ttu-id="cd2a2-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="cd2a2-114">Message Text</span></span>|<span data-ttu-id="cd2a2-115">Nicht genügend Arbeitsspeicher für die konfigurierte Anzahl von Sperren.</span><span class="sxs-lookup"><span data-stu-id="cd2a2-115">Not enough memory for the configured number of locks.</span></span> <span data-ttu-id="cd2a2-116">Das Starten wird mit einer kleineren Sperrhashtabelle versucht. Dies kann Auswirkungen auf die Leistung haben.</span><span class="sxs-lookup"><span data-stu-id="cd2a2-116">Attempting to start with a smaller lock hash table, which may impact performance.</span></span> <span data-ttu-id="cd2a2-117">Bitten Sie den Datenbankadministrator, mehr Arbeitsspeicher für diese Instanz der Datenbank-Engine zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="cd2a2-117">Contact the database administrator to configure more memory for this instance of the Database Engine.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cd2a2-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="cd2a2-118">Explanation</span></span>  
 <span data-ttu-id="cd2a2-119">Nicht genug Arbeitsspeicher für die gewünschte Hashtabellengröße des Sperren-Managers.</span><span class="sxs-lookup"><span data-stu-id="cd2a2-119">Not enough memory for the desired lock manager hash table size.</span></span>  <span data-ttu-id="cd2a2-120">Es wird versucht, eine kleinere Hashtabelle zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="cd2a2-120">An attempt will be made to allocate a smaller hash table.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cd2a2-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="cd2a2-121">User Action</span></span>  
 <span data-ttu-id="cd2a2-122">Überprüfen Sie die Konfigurationsparameter des Serverarbeitsspeichers (minimaler/maximaler Serverarbeitsspeicher) und die Arbeitsspeicherauslastung.</span><span class="sxs-lookup"><span data-stu-id="cd2a2-122">Check server memory configuration parameters (min/max server memory), check for memory pressures.</span></span> <span data-ttu-id="cd2a2-123">Stellen Sie für SQL Server mehr Arbeitsspeicher zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cd2a2-123">Provide SQL Server more memory.</span></span>  
  
  
