---
title: MSSQLSERVER_611 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 611 (Database Engine error)
ms.assetid: ac6a213f-5c38-44ad-bc85-a62863786614
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f0caa1c218e8b80059c0c97aac652da7db870af3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622151"
---
# <a name="mssqlserver_611"></a><span data-ttu-id="60489-102">MSSQLSERVER_611</span><span class="sxs-lookup"><span data-stu-id="60489-102">MSSQLSERVER_611</span></span>
    
## <a name="details"></a><span data-ttu-id="60489-103">Details</span><span class="sxs-lookup"><span data-stu-id="60489-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="60489-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="60489-104">Product Name</span></span>|<span data-ttu-id="60489-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="60489-105">SQL Server</span></span>|  
|<span data-ttu-id="60489-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="60489-106">Event ID</span></span>|<span data-ttu-id="60489-107">611</span><span class="sxs-lookup"><span data-stu-id="60489-107">611</span></span>|  
|<span data-ttu-id="60489-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="60489-108">Event Source</span></span>|<span data-ttu-id="60489-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="60489-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="60489-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="60489-110">Component</span></span>|<span data-ttu-id="60489-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="60489-111">SQLEngine</span></span>|  
|<span data-ttu-id="60489-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="60489-112">Symbolic Name</span></span>|<span data-ttu-id="60489-113">VAR_SIZE_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="60489-113">VAR_SIZE_TOO_BIG</span></span>|  
|<span data-ttu-id="60489-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="60489-114">Message Text</span></span>|<span data-ttu-id="60489-115">Es kann keine Zeile eingefügt oder aktualisiert werden, da die Gesamtgröße der Variablenspalte, einschließlich Verwaltungsbytes, die maximal zulässige Größe um %d Bytes überschreitet.</span><span class="sxs-lookup"><span data-stu-id="60489-115">Cannot insert or update a row because total variable column size, including overhead, is %d bytes more than the limit.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="60489-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="60489-116">Explanation</span></span>  
 <span data-ttu-id="60489-117">Die Maximalgröße der Variablenspalte übersteigt die vom Schema zugelassene Größe.</span><span class="sxs-lookup"><span data-stu-id="60489-117">The maximum variable column size is more than that allowed by the schema.</span></span> <span data-ttu-id="60489-118">Fehler 611 wird zurückgegeben, wenn die Variablenspalte die maximal zulässige Größe überschreitet, sofern das vardecimal-Speicherformat aktiviert ist, oder wenn die Größe der Variablenspalte die in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] für komprimierte Datensätze maximal zulässige Größe überschreitet.</span><span class="sxs-lookup"><span data-stu-id="60489-118">Error 611 is returned when the variable column is over the limit in the fixed case when vardecimal storage format is enabled, or when the variable column size is over the limit allowed in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] for a compressed data record.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="60489-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="60489-119">User Action</span></span>  
 <span data-ttu-id="60489-120">Reduzieren Sie die Größe des Datensatzes.</span><span class="sxs-lookup"><span data-stu-id="60489-120">Reduce the size of the record.</span></span>  
  
  
