---
title: Serverkonfigurationsoptionen für den Zugriffsüberprüfungscache | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- access check cache option
- access check cache bucket count
- access check cache quota
ms.assetid: 0a992ea8-3ec6-4a4d-97b5-460ae7326247
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: feed895eeb7b11b4c41c51c4c26859a1057d2733
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607988"
---
# <a name="access-check-cache-server-configuration-options"></a><span data-ttu-id="0bda0-102">Serverkonfigurationsoptionen für den Zugriffsüberprüfungscache</span><span class="sxs-lookup"><span data-stu-id="0bda0-102">access check cache Server Configuration Options</span></span>
<span data-ttu-id="0bda0-103">Beim Zugriff auf Datenbankobjekte durch [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]wird die Zugriffsprüfung in einer internen Struktur zwischengespeichert, die als **access check result cache**bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="0bda0-103">When database objects are accessed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the access check is cached in an internal structure called the **access check result cache**.</span></span> 
  
<span data-ttu-id="0bda0-104">Die Option **access check cache bucket count** steuert die Anzahl der Hashbuckets, die für den Ergebniscache der Zugriffsüberprüfung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0bda0-104">The **access check cache bucket count** option controls the number of hash buckets that are used for the access check result cache.</span></span> 

<span data-ttu-id="0bda0-105">Die Option **access check cache quota** steuert die Anzahl der Einträge, die im Ergebniscache der Zugriffsüberprüfung gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="0bda0-105">The **access check cache quota** option controls the number of entries that are stored in the access check result cache.</span></span> <span data-ttu-id="0bda0-106">Wenn die maximale Anzahl von Einträgen erreicht ist, werden die ältesten Einträge aus dem Ergebniscache der Zugriffsüberprüfung entfernt.</span><span class="sxs-lookup"><span data-stu-id="0bda0-106">When the maximum number of entries is reached, the oldest entries are removed from the access check result cache.</span></span>
  
<span data-ttu-id="0bda0-107">Die Standardwerte 0 geben an, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] diese Optionen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="0bda0-107">The default values of 0 indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is managing these options.</span></span> <span data-ttu-id="0bda0-108">Von [!INCLUDE[ssKatmai](../../includes/ssKatmai-md.md)] bis [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] werden die Standardwerte in die folgenden internen Konfigurationen übersetzt:</span><span class="sxs-lookup"><span data-stu-id="0bda0-108">From [!INCLUDE[ssKatmai](../../includes/ssKatmai-md.md)] through [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], the default values translate to the following internal configurations:</span></span>
-   <span data-ttu-id="0bda0-109">Bei der Bucketanzahl für den Zugriffs Check Cache legt der Wert 0 einen Standardwert von 256-Bucket für die x86-Architektur und 2.048-Bucket für x64-und IA-64-Architekturen fest.</span><span class="sxs-lookup"><span data-stu-id="0bda0-109">For access check cache bucket count, the value 0 sets a default value of 256 buckets for x86 architecture, and 2,048 buckets for x64 and IA-64 architectures.</span></span>
-   <span data-ttu-id="0bda0-110">Bei der Zugriffs Überprüfung des Cache Kontingents legt der Wert 0 einen Standardwert von 1.024 Einträge für die x86-Architektur und 28.192.048-Bucket für x64-und IA-64-Architekturen fest.</span><span class="sxs-lookup"><span data-stu-id="0bda0-110">For access check cache quota, the value 0 sets a default value of 1,024 entries for x86 architecture, and 28,192,048 buckets for x64 and IA-64 architectures.</span></span>

<span data-ttu-id="0bda0-111">In seltenen Fällen kann die Leistung durch das Ändern dieser Optionen verbessert werden.</span><span class="sxs-lookup"><span data-stu-id="0bda0-111">In rare circumstances, performance can be improved by changing these options.</span></span> <span data-ttu-id="0bda0-112">Beispielsweise können Sie den Ergebniscache für die Zugriffsüberprüfung verkleinern, wenn zu viel Arbeitsspeicher verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0bda0-112">For example, you may want to reduce the size of the access check result cache if too much memory is used.</span></span> <span data-ttu-id="0bda0-113">Sie können den Ergebniscache für die Zugriffsüberprüfung auch vergrößern, wenn Sie bei der Neuberechnung von Berechtigungen eine hohe CPU-Auslastung feststellen.</span><span class="sxs-lookup"><span data-stu-id="0bda0-113">Or, you may want to increase the size of the access check result cache if you experience high CPU usage when permissions are recalculated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0bda0-114">Microsoft empfiehlt, diese Optionen nur auf Anweisung des Microsoft-Kundendiensts zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0bda0-114">Microsoft recommends only changing these options when directed by Microsoft Customer Support Services.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0bda0-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0bda0-115">See Also</span></span>  
 <span data-ttu-id="0bda0-116">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0bda0-116">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="0bda0-117">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0bda0-117">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
