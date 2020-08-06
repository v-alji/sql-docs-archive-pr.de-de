---
title: Überprüfen, ob während des Upgradevorgangs alle Dateigruppen beschreibbar sind | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- filegroups [SQL Server], writeable
- writeable filegroups [SQL Server]
ms.assetid: 2985efc1-4b14-46c3-abbd-a656b159f23c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8146efb876bf97c36c549a2b58d104592df611e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726429"
---
# <a name="verify-all-filegroups-are-writeable-during-the-upgrade-process"></a><span data-ttu-id="2422e-102">Überprüfen, ob während des Upgrades Schreibzugriff auf alle Dateigruppen möglich ist</span><span class="sxs-lookup"><span data-stu-id="2422e-102">Verify all filegroups are writeable during the upgrade process</span></span>
  <span data-ttu-id="2422e-103">Upgrade Advisor hat eine Datenbank erkannt, die über eine oder mehrere schreibgeschützte Dateigruppen verfügt.</span><span class="sxs-lookup"><span data-stu-id="2422e-103">Upgrade Advisor detected a database that has one or more read-only filegroups.</span></span> <span data-ttu-id="2422e-104">Für die Dateigruppen aller Datenbanken in der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] muss READ_WRITE festgelegt werden, bevor ein Upgrade durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2422e-104">All databases in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must have filegroups set to READ_WRITE before upgrading.</span></span>  
  
## <a name="component"></a><span data-ttu-id="2422e-105">Komponente</span><span class="sxs-lookup"><span data-stu-id="2422e-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="2422e-106">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="2422e-106">Corrective Action</span></span>  
 <span data-ttu-id="2422e-107">Sie können eine Dateigruppe mithilfe von ALTER DATABASE auf READ_WRITE festlegen.</span><span class="sxs-lookup"><span data-stu-id="2422e-107">Use ALTER DATABASE to set the filegroup to READ_WRITE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2422e-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2422e-108">See Also</span></span>  
 <span data-ttu-id="2422e-109">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="2422e-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="2422e-110">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="2422e-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
