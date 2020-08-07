---
title: Starten des Datenbankspiegelungs-Monitors (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- monitoring database mirroring [SQL Server]
- Database Mirroring Monitor [SQL Server], starting
- database mirroring [SQL Server], monitoring
ms.assetid: 53165335-97ca-4f88-8e78-22f1839dee98
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67c7b393b28d4d400535281c18c637146a5d8da7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607982"
---
# <a name="start-database-mirroring-monitor-sql-server-management-studio"></a><span data-ttu-id="5b401-102">Starten des Datenbankspiegelungs-Monitors (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="5b401-102">Start Database Mirroring Monitor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="5b401-103">Der Datenbankspiegelungs-Monitor ist Teil des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Monitors, der aus [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="5b401-103">The Database Mirroring Monitor is part of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Monitor, which is launched from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5b401-104">Der Datenbankspiegelungs-Monitor ist nicht in jeder Edition von [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b401-104">Database Mirroring Monitor is not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5b401-105">Eine Liste der Funktionen, die von den Editionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]unterstützt werden, finden Sie unter [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="5b401-105">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
### <a name="to-launch-the-database-mirroring-monitor"></a><span data-ttu-id="5b401-106">So starten Sie den Datenbankspiegelungs-Monitor</span><span class="sxs-lookup"><span data-stu-id="5b401-106">To launch the Database Mirroring Monitor</span></span>  
  
1.  <span data-ttu-id="5b401-107">Nachdem Sie eine Verbindung mit der Prinzipalserverinstanz hergestellt haben, klicken Sie im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="5b401-107">After connecting to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="5b401-108">Erweitern Sie **Datenbanken**, und wählen Sie die zu überwachende Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="5b401-108">Expand **Databases**, and select the database to be monitored.</span></span>  
  
3.  <span data-ttu-id="5b401-109">Klicken Sie mit der rechten Maustaste auf die Datenbank, wählen Sie **Tasks**aus, und klicken Sie dann auf **Datenbankspiegelungs-Monitor starten**.</span><span class="sxs-lookup"><span data-stu-id="5b401-109">Right-click the database, select **Tasks**, and then click **Launch Database Mirroring Monitor**.</span></span>  
  
4.  <span data-ttu-id="5b401-110">Klicken Sie im Dialogfeld **Datenbankspiegelungs-Monitor** auf **Gespiegelte Datenbank registrieren** , um eine oder mehrere gespiegelte Datenbanken zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="5b401-110">In the **Database Mirroring Monitor** dialog box, click **Register Mirrored Database** to register one or more mirrored database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5b401-111">Wenn Sie eine Datenbank bei einem der Partner registrieren, wird sie automatisch auch bei dem anderen Partner registriert.</span><span class="sxs-lookup"><span data-stu-id="5b401-111">When you register a database at one partner, the database is automatically registered at the other partner.</span></span> <span data-ttu-id="5b401-112">Wenn der Monitor bereits über Verbindungsanmeldeinformationen für die andere Partnerinstanz verfügt, werden diese für die Herstellung der Verbindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="5b401-112">If the monitor already has connection credentials for the other partner instance, those are used to connect.</span></span> <span data-ttu-id="5b401-113">Andernfalls versucht der Monitor, die Verbindung mithilfe der Windows-Authentifizierung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="5b401-113">Otherwise the monitor attempts to connect using Windows Authentication.</span></span> <span data-ttu-id="5b401-114">Wenn Sie für das Herstellen der Verbindung mit einer der Serverinstanzen andere Anmeldeinformationen verwenden möchten, klicken Sie auf **Beim Klicken auf 'OK' das Dialogfeld 'Serververbindungen verwalten' anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="5b401-114">If you want to change the credentials used to connect to either server instance, click **Show the Manage Server Connections dialog box when I click OK**.</span></span>  
  
 <span data-ttu-id="5b401-115">Weitere Informationen zur Datenbankspiegelung finden Sie unter [Datenbankspiegelungs-Monitor (Übersicht)](database-mirroring-monitor-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5b401-115">For more information about Database Mirroring Monitor, see [Database Mirroring Monitor Overview](database-mirroring-monitor-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b401-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b401-116">See Also</span></span>  
 <span data-ttu-id="5b401-117">[Datenbankspiegelung &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5b401-117">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="5b401-118">Einrichten einer Datenbank-Spiegelungssitzung mithilfe der Windows-Authentifizierung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="5b401-118">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
  
