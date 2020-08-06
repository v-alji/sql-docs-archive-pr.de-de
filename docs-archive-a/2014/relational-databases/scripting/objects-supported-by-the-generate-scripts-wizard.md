---
title: Vom Assistenten zum Generieren von Skripts unterstützte Objekte
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 071eb2cb-f073-41ca-9f4d-11d3b8803495
author: rothja
ms.author: jroth
ms.openlocfilehash: 5ddc1da0d2f87fc12dfbe034a683802f54b7d34f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621461"
---
# <a name="objects-supported-by-the-generate-scripts-wizard"></a><span data-ttu-id="69de5-102">Vom Assistenten zum Generieren von Skripts unterstützte Objekte</span><span class="sxs-lookup"><span data-stu-id="69de5-102">Objects Supported by the Generate Scripts Wizard</span></span>
  <span data-ttu-id="69de5-103">Der Assistent zum Generieren und Veröffentlichen von Skripts unterstützt eine Teilmenge der von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]unterstützten Objekte.</span><span class="sxs-lookup"><span data-stu-id="69de5-103">The Generate and Publish Scripts wizard supports a subset of the objects supported by the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
## <a name="supported-objects"></a><span data-ttu-id="69de5-104">Unterstützte Objekte</span><span class="sxs-lookup"><span data-stu-id="69de5-104">Supported Objects</span></span>  
 <span data-ttu-id="69de5-105">In der folgenden Tabelle finden Sie die Objekte, die vom Assistenten zum Generieren und Veröffentlichen von Skripts veröffentlicht werden können.</span><span class="sxs-lookup"><span data-stu-id="69de5-105">The following table lists the objects that can be published supported by the Generate and Publish Scripts Wizard.</span></span>  
  
||||||  
|-|-|-|-|-|  
|<span data-ttu-id="69de5-106">Anwendungsrolle</span><span class="sxs-lookup"><span data-stu-id="69de5-106">Application role</span></span>|<span data-ttu-id="69de5-107">Datenbankrolle</span><span class="sxs-lookup"><span data-stu-id="69de5-107">Database role</span></span>|<span data-ttu-id="69de5-108">Schema</span><span class="sxs-lookup"><span data-stu-id="69de5-108">Schema</span></span>|<span data-ttu-id="69de5-109">Benutzerdefiniertes Aggregat</span><span class="sxs-lookup"><span data-stu-id="69de5-109">User-defined aggregate</span></span>|<span data-ttu-id="69de5-110">Sicht<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="69de5-110">View<sup>1</sup></span></span>|  
|<span data-ttu-id="69de5-111">Assembly</span><span class="sxs-lookup"><span data-stu-id="69de5-111">Assembly</span></span>|<span data-ttu-id="69de5-112">DEFAULT-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="69de5-112">DEFAULT constraint</span></span>|<span data-ttu-id="69de5-113">Gespeicherte Prozedur<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="69de5-113">Stored procedure<sup>1</sup></span></span>|<span data-ttu-id="69de5-114">Benutzerdefinierter Datentyp</span><span class="sxs-lookup"><span data-stu-id="69de5-114">User-defined data type</span></span>|<span data-ttu-id="69de5-115">XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="69de5-115">XML schema collection</span></span>|  
|<span data-ttu-id="69de5-116">CHECK-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="69de5-116">CHECK constraint</span></span>|<span data-ttu-id="69de5-117">Volltextkatalog</span><span class="sxs-lookup"><span data-stu-id="69de5-117">Full-text catalog</span></span>|<span data-ttu-id="69de5-118">Synonym</span><span class="sxs-lookup"><span data-stu-id="69de5-118">Synonym</span></span>|<span data-ttu-id="69de5-119">Benutzerdefinierte Funktion</span><span class="sxs-lookup"><span data-stu-id="69de5-119">User-defined function</span></span>||  
|<span data-ttu-id="69de5-120">Gespeicherte CLR-Prozedur (Common Language Runtime)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="69de5-120">CLR (common language runtime) stored procedure<sup>1</sup></span></span>|<span data-ttu-id="69de5-121">Index</span><span class="sxs-lookup"><span data-stu-id="69de5-121">Index</span></span>|<span data-ttu-id="69de5-122">Tabelle</span><span class="sxs-lookup"><span data-stu-id="69de5-122">Table</span></span>|<span data-ttu-id="69de5-123">Benutzerdefinierte Tabelle</span><span class="sxs-lookup"><span data-stu-id="69de5-123">User-defined table</span></span>||  
|<span data-ttu-id="69de5-124">CLR-benutzerdefinierte Funktion</span><span class="sxs-lookup"><span data-stu-id="69de5-124">CLR user-defined function</span></span>|<span data-ttu-id="69de5-125">Regel</span><span class="sxs-lookup"><span data-stu-id="69de5-125">Rule</span></span>|<span data-ttu-id="69de5-126">Benutzer<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="69de5-126">User<sup>2</sup></span></span>|<span data-ttu-id="69de5-127">Benutzerdefinierter Typ</span><span class="sxs-lookup"><span data-stu-id="69de5-127">User-defined type</span></span>||  
  
 <span data-ttu-id="69de5-128"><sup>1</sup> ohne Verschlüsselung veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="69de5-128"><sup>1</sup> Published without encryption.</span></span>  
  
 <span data-ttu-id="69de5-129"><sup>2</sup> alle nicht-Systembenutzer, die in der-Datenbank vorhanden sind, werden als Rollen veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="69de5-129"><sup>2</sup> Any non-system users that exist in the database are published as Roles.</span></span>  
  
  
