---
title: Verbinden mit einem SQL Server-Hilfsprogramm | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: b9b90b8d-241f-4b74-ac14-de7b10ea1821
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e8e59a28e083fc302faebbcba932c18a04e73a7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609888"
---
# <a name="connect-to-a-sql-server-utility"></a><span data-ttu-id="6a958-102">Verbinden mit einem SQL Server-Hilfsprogramm</span><span class="sxs-lookup"><span data-stu-id="6a958-102">Connect to a SQL Server Utility</span></span>
  <span data-ttu-id="6a958-103">Bevor Sie eine Verbindung mit einem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramm herstellen können, müssen Sie einen Steuerungspunkt für das Hilfsprogramm erstellen.</span><span class="sxs-lookup"><span data-stu-id="6a958-103">Before you can connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, you must create a utility control point (UCP).</span></span> <span data-ttu-id="6a958-104">Weitere Informationen finden Sie unter [Funktionen und Tasks im SQL Server-Hilfsprogramm](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="6a958-104">For more information, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>

 <span data-ttu-id="6a958-105">Um die Ressourcenintegrität von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anzuzeigen und zu verwalten, stellen Sie mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] (SSMS) eine Verbindung mit einem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramm her.</span><span class="sxs-lookup"><span data-stu-id="6a958-105">To view and manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resource health, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] (SSMS) to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>

 <span data-ttu-id="6a958-106">So stellen Sie über SSMS eine Verbindung mit einem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramm her:</span><span class="sxs-lookup"><span data-stu-id="6a958-106">To connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility through SSMS:</span></span>

1.  <span data-ttu-id="6a958-107">Starten Sie SSMS.</span><span class="sxs-lookup"><span data-stu-id="6a958-107">Launch SSMS.</span></span>

2.  <span data-ttu-id="6a958-108">Stellen Sie in SSMS eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="6a958-108">In SSMS, connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>

3.  <span data-ttu-id="6a958-109">Klicken Sie auf **Ansicht** und dann auf **Hilfsprogramm-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="6a958-109">Click **View** and then **Utility Explorer**.</span></span>

4.  <span data-ttu-id="6a958-110">Klicken Sie im Navigationsbereich des Hilfsprogramm-Explorers auf ![](../../database-engine/media/connect-to-utility.gif "Connect_to_Utility")**Mit Hilfsprogramm verbinden**.</span><span class="sxs-lookup"><span data-stu-id="6a958-110">In the Utility Explorer navigation pane, click ![](../../database-engine/media/connect-to-utility.gif "Connect_to_Utility")**Connect to Utility**.</span></span>

5.  <span data-ttu-id="6a958-111">Geben Sie im Dialogfeld **Verbindung mit Server herstellen** den Namen der UCP-Instanz an, und klicken Sie dann auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="6a958-111">In the **Connect to Server** dialog box, specify the UCP instance name, then click **Connect**.</span></span>

6.  <span data-ttu-id="6a958-112">Zeigen Sie den Navigationsbereich des Hilfsprogramm-Explorers an, um eine Strukturansicht der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Ressourcen im UCP einzublenden.</span><span class="sxs-lookup"><span data-stu-id="6a958-112">View the Utility Explorer Navigation Pane to see a tree view of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources in the UCP.</span></span>

 <span data-ttu-id="6a958-113">Beim Erstellen eines neuen UCPs werden Sie ebenfalls mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramm verbunden.</span><span class="sxs-lookup"><span data-stu-id="6a958-113">Creating a new UCP also connects you to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="6a958-114">Weitere Informationen finden Sie unter [Erstellen eines Steuerungspunkts für das SQL Server-Hilfsprogramm &#40;SQL Server-Hilfsprogramm&#41;](create-a-sql-server-utility-control-point-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="6a958-114">For more information, see [Create a SQL Server Utility Control Point &#40;SQL Server Utility&#41;](create-a-sql-server-utility-control-point-sql-server-utility.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6a958-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6a958-115">See Also</span></span>
 <span data-ttu-id="6a958-116">[SQL Server-Hilfsprogramm Features und Aufgaben](sql-server-utility-features-and-tasks.md) [anzeigen Resource Health Richtlinien Ergebnisse &#40;SQL Server-Hilfsprogramm&#41;](view-resource-health-policy-results-sql-server-utility.md)</span><span class="sxs-lookup"><span data-stu-id="6a958-116">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) [View Resource Health Policy Results &#40;SQL Server Utility&#41;](view-resource-health-policy-results-sql-server-utility.md)</span></span>


