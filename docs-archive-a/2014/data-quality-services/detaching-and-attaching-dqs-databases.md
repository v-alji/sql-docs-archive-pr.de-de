---
title: Trennen und Anfügen von DQS-Datenbanken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 830e33bc-dd15-4f8e-a4ac-d8634b78fe45
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3bcac9d1f53b10cf6356b878ce4006f66c198d99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610064"
---
# <a name="detaching-and-attaching-dqs-databases"></a><span data-ttu-id="457ae-102">Trennen und Anfügen von DQS-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="457ae-102">Detaching and Attaching DQS Databases</span></span>
  <span data-ttu-id="457ae-103">In diesem Thema wird beschrieben, wie DQS-Datenbanken getrennt und angefügt werden.</span><span class="sxs-lookup"><span data-stu-id="457ae-103">This topic describes how to detach and attach the DQS databases.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="457ae-104">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="457ae-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Limitations"></a> <span data-ttu-id="457ae-105">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="457ae-105">Limitations and Restrictions</span></span>  
 <span data-ttu-id="457ae-106">Eine Liste der Einschränkungen finden Sie unter [Anfügen und Trennen von Datenbanken &#40;SQL Server&#41;](../relational-databases/databases/database-detach-and-attach-sql-server.md)getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="457ae-106">For a list of limitations and restrictions, see [Database Detach and Attach &#40;SQL Server&#41;](../relational-databases/databases/database-detach-and-attach-sql-server.md).</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="457ae-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="457ae-107">Prerequisites</span></span>  
  
-   <span data-ttu-id="457ae-108">Stellen Sie sicher, dass in DQS keine Aktivitäten oder Prozesse ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="457ae-108">Ensure that there are no running activities or processes in DQS.</span></span> <span data-ttu-id="457ae-109">Dies kann mithilfe des Bildschirms **Aktivitätsüberwachung** überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="457ae-109">This can be verified using the **Activity Monitoring** screen.</span></span> <span data-ttu-id="457ae-110">Weitere Informationen zum Verwenden dieses Bildschirms finden Sie unter [Monitor DQS Activities](../../2014/data-quality-services/monitor-dqs-activities.md).</span><span class="sxs-lookup"><span data-stu-id="457ae-110">For detailed information about working in this screen, see [Monitor DQS Activities](../../2014/data-quality-services/monitor-dqs-activities.md).</span></span>  
  
-   <span data-ttu-id="457ae-111">Stellen Sie sicher, dass keine Benutzer beim [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)]angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="457ae-111">Ensure that there are no users logged on the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="457ae-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="457ae-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="457ae-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="457ae-113">Permissions</span></span>  
  
-   <span data-ttu-id="457ae-114">Das Windows-Benutzerkonto muss Mitglied der festen Serverrolle db_owner in der SQL Server-Instanz sein, damit DQS-Datenbanken getrennt werden können.</span><span class="sxs-lookup"><span data-stu-id="457ae-114">Your Windows user account must be a member of the db_owner fixed server role in the SQL Server instance to detach DQS databases.</span></span>  
  
-   <span data-ttu-id="457ae-115">Das Windows-Benutzerkonto muss über die Berechtigung CREATE DATABASE, CREATE ANY DATABASE oder ALTER ANY DATABASE verfügen, damit eine Datenbank angefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="457ae-115">Your Windows user account must have CREATE DATABASE, CREATE ANY DATABASE, or ALTER ANY DATABASE permission to attach a database.</span></span>  
  
-   <span data-ttu-id="457ae-116">Sie müssen über die Rolle „dqs_administrator“ in der DQS_MAIN-Datenbank verfügen, um ausgeführte Aktivitäten abzubrechen oder ausgeführte Prozesse in DQS anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="457ae-116">You must have the dqs_administrator role on the DQS_MAIN database to terminate any running activities or stop any running processes in DQS.</span></span>  
  
##  <a name="detach-dqs-databases"></a><a name="Detach"></a><span data-ttu-id="457ae-117">Trennen von DQS-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="457ae-117">Detach DQS Databases</span></span>  
 <span data-ttu-id="457ae-118">Wenn Sie eine DQS-Datenbank unter Verwendung von SQL Server Management Studio trennen, verbleiben die getrennten Dateien auf dem Computer und können erneut an dieselbe SQL Server-Instanz angefügt oder auf einen anderen Server verschoben und dort angefügt werden.</span><span class="sxs-lookup"><span data-stu-id="457ae-118">When you detach a DQS database using SQL Server Management Studio, the detached files remain on your computer, and can be reattached to the same SQL Server instance or can be can be moved to another server and attached there.</span></span> <span data-ttu-id="457ae-119">Die DQS-Datenbankdateien sind in der Regel an folgendem Speicherort auf dem Data Quality Services-Computer verfügbar: c:\Programme\Microsoft SQL server\mssql12. *<Instance_Name>* \MSSQL\Data.</span><span class="sxs-lookup"><span data-stu-id="457ae-119">The DQS database files are typically available at the following location on your Data Quality Services computer: C:\Program Files\Microsoft SQL Server\MSSQL12.*<Instance_Name>* \MSSQL\DATA.</span></span>  
  
1.  <span data-ttu-id="457ae-120">Starten Sie Microsoft SQL Server Management Studio, und stellen Sie eine Verbindung mit der entsprechenden SQL Server-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="457ae-120">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="457ae-121">Erweitern Sie im Objekt-Explorer den Knoten **Datenbanken** .</span><span class="sxs-lookup"><span data-stu-id="457ae-121">In Object Explorer, expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="457ae-122">Klicken Sie mit der rechten Maustaste auf die **DQS_MAIN** -Datenbank, zeigen Sie auf **Tasks**, und klicken Sie dann auf **Trennen**.</span><span class="sxs-lookup"><span data-stu-id="457ae-122">Right-click the **DQS_MAIN** database, point to **Tasks**, and then click **Detach**.</span></span> <span data-ttu-id="457ae-123">Das Dialogfeld **Datenbank trennen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="457ae-123">The **Detach Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="457ae-124">Aktivieren Sie das Kontrollkästchen unter der Spalte **Löschen** , und klicken Sie auf **OK** , um die DQS_MAIN-Datenbank zu trennen.</span><span class="sxs-lookup"><span data-stu-id="457ae-124">Select the check box under the **Drop** column, and click **OK** to detach the DQS_MAIN database.</span></span>  
  
5.  <span data-ttu-id="457ae-125">Wiederholen Sie Schritt 3 und 4 für die DQS_PROJECTS- und DQS_STAGING_DATA-Datenbank, um sie zu trennen.</span><span class="sxs-lookup"><span data-stu-id="457ae-125">Repeat steps 3 and 4 with the DQS_PROJECTS and DQS_STAGING_DATA databases to detach them.</span></span>  
  
 <span data-ttu-id="457ae-126">DQS-Datenbanken können auch unter Verwendung der Transact-SQL-Anweisungen mit der gespeicherten Prozedur sp_detach_db getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="457ae-126">You can also detach DQS databases using the Transact-SQL statements by using the sp_detach_db stored procedure.</span></span> <span data-ttu-id="457ae-127">Weitere Informationen zum Trennen von Datenbanken mithilfe von Transact-SQL-Anweisungen finden Sie unter [Using Transact-SQL](../relational-databases/databases/detach-a-database.md#TsqlProcedure) in [Detach a Database](../relational-databases/databases/detach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="457ae-127">For more information about detaching databases using Transact-SQL statements, see [Using Transact-SQL](../relational-databases/databases/detach-a-database.md#TsqlProcedure) in [Detach a Database](../relational-databases/databases/detach-a-database.md).</span></span>  
  
##  <a name="attach-dqs-databases"></a><a name="Attach"></a><span data-ttu-id="457ae-128">DQS-Datenbanken anfügen</span><span class="sxs-lookup"><span data-stu-id="457ae-128">Attach DQS Databases</span></span>  
 <span data-ttu-id="457ae-129">In den folgenden Anweisungen wird erläutert, wie Sie eine DQS-Datenbank an dieselbe SQL Server-Instanz (von der sie getrennt wurde) oder an eine andere SQL Server-Instanz anfügen, auf der [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="457ae-129">Use the following instructions to attach a DQS database to the same SQL Server instance (from where you detached) or a different SQL Server instance where [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] is installed.</span></span>  
  
1.  <span data-ttu-id="457ae-130">Starten Sie Microsoft SQL Server Management Studio, und stellen Sie eine Verbindung mit der entsprechenden SQL Server-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="457ae-130">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="457ae-131">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf **Datenbanken**, und klicken Sie dann auf **Anfügen**.</span><span class="sxs-lookup"><span data-stu-id="457ae-131">In Object Explorer, right-click **Databases**, and then click **Attach**.</span></span> <span data-ttu-id="457ae-132">Das Dialogfeld **Datenbanken anfügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="457ae-132">The **Attach Databases** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="457ae-133">Klicken Sie auf **Hinzufügen**, um die anzufügende Datenbank anzugeben.</span><span class="sxs-lookup"><span data-stu-id="457ae-133">To specify the database to be attached, click **Add**.</span></span> <span data-ttu-id="457ae-134">Das Dialogfeld **Datenbankdateien suchen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="457ae-134">The **Locate Database Files** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="457ae-135">Wählen Sie das Laufwerk aus, auf dem die Datenbank gespeichert ist, und erweitern Sie die Verzeichnisstruktur, um die MDF-Datei der Datenbank zu suchen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="457ae-135">Select the disk drive where the database resides and expand the directory tree to find and select the .mdf file of the database.</span></span> <span data-ttu-id="457ae-136">Beispiel für die DQS_MAIN-Datenbank:</span><span class="sxs-lookup"><span data-stu-id="457ae-136">For example, for the DQS_MAIN database:</span></span>  
  
    ```  
    C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\DQS_MAIN.mdf  
    ```  
  
5.  <span data-ttu-id="457ae-137">Im (unteren) Bereich **Datenbankdetails** werden die Namen der anzufügenden Dateien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="457ae-137">The **database details** (lower) pane displays the names of the files to be attached.</span></span> <span data-ttu-id="457ae-138">Klicken Sie zum Überprüfen oder Ändern des Pfadnamens einer Datei auf die Schaltfläche **Durchsuchen** ( … ).</span><span class="sxs-lookup"><span data-stu-id="457ae-138">To verify or change the pathname of a file, click the **Browse** button (...).</span></span>  
  
6.  <span data-ttu-id="457ae-139">Klicken Sie auf **OK** , um die DQS_MAIN-Datenbank anzufügen.</span><span class="sxs-lookup"><span data-stu-id="457ae-139">Click **OK** to attach the DQS_MAIN database.</span></span>  
  
7.  <span data-ttu-id="457ae-140">Wiederholen Sie Schritt 2 bis 6 für die DQS_PROJECTS- und DQS_STAGING_DATA-Datenbank, um sie anzufügen.</span><span class="sxs-lookup"><span data-stu-id="457ae-140">Repeat steps 2-6 for the DQS_PROJECTS and DQS_STAGING_DATA databases to attach them.</span></span>  
  
8.  <span data-ttu-id="457ae-141">Sie müssen zusätzlich die Transact-SQL-Anweisungen im nächsten Schritt ausführen, nachdem die DQS_MAIN-Datenbank wiederhergestellt wurde. Andernfalls wird eine Fehlermeldung angezeigt, sobald Sie versuchen, über die Data Quality-Clientanwendung eine Verbindung mit dem Data Quality-Server herzustellen, und es kann keine Verbindung hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="457ae-141">You must also run the Transact-SQL statements in the next step after restoring the DQS_MAIN database otherwise an error message is displayed when you try to connect to Data Quality Server by using the Data Quality Client application, and you cannot connect.</span></span> <span data-ttu-id="457ae-142">Schritt 9 und 10 müssen jedoch nicht ausgeführt werden, wenn Sie gerade die DQS_PROJECTS- oder DQS_STAGING_DATA-Datenbank und nicht die DQS_MAIN-Datenbank angefügt haben.</span><span class="sxs-lookup"><span data-stu-id="457ae-142">However, you do not need to perform steps 9 and 10 if you have just attached the DQS_PROJECTS or DQS_STAGING_DATA database, and not DQS_MAIN.</span></span>  
  
     <span data-ttu-id="457ae-143">Um die Transact-SQL-Anweisungen auszuführen, klicken Sie im Objekt-Explorer mit der rechten Maustaste auf den Server, und klicken Sie dann auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="457ae-143">To run the Transact-SQL statements, in Object Explorer, right-click the server, and then click **New Query**.</span></span>  
  
9. <span data-ttu-id="457ae-144">Geben Sie im Fenster Abfrage-Editor die folgenden SQL-Anweisungen ein:</span><span class="sxs-lookup"><span data-stu-id="457ae-144">In the Query Editor window, copy the following SQL statements:</span></span>  
  
    ```sql  
    ALTER DATABASE [DQS_MAIN] SET TRUSTWORTHY ON;  
    EXEC sp_configure 'clr enabled', 1;  
    RECONFIGURE WITH OVERRIDE  
    ALTER DATABASE [DQS_MAIN] SET ENABLE_BROKER  
    ALTER AUTHORIZATION ON DATABASE::[DQS_MAIN] TO [##MS_dqs_db_owner_login##]  
    ALTER AUTHORIZATION ON DATABASE::[DQS_PROJECTS] TO [##MS_dqs_db_owner_login##]  
    ```  
  
10. <span data-ttu-id="457ae-145">Drücken Sie F5, um die Anweisungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="457ae-145">Press F5 to execute the statements.</span></span> <span data-ttu-id="457ae-146">Überprüfen Sie im Ergebnisbereich, ob die Anweisungen erfolgreich ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="457ae-146">Check the Results pane to verify that the statements have executed successfully.</span></span> <span data-ttu-id="457ae-147">Die folgende Meldung wird angezeigt: `Configuration option 'clr enabled' changed from 1 to 1. Run the RECONFIGURE statement to install.`</span><span class="sxs-lookup"><span data-stu-id="457ae-147">You will see the following message: `Configuration option 'clr enabled' changed from 1 to 1. Run the RECONFIGURE statement to install.`</span></span>  
  
11. <span data-ttu-id="457ae-148">Stellen Sie über den Data Quality-Client eine Verbindung mit dem Data Quality-Server her, um zu überprüfen, ob erfolgreich eine Verbindung hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="457ae-148">Connect to the Data Quality Server using the Data Quality Client to verify if you can connect successfully.</span></span>  
  
 <span data-ttu-id="457ae-149">Sie können DQS-Datenbanken auch mithilfe der Transact-SQL-Anweisungen anfügen.</span><span class="sxs-lookup"><span data-stu-id="457ae-149">You can also attach DQS databases using the Transact-SQL statements.</span></span> <span data-ttu-id="457ae-150">Weitere Informationen zum Anfügen von Datenbanken mithilfe von Transact-SQL-Anweisungen finden Sie unter [Using Transact-SQL](../relational-databases/databases/attach-a-database.md#TsqlProcedure) in [Attach a Database](../relational-databases/databases/attach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="457ae-150">For more information about attaching databases using Transact-SQL statements, see [Using Transact-SQL](../relational-databases/databases/attach-a-database.md#TsqlProcedure) in [Attach a Database](../relational-databases/databases/attach-a-database.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="457ae-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="457ae-151">See Also</span></span>  
 [<span data-ttu-id="457ae-152">Manage DQS Databases</span><span class="sxs-lookup"><span data-stu-id="457ae-152">Manage DQS Databases</span></span>](../../2014/data-quality-services/manage-dqs-databases.md)  
  
  
