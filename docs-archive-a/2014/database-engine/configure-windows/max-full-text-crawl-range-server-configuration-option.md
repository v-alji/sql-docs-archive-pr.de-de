---
title: Max. Bereich für Volltextdurchforstung (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- crawls [full-text search]
- max full-text crawl range option
ms.assetid: a49de86b-0891-4dcd-89c0-ead30aab00e0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e1dbd9e44518b6e849a06a76e21fc605172fd2ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696049"
---
# <a name="max-full-text-crawl-range-server-configuration-option"></a><span data-ttu-id="891f9-102">Max. Bereich für Volltextdurchforstung (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="891f9-102">max full-text crawl range Server Configuration Option</span></span>
  <span data-ttu-id="891f9-103">Verwenden Sie die Option **max full-text crawl range** , um die CPU-Auslastung zu optimieren. Hierdurch wird die Durchforstungsleistung während eines vollständigen Durchforstungsvorgangs verbessert.</span><span class="sxs-lookup"><span data-stu-id="891f9-103">Use the **max full-text crawl range** option to optimize CPU utilization, which improves crawl performance during a full crawl.</span></span> <span data-ttu-id="891f9-104">Mithilfe dieser Option können Sie die Anzahl von Partitionen angeben, die [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] während eines vollständigen Indexdurchforstungsvorgangs verwenden sollte.</span><span class="sxs-lookup"><span data-stu-id="891f9-104">Using this option, you can specify the number of partitions that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should use during a full index crawl.</span></span> <span data-ttu-id="891f9-105">Wenn z. B. viele CPUs vorhanden sind und ihre Auslastung nicht optimal ist, können Sie den maximalen Wert dieser Option erhöhen.</span><span class="sxs-lookup"><span data-stu-id="891f9-105">For example, if there are many CPUs and their utilization is not optimal, you can increase the maximum value of this option.</span></span> <span data-ttu-id="891f9-106">Zusätzlich zu dieser Option verwendet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine Reihe anderer Faktoren, wie z. B. die Anzahl von Zeilen in der Tabelle und die Anzahl von CPUs, um die tatsächliche Anzahl von verwendeten Partitionen zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="891f9-106">In addition to this option, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses a number of other factors, such as the number of rows in the table and the number of CPUs, to determine the actual number of partitions used.</span></span>  
  
 <span data-ttu-id="891f9-107">Der Standardwert dieser Option ist 4, der Mindestwert 1 und der maximale Wert 256.</span><span class="sxs-lookup"><span data-stu-id="891f9-107">The default value of this option is 4; the minimum value is 1, and the maximum value is 256.</span></span> <span data-ttu-id="891f9-108">Änderungen an dieser Option beeinflussen nur nachfolgende Crawls.</span><span class="sxs-lookup"><span data-stu-id="891f9-108">Changes made to this option affect only subsequent crawls.</span></span> <span data-ttu-id="891f9-109">Auf in Verarbeitung befindliche Durchforstungsvorgänge hat eine Änderung dieser Optionseinstellung keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="891f9-109">Crawls in process will not be affected by a change in this option setting.</span></span>  
  
 <span data-ttu-id="891f9-110">Bei der Option **max full-text crawl range** handelt es sich um eine erweiterte Option.</span><span class="sxs-lookup"><span data-stu-id="891f9-110">The **max full-text crawl range** option is an advanced option.</span></span> <span data-ttu-id="891f9-111">Wenn Sie die Einstellung mithilfe der gespeicherten Systemprozedur **sp_configure** ändern, können Sie **max full-text crawl range** nur ändern, wenn **Erweiterte Optionen anzeigen** auf 1 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="891f9-111">If you are using the **sp_configure** system stored procedure to change the setting, you can change **max full-text crawl range** only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="891f9-112">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="891f9-112">The setting takes effect immediately without a server restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="891f9-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="891f9-113">See Also</span></span>  
 <span data-ttu-id="891f9-114">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="891f9-114">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="891f9-115">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="891f9-115">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="891f9-116">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="891f9-116">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
