---
title: MSSQLSERVER_1101 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1101 (Database Engine error)
ms.assetid: d63b67d5-59f5-4f77-904e-5ba67f2dd850
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 631b0ab1466815cbacfd71b4f9fd714fabd0f7b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620967"
---
# <a name="mssqlserver_1101"></a><span data-ttu-id="23718-102">MSSQLSERVER_1101</span><span class="sxs-lookup"><span data-stu-id="23718-102">MSSQLSERVER_1101</span></span>
    
## <a name="details"></a><span data-ttu-id="23718-103">Details</span><span class="sxs-lookup"><span data-stu-id="23718-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="23718-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="23718-104">Product Name</span></span>|<span data-ttu-id="23718-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="23718-105">SQL Server</span></span>|  
|<span data-ttu-id="23718-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="23718-106">Event ID</span></span>|<span data-ttu-id="23718-107">1101</span><span class="sxs-lookup"><span data-stu-id="23718-107">1101</span></span>|  
|<span data-ttu-id="23718-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="23718-108">Event Source</span></span>|<span data-ttu-id="23718-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="23718-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="23718-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="23718-110">Component</span></span>|<span data-ttu-id="23718-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="23718-111">SQLEngine</span></span>|  
|<span data-ttu-id="23718-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="23718-112">Symbolic Name</span></span>|<span data-ttu-id="23718-113">NOALLOCPG</span><span class="sxs-lookup"><span data-stu-id="23718-113">NOALLOCPG</span></span>|  
|<span data-ttu-id="23718-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="23718-114">Message Text</span></span>|<span data-ttu-id="23718-115">Eine neue Seite für die '%.\*ls'-Datenbank konnte nicht zugeordnet werden, weil in der Dateigruppe '%.\*ls' nicht genügend Speicherplatz verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="23718-115">Could not allocate a new page for database '%.\*ls' because of insufficient disk space in filegroup '%.\*ls'.</span></span> <span data-ttu-id="23718-116">Speicherplatz kann durch Löschen von Objekten in der Dateigruppe, Hinzufügen von Dateien zur Dateigruppe oder Festlegen der automatischen Vergrößerung für vorhandene Dateien in der Dateigruppe gewonnen werden.</span><span class="sxs-lookup"><span data-stu-id="23718-116">Create the necessary space by dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="23718-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="23718-117">Explanation</span></span>  
 <span data-ttu-id="23718-118">In einer Dateigruppe ist kein Speicherplatz verfügbar.</span><span class="sxs-lookup"><span data-stu-id="23718-118">No disk space available in a filegroup.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="23718-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="23718-119">User Action</span></span>  
 <span data-ttu-id="23718-120">Durch die folgenden Aktionen kann Speicherplatz in der Dateigruppe verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="23718-120">The following actions may make space available in the filegroup.</span></span>  
  
-   <span data-ttu-id="23718-121">Aktivieren Sie AUTOGROW.</span><span class="sxs-lookup"><span data-stu-id="23718-121">Turn on AUTOGROW.</span></span>  
  
-   <span data-ttu-id="23718-122">Fügen Sie der Dateigruppe weitere Dateien hinzu.</span><span class="sxs-lookup"><span data-stu-id="23718-122">Add more files to the file group.</span></span>  
  
-   <span data-ttu-id="23718-123">Geben Sie Speicherplatz frei, indem sich nicht benötigte Indizes oder Tabellen in der Dateigruppe löschen.</span><span class="sxs-lookup"><span data-stu-id="23718-123">Free up disk space by dropping unnecessary indexes or tables in the filegroup.</span></span>  
  
  
