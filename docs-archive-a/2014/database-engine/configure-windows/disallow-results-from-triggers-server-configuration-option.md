---
title: Ergebnisse von Triggern nicht zulassen (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- triggers [SQL Server], result sets
- result sets [SQL Server], triggers
- disallow results from triggers option
ms.assetid: 47149073-307d-47a5-b7d2-66a737d3231d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f162a6e06706561d861bfc54a1ae4027f2c3466e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694706"
---
# <a name="disallow-results-from-triggers-server-configuration-option"></a><span data-ttu-id="7b987-102">Ergebnisse von Triggern nicht zulassen (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="7b987-102">disallow results from triggers Server Configuration Option</span></span>
  <span data-ttu-id="7b987-103">Verwenden Sie die Option **Ergebnisse von Triggern nicht zulassen** , um zu steuern, ob Trigger Resultsets zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="7b987-103">Use the **disallow results from triggers** option to control whether triggers return result sets.</span></span> <span data-ttu-id="7b987-104">Durch Trigger, die Resultsets zurückgeben, kann es in Anwendungen, die hierfür nicht konzipiert wurden, zu unerwartetem Verhalten kommen.</span><span class="sxs-lookup"><span data-stu-id="7b987-104">Triggers that return result sets may cause unexpected behavior in applications that are not designed to work with them.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextDontUse](../../includes/ssnotedepnextdontuse-md.md)] <span data-ttu-id="7b987-105">Diesen Wert sollten Sie auf 1 festlegen.</span><span class="sxs-lookup"><span data-stu-id="7b987-105">We recommend that you set this value to 1.</span></span>  
  
 <span data-ttu-id="7b987-106">1 bedeutet, dass die Option **Ergebnisse von Triggern nicht zulassen** auf ON festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7b987-106">When set to 1, the **disallow results from triggers** option is set to ON.</span></span> <span data-ttu-id="7b987-107">Die Standardeinstellung für diese Option ist 0 (OFF).</span><span class="sxs-lookup"><span data-stu-id="7b987-107">The default setting for this option is 0 (OFF).</span></span> <span data-ttu-id="7b987-108">Wenn diese Option auf 1 (ON) festgelegt ist, können Trigger keine Resultsets zurückgeben, und es wird folgende Fehlermeldung ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="7b987-108">If this option is set to 1 (ON), any attempt by a trigger to return a result set fails, and the user receives the following error message:</span></span>  
  
 <span data-ttu-id="7b987-109">"Meldung 524, Ebene 16, Status 1, Prozedur \<Procedure Name>, Zeile \<Line#></span><span class="sxs-lookup"><span data-stu-id="7b987-109">"Msg 524, Level 16, State 1, Procedure \<Procedure Name>, Line \<Line#></span></span>  
  
 <span data-ttu-id="7b987-110">"Ein Trigger hat ein Resultset zurückgegeben, und die disallow_results_from_triggers-Serveroption ist TRUE".</span><span class="sxs-lookup"><span data-stu-id="7b987-110">"A trigger returned a resultset and the server option 'disallow_results_from_triggers' is true."</span></span>  
  
 <span data-ttu-id="7b987-111">Die Option **Ergebnisse von Triggern nicht zulassen** wird auf der Instanzebene von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] angewendet und bestimmt das Verhalten sämtlicher vorhandener Trigger in der Instanz.</span><span class="sxs-lookup"><span data-stu-id="7b987-111">The **disallow results from triggers** option is applied at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance level, and it will determine behavior for all existing triggers within the instance.</span></span>  
  
 <span data-ttu-id="7b987-112">Bei der Option **Ergebnisse von Triggern nicht zulassen** handelt es sich um eine erweiterte Option.</span><span class="sxs-lookup"><span data-stu-id="7b987-112">The **disallow results from triggers** option is an advanced option.</span></span> <span data-ttu-id="7b987-113">Wenn Sie die Einstellung mithilfe der gespeicherten Systemprozedur **sp_configure** ändern, können Sie **Ergebnisse von Triggern nicht zulassen** nur ändern, wenn Erweiterte Optionen anzeigen auf 1 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7b987-113">If you are using the **sp_configure** system stored procedure to change the setting, you can change disallow results from triggers only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="7b987-114">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="7b987-114">The setting takes effect immediately without a server restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b987-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7b987-115">See Also</span></span>  
 <span data-ttu-id="7b987-116">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7b987-116">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="7b987-117">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7b987-117">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="7b987-118">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7b987-118">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
