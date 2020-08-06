---
title: Zugriff auf Daten für DQS-Vorgänge | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 88dfb9ea-6321-4eaf-b9e4-45d36ef048f6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 515b087a8d16e44314d1a21d3dfbd6f13c767f5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701990"
---
# <a name="access-data-for-the-dqs-operations"></a><span data-ttu-id="7b70f-102">Zugriff auf Daten für DQS-Vorgänge</span><span class="sxs-lookup"><span data-stu-id="7b70f-102">Access Data for the DQS Operations</span></span>
  <span data-ttu-id="7b70f-103">Sie haben die folgenden Möglichkeiten, um die Quelldaten für [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS)-Vorgänge zu verwenden und die verarbeiteten Daten zu exportieren:</span><span class="sxs-lookup"><span data-stu-id="7b70f-103">To use your source data for [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS) operations, and export your processed data, you can do either of the following:</span></span>  
  
-   <span data-ttu-id="7b70f-104">Kopieren Sie die Quelldaten in eine Tabelle/Sicht in der DQS_STAGING_DATA-Datenbank, und verwenden Sie sie dann für DQS-Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="7b70f-104">Copy your source data to a table/view in the DQS_STAGING_DATA database, and then use it for DQS operations.</span></span> <span data-ttu-id="7b70f-105">Sie können die verarbeiteten Daten auch in eine neue Tabelle in der DQS_STAGING_DATA-Datenbank exportieren.</span><span class="sxs-lookup"><span data-stu-id="7b70f-105">You can also export the processed data to a new table in the DQS_STAGING_DATA database.</span></span> <span data-ttu-id="7b70f-106">Hierzu muss dem Windows-Benutzerkonto Lese-/Schreibzugriff auf die Datenbank DQS_STAGING_DATA gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="7b70f-106">To do so, your Windows user account must be granted read/write access to the DQS_STAGING_DATA database.</span></span>  
  
-   <span data-ttu-id="7b70f-107">Verwenden Sie die eigene Datenbank als Datenquelle für die DQS-Vorgänge und als Ziel zum Exportieren der verarbeiteten Daten.</span><span class="sxs-lookup"><span data-stu-id="7b70f-107">Use your own database as the source data for the DQS operations, and destination for exporting the processed data.</span></span> <span data-ttu-id="7b70f-108">Stellen Sie deswegen sicher, dass sich die Datenbank in der gleichen SQL Server-Instanz wie die Data Quality Server-Datenbanken befindet.</span><span class="sxs-lookup"><span data-stu-id="7b70f-108">To do so, ensure that your database is in the same SQL Server instance as the Data Quality Server databases.</span></span> <span data-ttu-id="7b70f-109">Andernfalls steht die Datenbank nicht für DQS-Vorgänge im Data Quality-Client zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7b70f-109">Otherwise, the database will not be available in the Data Quality Client for DQS operations.</span></span> <span data-ttu-id="7b70f-110">Außerdem muss dem Windows-Benutzerkonto Zugriff auf die Datenbank DQS_STAGING_DATA zum Exportieren der Abgleichsergebnisse gewährt werden, da der Export der Abgleichsergebnisse ein zweiphasiger Prozess ist: zuerst werden die Abgleichsergebnisse in die temporären Tabellen in der Datenbank DQS_STAGING_DATA exportiert und dann in die Tabelle in der Zieldatenbank verschoben.</span><span class="sxs-lookup"><span data-stu-id="7b70f-110">Also, your Windows user account must be granted access on the DQS_STAGING_DATA database for exporting the matching results because matching results are exported in two phases: first, the matching results are exported to the temporary tables in the DQS_STAGING_DATA database, and then moved to the table in your destination database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7b70f-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7b70f-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="7b70f-112">Sie müssen die Installation des [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] durch Ausführen der Datei DQSInstaller.exe abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="7b70f-112">You must have completed the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] installation by running the DQSInstaller.exe file.</span></span> <span data-ttu-id="7b70f-113">Weitere Informationen finden Sie unter [Ausführen von DQSInstaller.exe zum Abschließen der Installation von Data Quality Server](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="7b70f-113">For more information, see [Run DQSInstaller.exe to Complete Data Quality Server Installation](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
-   <span data-ttu-id="7b70f-114">Das Windows-Benutzerkonto muss ein Element der entsprechenden festen Serverrolle (z. B. securityadmin, serveradmin oder sysadmin) in der Datenbank-Engine-Instanz sein, um Zugriff auf die SQL-Anmeldung in Datenbanken zu gewähren/zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7b70f-114">Your Windows user account must be a member of the appropriate fixed server role (such as securityadmin, serveradmin, or sysadmin) in the database engine instance to grant/modify access to SQL login on databases.</span></span>  
  
### <a name="to-grant-readwrite-access-to-a-user-on-the-dqs_staging_data-database"></a><span data-ttu-id="7b70f-115">So gewähren Sie einem Benutzer Lese-/Schreibzugriff auf die DQS_STAGING_DATA-Datenbank</span><span class="sxs-lookup"><span data-stu-id="7b70f-115">To grant read/write access to a User on the DQS_STAGING_DATA Database</span></span>  
  
1.  <span data-ttu-id="7b70f-116">Starten Sie Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="7b70f-116">Start Microsoft SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="7b70f-117">Erweitern Sie in Microsoft SQL Server Management Studio die SQL Server-Instanz, und erweitern Sie anschließend **Sicherheit**und **Anmeldungen**.</span><span class="sxs-lookup"><span data-stu-id="7b70f-117">In Microsoft SQL Server Management Studio, expand your SQL Server instance, and expand **Security**, and then expand **Logins**.</span></span>  
  
3.  <span data-ttu-id="7b70f-118">Klicken Sie mit der rechten Maustaste auf eine SQL-Anmeldung, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="7b70f-118">Right-click a SQL login, and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="7b70f-119">Klicken Sie im Dialogfeld **Anmeldungseigenschaften** auf die Seite **Benutzerzuordnung** im linken Bereich.</span><span class="sxs-lookup"><span data-stu-id="7b70f-119">In the **Login Properties** dialog box, click the **User Mapping** page in the left pane.</span></span>  
  
5.  <span data-ttu-id="7b70f-120">Aktivieren Sie im rechten Bereich in der Spalte **Zuordnen** das Kontrollkästchen für die **DQS_STAGING_DATA** -Datenbank, und wählen Sie anschließend im Bereich **Mitgliedschaft in Datenbankrolle für: DQS_STAGING_DATA** die folgenden Rollen aus:</span><span class="sxs-lookup"><span data-stu-id="7b70f-120">In the right pane, select the check box under the **Map** column for the **DQS_STAGING_DATA** database, and then select the following roles in the **Database role membership for: DQS_STAGING_DATA** pane:</span></span>  
  
    -   <span data-ttu-id="7b70f-121">**db_datareader**: Lesen von Daten aus Tabellen/Sichten.</span><span class="sxs-lookup"><span data-stu-id="7b70f-121">**db_datareader**: Read data from tables/views.</span></span>  
  
    -   <span data-ttu-id="7b70f-122">**db_datawriter**: Hinzufügen, Löschen oder Ändern von Daten in Tabellen.</span><span class="sxs-lookup"><span data-stu-id="7b70f-122">**db_datawriter**: Add, delete, or change data in tables.</span></span>  
  
    -   <span data-ttu-id="7b70f-123">**db_ddladmin**: Erstellen, Ändern oder Löschen von Tabellen/Sichten.</span><span class="sxs-lookup"><span data-stu-id="7b70f-123">**db_ddladmin**: Create, modify, or delete tables/views.</span></span>  
  
6.  <span data-ttu-id="7b70f-124">Klicken Sie im Dialogfeld **Anmeldungseigenschaften** auf **OK** , um die Änderungen zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="7b70f-124">In the **Login Properties** dialog box, click **OK** to apply the changes.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7b70f-125">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7b70f-125">Next Steps</span></span>  
 <span data-ttu-id="7b70f-126">Versuchen Sie, DQS-Vorgänge auszuführen, die auf die Datenbank als Datenquelle für den DQS-Vorgang zugreifen, und exportieren Sie dann die verarbeiteten Daten in die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="7b70f-126">Try performing DQS operations that accesses the database as data source for DQS operation, and then exports the processed data to the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b70f-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7b70f-127">See Also</span></span>  
 [<span data-ttu-id="7b70f-128">Installieren von Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="7b70f-128">Install Data Quality Services</span></span>](install-data-quality-services.md)  
  
  
