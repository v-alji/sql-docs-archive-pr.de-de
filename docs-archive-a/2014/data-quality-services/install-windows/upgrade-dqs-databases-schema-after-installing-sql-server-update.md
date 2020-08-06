---
title: Aktualisieren des DQS-Datenbankschemas nach der Installation eines SQL Server-Updates | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: c8f3fbae-02c4-464d-a35c-7108f48c58cb
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 80a1714ea250cf7cf5d34bc9d208a42a64284308
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618918"
---
# <a name="upgrade-dqs-databases-schema-after-installing-sql-server-update"></a><span data-ttu-id="fd6a3-102">Aktualisieren des DQS-Datenbankschemas nach der Installation eines SQL Server-Updates</span><span class="sxs-lookup"><span data-stu-id="fd6a3-102">Upgrade DQS Databases Schema After Installing SQL Server Update</span></span>
  <span data-ttu-id="fd6a3-103">Nachdem Sie ein SQL Server-Update (Patch, Hotfix oder kumulatives Update) auf einer zuvor konfigurierten DQS-Instanz installiert haben, muss das DQS-Datenbankschema u. U. aktualisiert werden, indem Sie die Datei DQSInstaller.exe mit dem Befehlszeilenparameter **upgrade** ausführen.</span><span class="sxs-lookup"><span data-stu-id="fd6a3-103">After you have installed a SQL Server update (patch, hotfix, or cumulative update) on a previously configured DQS instance, you might have to upgrade the DQS databases schema by running the DQSInstaller.exe file with the **upgrade** command line parameter.</span></span> <span data-ttu-id="fd6a3-104">Andernfalls kann beim Versuch, über den Data Quality-Client eine Verbindung mit dem Data Quality-Server herzustellen, der folgende Fehler ausgegeben werden:</span><span class="sxs-lookup"><span data-stu-id="fd6a3-104">Otherwise, you might receive the following error while trying to connect to Data Quality Server using your Data Quality Client:</span></span>  
  
```  
An error occurred in the Microsoft .NET Framework while trying to load assembly id 65581.  
```  
  
 <span data-ttu-id="fd6a3-105">Für das DQS-Datenbankschema ausgeführte Upgrades haben keine Auswirkungen auf vorhandene Daten in den DQS-Datenbanken (Wissensdatenbanken, Data Quality-Projekte und exportierte Ergebnisse in der DQS_STAGING_DATA-Datenbank).</span><span class="sxs-lookup"><span data-stu-id="fd6a3-105">Upgrading DQS databases schema does not impact your existing data in the DQS databases (knowledge bases, data quality projects, and exported results in the DQS_STAGING_DATA database).</span></span> <span data-ttu-id="fd6a3-106">Sie müssen die DQS-Datenbanken jedoch sichern, bevor Sie das DQS-Datenbankschema aktualisieren, um versehentliche Datenverluste während des Schemaupgrades zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="fd6a3-106">However, you must back up your DQS databases before upgrading DQS databases schema to prevent any accidental data loss during the schema upgrade.</span></span> <span data-ttu-id="fd6a3-107">Informationen zum Sichern von DQS-Datenbanken finden Sie unter [Backing Up and Restoring DQS Databases](../backing-up-and-restoring-dqs-databases.md).</span><span class="sxs-lookup"><span data-stu-id="fd6a3-107">For information about backing up DQS databases, see [Backing Up and Restoring DQS Databases](../backing-up-and-restoring-dqs-databases.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fd6a3-108">Die meisten SQL Server-Updates erfordern ein Upgrade auf das DQS-Datenbankschema.</span><span class="sxs-lookup"><span data-stu-id="fd6a3-108">Most of the SQL Server updates will require an upgrade to the DQS databases schema.</span></span> <span data-ttu-id="fd6a3-109">Informationen zu den SQL Server-Updates, die ein Upgrade auf das DQS-Datenbankschema erfordern, finden Sie im Diagramm in Schritt 1.A unter [Aktualisieren von DQS: Installieren von kumulativen Updates oder Hotfixpatches für Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565).</span><span class="sxs-lookup"><span data-stu-id="fd6a3-109">For information about the SQL Server updates that will require an upgrade to the DQS databases schema, see the chart in step 1.A in [Upgrade DQS: Installing Cumulative Updates or Hotfix Patches on Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fd6a3-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="fd6a3-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="fd6a3-111">Sie müssen als Mitglied der Administratorgruppe auf dem [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] -Computer angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="fd6a3-111">You must be logged on as a member of the Administrators group on the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer.</span></span>  
  
-   <span data-ttu-id="fd6a3-112">Ihr Windows-Benutzerkonto muss Mitglied der festen Serverrolle sysadmin auf der SQL Server-Instanz sein, auf der der [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] installiert ist.</span><span class="sxs-lookup"><span data-stu-id="fd6a3-112">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance where [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] is installed.</span></span>  
  
### <a name="to-upgrade-dqs-databases-schema"></a><span data-ttu-id="fd6a3-113">So aktualisieren Sie das DQS-Datenbankschema</span><span class="sxs-lookup"><span data-stu-id="fd6a3-113">To upgrade DQS databases schema</span></span>  
  
1.  <span data-ttu-id="fd6a3-114">(Empfohlen) Sichern Sie die DQS-Datenbanken, bevor Sie das Schemaupgrade fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="fd6a3-114">(Recommended) Back up your DQS databases before you proceed with the schema upgrade.</span></span> <span data-ttu-id="fd6a3-115">Informationen zum Sichern von DQS-Datenbanken finden Sie unter [Backing Up and Restoring DQS Databases](../backing-up-and-restoring-dqs-databases.md).</span><span class="sxs-lookup"><span data-stu-id="fd6a3-115">For information about backing up DQS databases, see [Backing Up and Restoring DQS Databases](../backing-up-and-restoring-dqs-databases.md).</span></span>  
  
2.  <span data-ttu-id="fd6a3-116">Öffnen Sie die Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="fd6a3-116">Start Command Prompt.</span></span>  
  
3.  <span data-ttu-id="fd6a3-117">Wechseln Sie an der Eingabeaufforderung zu dem Verzeichnis, in dem DQSInstaller.exe enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="fd6a3-117">At the command prompt, change your directory to the location where DQSInstaller.exe is available.</span></span> <span data-ttu-id="fd6a3-118">Wenn Sie z. B. die Standardinstanz von SQL Server installiert haben, steht die Datei DQSInstaller.exe in der Regel unter C:\Programme\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="fd6a3-118">If you installed the default instance of SQL Server, the DQSInstaller.exe file will be available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn:</span></span>  
  
    ```  
    cd C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn  
    ```  
  
4.  <span data-ttu-id="fd6a3-119">Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="fd6a3-119">At the command prompt, type the following command, and press ENTER:</span></span>  
  
    ```  
    dqsinstaller.exe -upgrade  
    ```  
  
5.  <span data-ttu-id="fd6a3-120">Sie werden vom Installationsprogramm aufgefordert, die DQS-Datenbanken zu sichern, bevor Sie den Vorgang fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="fd6a3-120">The installer prompts you for backing up the DQS databases before proceeding.</span></span> <span data-ttu-id="fd6a3-121">Wenn Sie die DQS-Datenbanken bereits gesichert haben, geben Sie `Y` oder `Yes` ein und drücken die EINGABETASTE, um das Upgrade fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="fd6a3-121">If you have already backed up your DQS databases, type `Y` or `Yes` and press ENTER to continue with the upgrade.</span></span>  
  
6.  <span data-ttu-id="fd6a3-122">Nach dem erfolgreichen Upgrade des DQS-Datenbankschemas wird eine Abschlussmeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fd6a3-122">A completion message is displayed after successful upgrade of the DQS databases schema.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fd6a3-123">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="fd6a3-123">Next Steps</span></span>  
 <span data-ttu-id="fd6a3-124">Melden Sie sich in einer Data Quality-Clientanwendung beim aktualisierten Data Quality-Server an.</span><span class="sxs-lookup"><span data-stu-id="fd6a3-124">Log on to the upgraded Data Quality Server from a Data Quality Client application.</span></span>  
  
 <span data-ttu-id="fd6a3-125">Weitere Informationen zum Aktualisieren des DQS-Datenbankschemas nach der Installation von SQL Server-Updates sowie Schritte zur Problembehandlung finden Sie unter [Aktualisieren von DQS: Installieren von kumulativen Updates oder Hotfixpatches für Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565).</span><span class="sxs-lookup"><span data-stu-id="fd6a3-125">For more information about upgrading DQS databases schema after installing SQL Server updates and associated troubleshooting steps, see [Upgrade DQS: Installing Cumulative Updates or Hotfix Patches on Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd6a3-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fd6a3-126">See Also</span></span>  
 <span data-ttu-id="fd6a3-127">[Installieren von Data Quality Services](install-data-quality-services.md) </span><span class="sxs-lookup"><span data-stu-id="fd6a3-127">[Install Data Quality Services](install-data-quality-services.md) </span></span>  
 [<span data-ttu-id="fd6a3-128">Aktualisieren der SQLCLR-Assemblys nach dem Aktualisieren von .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fd6a3-128">Upgrade SQLCLR Assemblies After .NET Framework Update</span></span>](upgrade-sqlclr-assemblies-after-net-framework-update.md)  
  
  
