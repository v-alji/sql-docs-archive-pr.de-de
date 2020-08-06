---
title: Eigenschaften des Sperren-Managers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- lock manager properties [Analysis Services]
- LockWaitGranularityMS property
- DefaultLockTimeoutMS property
- DeadlockDetectionGranularityMS property
ms.assetid: 15fe9ead-825b-4ac3-9191-7a07caa2861b
author: minewiskan
ms.author: owend
ms.openlocfilehash: d10927f1c549f00625b8affb801ec7b0831827c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727170"
---
# <a name="lock-manager-properties"></a><span data-ttu-id="77377-102">Eigenschaften des Sperren-Managers</span><span class="sxs-lookup"><span data-stu-id="77377-102">Lock Manager Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="77377-103">werden die in der folgenden Tabelle aufgeführten Sperren-Manager-Servereigenschaften unterstützt.</span><span class="sxs-lookup"><span data-stu-id="77377-103">supports the lock manager server properties listed in the following table.</span></span> <span data-ttu-id="77377-104">Weitere Informationen zu zusätzlichen Servereigenschaften und zum Festlegen dieser Eigenschaften finden Sie unter [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="77377-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="77377-105">**Gilt für:** mehrdimensionalen und Tabellenservermodus</span><span class="sxs-lookup"><span data-stu-id="77377-105">**Applies to:** Multidimensional and Tabular server mode</span></span>  
  
## <a name="properties"></a><span data-ttu-id="77377-106">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="77377-106">Properties</span></span>  
 `DefaultLockTimeoutMS`  
 <span data-ttu-id="77377-107">Eine ganze 32-Bit-Zahl mit Vorzeichen, die das Standardsperrtimeout in Millisekunden für interne Sperranforderungen definiert.</span><span class="sxs-lookup"><span data-stu-id="77377-107">A signed 32-bit integer property that defines default lock timeout in milliseconds for internal lock requests.</span></span>  
  
 <span data-ttu-id="77377-108">Der Standardwert für diese Eigenschaft ist -1, d. h. es wurde kein Timeout für interne Sperranforderungen definiert.</span><span class="sxs-lookup"><span data-stu-id="77377-108">The default value for this property is -1, which indicates there is no timeout for internal lock requests.</span></span>  
  
 `LockWaitGranularityMS`  
 <span data-ttu-id="77377-109">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="77377-109">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DeadlockDetectionGranularityMS`  
 <span data-ttu-id="77377-110">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="77377-110">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77377-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="77377-111">See Also</span></span>  
 <span data-ttu-id="77377-112">[Konfigurieren von Server Eigenschaften in Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="77377-112">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="77377-113">Bestimmen des Servermodus einer Analysis Services-Instanz</span><span class="sxs-lookup"><span data-stu-id="77377-113">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
