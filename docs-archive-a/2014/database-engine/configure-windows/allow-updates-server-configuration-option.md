---
title: Updates zulassen (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- allow updates option
ms.assetid: 3967c3ed-280a-4de8-a2ce-393e82745a7b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d7e3ede317509a2044be90635db46e30a932af66
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619346"
---
# <a name="allow-updates-server-configuration-option"></a><span data-ttu-id="7916b-102">Updates zulassen (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="7916b-102">allow updates Server Configuration Option</span></span>
  <span data-ttu-id="7916b-103">Diese Option ist in der gespeicherten Prozedur **sp_configure** weiterhin vorhanden, obwohl ihre Funktionalität nicht in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="7916b-103">This option is still present in the **sp_configure** stored procedure, although its functionality is unavailable in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7916b-104">(Die Einstellung hat keine Auswirkungen.)</span><span class="sxs-lookup"><span data-stu-id="7916b-104">The setting has no effect.</span></span> <span data-ttu-id="7916b-105">Für Systemtabellen werden keine direkten Updates unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7916b-105">Direct updates to the system tables are not supported.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="7916b-106">Wird die Option **Updates zulassen** geändert, führt dies zu einem Fehler bei der RECONFIGURE-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="7916b-106">Changing the **allow updates** option will cause the RECONFIGURE statement to fail.</span></span> <span data-ttu-id="7916b-107">Änderungen an der Option **Updates zulassen** sollten aus allen Skripts entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="7916b-107">Changes to the **allow updates** option should be removed from all scripts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7916b-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7916b-108">See Also</span></span>  
 [<span data-ttu-id="7916b-109">Serverkonfigurationsoptionen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7916b-109">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
