---
title: Überlegungen zum Ausführen von Hilfsprogramm-und nicht-Hilfsprogramm-Sammlungs Sätzen auf derselben Instanz von SQL Server | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: ca7ee9b3-ef9a-4ba4-83d0-9ee9f80dab27
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67df2d65cc9da4026377e77c152c0d78f3749932
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619111"
---
# <a name="considerations-for-running-utility-and-non-utility-collection-sets-on-the-same-instance-of-sql-server"></a><span data-ttu-id="6af7f-102">Überlegungen zum Ausführen von Hilfsprogramm- und Nicht-Hilfsprogramm-Sammlungssätzen auf derselben Instanz von SQL Server</span><span class="sxs-lookup"><span data-stu-id="6af7f-102">Considerations for Running Utility and non-Utility Collection Sets on the Same Instance of SQL Server</span></span>
  <span data-ttu-id="6af7f-103">Der Sammlungssatz des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramms kann parallel mit Sammlungssätzen verwendet werden, die nicht zum [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramm gehören.</span><span class="sxs-lookup"><span data-stu-id="6af7f-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection set is supported side-by-side with non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets.</span></span> <span data-ttu-id="6af7f-104">Eine verwaltete Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] kann also von anderen Sammlungssätzen überwacht werden, während sie einem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramm zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="6af7f-104">That is, a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be monitored by other collection sets while it is a member of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="6af7f-105">Sie müssen den Nicht-Hilfprogramm-Sammlungssatz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] jedoch deaktivieren, während die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramm registriert wird.</span><span class="sxs-lookup"><span data-stu-id="6af7f-105">However, you must disable non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility data collection functionality while the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is being enrolled into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
 <span data-ttu-id="6af7f-106">Nachdem die Instanz beim UCP registriert wurde, können Sie Nicht-Hilfsprogramm-Sammlungssätze von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] erneut starten.</span><span class="sxs-lookup"><span data-stu-id="6af7f-106">After the instance is enrolled with the UCP, you can restart non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets.</span></span> <span data-ttu-id="6af7f-107">Beachten Sie jedoch, dass alle Sammlungssätze für die verwaltete Instanz ihre Daten in das UMDW (Utility Management Data Warehouse) hochladen. Der UMDW-Dateiname lautet sysutility_mdw.</span><span class="sxs-lookup"><span data-stu-id="6af7f-107">Note, however, that all collection sets on the managed instance will upload their data to the utility management data warehouse (UMDW); the UMDW file name is sysutility_mdw.</span></span>  
  
 <span data-ttu-id="6af7f-108">Um Hilfsprogramm-Sammlungssätze von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] parallel mit Nicht-Hilfsprogramm-Sammlungssätzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auszuführen, sollten Sie Folgendes berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="6af7f-108">To run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets side-by-side with non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets, consider the following points:</span></span>  
  
-   <span data-ttu-id="6af7f-109">Parallele Sammlungssätze werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6af7f-109">Side-by-side collection sets are supported.</span></span>  
  
-   <span data-ttu-id="6af7f-110">Sie müssen vorhandene Datensammler deaktivieren, während Sie Instanzen im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramm registrieren.</span><span class="sxs-lookup"><span data-stu-id="6af7f-110">You must disable existing data collectors while enrolling instances into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
-   <span data-ttu-id="6af7f-111">Um die Überprüfungsanforderungen zu erfüllen, müssen Sie die folgenden gespeicherten Prozeduren für die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausführen, bevor Sie einen UCP erstellen, und für eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , bevor Sie die Instanz im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramm registrieren:</span><span class="sxs-lookup"><span data-stu-id="6af7f-111">To pass validation requirements, you must run the following stored procedures on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before you create a UCP, and on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before you enroll it into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility:</span></span>  
  
    ```  
    exec msdb.dbo.sp_syscollector_set_warehouse_database_name NULL  
    exec msdb.dbo.sp_syscollector_set_warehouse_instance_name NULL  
    ```  
  
     <span data-ttu-id="6af7f-112">Wenn Sie diese gespeicherten Prozeduren nicht ausführen, bevor Sie den Assistenten zum Erstellen von UCPs oder den Assistenten zum Hinzufügen verwalteter Instanzen starten, schlägt der Vorgang fehl.</span><span class="sxs-lookup"><span data-stu-id="6af7f-112">If you do not run these stored procedures before you launch the Create UCP Wizard or Add Managed Instance Wizard, the operation will fail.</span></span>  
  
-   <span data-ttu-id="6af7f-113">Sie müssen das UMDW des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramms (sysutility_mdw) für alle Sammlungssätze auf einer verwalteten Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verwenden.</span><span class="sxs-lookup"><span data-stu-id="6af7f-113">You must use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility UMDW (sysutility_mdw) for all collection sets on a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6af7f-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6af7f-114">See Also</span></span>  
 <span data-ttu-id="6af7f-115">[Funktionen und Tasks im SQL Server-Hilfsprogramm](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="6af7f-115">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 [<span data-ttu-id="6af7f-116">Konfigurieren des Data Warehouse für den Steuerungspunkt für das Hilfsprogramm &#40;SQL Server-Hilfsprogramm&#41;</span><span class="sxs-lookup"><span data-stu-id="6af7f-116">Configure Your Utility Control Point Data Warehouse &#40;SQL Server Utility&#41;</span></span>](configure-your-utility-control-point-data-warehouse-sql-server-utility.md)  
  
  
