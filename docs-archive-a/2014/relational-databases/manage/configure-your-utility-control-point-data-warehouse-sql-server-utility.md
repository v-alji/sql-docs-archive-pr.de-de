---
title: Konfigurieren des Data Warehouses für den Steuerungspunkt für das Hilfsprogramm (SQL Server-Hilfsprogramm) | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c2c6f050-8cdb-4b8e-ad38-4aae0a949847
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 60b9623b468f2763cf619c325412373e3603f3a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609892"
---
# <a name="configure-your-utility-control-point-data-warehouse-sql-server-utility"></a><span data-ttu-id="99bfa-102">Konfigurieren des Data Warehouses für den Steuerungspunkt für das Hilfsprogramm (SQL Server-Hilfsprogramm)</span><span class="sxs-lookup"><span data-stu-id="99bfa-102">Configure Your Utility Control Point Data Warehouse (SQL Server Utility)</span></span>
  <span data-ttu-id="99bfa-103">Die von verwalteten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanzen gesammelten Daten werden im UMDW (Utility Management Data Warehouse) gespeichert. Der UMDW-Dateiname lautet sysutility_mdw.</span><span class="sxs-lookup"><span data-stu-id="99bfa-103">Data collected by managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are stored in the utility management data warehouse (UMDW); the UMDW file name is sysutility_mdw.</span></span>  
  
 <span data-ttu-id="99bfa-104">Sie können die Beibehaltungsdauer der UMDW-Daten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="99bfa-104">You can configure the UMDW data retention period.</span></span> <span data-ttu-id="99bfa-105">Weitere Informationen finden Sie unter [Hilfsprogrammverwaltung &#40;SQL Server-Hilfsprogramm&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="99bfa-105">For more information, see [Utility Administration &#40;SQL Server Utility&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span></span>  
  
 <span data-ttu-id="99bfa-106">Die folgenden Konfigurationseinstellungen sind in dieser Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]nicht konfigurierbar:</span><span class="sxs-lookup"><span data-stu-id="99bfa-106">The following configuration settings are not configurable in this release of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="99bfa-107">UMDW name (UMDW-Name): Sysutility_mdw.</span><span class="sxs-lookup"><span data-stu-id="99bfa-107">UMDW name: Sysutility_mdw.</span></span>  
  
-   <span data-ttu-id="99bfa-108">Collection set upload frequency (Uploadhäufigkeit des Sammlungssatzes): Every 15 minutes (Alle 15 Minuten).</span><span class="sxs-lookup"><span data-stu-id="99bfa-108">Collection set upload frequency: Every 15 minutes.</span></span>  
  
 <span data-ttu-id="99bfa-109">Das UMDW-Verzeichnis ist konfigurierbar: \<System drive>:\Programme\Microsoft SQL Server\MSSQL10_50.<UCP_Name>\MSSQL\Data\\, wobei \<System drive> normalerweise dem Laufwerk „C:\“ entspricht.</span><span class="sxs-lookup"><span data-stu-id="99bfa-109">The UMDW directory is configurable: \<System drive>:\Program Files\Microsoft SQL Server\MSSQL10_50.<UCP_Name>\MSSQL\Data\\, where \<System drive> is normally the C:\ drive.</span></span> <span data-ttu-id="99bfa-110">Die Protokolldatei „Sysutility_mdw_\<GUID>_LOG“ befindet sich im selben Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="99bfa-110">The log file, Sysutility_mdw_\<GUID>_LOG, is located in the same directory.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="99bfa-111">Der Speicherort der UMDW-Datei (sysutility_mdw) kann mithilfe von Detach/Attach oder ALTER DATABASE geändert werden.</span><span class="sxs-lookup"><span data-stu-id="99bfa-111">The UMDW (sysutility_mdw) file location can be changed using detach/attach or ALTER DATABASE.</span></span> <span data-ttu-id="99bfa-112">Es wird empfohlen, ALTER DATABASE zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="99bfa-112">We recommend the use of ALTER DATABASE.</span></span> <span data-ttu-id="99bfa-113">Weitere Informationen finden Sie unter [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="99bfa-113">For more information see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99bfa-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="99bfa-114">See Also</span></span>  
 [<span data-ttu-id="99bfa-115">Funktionen und Tasks im SQL Server-Hilfsprogramm</span><span class="sxs-lookup"><span data-stu-id="99bfa-115">SQL Server Utility Features and Tasks</span></span>](sql-server-utility-features-and-tasks.md)  
  
  
