---
title: Fehlerbehebung für die SQL Server-Ressourcenintegrität (SQL Server-Hilfsprogramm) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 614f07b5-f221-4013-9f8d-22964cf42270
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 182225dd618dd1e9e058c549bdc07818813ba764
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609886"
---
# <a name="troubleshoot-sql-server-resource-health-sql-server-utility"></a><span data-ttu-id="68e53-102">Fehlerbehebung für die SQL Server-Ressourcenintegrität (SQL Server-Hilfsprogramm)</span><span class="sxs-lookup"><span data-stu-id="68e53-102">Troubleshoot SQL Server Resource Health (SQL Server Utility)</span></span>
  <span data-ttu-id="68e53-103">Die Fehlerbehebung von Problemen mit der Ressourcenintegrität, die von einem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -UCP identifiziert wurden, schließt möglicherweise die Abhilfe für eine überbeanspruchte CPU auf einem Computer oder einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ein, oder die Abhilfe für eine überbeanspruchte CPU für eine Datenebenenanwendung.</span><span class="sxs-lookup"><span data-stu-id="68e53-103">Troubleshooting resource health issues identified by a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] UCP might include mitigating overutilized CPU on a computer or on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or mitigating overutilized CPU for a data-tier application.</span></span> <span data-ttu-id="68e53-104">Bei anderen Problemen muss möglicherweise eine Abhilfe für überausgelasteten Dateispeicherplatz für Datenbankdateien oder die Überauslastung des zugewiesenen Speicherplatzes auf einem Speichervolume gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="68e53-104">Other issues might include resolving overutilized file space for database files or resolving overutilization of allocated disk space on a storage volume.</span></span>  
  
 <span data-ttu-id="68e53-105">Wenn eine Datenbank den Status „emergency“ (Notfall) aufweist, wird für den Integritätsstatus der überausgelastete Protokolldateispeicherplatz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="68e53-105">Note that if a database is in "emergency" state, the health state will display overutilized log file space.</span></span>  
  
 <span data-ttu-id="68e53-106">Weitere Informationen zu fehlgeschlagenen Datensammlungen, die zu grauen Statussymbolen auf der verwalteten Instanzlistenansicht auf einem UCP führen, finden Sie unter [Problembehandlung beim SQL Server-Hilfsprogramm](../../database-engine/troubleshoot-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="68e53-106">For more information about failed data collection resulting in gray status icons in the managed instance list view on a UCP, see [Troubleshoot the SQL Server Utility](../../database-engine/troubleshoot-the-sql-server-utility.md).</span></span> <span data-ttu-id="68e53-107">Weitere Informationen zu ersten Schritten mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramm finden Sie unter [Funktionen und Tasks im SQL Server-Hilfsprogramm](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="68e53-107">For more information about getting started with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
 <span data-ttu-id="68e53-108">Weitere Informationen zur Abhilfe für bestimmte Ressourcenintegritätsprobleme, die von einem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -UCP identifiziert wurden, finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="68e53-108">For more information about mitigating specific resource health issues identified by a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] UCP, see the following topics:</span></span>  
  
-   [<span data-ttu-id="68e53-109">So identifizieren Sie die SQL Server-Version und -Edition</span><span class="sxs-lookup"><span data-stu-id="68e53-109">How to identify your SQL Server version and edition</span></span>](https://go.microsoft.com/fwlink/?LinkID=178504)  
  
-   [<span data-ttu-id="68e53-110">Behandlung von Leistungsproblemen in SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="68e53-110">Troubleshooting Performance Problems in SQL Server 2008</span></span>](https://go.microsoft.com/fwlink/?LinkId=151354)  
  
  
