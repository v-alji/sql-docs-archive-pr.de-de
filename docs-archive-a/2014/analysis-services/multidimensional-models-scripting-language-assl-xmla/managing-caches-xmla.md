---
title: Verwalten von Caches (XMLA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- XMLA, cache
- XML for Analysis, cache
- clearing cache
- cache [Analysis Services]
ms.assetid: afad5c39-d4c3-4307-b3b9-a06617da0028
author: minewiskan
ms.author: owend
ms.openlocfilehash: cdc5bcd2e0500749edfa298a871b6fec7243ddfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616773"
---
# <a name="managing-caches-xmla"></a><span data-ttu-id="4fd38-102">Verwalten von Caches (XMLA)</span><span class="sxs-lookup"><span data-stu-id="4fd38-102">Managing Caches (XMLA)</span></span>
  <span data-ttu-id="4fd38-103">Sie können den [ClearCache](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/clearcache-element-xmla) -Befehl in XML for Analysis (XMLA) verwenden, um den Cache einer angegebenen Dimension oder Partition zu löschen.</span><span class="sxs-lookup"><span data-stu-id="4fd38-103">You can use the [ClearCache](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/clearcache-element-xmla) command in XML for Analysis (XMLA) to clear the cache of a specified dimension or partition.</span></span> <span data-ttu-id="4fd38-104">Das Löschen des Caches zwingt [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , den Cache für dieses Objekt neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4fd38-104">Clearing the cache forces [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to rebuild the cache for that object.</span></span>  
  
## <a name="specifying-objects"></a><span data-ttu-id="4fd38-105">Angeben von Objekten</span><span class="sxs-lookup"><span data-stu-id="4fd38-105">Specifying Objects</span></span>  
 <span data-ttu-id="4fd38-106">Die [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) -Eigenschaft des- `ClearCache` Befehls kann nur einen Objekt Verweis für eines der folgenden Objekte enthalten.</span><span class="sxs-lookup"><span data-stu-id="4fd38-106">The [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `ClearCache` command can contain an object reference only for one of the following objects.</span></span> <span data-ttu-id="4fd38-107">Bei einem Objektverweis, der sich nicht auf eines der folgenden Objekte bezieht, tritt ein Fehler auf:</span><span class="sxs-lookup"><span data-stu-id="4fd38-107">An error occurs if an object reference is for an object other than one of following objects:</span></span>  
  
 <span data-ttu-id="4fd38-108">Datenbank</span><span class="sxs-lookup"><span data-stu-id="4fd38-108">Database</span></span>  
 <span data-ttu-id="4fd38-109">Löscht den Cache für alle Dimensionen und Partitionen, die in der Datenbank enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="4fd38-109">Clears the cache for all dimensions and partitions contained in the database.</span></span>  
  
 <span data-ttu-id="4fd38-110">Dimension</span><span class="sxs-lookup"><span data-stu-id="4fd38-110">Dimension</span></span>  
 <span data-ttu-id="4fd38-111">Löscht den Cache für die angegebene Dimension.</span><span class="sxs-lookup"><span data-stu-id="4fd38-111">Clears the cache for the specified dimension.</span></span>  
  
 <span data-ttu-id="4fd38-112">Cube</span><span class="sxs-lookup"><span data-stu-id="4fd38-112">Cube</span></span>  
 <span data-ttu-id="4fd38-113">Löscht den Cache für alle Partitionen, die in den Measuregruppen für den Cube enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="4fd38-113">Clears the cache for all partitions contained in the measure groups for the cube.</span></span>  
  
 <span data-ttu-id="4fd38-114">Measuregruppe</span><span class="sxs-lookup"><span data-stu-id="4fd38-114">Measure group</span></span>  
 <span data-ttu-id="4fd38-115">Löscht den Cache für alle Partitionen, die in der Measuregruppe enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="4fd38-115">Clears the cache for all partitions contained in the measure group.</span></span>  
  
 <span data-ttu-id="4fd38-116">Partition</span><span class="sxs-lookup"><span data-stu-id="4fd38-116">Partition</span></span>  
 <span data-ttu-id="4fd38-117">Löscht den Cache für die angegebene Partition.</span><span class="sxs-lookup"><span data-stu-id="4fd38-117">Clears the cache for the specified partition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fd38-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4fd38-118">See Also</span></span>  
 [<span data-ttu-id="4fd38-119">Entwickeln mit XMLA in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4fd38-119">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
