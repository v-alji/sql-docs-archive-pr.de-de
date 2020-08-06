---
title: SQL Server-Verbindung für die Instanzerstellung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 81d0e7e2-d8f0-4bd9-9565-218ce996f28e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cdff17b763257c2a3280981c1f5c16040cc61413
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610014"
---
# <a name="sql-server-connection-for-instance-creation"></a><span data-ttu-id="114d8-102">SQL Server-Verbindung für die Instanzerstellung</span><span class="sxs-lookup"><span data-stu-id="114d8-102">SQL Server Connection for Instance Creation</span></span>
  <span data-ttu-id="114d8-103">Einer der ersten Schritte beim Erstellen einer Oracle CDC-Instanz ist die Erstellung einer CDC-Datenbank auf der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Zielinstanz.</span><span class="sxs-lookup"><span data-stu-id="114d8-103">One of the first steps when creating an Oracle CDC Instance is the creation of a CDC database on the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="114d8-104">Diese CDC-Datenbank wird für SQL Server CDC aktiviert, und für diese Aktivierung ist eine Anmeldung durch einen Benutzer erforderlich, der Mitglied der festen Serverrolle `sysadmin` ist.</span><span class="sxs-lookup"><span data-stu-id="114d8-104">This CDC database is enabled for SQL Server CDC and this enablement requires a login that is a member of the `sysadmin` fixed-server role.</span></span>  
  
 <span data-ttu-id="114d8-105">Wenn ein Benutzer, der den Assistenten zum **Erstellen einer Oracle-CDC-Instanz** startet, kein Mitglied der festen Serverrolle `sysadmin` ist, wird das Dialogfeld **Verbindung mit SQL Server herstellen** geöffnet. Darin werden die Anmeldeinformationen für ein Mitglied der Rolle `sysadmin` angefordert, damit der Task zum Aktivieren der Datenbank für SQL Server CDC ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="114d8-105">When a user that starts the **Create an Oracle CDC Instance** wizard is not a member of the `sysadmin` fixed-server role, the **Connect to SQL Server** dialog box opens and requests the credentials for a member of the `sysadmin` role to carry out the Enable the database for SQL Server CDC task.</span></span> <span data-ttu-id="114d8-106">Wenn die CDC-Datenbank erstellt wird, wird die `sysadmin` -Anmeldung verworfen, und der Vorgang wird mit der ursprünglichen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung fortgesetzt, die beim Zugreifen auf die Oracle Designer Console verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="114d8-106">When the CDC database is created, the `sysadmin` login is discarded and work resumes with the original [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used when the Oracle Designer Console was entered.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="114d8-107">Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="114d8-107">Task List</span></span>  
 <span data-ttu-id="114d8-108">Geben Sie im Dialogfeld **Verbindung mit SQL Server herstellen** die folgenden Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="114d8-108">Enter the following information in the **Connect to SQL Server** dialog box.</span></span>  
  
 <span data-ttu-id="114d8-109">**Servername**</span><span class="sxs-lookup"><span data-stu-id="114d8-109">**Server Name**</span></span>  
 <span data-ttu-id="114d8-110">Geben Sie den Namen des Servers ein, auf dem sich [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] befindet.</span><span class="sxs-lookup"><span data-stu-id="114d8-110">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
 <span data-ttu-id="114d8-111">**Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="114d8-111">**Authentication**</span></span>  
 <span data-ttu-id="114d8-112">Wählen Sie eines der folgenden Szenarien aus:</span><span class="sxs-lookup"><span data-stu-id="114d8-112">Select one of the following:</span></span>  
  
-   <span data-ttu-id="114d8-113">**Windows-Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="114d8-113">**Windows Authentication**</span></span>  
  
-   <span data-ttu-id="114d8-114">**SQL Server-Authentifizierung**: Wenn Sie diese Option auswählen, müssen Sie den **Anmeldenamen** und das **Kennwort** für den Benutzer von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eingeben, mit dem Sie eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="114d8-114">**SQL Server Authentication**: If you select this option, you must type the **Login** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
 <span data-ttu-id="114d8-115">Der angemeldete Benutzer muss über eine Datenbankrolle verfügen, die den Zugriff auf die MSXCDCDB-Datenbank ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="114d8-115">The login must have a database role that allows access to the MSXCDCDB database.</span></span> <span data-ttu-id="114d8-116">Es wird empfohlen, dass der angemeldete Benutzer außerdem Zugriff auf weitere Datenbanken hat, die verwendet werden, da der Benutzer die Daten in diesen Datenbanken sonst nicht anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="114d8-116">It is recommended that the login also have access to any additional databases being used or the user will not be able to view the data in those databases.</span></span>  
  
 <span data-ttu-id="114d8-117">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="114d8-117">**Options**</span></span>  
 <span data-ttu-id="114d8-118">Klicken Sie auf den Pfeil, um die verfügbaren Optionen anzuzeigen, die konfiguriert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="114d8-118">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="114d8-119">Sie können für diese Optionen auch die Standardwerte unverändert lassen.</span><span class="sxs-lookup"><span data-stu-id="114d8-119">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="114d8-120">Verfügbare Optionen:</span><span class="sxs-lookup"><span data-stu-id="114d8-120">The available options are:</span></span>  
  
-   <span data-ttu-id="114d8-121">**Verbindungstimeout**: Geben Sie den Zeitraum (in Sekunden) ein, wie lange der CDC Service for Oracle auf eine Verbindung zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] warten soll, bevor ein Timeout eintritt. Der Standardwert lautet **15**.</span><span class="sxs-lookup"><span data-stu-id="114d8-121">**Connection Timeout**: Type the time (in seconds) that the CDC Service for Oracle waits for a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before timing out. The default value is **15**.</span></span>  
  
-   <span data-ttu-id="114d8-122">**Ausführungstimeout**: Geben Sie den Zeitraum (in Sekunden) ein, wie lange der Oracle CDC-Windows-Dienst auf die Ausführung eines Befehls wartet, bis ein Timeout eintritt. Der Standardwert ist **30**.</span><span class="sxs-lookup"><span data-stu-id="114d8-122">**Execution Timeout**: Type the time (in seconds) that the Oracle CDC Windows Service waits for a command to execute before timing out. The default value is **30**.</span></span>  
  
-   <span data-ttu-id="114d8-123">**Verbindung verschlüsseln**: Wählen Sie **Verbindung verschlüsseln** für die Kommunikation zwischen dem Oracle CDC Service und der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Zielinstanz aus, bei der eine verschlüsselte Verbindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="114d8-123">**Encrypt Connection**: Select **Encrypt Connection** for communication between the Oracle CDC Service and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance using an encrypted connection.</span></span>  
  
-   <span data-ttu-id="114d8-124">**Erweitert**: Klicken Sie auf **Erweitert** , und geben Sie ggf. zusätzliche Verbindungseigenschaften in das Dialogfeld „Erweiterte Verbindungseigenschaften“ ein.</span><span class="sxs-lookup"><span data-stu-id="114d8-124">**Advanced**: Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
     <span data-ttu-id="114d8-125">Weitere Informationen zum Dialogfeld „Erweiterte Verbindungseigenschaften“ finden Sie unter [Erweiterte Verbindungseigenschaften](advanced-connection-properties.md).</span><span class="sxs-lookup"><span data-stu-id="114d8-125">For information about the Advanced Connection Properties dialog box, see [Advanced Connection Properties](advanced-connection-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="114d8-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="114d8-126">See Also</span></span>  
 <span data-ttu-id="114d8-127">[Erstellen der SQL Server-Änderungsdatenbank](create-the-sql-server-change-database.md) </span><span class="sxs-lookup"><span data-stu-id="114d8-127">[Create the SQL Server Change Database](create-the-sql-server-change-database.md) </span></span>  
 [<span data-ttu-id="114d8-128">SQL Server-Verbindung erfordert Berechtigungen für den CDC Designer</span><span class="sxs-lookup"><span data-stu-id="114d8-128">SQL Server Connection Required Permissions for the CDC Designer</span></span>](sql-server-connection-required-permissions-for-the-cdc-designer.md)  
  
  
