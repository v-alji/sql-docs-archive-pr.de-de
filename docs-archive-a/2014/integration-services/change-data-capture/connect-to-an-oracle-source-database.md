---
title: Herstellen einer Verbindung mit einer Oracle-Quelldatenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- oraDb
ms.assetid: 220cf555-0db2-443c-8f87-8e413f3ca731
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fccba3d11adc67b3f5ef4f8648ec5d0de07a5648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720317"
---
# <a name="connect-to-an-oracle-source-database"></a><span data-ttu-id="4415c-102">Herstellen einer Verbindung zu einer Oracle-Quelldatenbank</span><span class="sxs-lookup"><span data-stu-id="4415c-102">Connect to an Oracle Source Database</span></span>
  <span data-ttu-id="4415c-103">Verwenden Sie die Seite der Oracle-Quelle zum Eingeben der Informationen, die zum Herstellen einer Verbindung mit der Oracle-Quelldatenbank erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4415c-103">Use the Oracle Source page to provide the information necessary to connect to the Oracle source database.</span></span> <span data-ttu-id="4415c-104">Die CDC-Instanz liest die Wiederholungsprotokolle (Redo Logs) der Oracle-Datenbank, mit der Sie verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="4415c-104">The CDC instance will read the redo logs of the Oracle database you are connected to.</span></span>  
  
 <span data-ttu-id="4415c-105">**Oracle Connect String**</span><span class="sxs-lookup"><span data-stu-id="4415c-105">**Oracle Connect String**</span></span>  
 <span data-ttu-id="4415c-106">Geben Sie die Oracle-Verbindungszeichenfolge zum Computer mit der verwendeten Oracle-Datenbank ein.</span><span class="sxs-lookup"><span data-stu-id="4415c-106">Enter the Oracle connect string to the computer with the Oracle database you are using.</span></span> <span data-ttu-id="4415c-107">Zum Schreiben der Verbindungszeichenfolge wird eine der folgenden Methoden verwendet:</span><span class="sxs-lookup"><span data-stu-id="4415c-107">The connect string is written in one of the following ways:</span></span>  
  
 `host[:port][/service name]`  
  
 <span data-ttu-id="4415c-108">In der Verbindungszeichenfolge kann auch ein Oracle Net-Verbindungsdeskriptor angegeben werden, z. B. `(DESCRIPTION=(ADDRESS=(PROTOCOL=tcp) (HOST=erp.contoso.com) (PORT=1521)) (CONNECT_DATA=(SERVICE_NAME=orcl)))`</span><span class="sxs-lookup"><span data-stu-id="4415c-108">The connection string can also specify an Oracle Net connect descriptor, for example, `(DESCRIPTION=(ADDRESS=(PROTOCOL=tcp) (HOST=erp.contoso.com) (PORT=1521)) (CONNECT_DATA=(SERVICE_NAME=orcl)))`</span></span>  
  
 <span data-ttu-id="4415c-109">Wenn Sie einen Verzeichnisserver oder tnsnames verwenden, kann die Verbindungszeichenfolge der Name der Verbindung sein.</span><span class="sxs-lookup"><span data-stu-id="4415c-109">If using a directory server or tnsnames, the connect string can be the name of the connection.</span></span>  
  
 <span data-ttu-id="4415c-110">**Oracle Log Mining Authentication**</span><span class="sxs-lookup"><span data-stu-id="4415c-110">**Oracle Log Mining Authentication**</span></span>  
 <span data-ttu-id="4415c-111">Um die Anmeldeinformationen für den Oracle-Datenbankbenutzer einzugeben, der für das Log Mining autorisiert ist, wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="4415c-111">To enter the credentials for the Oracle database user that is authorized for log mining, select one of the following:</span></span>  
  
-   <span data-ttu-id="4415c-112">**Windows-Authentifizierung**: Wählen Sie diese Option, um die aktuellen Anmeldeinformationen für die Windows-Domäne zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4415c-112">**Windows Authentication**: Select this to use the current Windows domain credentials.</span></span> <span data-ttu-id="4415c-113">Sie können diese Option nur verwenden, wenn die Oracle-Datenbank für die Nutzung der Windows-Authentifizierung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="4415c-113">You can use this option only if the Oracle database is configured to work with Windows authentication.</span></span>  
  
-   <span data-ttu-id="4415c-114">**Oracle Authentication**: Wenn Sie diese Option aktivieren, müssen Sie **Benutzername** und **Kennwort** für den Benutzer der Oracle-Datenbank eingeben, mit der Sie eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="4415c-114">**Oracle Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the Oracle database you are connecting to.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4415c-115">Einem Benutzer müssen in der Oracle-Datenbank die folgenden Berechtigungen gewährt werden, um als Log Mining-Benutzer fungieren zu können.</span><span class="sxs-lookup"><span data-stu-id="4415c-115">A user must have the following privileges granted in the Oracle database to be a log-mining user.</span></span>  
> 
>  -   <span data-ttu-id="4415c-116">SELECT on \<any-captured-table></span><span class="sxs-lookup"><span data-stu-id="4415c-116">SELECT on \<any-captured-table></span></span>  
> -   <span data-ttu-id="4415c-117">SELECT ANY TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="4415c-117">SELECT ANY TRANSACTION</span></span>  
> -   <span data-ttu-id="4415c-118">EXECUTE on DBMS LOGMNR</span><span class="sxs-lookup"><span data-stu-id="4415c-118">EXECUTE on DBMS LOGMNR</span></span>  
> -   <span data-ttu-id="4415c-119">SELECT on V$LOGMNR CONTENTS</span><span class="sxs-lookup"><span data-stu-id="4415c-119">SELECT on V$LOGMNR CONTENTS</span></span>  
> -   <span data-ttu-id="4415c-120">SELECT on V$ARCHIVED LOG</span><span class="sxs-lookup"><span data-stu-id="4415c-120">SELECT on V$ARCHIVED LOG</span></span>  
> -   <span data-ttu-id="4415c-121">SELECT on V$LOG</span><span class="sxs-lookup"><span data-stu-id="4415c-121">SELECT on V$LOG</span></span>  
> -   <span data-ttu-id="4415c-122">SELECT on V$LOGFILE</span><span class="sxs-lookup"><span data-stu-id="4415c-122">SELECT on V$LOGFILE</span></span>  
> -   <span data-ttu-id="4415c-123">SELECT on V$DATABASE</span><span class="sxs-lookup"><span data-stu-id="4415c-123">SELECT on V$DATABASE</span></span>  
> -   <span data-ttu-id="4415c-124">SELECT on V$THREAD</span><span class="sxs-lookup"><span data-stu-id="4415c-124">SELECT on V$THREAD</span></span>  
> -   <span data-ttu-id="4415c-125">SELECT on ALL INDEXES</span><span class="sxs-lookup"><span data-stu-id="4415c-125">SELECT on ALL INDEXES</span></span>  
> -   <span data-ttu-id="4415c-126">SELECT on ALL OBJECTS</span><span class="sxs-lookup"><span data-stu-id="4415c-126">SELECT on ALL OBJECTS</span></span>  
> -   <span data-ttu-id="4415c-127">SELECT on DBA OBJECTS</span><span class="sxs-lookup"><span data-stu-id="4415c-127">SELECT on DBA OBJECTS</span></span>  
> -   <span data-ttu-id="4415c-128">SELECT on ALL TABLES</span><span class="sxs-lookup"><span data-stu-id="4415c-128">SELECT on ALL TABLES</span></span>  
> 
>  <span data-ttu-id="4415c-129">Falls eine dieser Berechtigungen nicht für V$xxx gewährt werden kann, können Sie diese V_S$xxx gewähren.</span><span class="sxs-lookup"><span data-stu-id="4415c-129">If any of these privileges cannot be granted to a V$xxx, then grant them to the V_S$xxx.</span></span>  
  
 <span data-ttu-id="4415c-130">**Verbindung testen**</span><span class="sxs-lookup"><span data-stu-id="4415c-130">**Test Connection**</span></span>  
 <span data-ttu-id="4415c-131">Klicken Sie auf **Verbindung testen** , um zu ermitteln, ob Sie eine Verbindung mit dem Remotecomputer hergestellt haben, der über die Oracle-Datenbank verfügt.</span><span class="sxs-lookup"><span data-stu-id="4415c-131">Click **Test Connection** to determine whether you established a connection with the remote computer that has the Oracle database.</span></span> <span data-ttu-id="4415c-132">Ein Dialogfeld wird geöffnet, in dem Sie informiert werden, ob die Verbindungsherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="4415c-132">A dialog box opens to inform you whether the connection was successful.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4415c-133">Aufgrund eines bekannten Problems kann beim Herstellen der Verbindung zur Oracle-Quelldatenbank ein Fehler auftreten, wenn der CDC Designer nicht als Administrator ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4415c-133">Due to a known issue connection to the Oracle source database may fail if the CDC Designer is not run as an administrator.</span></span> <span data-ttu-id="4415c-134">Falls bei der Verbindungsherstellung ein Fehler auftritt, schließen Sie den CDC Designer, und starten Sie die Anwendung unter Verwendung der Option **Als Administrator ausführen** neu.</span><span class="sxs-lookup"><span data-stu-id="4415c-134">If connection fails, close and restart the CDC Designer using the **Run as administrator** option.</span></span>  
  
 <span data-ttu-id="4415c-135">Klicken Sie **Weiter** , wenn Sie alle Informationen auf dieser Seite eingegeben haben, um den Schritt [Select Oracle Tables and Columns](select-oracle-tables-and-columns.md)auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4415c-135">After you finish entering information on this page, click **Next** to [Select Oracle Tables and Columns](select-oracle-tables-and-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4415c-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4415c-136">See Also</span></span>  
 <span data-ttu-id="4415c-137">[Erstellen der Instanz für die SQL Server-Änderungsdatenbank](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="4415c-137">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="4415c-138">Bearbeiten von Instanzeigenschaften</span><span class="sxs-lookup"><span data-stu-id="4415c-138">Edit Instance Properties</span></span>](edit-instance-properties.md)  
  
  
