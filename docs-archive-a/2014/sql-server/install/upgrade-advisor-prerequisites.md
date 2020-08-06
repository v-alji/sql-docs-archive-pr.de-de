---
title: Voraussetzungen für den Upgrade Advisor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- requirements [Upgrade Advisor]
- software [Upgrade Advisor]
- system requirements [Upgrade Advisor]
- Setup [Upgrade Advisor]
- SQL Server Upgrade Advisor, prerequisites
- prerequisites [Upgrade Advisor]
- Upgrade Advisor [SQL Server], prerequisites
ms.assetid: d21a39e5-5f81-4096-a7dd-f244e4779992
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 41c97cf585d1768c7aebeec2613ee8744cb220da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617413"
---
# <a name="upgrade-advisor-prerequisites"></a><span data-ttu-id="fec85-102">Voraussetzungen für den Upgrade Advisor</span><span class="sxs-lookup"><span data-stu-id="fec85-102">Upgrade Advisor Prerequisites</span></span>
  <span data-ttu-id="fec85-103">In diesem Thema werden die Softwareanforderungen für den Upgrade Advisor beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fec85-103">This topic describes the software requirements for Upgrade Advisor.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fec85-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="fec85-104">Prerequisites</span></span>  
 <span data-ttu-id="fec85-105">Zum Installieren und Ausführen des Upgrade Advisors müssen folgende Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="fec85-105">The prerequisites for installing and running Upgrade Advisor are as follows:</span></span>  
  
-   [!INCLUDE[wiprlhext](../../includes/wiprlhext-md.md)] <span data-ttu-id="fec85-106">SP1, [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] beginnend mit SP2, Windows 7 oder [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] R2.</span><span class="sxs-lookup"><span data-stu-id="fec85-106">SP1, [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] beginning with SP2, Windows 7, or [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] R2.</span></span>  
  
-   <span data-ttu-id="fec85-107">Windows Installer 4.5.</span><span class="sxs-lookup"><span data-stu-id="fec85-107">Windows Installer 4.5.</span></span> <span data-ttu-id="fec85-108">Sie können Windows Installer von der [Windows Installer Website](https://www.microsoft.com/download/details.aspx?id=8483)installieren.</span><span class="sxs-lookup"><span data-stu-id="fec85-108">You can install Windows Installer from the [Windows Installer Web site](https://www.microsoft.com/download/details.aspx?id=8483).</span></span>  
  
-   <span data-ttu-id="fec85-109">Der [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], beginnend mit .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="fec85-109">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], beginning with .NET Framework 4.</span></span> <span data-ttu-id="fec85-110">Der [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] ist auf dem [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Produkt Medium und auf der Website des [SDK, der weitervertreibbaren Website und der Service Pack Download-](https://go.microsoft.com/fwlink/?LinkId=48882)Website verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fec85-110">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] is available on the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] product media, and from the [SDK, redistributable, and service pack download Web site](https://go.microsoft.com/fwlink/?LinkId=48882).</span></span>  
  
    -   <span data-ttu-id="fec85-111">Um .NET Framework 4 von den [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]-Medien zu installieren, suchen Sie das Stammverzeichnis des Datenträgerlaufwerks.</span><span class="sxs-lookup"><span data-stu-id="fec85-111">To install the .NET Framework 4 from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] media, locate the root of the disk drive.</span></span> <span data-ttu-id="fec85-112">Doppelklicken Sie dann auf den Ordner \redist und auf den Ordner DotNetFrameworks und führen Sie dotNetFx40_Full_x86_x64.exe aus (für 32-Bit- und 64-Bit-Betriebssysteme).</span><span class="sxs-lookup"><span data-stu-id="fec85-112">Then double-click the \redist folder, double-click the DotNetFrameworks folder, and run dotNetFx40_Full_x86_x64.exe (for both 32-bit and 64-bit operating systems).</span></span>  
  
-   <span data-ttu-id="fec85-113">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom ist eine Voraussetzung für die Installation [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] von Upgrade Advisor und wird vom Upgrade Advisor-Setup nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="fec85-113">The [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom is a prerequisite for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor, and is not installed by Upgrade Advisor Setup.</span></span> <span data-ttu-id="fec85-114">Das Setup erfordert, dass Sie das [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom aus dem [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="fec85-114">The Setup requires you to download and install the [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fec85-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fec85-115">See Also</span></span>  
 [<span data-ttu-id="fec85-116">Gewusst wie: Installieren des Upgrade Advisors</span><span class="sxs-lookup"><span data-stu-id="fec85-116">How to: Install Upgrade Advisor</span></span>](../../../2014/sql-server/install/how-to-install-upgrade-advisor.md)  
  
  
