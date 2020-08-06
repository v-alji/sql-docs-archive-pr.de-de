---
title: Vorbereiten von SQL Server für CDC | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- prepSqlSrv
ms.assetid: 20b51dbf-a545-4234-87ae-4228268a0fb2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dafa29d9bdb0c27decb605398a6d1cfe383427e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610016"
---
# <a name="prepare-sql-server-for-cdc"></a><span data-ttu-id="150e6-102">Vorbereiten von SQL Server für CDC</span><span class="sxs-lookup"><span data-stu-id="150e6-102">Prepare SQL Server for CDC</span></span>
  <span data-ttu-id="150e6-103">Der Oracle CDC Service erfordert, dass alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Zielinstanzen die MSXDBCDC-Datenbank enthalten.</span><span class="sxs-lookup"><span data-stu-id="150e6-103">The Oracle CDC service requires all target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances to contain the MSXDBCDC database.</span></span> <span data-ttu-id="150e6-104">Sie erstellen diese Datenbank mithilfe der Aktion Prepare SQL Server in der CDC Service Configuration Console.</span><span class="sxs-lookup"><span data-stu-id="150e6-104">You create this database using the Prepare SQL Server action in the CDC Service Configuration Console.</span></span> <span data-ttu-id="150e6-105">Dabei wird ein spezielles Skript erstellt, das ausgeführt wird, um die erforderlichen Tabellen, gespeicherten Prozeduren und anderen erforderlichen Artefakte für diese Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="150e6-105">This creates a special script that is run to create the required tables, stored procedures, and other required artifacts for this database.</span></span> <span data-ttu-id="150e6-106">Dieser Task wird für jede [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Zielinstanz nur einmal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="150e6-106">This task is done one time only for each target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="150e6-107">Weitere Informationen zur MSXDBCDC-Datenbank finden Sie unter MSXDBCDC-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="150e6-107">For more information about the MSXDBCDC database, see The MSXDBCDC Database.</span></span>  
  
 <span data-ttu-id="150e6-108">Klicken Sie in der CDC Service Configuration Console auf **Prepare SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="150e6-108">In the CDC Service Configuration Console, click **Prepare SQL Server**.</span></span> <span data-ttu-id="150e6-109">Wenn diese Option nicht verfügbar ist, sollten Sie sicherstellen, dass **Local CDC Services** im linken Bereich der Konsole aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="150e6-109">If this option is not available, make sure that **Local CDC Services** is selected in the left pane of the console.</span></span>  
  
## <a name="options"></a><span data-ttu-id="150e6-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="150e6-110">Options</span></span>  
  
### <a name="server-name"></a><span data-ttu-id="150e6-111">Servername</span><span class="sxs-lookup"><span data-stu-id="150e6-111">Server Name</span></span>  
 <span data-ttu-id="150e6-112">Geben Sie den Namen des Servers ein, auf dem sich [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] befindet.</span><span class="sxs-lookup"><span data-stu-id="150e6-112">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
### <a name="authentication"></a><span data-ttu-id="150e6-113">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="150e6-113">Authentication</span></span>  
 <span data-ttu-id="150e6-114">Wählen Sie eines der folgenden Szenarien aus:</span><span class="sxs-lookup"><span data-stu-id="150e6-114">Select one of the following:</span></span>  
  
-   <span data-ttu-id="150e6-115">**Windows-Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="150e6-115">**Windows Authentication**</span></span>  
  
-   <span data-ttu-id="150e6-116">**SQL Server-Authentifizierung**: Wenn Sie diese Option auswählen, müssen Sie den **Benutzernamen** und das **Kennwort** für den Benutzer von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eingeben, mit dem Sie eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="150e6-116">**SQL Server Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
 <span data-ttu-id="150e6-117">Um die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz für Oracle CDC vorzubereiten, muss die Anmeldung über die Schreibberechtigung für die MSXDBCDC-Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="150e6-117">To prepare the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance for Oracle CDC, the login must have write permission to the MSXDBCDC database.</span></span> <span data-ttu-id="150e6-118">Geben Sie die Anmeldeinformationen für eine Anmeldung ein, die über die Schreibberechtigung für die MSXDBCDC-Datenbank verfügt, z. B. als Mitglied der Rolle `sysasmin` .</span><span class="sxs-lookup"><span data-stu-id="150e6-118">Enter the credentials for a login that has write permission to the MSXDBCDC database, such as a member of the `sysasmin` role.</span></span>  
  
### <a name="options"></a><span data-ttu-id="150e6-119">Tastatur</span><span class="sxs-lookup"><span data-stu-id="150e6-119">Options</span></span>  
 <span data-ttu-id="150e6-120">Klicken Sie auf den Pfeil, um die verfügbaren Optionen anzuzeigen, die konfiguriert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="150e6-120">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="150e6-121">Sie können für diese Optionen auch die Standardwerte unverändert lassen.</span><span class="sxs-lookup"><span data-stu-id="150e6-121">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="150e6-122">Verfügbare Optionen:</span><span class="sxs-lookup"><span data-stu-id="150e6-122">The available options are:</span></span>  
  
-   <span data-ttu-id="150e6-123">**Verbindungstimeout**: Geben Sie den Zeitraum (in Sekunden) ein, wie lange der CDC Service for Oracle auf eine Verbindung zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] warten soll, bevor ein Timeout eintritt. Der Standardwert lautet **15**.</span><span class="sxs-lookup"><span data-stu-id="150e6-123">**Connection Timeout**: Type the time (in seconds) that the CDC Service for Oracle waits for a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before timing out. The default value is **15**.</span></span>  
  
-   <span data-ttu-id="150e6-124">**Ausführungstimeout**: Geben Sie den Zeitraum (in Sekunden) ein, wie lange der Oracle CDC-Windows-Dienst auf die Ausführung eines Befehls wartet, bis ein Timeout eintritt. Der Standardwert ist **30**.</span><span class="sxs-lookup"><span data-stu-id="150e6-124">**Execution Timeout**: Type the time (in seconds) that the Oracle CDC Windows Service waits for a command to execute before timing out. The default value is **30**.</span></span>  
  
-   <span data-ttu-id="150e6-125">**Verbindung verschlüsseln**: Wählen Sie **Verbindung verschlüsseln** für die Kommunikation zwischen dem Oracle CDC Service und der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Zielinstanz aus, bei der eine verschlüsselte Verbindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="150e6-125">**Encrypt Connection**: Select **Encrypt Connection** for communication between the Oracle CDC Service and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance using an encrypted connection.</span></span>  
  
-   <span data-ttu-id="150e6-126">**Erweitert**: Geben Sie bei Bedarf zusätzliche Verbindungseigenschaften ein.</span><span class="sxs-lookup"><span data-stu-id="150e6-126">**Advanced**: Type any additional connection properties, if necessary.</span></span>  
  
### <a name="view-script"></a><span data-ttu-id="150e6-127">Skript anzeigen</span><span class="sxs-lookup"><span data-stu-id="150e6-127">View Script</span></span>  
 <span data-ttu-id="150e6-128">Klicken Sie auf **Skript anzeigen** , um eine schreibgeschützte Version des Setupskripts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="150e6-128">Click **View Script** to view a read-only version of the setup script.</span></span> <span data-ttu-id="150e6-129">Ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Systemadministrator kann dieses Skript bei Bedarf in die SQL Server Management Console kopieren, um sie zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="150e6-129">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator can copy this script into the SQL Server Management Console to edit it, if necessary.</span></span> <span data-ttu-id="150e6-130">Weitere Informationen über Prepare SQL Server Script finden Sie unter [Vorbereiten von SQL Server für Oracle CDC – Skript anzeigen](prepare-sql-server-for-oracle-cdc-view-script.md).</span><span class="sxs-lookup"><span data-stu-id="150e6-130">For more information about the Prepare SQL Server Script, see [Prepare SQL Server for Oracle CDC-View Script](prepare-sql-server-for-oracle-cdc-view-script.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="150e6-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="150e6-131">See Also</span></span>  
 <span data-ttu-id="150e6-132">[Verwenden von CDC Services](work-with-cdc-services.md) </span><span class="sxs-lookup"><span data-stu-id="150e6-132">[How to Work with CDC Services](work-with-cdc-services.md) </span></span>  
 [<span data-ttu-id="150e6-133">Vorbereiten von SQL Server für CDC</span><span class="sxs-lookup"><span data-stu-id="150e6-133">How to Prepare SQL Server for CDC</span></span>](prepare-sql-server-for-cdc.md)  
  
  
