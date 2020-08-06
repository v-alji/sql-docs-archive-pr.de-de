---
title: Standardmäßig deaktivierte Funktionen (Analysis Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a9529edf-337e-4fdd-9a13-99cfe96b4fa1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 87752b8760ffc80e80c87ac1132cae36f2f151b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698786"
---
# <a name="features-off-by-default-analysis-services"></a><span data-ttu-id="a6ca5-102">Standardmäßig deaktivierte Funktionen (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="a6ca5-102">Features off by default (Analysis Services)</span></span>
  <span data-ttu-id="a6ca5-103">Eine Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ist standardmäßig für Sicherheit ausgelegt.</span><span class="sxs-lookup"><span data-stu-id="a6ca5-103">An instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is designed to be secure by default.</span></span> <span data-ttu-id="a6ca5-104">Aus diesem Grund sind in der Standardeinstellung alle Funktionen deaktiviert, die sich auf die Sicherheit auswirken können.</span><span class="sxs-lookup"><span data-stu-id="a6ca5-104">Therefore, features that might compromise security are disabled by default.</span></span> <span data-ttu-id="a6ca5-105">Die folgenden Funktionen sind bei der Installation deaktiviert und müssen gesondert aktiviert werden, wenn sie verwendet werden sollen:</span><span class="sxs-lookup"><span data-stu-id="a6ca5-105">The following features are installed in a disabled state and must specifically be enabled if you want to use them.</span></span>  
  
## <a name="feature-list"></a><span data-ttu-id="a6ca5-106">Funktionsliste</span><span class="sxs-lookup"><span data-stu-id="a6ca5-106">Feature List</span></span>  
 <span data-ttu-id="a6ca5-107">Wenn Sie die folgenden Funktionen aktivieren möchten, stellen Sie eine Verbindung zu [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] über [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="a6ca5-107">To enable the following features, connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="a6ca5-108">Klicken Sie mit der rechten Maustaste auf den Instanznamen, und wählen Sie **Facets**aus.</span><span class="sxs-lookup"><span data-stu-id="a6ca5-108">Right-click the instance name and choose **Facets**.</span></span> <span data-ttu-id="a6ca5-109">Alternativ können Sie diese Funktionen auch über die Servereigenschaften aktivieren. Dies wird im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a6ca5-109">Alternatively, you can enable these features through server properties, as described in the next section.</span></span>  
  
-   <span data-ttu-id="a6ca5-110">Ad-Hoc-Data-Mining-Abfragen (OpenRowset)</span><span class="sxs-lookup"><span data-stu-id="a6ca5-110">Ad Hoc Data Mining (OpenRowset) Queries</span></span>  
  
-   <span data-ttu-id="a6ca5-111">Verknüpfte Objekte (An)</span><span class="sxs-lookup"><span data-stu-id="a6ca5-111">Linked Objects (To)</span></span>  
  
-   <span data-ttu-id="a6ca5-112">Verknüpfte Objekte (Von)</span><span class="sxs-lookup"><span data-stu-id="a6ca5-112">Linked Objects (From)</span></span>  
  
-   <span data-ttu-id="a6ca5-113">Nur lokale Verbindungen überwachen</span><span class="sxs-lookup"><span data-stu-id="a6ca5-113">Listen Only On Local Connections</span></span>  
  
-   <span data-ttu-id="a6ca5-114">Benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="a6ca5-114">User Defined Functions</span></span>  
  
## <a name="server-properties"></a><span data-ttu-id="a6ca5-115">Servereigenschaften</span><span class="sxs-lookup"><span data-stu-id="a6ca5-115">Server properties</span></span>  
 <span data-ttu-id="a6ca5-116">Zusätzliche standardmäßig deaktivierte Funktionen können Sie über die Servereigenschaften aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a6ca5-116">Additional features that are off by default can be enabled through server properties.</span></span> <span data-ttu-id="a6ca5-117">Stellen Sie eine Verbindung zu [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] über [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="a6ca5-117">Connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="a6ca5-118">Klicken Sie mit der rechten Maustaste auf den Instanznamen, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="a6ca5-118">Right-click the instance name and choose **Properties**.</span></span> <span data-ttu-id="a6ca5-119">Klicken Sie auf **Allgemein**, und klicken Sie dann auf **Show Advanced** , um eine umfangreichere Liste mit Eigenschaften anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a6ca5-119">Click **General**, and then click **Show Advanced** to display a larger property list.</span></span>  
  
-   <span data-ttu-id="a6ca5-120">Ad-Hoc-Data-Mining-Abfragen (OpenRowset)</span><span class="sxs-lookup"><span data-stu-id="a6ca5-120">Ad Hoc Data Mining (OpenRowset) Queries</span></span>  
  
-   <span data-ttu-id="a6ca5-121">Sitzungsminingmodelle zulassen (Data Mining)</span><span class="sxs-lookup"><span data-stu-id="a6ca5-121">Allow Session Mining Models (Data Mining)</span></span>  
  
-   <span data-ttu-id="a6ca5-122">Verknüpfte Objekte (An)</span><span class="sxs-lookup"><span data-stu-id="a6ca5-122">Linked Objects (To)</span></span>  
  
-   <span data-ttu-id="a6ca5-123">Verknüpfte Objekte (Von)</span><span class="sxs-lookup"><span data-stu-id="a6ca5-123">Linked Objects (From)</span></span>  
  
-   <span data-ttu-id="a6ca5-124">COM-basierte benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="a6ca5-124">COM based user-defined functions</span></span>  
  
-   <span data-ttu-id="a6ca5-125">Ablaufverfolgungsdefinitionen (Vorlagen).</span><span class="sxs-lookup"><span data-stu-id="a6ca5-125">Flight Recorder Trace Definitions (templates).</span></span>  
  
-   <span data-ttu-id="a6ca5-126">Abfrageprotokollierung</span><span class="sxs-lookup"><span data-stu-id="a6ca5-126">Query logging</span></span>  
  
-   <span data-ttu-id="a6ca5-127">Nur lokale Verbindungen überwachen</span><span class="sxs-lookup"><span data-stu-id="a6ca5-127">Listen Only On Local Connections</span></span>  
  
-   <span data-ttu-id="a6ca5-128">Binäres XML</span><span class="sxs-lookup"><span data-stu-id="a6ca5-128">Binary XML</span></span>  
  
-   <span data-ttu-id="a6ca5-129">Komprimierung</span><span class="sxs-lookup"><span data-stu-id="a6ca5-129">Compression</span></span>  
  
-   <span data-ttu-id="a6ca5-130">Gruppenaffinität.</span><span class="sxs-lookup"><span data-stu-id="a6ca5-130">Group affinity.</span></span> <span data-ttu-id="a6ca5-131">Einzelheiten dazu finden Sie unter [Thread Pool Properties](../server-properties/thread-pool-properties.md) .</span><span class="sxs-lookup"><span data-stu-id="a6ca5-131">See [Thread Pool Properties](../server-properties/thread-pool-properties.md) for details.</span></span>  
  
  
