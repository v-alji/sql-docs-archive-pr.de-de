---
title: Lösung für unklare Transaktion (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- distributed transactions [SQL Server], unresolved transactions
- unresolved transactions
- in-doubt xact resolution option
ms.assetid: 3426fd32-cad2-4f2f-8ca9-e0296cc12703
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6b8db57ef2a4ee85d65e8c25de28ff7ada7994e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697185"
---
# <a name="in-doubt-xact-resolution-server-configuration-option"></a><span data-ttu-id="050ea-102">Lösung für unklare Transaktion (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="050ea-102">in-doubt xact resolution Server Configuration Option</span></span>
  <span data-ttu-id="050ea-103">Mit der Option **in-doubt xact resolution** steuern Sie das Standardergebnis von Transaktionen, die der [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) nicht auflösen kann.</span><span class="sxs-lookup"><span data-stu-id="050ea-103">Use the **in-doubt xact resolution** option to control the default outcome of transactions that the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) is unable to resolve.</span></span> <span data-ttu-id="050ea-104">Die mangelnde Fähigkeit zur Auflösung von Transaktionen kann mit der Ausfalldauer des MS DTC zusammenhängen oder auch mit einem unbekannten Transaktionsergebnis zum Zeitpunkt der Wiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="050ea-104">Inability to resolve transactions may be related to the MS DTC down time or an unknown transaction outcome at the time of recovery.</span></span>  
  
 <span data-ttu-id="050ea-105">Die nachstehende Tabelle enthält die möglichen Ergebniswerte für das Auflösen einer unsicheren Transaktion.</span><span class="sxs-lookup"><span data-stu-id="050ea-105">The following table lists the possible outcome values for resolving an in-doubt transaction.</span></span>  
  
|<span data-ttu-id="050ea-106">Ergebniswert</span><span class="sxs-lookup"><span data-stu-id="050ea-106">Outcome value</span></span>|<span data-ttu-id="050ea-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="050ea-107">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="050ea-108">0</span><span class="sxs-lookup"><span data-stu-id="050ea-108">0</span></span>|<span data-ttu-id="050ea-109">Keine Annahme.</span><span class="sxs-lookup"><span data-stu-id="050ea-109">No presumption.</span></span> <span data-ttu-id="050ea-110">Die Wiederherstellung erzeugt einen Fehler, falls der MS DTC keine unsicheren Transaktionen auflösen kann.</span><span class="sxs-lookup"><span data-stu-id="050ea-110">Recovery fails if MS DTC cannot resolve any in-doubt transactions.</span></span>|  
|<span data-ttu-id="050ea-111">1</span><span class="sxs-lookup"><span data-stu-id="050ea-111">1</span></span>|<span data-ttu-id="050ea-112">Commit annehmen.</span><span class="sxs-lookup"><span data-stu-id="050ea-112">Presume commit.</span></span> <span data-ttu-id="050ea-113">Alle unsicheren MS DTC-Transaktionen werden als übermittelt angesehen.</span><span class="sxs-lookup"><span data-stu-id="050ea-113">Any MS DTC in-doubt transactions are presumed to have committed.</span></span>|  
|<span data-ttu-id="050ea-114">2</span><span class="sxs-lookup"><span data-stu-id="050ea-114">2</span></span>|<span data-ttu-id="050ea-115">Abbruch annehmen.</span><span class="sxs-lookup"><span data-stu-id="050ea-115">Presume abort.</span></span> <span data-ttu-id="050ea-116">Alle unsicheren MS DTC-Transaktionen werden als abgebrochen angesehen.</span><span class="sxs-lookup"><span data-stu-id="050ea-116">Any MS DTC in-doubt transactions are presumed to have aborted.</span></span>|  
  
 <span data-ttu-id="050ea-117">Um die Gefahr längerer Ausfallzeiten zu minimieren, kann ein Administrator diese Option so konfigurieren, dass entweder die Übermittlung oder der Abbruch angenommen wird, wie im nachstehenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="050ea-117">To minimize the possibility of extended down time, an administrator might choose to configure this option either to presume commit or presume abort, as shown in the following example.</span></span>  
  
```  
sp_configure 'show advanced options', 1  
GO  
RECONFIGURE  
GO  
sp_configure 'in-doubt xact resolution', 2 -- presume abort  
GO  
RECONFIGURE  
GO  
sp_configure 'show advanced options', 0  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="050ea-118">Alternativ hat der Administrator die Möglichkeit, die Standardeinstellung beizubehalten (also keine Annahmen) und das Fehlschlagen der Wiederherstellung zuzulassen, damit ein eventueller DTC-Ausfall sofort bemerkt werden kann, wie im nachstehenden Beispiel erläutert.</span><span class="sxs-lookup"><span data-stu-id="050ea-118">Alternatively, the administrator might want to leave the default (no presumption) and allow recovery to fail in order to be made aware of a DTC failure, as shown in the following example.</span></span>  
  
```  
sp_configure 'show advanced options', 1  
GO  
RECONFIGURE  
GO  
sp_configure 'in-doubt xact resolution', 1 -- presume commit  
GO  
reconfigure  
GO  
ALTER DATABASE pubs SET ONLINE -- run recovery again  
GO  
sp_configure 'in-doubt xact resolution', 0 -- back to no assumptions  
GO  
sp_configure 'show advanced options', 0  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="050ea-119">Bei **in-doubt xact resolution** handelt es sich um eine erweiterte Option.</span><span class="sxs-lookup"><span data-stu-id="050ea-119">The **in-doubt xact resolution** option is an advanced option.</span></span> <span data-ttu-id="050ea-120">Wenn Sie die Einstellung mithilfe der gespeicherten Systemprozedur **sp_configure** ändern, können Sie **in-doubt xact resolution** nur ändern, wenn **Erweiterte Optionen anzeigen** auf 1 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="050ea-120">If you are using the **sp_configure** system stored procedure to change the setting, you can change **in-doubt xact resolution** only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="050ea-121">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="050ea-121">The setting takes effect immediately without a server restart.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="050ea-122">Die konsistente Konfiguration dieser Option auf allen [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanzen, die an verteilten Transaktionen beteiligt sind, trägt dazu bei, Inkonsistenzen in den Daten zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="050ea-122">Consistent configuration of this option across all [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances involved in any distributed transactions will help avoid data inconsistencies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="050ea-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="050ea-123">See Also</span></span>  
 <span data-ttu-id="050ea-124">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="050ea-124">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="050ea-125">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="050ea-125">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="050ea-126">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="050ea-126">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  