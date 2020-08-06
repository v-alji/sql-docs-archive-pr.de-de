---
title: Verbindung mit SQL Server zum Löschen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 030b10c2-6b88-4c2c-bf67-22994be25a60
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f5f069f7686e8b6fa9176f92c9e2f47be5f2c71a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610018"
---
# <a name="connection-to-sql-server-for-delete"></a><span data-ttu-id="3aa66-102">Verbindung zu SQL Server zum Löschen</span><span class="sxs-lookup"><span data-stu-id="3aa66-102">Connection to SQL Server for Delete</span></span>
  <span data-ttu-id="3aa66-103">Wenn eine Anmeldung ohne Datenbankrolle, die über die Schreibberechtigung für die MSXDBCDC-Datenbank verfügt (z.B. die Rolle **db_owner** ), versucht, eine Oracle CDC-Instanz zu löschen, wird das Dialogfeld „Verbindung mit SQL Server herstellen“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3aa66-103">When a login without a database role that includes write permission (for example the **db_owner** role) to the MSXDBCDC database attempts to delete an Oracle CDC instance, the Connect to SQL Server dialog box is displayed.</span></span>  
  
 <span data-ttu-id="3aa66-104">In diesem Dialogfeld müssen Sie die Anmeldeinformationen für eine Anmeldung eingeben, die über die Schreibberechtigung für die MSXDBCDC-Datenbank verfügt, z.B. die Datenbankrolle **db_owner** zum Löschen der Oracle CDC-Instanz.</span><span class="sxs-lookup"><span data-stu-id="3aa66-104">In this dialog box you must enter the credentials for a login that has write permission to the MSXDBCDC database, such the **db_owner** database role to delete the Oracle CDC instance.</span></span>  
  
 <span data-ttu-id="3aa66-105">Geben Sie im Dialogfeld Verbindung mit SQL Server herstellen die folgenden Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="3aa66-105">Enter the following information in the Connect to SQL Server dialog box.</span></span>  
  
 <span data-ttu-id="3aa66-106">**Servername**</span><span class="sxs-lookup"><span data-stu-id="3aa66-106">**Server Name**</span></span>  
 <span data-ttu-id="3aa66-107">Geben Sie den Namen des Servers ein, auf dem sich [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] befindet.</span><span class="sxs-lookup"><span data-stu-id="3aa66-107">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
 <span data-ttu-id="3aa66-108">**Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="3aa66-108">**Authentication**</span></span>  
 <span data-ttu-id="3aa66-109">Wählen Sie eines der folgenden Szenarien aus:</span><span class="sxs-lookup"><span data-stu-id="3aa66-109">Select one of the following:</span></span>  
  
-   <span data-ttu-id="3aa66-110">**Windows-Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="3aa66-110">**Windows Authentication**</span></span>  
  
-   <span data-ttu-id="3aa66-111">**SQL Server-Authentifizierung**: Wenn Sie diese Option auswählen, müssen Sie den **Benutzernamen** und das **Kennwort** für den Benutzer von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eingeben, mit dem Sie eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="3aa66-111">**SQL Server Authentication**: If you select this option, you must type the **Login** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
 <span data-ttu-id="3aa66-112">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="3aa66-112">**Options**</span></span>  
 <span data-ttu-id="3aa66-113">Klicken Sie auf den Pfeil, um die verfügbaren Optionen anzuzeigen, die konfiguriert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3aa66-113">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="3aa66-114">Sie können für diese Optionen auch die Standardwerte unverändert lassen.</span><span class="sxs-lookup"><span data-stu-id="3aa66-114">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="3aa66-115">Verfügbare Optionen:</span><span class="sxs-lookup"><span data-stu-id="3aa66-115">The available options are:</span></span>  
  
-   <span data-ttu-id="3aa66-116">**Verbindungstimeout**: Geben Sie den Zeitraum (in Sekunden) ein, wie lange das Programm auf die Herstellung der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Verbindung warten soll, bevor ein Timeoutfehler eintritt.</span><span class="sxs-lookup"><span data-stu-id="3aa66-116">**Connection Timeout**: Type the time (in seconds) the program waits for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection to be established before producing a timeout error.</span></span> <span data-ttu-id="3aa66-117">Der Standardwert lautet **15**.</span><span class="sxs-lookup"><span data-stu-id="3aa66-117">The default value is **15**.</span></span>  
  
-   <span data-ttu-id="3aa66-118">**Ausführungstimeout**: Geben Sie den Zeitraum (in Sekunden) ein, wie lange das Programm auf die Beendigung der SQL-Befehlsausführung warten soll, bevor ein Timeoutfehler eintritt.</span><span class="sxs-lookup"><span data-stu-id="3aa66-118">**Execution Timeout**: Type the time (in seconds) that the program waits for SQL command execution to finish before producing a timeout error.</span></span> <span data-ttu-id="3aa66-119">Der Standardwert ist **30**.</span><span class="sxs-lookup"><span data-stu-id="3aa66-119">The default value is **30**.</span></span>  
  
-   <span data-ttu-id="3aa66-120">**Verbindung verschlüsseln**: Aktivieren Sie **Verbindung verschlüsseln** , um sicherzustellen, dass die hergestellte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Verbindung verschlüsselt wird, um Datenschutz zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="3aa66-120">**Encrypt Connection**: Select **Encrypt Connection** to ensure that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection that being established is encrypted to guarantee privacy.</span></span>  
  
-   <span data-ttu-id="3aa66-121">**Erweitert**: Klicken Sie auf **Erweitert** , und geben Sie ggf. zusätzliche Verbindungseigenschaften in das Dialogfeld „Erweiterte Verbindungseigenschaften“ ein.</span><span class="sxs-lookup"><span data-stu-id="3aa66-121">**Advanced**: Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aa66-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3aa66-122">See Also</span></span>  
 [<span data-ttu-id="3aa66-123">Für SQL Server-Verbindung erforderliche Berechtigungen für den CDC Service</span><span class="sxs-lookup"><span data-stu-id="3aa66-123">SQL Server Connection Required Permissions for the CDC Service</span></span>](sql-server-connection-required-permissions-for-the-cdc-service.md)  
  
  
