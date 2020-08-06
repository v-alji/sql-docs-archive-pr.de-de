---
title: Geöffnete Objekte (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- open objects option
ms.assetid: c8424d3c-86ba-4cc5-bf0c-be4ce44bdd04
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6d22a3d6dd358afe9cf921376664c2d25705a6a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696034"
---
# <a name="open-objects-server-configuration-option"></a><span data-ttu-id="a47e3-102">Geöffnete Objekte (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="a47e3-102">open objects Server Configuration Option</span></span>
  <span data-ttu-id="a47e3-103">Diese Option ist in **sp_configure** weiterhin vorhanden, obwohl die zugehörige Funktionalität in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="a47e3-103">This option is still present in **sp_configure**, although its functionality has been disabled in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a47e3-104">(Die Einstellung hat keine Auswirkungen.) In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird die Anzahl von geöffneten Datenbankobjekten dynamisch verwaltet und nur durch den verfügbaren Arbeitsspeicher beschränkt.</span><span class="sxs-lookup"><span data-stu-id="a47e3-104">(The setting has no effect.) In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the number of open database objects is managed dynamically and is limited only by the available memory.</span></span> <span data-ttu-id="a47e3-105">Die Option **Geöffnete Objekte** wurde in **sp_configure** belassen, um die Abwärtskompatibilität mit vorhandenen Skripts sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="a47e3-105">The **open objects** option available in **sp_configure** for backward compatibility with existing scripts.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a47e3-106">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a47e3-106">See Also</span></span>  
 [<span data-ttu-id="a47e3-107">Serverkonfigurationsoptionen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a47e3-107">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
