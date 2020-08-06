---
title: Überprüfen der Parameter für die Systemkonfigurationsprüfung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- installing SQL Server, system configuration checks
- failed system configuration checks [SQL Server]
- verifying configuration before installation
- SCC [SQL Server]
- system configuration checker
- scanning computer before installation [SQL Server]
- checking configuration before installation
- status information [SQL Server], system configuration checker
- parameters [SQL Server], system configuration checker
- configuration checkers [SQL Server]
- Setup [SQL Server], system configuration checker
ms.assetid: 8e712c15-6bfa-4d71-b303-9526101e5594
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0bf159d3c6184974d108075cd65e32b449d441bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718682"
---
# <a name="check-parameters-for-the-system-configuration-checker"></a><span data-ttu-id="15033-102">Überprüfen der Parameter für die Systemkonfigurationsprüfung</span><span class="sxs-lookup"><span data-stu-id="15033-102">Check Parameters for the System Configuration Checker</span></span>
  <span data-ttu-id="15033-103">Während des Setups von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] durchsucht die Systemkonfigurationsprüfung (System Configuration Checker, SCC) den Computer, auf dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="15033-103">During [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, the System Configuration Checker (SCC) scans the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be installed.</span></span> <span data-ttu-id="15033-104">Die SCC sucht nach Bedingungen, die eine erfolgreiche Installation von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verhindern.</span><span class="sxs-lookup"><span data-stu-id="15033-104">The SCC checks for conditions that prevent a successful [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="15033-105">Bevor Setup den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Installations-Assistenten startet, ruft SCC den Status jedes Elements ab.</span><span class="sxs-lookup"><span data-stu-id="15033-105">Before Setup starts the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard, the SCC retrieves the status of each item.</span></span> <span data-ttu-id="15033-106">SCC vergleicht dann das Ergebnis mit den erforderlichen Bedingungen und gibt Anweisungen zum Entfernen der Blockierungsprobleme.</span><span class="sxs-lookup"><span data-stu-id="15033-106">It then compares the result with required conditions and provides guidance for removal of blocking issues.</span></span>  
  
 <span data-ttu-id="15033-107">Die Systemkonfigurationsprüfung generiert einen Bericht, der eine kurze Beschreibung für jede ausgeführte Regel sowie den Ausführungsstatus enthält.</span><span class="sxs-lookup"><span data-stu-id="15033-107">The system configuration checker generates a report which contains a short description for each executed rule, and the execution status.</span></span> <span data-ttu-id="15033-108">Der Bericht der Systemkonfigurations Prüfung befindet sich unter% Program Files% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="15033-108">The system configuration check report is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15033-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="15033-109">See Also</span></span>  
 <span data-ttu-id="15033-110">[Hardware-und Software Anforderungen für die Installation von SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="15033-110">[Hardware and Software Requirements for Installing SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md) </span></span>  
 <span data-ttu-id="15033-111">[Sicherheitsüberlegungen für eine SQL Server Installation](../../sql-server/install/security-considerations-for-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="15033-111">[Security Considerations for a SQL Server Installation](../../sql-server/install/security-considerations-for-a-sql-server-installation.md) </span></span>  
 [<span data-ttu-id="15033-112">Unterstützte Versions- und Editionsupgrades</span><span class="sxs-lookup"><span data-stu-id="15033-112">Supported Version and Edition Upgrades</span></span>](supported-version-and-edition-upgrades.md)  
  
  
