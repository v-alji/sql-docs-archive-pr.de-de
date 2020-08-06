---
title: Aktualisieren von Data Quality Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: f396666b-7754-4efc-9507-0fd114cc32d5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9d2544df341a831f2f676ec58150ed64a800fb96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616162"
---
# <a name="upgrade-data-quality-services"></a><span data-ttu-id="1ffd9-102">Aktualisieren von Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="1ffd9-102">Upgrade Data Quality Services</span></span>
  <span data-ttu-id="1ffd9-103">Dieses Thema enthält Informationen dazu, wie Sie die vorhandene Data Quality Services-Installation (DQS) auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] CTP2 aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-103">This topic provides information on how to upgrade your existing installation of Data Quality Services (DQS) to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] CTP2.</span></span> <span data-ttu-id="1ffd9-104">Während des Upgrades des Data Quality-Servers in DQS auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]muss auch das DQS-Datenbankschema aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-104">As part of upgrading your Data Quality Server in DQS to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you must also upgrade the DQS databases schema.</span></span>  
  
> [!IMPORTANT]
>  -   <span data-ttu-id="1ffd9-105">Sie müssen die DQS-Datenbanken sichern, bevor Sie DQS aktualisieren, um versehentliche Datenverluste während des Schemaupgrades zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-105">You must back up your DQS databases before upgrading DQS to prevent any accidental data loss during the schema upgrade.</span></span> <span data-ttu-id="1ffd9-106">Informationen zum Sichern von DQS-Datenbanken finden Sie unter [Backing Up and Restoring DQS Databases](../../data-quality-services/backing-up-and-restoring-dqs-databases.md).</span><span class="sxs-lookup"><span data-stu-id="1ffd9-106">For information about backing up DQS databases, see [Backing Up and Restoring DQS Databases](../../data-quality-services/backing-up-and-restoring-dqs-databases.md).</span></span>  
> -   <span data-ttu-id="1ffd9-107">Um eine Verbindung mit der [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] -Version des Data Quality-Servers herzustellen und Data Quality-Aufgaben auszuführen, können Sie die aktuelle oder eine frühere Version des Data Quality-Clients oder die [DQS-Bereinigungstransformation](../../integration-services/data-flow/transformations/dqs-cleansing-transformation.md) in Integration Services verwenden.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-107">You can connect to the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] version of Data Quality Server by using the current or an earlier version of Data Quality Client or the [DQS Cleansing Transformation](../../integration-services/data-flow/transformations/dqs-cleansing-transformation.md) in Integration Services to perform your data quality tasks.</span></span>  
> -   <span data-ttu-id="1ffd9-108">Nachdem Data Quality Services und Master Data Services auf [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] CTP2 aktualisiert wurden, kann die [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] SP1-Version des Master Data Services-Add-Ins für Excel weiterverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-108">You can continue using the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] SP1 version of Master Data Services Add-In for Excel after upgrading Data Quality Services and Master Data Services to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] CTP2.</span></span> <span data-ttu-id="1ffd9-109">Frühere Versionen des Master Data Services-Add-Ins für Excel sind nach einem Upgrade auf SQL Server 2014 CTP2 jedoch nicht funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-109">However, any earlier version of the Master Data Services Add-In for Excel will not work after upgrading to SQL Server 2014 CTP2.</span></span> <span data-ttu-id="1ffd9-110">Sie können die [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] SP1-Version des Master Data Services-Add-Ins für Excel [hier](https://go.microsoft.com/fwlink/?LinkId=328664)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-110">You can download the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] SP1 version of Master Data Services Add-In for Excel from [here](https://go.microsoft.com/fwlink/?LinkId=328664).</span></span>  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="1ffd9-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1ffd9-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="1ffd9-112">Sie müssen als Mitglied der Administratorgruppe auf dem [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] -Computer angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-112">You must be logged on as a member of the Administrators group on the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer.</span></span>  
  
-   <span data-ttu-id="1ffd9-113">Ihr Windows-Benutzerkonto muss Mitglied der festen Serverrolle sysadmin auf der SQL Server-Instanz sein, auf der der [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] installiert ist.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-113">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance where [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] is installed.</span></span>  
  
##  <a name="upgrading-dqs"></a><a name="Upgrade"></a> <span data-ttu-id="1ffd9-114">Aktualisieren von DQS</span><span class="sxs-lookup"><span data-stu-id="1ffd9-114">Upgrading DQS</span></span>  
 <span data-ttu-id="1ffd9-115">So aktualisieren Sie DQS</span><span class="sxs-lookup"><span data-stu-id="1ffd9-115">To upgrade DQS:</span></span>  
  
1.  <span data-ttu-id="1ffd9-116">Sichern Sie die DQS-Datenbanken, bevor Sie den Upgradevorgang starten.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-116">Back up your DQS databases before you start the upgrade process.</span></span> <span data-ttu-id="1ffd9-117">Informationen zum Sichern von DQS-Datenbanken finden Sie unter [Backing Up and Restoring DQS Databases](../../data-quality-services/backing-up-and-restoring-dqs-databases.md).</span><span class="sxs-lookup"><span data-stu-id="1ffd9-117">For information about backing up DQS databases, see [Backing Up and Restoring DQS Databases](../../data-quality-services/backing-up-and-restoring-dqs-databases.md).</span></span>  
  
2.  <span data-ttu-id="1ffd9-118">Aktualisieren Sie die SQL Server-Instanz mit der DQS-Installation auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ffd9-118">Upgrade the SQL Server instance where DQS is installed to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
    1.  <span data-ttu-id="1ffd9-119">Führen Sie den [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] -Setup-Assistenten aus.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-119">Run the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Setup wizard.</span></span>  
  
    2.  <span data-ttu-id="1ffd9-120">Klicken Sie im linken Bereich auf **Installation**.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-120">In the left pane, click **Installation**.</span></span>  
  
    3.  <span data-ttu-id="1ffd9-121">Klicken Sie im rechten Bereich auf **Upgrade von SQL Server 2005, SQL Server 2008, SQL Server 2008 R2 oder SQL Server 2012**.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-121">In the right pane, click **Upgrade from SQL Server 2005, SQL Server 2008, SQL Server 2008 R2 or SQL Server 2012**.</span></span>  
  
    4.  <span data-ttu-id="1ffd9-122">Schließen Sie den Setup-Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-122">Complete the Setup wizard.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="1ffd9-123">Auf diese Weise wird die SQL Server-Instanz auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] aktualisiert. Außerdem wird der neueste Data Quality-Client installiert, wenn zuvor ein Data Quality-Client auf dem Computer installiert war.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-123">This will upgrade your SQL Server instance to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] and also install the latest Data Quality Client, if Data Quality Client was previously installed on this computer.</span></span> <span data-ttu-id="1ffd9-124">Wenn auf anderen Computern ein Data Quality-Client installiert ist, müssen Sie auf diesen Computern die Teilschritte unter Schritt 2 ausführen, um die aktuelle Version des Data Quality-Clients zu installieren.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-124">If you have Data Quality Client installed on other computers, you must run the sub steps in Step 2 on those computers to install the current version of Data Quality Client.</span></span> <span data-ttu-id="1ffd9-125">Der Setup-Assistent installiert die aktuelle Version neben der vorhandenen Version des Data Quality-Clients.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-125">The Setup wizard installs the current version of Data Quality Client alongside the existing version of Data Quality Client.</span></span> <span data-ttu-id="1ffd9-126">Nachdem Sie das DQS-Datenbankschema aktualisiert haben, können Sie mit der aktuellen oder einer früheren Version des Data Quality-Clients eine Verbindung mit der [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] -Version des Data Quality-Servers herstellen.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-126">After you upgrade the DQS databases schema, you can connect to the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] version of Data Quality Server by using the current or an earlier version of Data Quality Client.</span></span>  
  
3.  <span data-ttu-id="1ffd9-127">Aktualisieren Sie das DQS-Datenbankschema.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-127">Upgrade the DQS databases schema.</span></span>  
  
    1.  <span data-ttu-id="1ffd9-128">Starten Sie eine -Eingabeaufforderung als Administrator.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-128">Start Command Prompt as an administrator.</span></span>  
  
    2.  <span data-ttu-id="1ffd9-129">Wechseln Sie an der Eingabeaufforderung zu dem Verzeichnis, in dem DQSInstaller.exe enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-129">At the command prompt, change your directory to the location where DQSInstaller.exe is available.</span></span> <span data-ttu-id="1ffd9-130">Bei Verwendung der Standardinstanz von SQL Server steht die Datei DQSInstaller.exe unter C:\Programme\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="1ffd9-130">For the default instance of SQL Server, the DQSInstaller.exe file is available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn:</span></span>  
  
        ```  
        cd C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn  
        ```  
  
    3.  <span data-ttu-id="1ffd9-131">Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="1ffd9-131">At the command prompt, type the following command, and press ENTER:</span></span>  
  
        ```  
        dqsinstaller.exe -upgrade  
        ```  
  
    4.  <span data-ttu-id="1ffd9-132">Sie werden vom Installationsprogramm aufgefordert, die DQS-Datenbanken zu sichern, bevor Sie den Vorgang fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-132">The installer prompts you for backing up the DQS databases before proceeding.</span></span> <span data-ttu-id="1ffd9-133">Wenn Sie die DQS-Datenbanken bereits gesichert haben, geben Sie `Y` oder `Yes` ein und drücken dann die EINGABETASTE, um das Upgrade fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-133">If you have already backed up your DQS databases, type `Y` or `Yes`, and then press ENTER to continue with the upgrade.</span></span>  
  
    5.  <span data-ttu-id="1ffd9-134">Nach dem erfolgreichen Upgrade des DQS-Datenbankschemas wird eine Abschlussmeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-134">A completion message is displayed after successful upgrade of the DQS databases schema.</span></span>  
  
##  <a name="verifying-the-dqs-databases-schema-upgrade"></a><a name="Verify"></a> <span data-ttu-id="1ffd9-135">Überprüfen des Upgrades des DQS-Datenbankschemas</span><span class="sxs-lookup"><span data-stu-id="1ffd9-135">Verifying the DQS Databases Schema Upgrade</span></span>  
 <span data-ttu-id="1ffd9-136">Um sicherzustellen, dass das DQS-Datenbankschema erfolgreich aktualisiert wurde, können Sie die aktuelle Version in den Datenbanken DQS_MAIN und DQS_PROJECTS überprüfen, indem Sie die A_DB_VERSION-Tabelle in der jeweiligen Datenbank abfragen.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-136">To verify that DQS databases schema have successfully upgraded, you can check the current version in the DQS_MAIN and DQS_PROJECTS databases by querying the A_DB_VERSION table in each database.</span></span> <span data-ttu-id="1ffd9-137">Gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="1ffd9-137">To do so:</span></span>  
  
1.  <span data-ttu-id="1ffd9-138">Starten Sie SQL Server Management Studio, und stellen Sie eine Verbindung mit der SQL Server-Instanz her, die das aktualisierte DQS-Datenbankschema enthält.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-138">Start SQL Server Management Studio, and connect to the SQL Server instance that contains the upgraded DQS databases schema.</span></span>  
  
2.  <span data-ttu-id="1ffd9-139">Führen Sie die folgende Abfrage aus:</span><span class="sxs-lookup"><span data-stu-id="1ffd9-139">Run the following query:</span></span>  
  
    ```  
    SELECT * FROM DQS_MAIN.dbo.A_DB_VERSION WHERE STATUS=2;  
    SELECT * FROM DQS_PROJECTS.dbo.A_DB_VERSION WHERE STATUS=2;  
    ```  
  
3.  <span data-ttu-id="1ffd9-140">In der Ausgabe wird ein Eintrag für jedes Upgrade zusammen mit dem Upgradedatum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-140">The output will display an entry for each upgrade along with the date of the upgrade.</span></span> <span data-ttu-id="1ffd9-141">Der höchste VERSION_ID- und ASSEMBLY_VERSION-Wert zum letzten angegebenen Datum entspricht der aktuellen Version.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-141">The maximum VERSION_ID and ASSEMBLY_VERSION on the latest date is the current version.</span></span> <span data-ttu-id="1ffd9-142">Der Wert 2 in der STATUS-Spalte gibt die erfolgreiche Ausführung an.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-142">A value of 2 in the STATUS column indicates success.</span></span> <span data-ttu-id="1ffd9-143">Falls ein Fehler aufgetreten ist, wird dieser in der ERROR-Spalte aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="1ffd9-143">If an error has occurred, the error will be listed in the ERROR column.</span></span> <span data-ttu-id="1ffd9-144">Beispiel für eine Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1ffd9-144">A sample output:</span></span>  
  
    |<span data-ttu-id="1ffd9-145">id</span><span class="sxs-lookup"><span data-stu-id="1ffd9-145">ID</span></span>|<span data-ttu-id="1ffd9-146">UPGRADE_DATE</span><span class="sxs-lookup"><span data-stu-id="1ffd9-146">UPGRADE_DATE</span></span>|<span data-ttu-id="1ffd9-147">VERSION_ID</span><span class="sxs-lookup"><span data-stu-id="1ffd9-147">VERSION_ID</span></span>|<span data-ttu-id="1ffd9-148">ASSEMBLY_VERSION</span><span class="sxs-lookup"><span data-stu-id="1ffd9-148">ASSEMBLY_VERSION</span></span>|<span data-ttu-id="1ffd9-149">USER_NAME</span><span class="sxs-lookup"><span data-stu-id="1ffd9-149">USER_NAME</span></span>|<span data-ttu-id="1ffd9-150">STATUS</span><span class="sxs-lookup"><span data-stu-id="1ffd9-150">STATUS</span></span>|<span data-ttu-id="1ffd9-151">ERROR</span><span class="sxs-lookup"><span data-stu-id="1ffd9-151">ERROR</span></span>|  
    |--------|-------------------|-----------------|-----------------------|----------------|------------|-----------|  
    |<span data-ttu-id="1ffd9-152">1000</span><span class="sxs-lookup"><span data-stu-id="1ffd9-152">1000</span></span>|<span data-ttu-id="1ffd9-153">2013-08-11 05:26:39.567</span><span class="sxs-lookup"><span data-stu-id="1ffd9-153">2013-08-11 05:26:39.567</span></span>|<span data-ttu-id="1ffd9-154">1200</span><span class="sxs-lookup"><span data-stu-id="1ffd9-154">1200</span></span>|<span data-ttu-id="1ffd9-155">11.0.3000.0</span><span class="sxs-lookup"><span data-stu-id="1ffd9-155">11.0.3000.0</span></span>|\<DOMAIN\UserName>|<span data-ttu-id="1ffd9-156">2</span><span class="sxs-lookup"><span data-stu-id="1ffd9-156">2</span></span>||  
    |<span data-ttu-id="1ffd9-157">1001</span><span class="sxs-lookup"><span data-stu-id="1ffd9-157">1001</span></span>|<span data-ttu-id="1ffd9-158">2013-09-19 15:09:37.750</span><span class="sxs-lookup"><span data-stu-id="1ffd9-158">2013-09-19 15:09:37.750</span></span>|<span data-ttu-id="1ffd9-159">1600</span><span class="sxs-lookup"><span data-stu-id="1ffd9-159">1600</span></span>|<span data-ttu-id="1ffd9-160">12.0.xxxx.0</span><span class="sxs-lookup"><span data-stu-id="1ffd9-160">12.0.xxxx.0</span></span>|\<DOMAIN\UserName>|<span data-ttu-id="1ffd9-161">2</span><span class="sxs-lookup"><span data-stu-id="1ffd9-161">2</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="1ffd9-162">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ffd9-162">See Also</span></span>  
 <span data-ttu-id="1ffd9-163">[Installieren von Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md) </span><span class="sxs-lookup"><span data-stu-id="1ffd9-163">[Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md) </span></span>  
 <span data-ttu-id="1ffd9-164">[Entfernen von Data Quality Server-Objekten](../../sql-server/install/remove-data-quality-server-objects.md) </span><span class="sxs-lookup"><span data-stu-id="1ffd9-164">[Remove Data Quality Server Objects](../../sql-server/install/remove-data-quality-server-objects.md) </span></span>  
 [<span data-ttu-id="1ffd9-165">Upgrade auf SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="1ffd9-165">Upgrade to SQL Server 2014</span></span>](upgrade-sql-server.md)  
  
  