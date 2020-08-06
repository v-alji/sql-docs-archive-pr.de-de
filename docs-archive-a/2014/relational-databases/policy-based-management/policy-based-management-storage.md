---
title: Speicher der richtlinienbasierten Verwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, storage
ms.assetid: d0cbf214-fc2e-4917-8d31-1d71c9ffa61d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0e775d038c5bb4f7a467f2691e374296f1389d84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699458"
---
# <a name="policy-based-management-storage"></a><span data-ttu-id="d300f-102">Speicher der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="d300f-102">Policy-Based Management Storage</span></span>
  <span data-ttu-id="d300f-103">Richtlinien werden in der msdb-Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d300f-103">Policies are stored in the msdb database.</span></span> <span data-ttu-id="d300f-104">Nachdem eine Richtlinie oder Bedingung geändert wurde, sollte die msdb-Datenbank gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="d300f-104">After a policy or condition is changed, msdb should be backed up.</span></span> <span data-ttu-id="d300f-105">Weitere Informationen finden Sie unter [Sichern und Wiederherstellen von Systemdatenbanken &#40;SQL Server&#41;](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d300f-105">For more information, see [Back Up and Restore of System Databases &#40;SQL Server&#41;](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md).</span></span>  
  
## <a name="storing-policies"></a><span data-ttu-id="d300f-106">Speichern von Richtlinien</span><span class="sxs-lookup"><span data-stu-id="d300f-106">Storing Policies</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="d300f-107">enthält Richtlinien, die verwendet werden können, um eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="d300f-107">includes policies that can be used to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d300f-108">Diese Richtlinien sind standardmäßig nicht auf dem installiert [!INCLUDE[ssDE](../../includes/ssde-md.md)] . Sie können jedoch vom Standard Speicherort c:\Programme (x86) \Microsoft SQL server\120\tools\policies\databaseengine\1033. importiert werden.</span><span class="sxs-lookup"><span data-stu-id="d300f-108">By default, these policies are not installed on the [!INCLUDE[ssDE](../../includes/ssde-md.md)]; however, they can be imported from the default installation location of C:\Program Files (x86)\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033.</span></span>  
  
 <span data-ttu-id="d300f-109">Sie können Richtlinien über das Menü **Datei/Neu** direkt erstellen und diese dann in einer Datei speichern.</span><span class="sxs-lookup"><span data-stu-id="d300f-109">You can directly create policies by using the **File/New** menu, and then saving them to a file.</span></span> <span data-ttu-id="d300f-110">Auf diese Weise können Sie Richtlinien erstellen, wenn Sie nicht mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)]verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="d300f-110">This enables you to create policies when you are not connected to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="d300f-111">Der Richtlinienverlauf für Richtlinien, die in der aktuellen Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] ausgewertet werden, wird in msdb-Systemtabellen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="d300f-111">Policy history for policies evaluated in the current instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is maintained in msdb system tables.</span></span> <span data-ttu-id="d300f-112">Der Richtlinienverlauf für Richtlinien, die auf andere Instanzen von [!INCLUDE[ssDE](../../includes/ssde-md.md)] oder auf [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] oder [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] angewendet werden, bleibt nicht erhalten.</span><span class="sxs-lookup"><span data-stu-id="d300f-112">Policy history for policies applied to other instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] or applied to [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is not retained.</span></span>  
  
  
