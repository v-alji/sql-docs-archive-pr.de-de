---
title: Agent XPs (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Agent XPs option
- extended stored procedures [SQL Server], SQL Server Agent
ms.assetid: 2e1c6c64-5ce7-4357-98c7-ac7763a9f9de
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 541c81ea8d9f782a9c1ea391824b90a6fee772d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619348"
---
# <a name="agent-xps-server-configuration-option"></a><span data-ttu-id="caad3-102">Agent XPs (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="caad3-102">Agent XPs Server Configuration Option</span></span>
  <span data-ttu-id="caad3-103">Mithilfe der Option **Agent XPs** können Sie die erweiterten gespeicherten Prozeduren des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents auf diesem Server aktivieren.</span><span class="sxs-lookup"><span data-stu-id="caad3-103">Use the **Agent XPs** option to enable the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent extended stored procedures on this server.</span></span> <span data-ttu-id="caad3-104">Wenn diese Option nicht aktiviert ist, ist der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Knoten im Objekt-Explorer von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="caad3-104">When this option is not enabled, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node is not available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer.</span></span>  
  
 <span data-ttu-id="caad3-105">Wenn Sie den [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] -Agent-Dienst mithilfe des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Tools starten, werden diese erweiterten gespeicherten Prozeduren automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="caad3-105">When you use the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] tool to start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, these extended stored procedures are enabled automatically.</span></span> <span data-ttu-id="caad3-106">Weitere Informationen finden Sie unter [Oberflächenkonfiguration](../../relational-databases/security/surface-area-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="caad3-106">For more information, see [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] <span data-ttu-id="caad3-107">Wenn diese erweiterten gespeicherten Prozeduren nicht aktiviert sind, wird der Inhalt des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent-Knotens im Objekt-Explorer von Management Studio, unabhängig vom Status des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent-Diensts, nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="caad3-107">Object Explorer does not display the contents of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Agent node unless these extended stored procedures are enabled regardless of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service state.</span></span>  
  
 <span data-ttu-id="caad3-108">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="caad3-108">The possible values are:</span></span>  
  
-   <span data-ttu-id="caad3-109">**0** gibt an, dass die erweiterten gespeicherten Prozeduren des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents nicht verfügbar sind (Standardeinstellung).</span><span class="sxs-lookup"><span data-stu-id="caad3-109">**0**, indicating that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent extended stored procedures are not available (the default).</span></span>  
  
-   <span data-ttu-id="caad3-110">**1** gibt an, dass die erweiterten gespeicherten Prozeduren des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="caad3-110">**1**, indicating that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent extended stored procedures are available.</span></span>  
  
 <span data-ttu-id="caad3-111">Die Einstellung tritt ohne Beenden und Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="caad3-111">The setting takes effect immediately without a server stop and restart.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="caad3-112">Beispiele</span><span class="sxs-lookup"><span data-stu-id="caad3-112">Examples</span></span>  
 <span data-ttu-id="caad3-113">Im folgenden Beispiel werden die erweiterten gespeicherten Prozeduren des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents aktiviert.</span><span class="sxs-lookup"><span data-stu-id="caad3-113">The following example enables the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent extended stored procedures.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'Agent XPs', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="caad3-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="caad3-114">See Also</span></span>  
 <span data-ttu-id="caad3-115">[Automatisierte Administrationstasks &#40;SQL Server Agent&#41;](../../ssms/agent/sql-server-agent.md) </span><span class="sxs-lookup"><span data-stu-id="caad3-115">[Automated Administration Tasks &#40;SQL Server Agent&#41;](../../ssms/agent/sql-server-agent.md) </span></span>  
 [<span data-ttu-id="caad3-116">Starten, Beenden oder Anhalten des SQL Server-Agent-Diensts</span><span class="sxs-lookup"><span data-stu-id="caad3-116">Start, Stop, or Pause the SQL Server Agent Service</span></span>](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md)  
  
  
