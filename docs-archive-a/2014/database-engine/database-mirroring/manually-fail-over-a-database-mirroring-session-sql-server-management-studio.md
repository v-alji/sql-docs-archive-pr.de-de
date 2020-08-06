---
title: Manuelles Failover für eine Datenbank-Spiegelungssitzung (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover [SQL Server], database mirroring
- manual failover [SQL Server]
- database mirroring [SQL Server], failover
ms.assetid: 4ecf9c63-b3a4-4c54-b553-5bc37973232b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7f7f4547058b2dfd4229142dca73a7d9b4bdb239
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726237"
---
# <a name="manually-fail-over-a-database-mirroring-session-sql-server-management-studio"></a><span data-ttu-id="f9754-102">Manueller Failover für eine Datenbank-Spiegelungssitzung (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="f9754-102">Manually Fail Over a Database Mirroring Session (SQL Server Management Studio)</span></span>
  <span data-ttu-id="f9754-103">Wenn die gespiegelte Datenbank synchronisiert wird, also den Status SYNCHRONIZED aufweist, kann der Datenbankbesitzer ein manuelles Failover zu dem gespiegelten Server initiieren.</span><span class="sxs-lookup"><span data-stu-id="f9754-103">When the mirrored database is synchronized (that is, when the database is in the SYNCHRONIZED state), the database owner can initiate manual failover to the mirror server.</span></span>  
  
 <span data-ttu-id="f9754-104">Während eines manuellen Failovers werden die Prinzipal- und Spiegelserverrollen für die Datenbank getauscht, auf der das Failover auftritt.</span><span class="sxs-lookup"><span data-stu-id="f9754-104">During a manual failover, the principal and mirror server roles are swapped for the database on which the failover occurs.</span></span> <span data-ttu-id="f9754-105">Die Spiegelungsdatenbank wird zur Prinzipaldatenbank, die Prinzipaldatenbank zum Spiegel.</span><span class="sxs-lookup"><span data-stu-id="f9754-105">The mirror database becomes the principal database and the principal database becomes the mirror.</span></span> <span data-ttu-id="f9754-106">Beispielsweise wird in der folgenden Tabelle das Tauschen von zwei Spiegelungspartnern durch ein manuelles Failover dargestellt: `SQLDBENGINE0_1` und `SQLDBENGINE0_2`.</span><span class="sxs-lookup"><span data-stu-id="f9754-106">For example, the following table shows the how a manual failover swaps the roles of two mirroring partners: `SQLDBENGINE0_1` and `SQLDBENGINE0_2`.</span></span>  
  
|<span data-ttu-id="f9754-107">Server</span><span class="sxs-lookup"><span data-stu-id="f9754-107">Server</span></span>|<span data-ttu-id="f9754-108">Vor dem Failover</span><span class="sxs-lookup"><span data-stu-id="f9754-108">Before failover</span></span>|<span data-ttu-id="f9754-109">Nach dem Failover</span><span class="sxs-lookup"><span data-stu-id="f9754-109">After failover</span></span>|  
|------------|---------------------|--------------------|  
|`SQLDBENGINE0_1`|<span data-ttu-id="f9754-110">PRINCIPAL</span><span class="sxs-lookup"><span data-stu-id="f9754-110">PRINCIPAL</span></span>|<span data-ttu-id="f9754-111">MIRROR</span><span class="sxs-lookup"><span data-stu-id="f9754-111">MIRROR</span></span>|  
|`SQLDBENGINE0_2`|<span data-ttu-id="f9754-112">MIRROR</span><span class="sxs-lookup"><span data-stu-id="f9754-112">MIRROR</span></span>|<span data-ttu-id="f9754-113">PRINCIPAL</span><span class="sxs-lookup"><span data-stu-id="f9754-113">PRINCIPAL</span></span>|  
  
 <span data-ttu-id="f9754-114">Beachten Sie, dass die Serverrollen für andere Datenbank-Spiegelungssitzungen nicht davon betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="f9754-114">Note that the server roles for other database mirroring sessions are not affected.</span></span> <span data-ttu-id="f9754-115">Weitere Informationen finden Sie unter [Rollenwechsel während einer Datenbank-Spiegelungssitzung &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md)herunter.</span><span class="sxs-lookup"><span data-stu-id="f9754-115">For more information, see [Role Switching During a Database Mirroring Session &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md).</span></span>  
  
### <a name="to-manually-fail-over-database-mirroring"></a><span data-ttu-id="f9754-116">Sie führen Sie ein manuelles Failover für Datenbankspiegelungen durch</span><span class="sxs-lookup"><span data-stu-id="f9754-116">To manually fail over database mirroring</span></span>  
  
1.  <span data-ttu-id="f9754-117">Stellen Sie eine Verbindung zur Prinzipalserverinstanz her, und klicken Sie im Bereich **Objekt-Explorer** auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="f9754-117">Connect to the principal server instance and, in the **Object Explorer** pane, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="f9754-118">Erweitern Sie **Datenbanken**, und wählen Sie die Datenbank aus, für die ein Failover durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f9754-118">Expand **Databases**, and select the database to be failed over.</span></span>  
  
3.  <span data-ttu-id="f9754-119">Klicken Sie mit der rechten Maustaste auf die Datenbank, wählen Sie **Tasks**aus, und klicken Sie dann auf **Spiegeln**.</span><span class="sxs-lookup"><span data-stu-id="f9754-119">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="f9754-120">Dadurch wird die Seite **Spiegelung** im Dialogfeld **Datenbankeigenschaften** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f9754-120">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="f9754-121">Klicken Sie auf **Failover**.</span><span class="sxs-lookup"><span data-stu-id="f9754-121">Click **Failover**.</span></span>  
  
     <span data-ttu-id="f9754-122">Es wird ein Bestätigungsdialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f9754-122">A confirmation box appears.</span></span>  <span data-ttu-id="f9754-123">Der Prinzipalserver versucht als erstes, mithilfe der Windows-Authentifizierung eine Verbindung mit dem Spiegelserver herzustellen.</span><span class="sxs-lookup"><span data-stu-id="f9754-123">The principal server begins by trying to connect to the mirror server by using Windows Authentication.</span></span> <span data-ttu-id="f9754-124">Wenn die Windows-Authentifizierung nicht funktioniert, zeigt der Prinzipalserver das Dialogfeld **Verbindung mit Server herstellen** an.</span><span class="sxs-lookup"><span data-stu-id="f9754-124">If Windows Authentication does not work, the principal server displays the **Connect to Server** dialog box.</span></span> <span data-ttu-id="f9754-125">Wenn der Spiegelserver die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung verwendet, wählen Sie im Feld **Authentifizierung** die Option **SQL Server-Authentifizierung** aus.</span><span class="sxs-lookup"><span data-stu-id="f9754-125">If the mirror server uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, select **SQL Server Authentication** in the **Authentication** box.</span></span> <span data-ttu-id="f9754-126">Geben Sie im Textfeld **Anmeldename** das Anmeldekonto an, mit dem auf dem Spiegelserver eine Verbindung hergestellt werden soll, und geben Sie im Textfeld **Kennwort** das Kennwort für dieses Konto an.</span><span class="sxs-lookup"><span data-stu-id="f9754-126">In the **Login** text box, specify the login account to connect with on the mirror server, and in the **Password** text box, specify the password for that account.</span></span>  
  
     <span data-ttu-id="f9754-127">Nach erfolgreicher Ausführung des Failovers, wird das Dialogfeld **Datenbankeigenschaften** geschlossen.</span><span class="sxs-lookup"><span data-stu-id="f9754-127">If failover succeeds, the **Database Properties** dialog box closes.</span></span> <span data-ttu-id="f9754-128">Die Spiegelungsdatenbank wird zur Prinzipaldatenbank, die Prinzipaldatenbank zum Spiegel.</span><span class="sxs-lookup"><span data-stu-id="f9754-128">The mirror database becomes the principal database and the principal database becomes the mirror.</span></span>  
  
     <span data-ttu-id="f9754-129">Falls ein Fehler beim Failover auftritt, wird eine Fehlermeldung angezeigt, und das Dialogfeld bleibt geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f9754-129">If failover fails, an error message is displayed and the dialog box remains open.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="f9754-130">Wenn Sie Eigenschaften seit dem Öffnen der Seite **Spiegelung** geändert haben, werden diese Änderungen nicht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f9754-130">If you have modified any properties since opening the **Mirroring** page, those changes will not be saved.</span></span>  
  
     <span data-ttu-id="f9754-131">Das Dialogfeld wird automatisch geschlossen.</span><span class="sxs-lookup"><span data-stu-id="f9754-131">The dialog box closes automatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9754-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f9754-132">See Also</span></span>  
 <span data-ttu-id="f9754-133">[Datenbankeigenschaften &#40;Seite Wird gespiegelt&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="f9754-133">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="f9754-134">[Datenbankspiegelung &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f9754-134">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="f9754-135">[Ausführen des manuellen Failovers einer Datenbank-Spiegelungssitzung (Transact-SQL)](manually-fail-over-a-database-mirroring-session-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="f9754-135">[Manually Fail Over a Database Mirroring Session &#40;Transact-SQL&#41;](manually-fail-over-a-database-mirroring-session-transact-sql.md) </span></span>  
 <span data-ttu-id="f9754-136">[Anhalten oder Fortsetzen einer Datenbank-Spiegelungssitzung (SQL Server)](pause-or-resume-a-database-mirroring-session-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f9754-136">[Pause or Resume a Database Mirroring Session &#40;SQL Server&#41;](pause-or-resume-a-database-mirroring-session-sql-server.md) </span></span>  
 [<span data-ttu-id="f9754-137">Entfernen der Datenbankspiegelung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f9754-137">Remove Database Mirroring &#40;SQL Server&#41;</span></span>](remove-database-mirroring-sql-server.md)  
  
  
