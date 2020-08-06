---
title: Zugreifen auf die CDC Designer Console | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- accMsDes
ms.assetid: b168c64e-c1b5-42d4-a92a-84de1dd0324e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f4f6e4df0a514cb29e36bcd1270b2537dc3ba68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724881"
---
# <a name="access-the-cdc-designer-console"></a><span data-ttu-id="186c6-102">Zugreifen auf die CDC Designer Console</span><span class="sxs-lookup"><span data-stu-id="186c6-102">Access the CDC Designer Console</span></span>
  <span data-ttu-id="186c6-103">Sie können auf die CDC Designer Console über den Computer zugreifen, auf dem Sie die Konsole installiert haben.</span><span class="sxs-lookup"><span data-stu-id="186c6-103">You can access the CDC Designer Console from the computer where you installed the console.</span></span> <span data-ttu-id="186c6-104">Weitere Informationen zur Installation finden Sie unter Installation.</span><span class="sxs-lookup"><span data-stu-id="186c6-104">For more information about installation, see Installation.</span></span>  
  
 <span data-ttu-id="186c6-105">Wenn Sie die CDC Designer Console öffnen, wird das Dialogfeld Verbindung mit SQL Server herstellen geöffnet.</span><span class="sxs-lookup"><span data-stu-id="186c6-105">When you open the CDC Designer Console, the Connect to SQL Server dialog box opens.</span></span>  
  
 <span data-ttu-id="186c6-106">Die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung, mit der auf den CDC Designer zugegriffen wird, muss über UPDATE-Berechtigungen für die MSXDBCDC-Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="186c6-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login that accesses the CDC Designer must have UPDATE permissions on the MSXDBCDC database.</span></span> <span data-ttu-id="186c6-107">Außerdem muss die Anmeldung auch über die feste Serverrolle `dbcreator` verfügen, um neue Oracle CDC-Instanzen erstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="186c6-107">In addition, the login must also have the `dbcreator` fixed-server role to create new Oracle CDC Instances.</span></span> <span data-ttu-id="186c6-108">Es wird empfohlen, dass die Anmeldung auch über den SELECT-Zugriff auf die verwendeten CDC-Datenbanken verfügt. Andernfalls kann der Benutzer den Status dieser Datenbanken nicht anzeigen.</span><span class="sxs-lookup"><span data-stu-id="186c6-108">It is recommended that the login also have SELECT access to the CDC databases being used or the user will not be able to view the state of those databases.</span></span>  
  
 <span data-ttu-id="186c6-109">Geben Sie im Dialogfeld Verbindung mit SQL Server herstellen die folgenden Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="186c6-109">Enter the following information in the Connect to SQL Server dialog box.</span></span>  
  
### <a name="server-name"></a><span data-ttu-id="186c6-110">Servername</span><span class="sxs-lookup"><span data-stu-id="186c6-110">Server Name</span></span>  
 <span data-ttu-id="186c6-111">Geben Sie den Namen des Servers ein, auf dem sich [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] befindet.</span><span class="sxs-lookup"><span data-stu-id="186c6-111">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
### <a name="authentication"></a><span data-ttu-id="186c6-112">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="186c6-112">Authentication</span></span>  
 <span data-ttu-id="186c6-113">Wählen Sie eines der folgenden Szenarien aus:</span><span class="sxs-lookup"><span data-stu-id="186c6-113">Select one of the following:</span></span>  
  
-   <span data-ttu-id="186c6-114">**Windows-Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="186c6-114">**Windows Authentication**</span></span>  
  
-   <span data-ttu-id="186c6-115">**SQL Server-Authentifizierung**: Wenn Sie diese Option auswählen, müssen Sie den **Anmeldenamen** und das **Kennwort** für den Benutzer von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eingeben, mit dem Sie eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="186c6-115">**SQL Server Authentication**: If you select this option, you must type the **Login** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
 <span data-ttu-id="186c6-116">Der angemeldete Benutzer muss über eine Datenbankrolle verfügen, die den Zugriff auf die MSXCDCDB-Datenbank ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="186c6-116">The login must have a database role that allows access to the MSXCDCDB database.</span></span> <span data-ttu-id="186c6-117">Es wird empfohlen, dass der angemeldete Benutzer außerdem Zugriff auf weitere Datenbanken hat, die verwendet werden, da der Benutzer die Daten in diesen Datenbanken sonst nicht anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="186c6-117">It is recommended that the login also have access to any additional databases being used or the user will not be able to view the data in those databases.</span></span>  
  
### <a name="options"></a><span data-ttu-id="186c6-118">Tastatur</span><span class="sxs-lookup"><span data-stu-id="186c6-118">Options</span></span>  
 <span data-ttu-id="186c6-119">Klicken Sie auf den Pfeil, um die verfügbaren Optionen anzuzeigen, die konfiguriert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="186c6-119">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="186c6-120">Sie können für diese Optionen auch die Standardwerte unverändert lassen.</span><span class="sxs-lookup"><span data-stu-id="186c6-120">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="186c6-121">Verfügbare Optionen:</span><span class="sxs-lookup"><span data-stu-id="186c6-121">The available options are:</span></span>  
  
 <span data-ttu-id="186c6-122">**Verbindungstimeout**</span><span class="sxs-lookup"><span data-stu-id="186c6-122">**Connection Timeout**</span></span>  
 <span data-ttu-id="186c6-123">Geben Sie den Zeitraum (in Sekunden) ein, wie lange der CDC Service for Oracle auf eine Verbindung zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] warten soll, bevor ein Timeout eintritt. Der Standardwert lautet **15**.</span><span class="sxs-lookup"><span data-stu-id="186c6-123">Type the time (in seconds) that the CDC Service for Oracle waits for a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before timing out. The default value is **15**.</span></span>  
  
 <span data-ttu-id="186c6-124">**Ausführungstimeout**</span><span class="sxs-lookup"><span data-stu-id="186c6-124">**Execution Timeout**</span></span>  
 <span data-ttu-id="186c6-125">Geben Sie den Zeitraum (in Sekunden) ein, wie lange der Oracle CDC-Windows-Dienst auf die Ausführung eines Befehls wartet, bis ein Timeout eintritt. Der Standardwert ist **30**.</span><span class="sxs-lookup"><span data-stu-id="186c6-125">Type the time (in seconds) that the Oracle CDC Windows Service waits for a command to execute before timing out. The default value is **30**.</span></span>  
  
 <span data-ttu-id="186c6-126">**Verbindung verschlüsseln**</span><span class="sxs-lookup"><span data-stu-id="186c6-126">**Encrypt Connection**</span></span>  
 <span data-ttu-id="186c6-127">Wählen Sie **Verbindung verschlüsseln** für die Kommunikation zwischen dem Oracle CDC Service und der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Zielinstanz aus, bei der eine verschlüsselte Verbindung verwendet werden soll. **Erweitert**: Klicken Sie auf **Erweitert** , und geben Sie ggf. zusätzliche Verbindungseigenschaften in das Dialogfeld „Erweiterte Verbindungseigenschaften“ ein.</span><span class="sxs-lookup"><span data-stu-id="186c6-127">Select **Encrypt Connection** for communication between the Oracle CDC Service and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance using an encrypted connection.**Advanced**: Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
 <span data-ttu-id="186c6-128">**Erweitert**</span><span class="sxs-lookup"><span data-stu-id="186c6-128">**Advanced**</span></span>  
 <span data-ttu-id="186c6-129">Klicken Sie auf **Erweitert** , und geben Sie ggf. zusätzliche Verbindungseigenschaften in das Dialogfeld „Erweiterte Verbindungseigenschaften“ ein.</span><span class="sxs-lookup"><span data-stu-id="186c6-129">Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
 <span data-ttu-id="186c6-130">Weitere Informationen zum Dialogfeld „Erweiterte Verbindungseigenschaften“ finden Sie unter [Erweiterte Verbindungseigenschaften](advanced-connection-properties.md).</span><span class="sxs-lookup"><span data-stu-id="186c6-130">For information about the Advanced Connection Properties dialog box, see [Advanced Connection Properties](advanced-connection-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="186c6-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="186c6-131">See Also</span></span>  
 [<span data-ttu-id="186c6-132">SQL Server-Verbindung erfordert Berechtigungen für den CDC Designer</span><span class="sxs-lookup"><span data-stu-id="186c6-132">SQL Server Connection Required Permissions for the CDC Designer</span></span>](sql-server-connection-required-permissions-for-the-cdc-designer.md)  
  
  
