---
title: Anzeigen der Ergebnisse zu Ressourcenintegritätsrichtlinien (SQL Server-Hilfsprogramm) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 80cb14fb-f4c6-4be2-ba17-eb4e4cddd35f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c4ab30ad0e87782f8187370a53747be4cf5d313d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701103"
---
# <a name="view-resource-health-policy-results-sql-server-utility"></a><span data-ttu-id="8543a-102">Anzeigen der Ergebnisse zu Ressourcenintegritätsrichtlinien (SQL Server-Hilfsprogramm)</span><span class="sxs-lookup"><span data-stu-id="8543a-102">View Resource Health Policy Results (SQL Server Utility)</span></span>
  <span data-ttu-id="8543a-103">Verwenden Sie das Dashboard des Hilfsprogramms in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , um Ressourcenparameter des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Hilfsprogramms für verwaltete Instanzen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] und Datenschichtanwendungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8543a-103">Use the Utility dashboard in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] to view [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Utility resource parameters for managed instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and data-tier applications.</span></span> <span data-ttu-id="8543a-104">Weitere Informationen finden Sie unter [Funktionen und Tasks im SQL Server-Hilfsprogramm](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="8543a-104">For more information, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="view-sql-server-utility-resource-health-policy-results"></a><span data-ttu-id="8543a-105">Anzeigen der Ergebnisse zu Ressourcenintegritätsrichtlinien des SQL Server-Hilfsprogramms</span><span class="sxs-lookup"><span data-stu-id="8543a-105">View SQL Server Utility resource health policy results.</span></span>  
  
1.  <span data-ttu-id="8543a-106">Klicken Sie in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] (SSMS) auf **Ansicht**und dann auf **Hilfsprogramm-Explorer** , um den Navigationsbereich des Hilfsprogramm-Explorers anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8543a-106">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] (SSMS), click **View**, then click **Utility Explorer** to view the Utility Explorer navigation pane.</span></span> <span data-ttu-id="8543a-107">Um den Inhaltsbereich anzuzeigen, klicken Sie auf **Ansicht**und dann auf **Inhalt des Hilfsprogramm-Explorers**.</span><span class="sxs-lookup"><span data-stu-id="8543a-107">To view the content pane, click **View**, then click **Utility Explorer Content**.</span></span>  
  
2.  <span data-ttu-id="8543a-108">Klicken Sie im Navigationsbereich auf ![](../../database-engine/media/connect-to-utility.gif "Connect_to_Utility")**Mit Hilfsprogramm verbinden**.</span><span class="sxs-lookup"><span data-stu-id="8543a-108">In the navigation pane, click ![](../../database-engine/media/connect-to-utility.gif "Connect_to_Utility")**Connect to Utility**.</span></span> <span data-ttu-id="8543a-109">Wenn Sie keinen Steuerungspunkt für das Hilfsprogramm erstellt bzw. keine Instanzen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] oder Datenschichtanwendungen im [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Hilfsprogramm registriert haben, erhalten Sie weitere Informationen unter [SQL Server-Hilfsprogramm – Features und Aufgaben](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="8543a-109">If you have not created a utility control point (UCP) or if you have not enrolled instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or data-tier applications into the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Utility, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
3.  <span data-ttu-id="8543a-110">Klicken Sie auf den UCP-Knoten, um Zusammenfassungsdaten für verwaltete Instanzen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] und Datenschichtanwendungen anzuzeigen (zum Aktualisieren mit der rechten Maustaste klicken).</span><span class="sxs-lookup"><span data-stu-id="8543a-110">Click the UCP node to view summary data for managed instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and data-tier applications (right-click to refresh).</span></span> <span data-ttu-id="8543a-111">Dashboarddaten werden im Inhaltsbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8543a-111">Dashboard data is displayed in the content pane.</span></span>  
  
4.  <span data-ttu-id="8543a-112">Klicken Sie auf den Knoten **Verwaltete Instanzen** , um Listenansichtsdaten für verwaltete Instanzen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] anzuzeigen (klicken Sie zum Aktualisieren mit der rechten Maustaste).</span><span class="sxs-lookup"><span data-stu-id="8543a-112">Click the **Managed Instances** node to view list view data for managed instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (right-click to refresh).</span></span> <span data-ttu-id="8543a-113">Listenansichtsdaten werden im Inhaltsbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8543a-113">List view data is displayed in the content pane.</span></span>  
  
5.  <span data-ttu-id="8543a-114">Klicken Sie auf den Knoten **Bereitgestellte Datenebenenanwendungen** , um Listenansichtsdaten für Datenebenenanwendungen anzuzeigen (klicken Sie zum Aktualisieren mit der rechten Maustaste).</span><span class="sxs-lookup"><span data-stu-id="8543a-114">Click the **Deployed Data-tier Applications** node to view list view data for data-tier applications (right-click to refresh).</span></span> <span data-ttu-id="8543a-115">Listenansichtsdaten werden im Inhaltsbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8543a-115">List view data is displayed in the content pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8543a-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8543a-116">See Also</span></span>  
 <span data-ttu-id="8543a-117">[Funktionen und Tasks im SQL Server-Hilfsprogramm](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="8543a-117">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 <span data-ttu-id="8543a-118">[Reduzieren Sie das Rauschen der Richtlinien zur CPU-Auslastung &#40;SQL Server-Hilfsprogramm&#41;](reduce-noise-in-cpu-utilization-policies-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="8543a-118">[Reduce Noise in CPU Utilization Policies &#40;SQL Server Utility&#41;](reduce-noise-in-cpu-utilization-policies-sql-server-utility.md) </span></span>  
 <span data-ttu-id="8543a-119">[Details zu bereitgestellten Datenebenenanwendungen &#40;SQL Server-Hilfsprogramm&#41;](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="8543a-119">[Deployed Data-tier Application Details &#40;SQL Server Utility&#41;](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md) </span></span>  
 <span data-ttu-id="8543a-120">[Verwaltete Instanz Details &#40;SQL Server-Hilfsprogramm&#41;](../../database-engine/managed-instance-details-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="8543a-120">[Managed Instance Details &#40;SQL Server Utility&#41;](../../database-engine/managed-instance-details-sql-server-utility.md) </span></span>  
 [<span data-ttu-id="8543a-121">Hilfsprogrammverwaltung &#40;SQL Server-Hilfsprogramm&#41;</span><span class="sxs-lookup"><span data-stu-id="8543a-121">Utility Administration &#40;SQL Server Utility&#41;</span></span>](../../database-engine/utility-administration-sql-server-utility.md)  
  
  
