---
title: Oracle-Anmeldeinformationen zum Ausführen von Skripts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4a301cb0-2f5b-41ba-81bf-46b41d07f137
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 683b313e5b1065c3709c4637ddf968641612cc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695942"
---
# <a name="oracle-credentials-for-running-script"></a><span data-ttu-id="049d2-102">Oracle Credentials for Running Script</span><span class="sxs-lookup"><span data-stu-id="049d2-102">Oracle Credentials for Running Script</span></span>
  <span data-ttu-id="049d2-103">Um das ergänzende Oracle-Protokollierungsskript in der Oracle CDC Designer Console auszuführen, werden Sie vom Programm zum Angeben der Anmeldeinformationen des Oracle-Benutzers aufgefordert, der das Skript ausführt.</span><span class="sxs-lookup"><span data-stu-id="049d2-103">To run the Oracle supplemental logging script from the Oracle CDC Designer console, the program prompts you for the credentials of the Oracle user who is running the script.</span></span> <span data-ttu-id="049d2-104">Zum Ausführen dieses Skripts muss der Oracle-Benutzer über die ALTER TABLE-Berechtigung für alle zu erfassenden Tabellen und die SELECT-Berechtigung für die DBA_LOG_GROUPS-Sicht verfügen.</span><span class="sxs-lookup"><span data-stu-id="049d2-104">To run this script, the Oracle user must have ALTER TABLE permission for all the tables to be captured and SELECT permission on the DBA_LOG_GROUPS view.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="049d2-105">Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="049d2-105">Task List</span></span>  
 <span data-ttu-id="049d2-106">Geben Sie in diesem Dialogfeld Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="049d2-106">Enter the following in this dialog box:</span></span>  
  
 <span data-ttu-id="049d2-107">**Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="049d2-107">**Authentication**</span></span>  
  
 <span data-ttu-id="049d2-108">Wählen Sie eines der folgenden Szenarien aus:</span><span class="sxs-lookup"><span data-stu-id="049d2-108">Select one of the following:</span></span>  
  
-   <span data-ttu-id="049d2-109">**Windows-Authentifizierung**: Wählen Sie diese Option, um die aktuellen Anmeldeinformationen für die Windows-Domäne zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="049d2-109">**Windows Authentication**: Select this to use the current Windows domain credentials.</span></span> <span data-ttu-id="049d2-110">Sie können diese Option nur verwenden, wenn die Oracle-Datenbank für die Nutzung der Windows-Authentifizierung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="049d2-110">You can use this option only if the Oracle database is configured to work with Windows authentication.</span></span>  
  
-   <span data-ttu-id="049d2-111">**Oracle Authentication**: Wenn Sie diese Option aktivieren, müssen Sie **Benutzername** und **Kennwort** für den Benutzer der Oracle-Quelldatenbank eingeben, mit der Sie eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="049d2-111">**Oracle Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the Source Oracle database you are connecting to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="049d2-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="049d2-112">See Also</span></span>  
 <span data-ttu-id="049d2-113">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="049d2-113">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="049d2-114">Überprüfen und Generieren ergänzender Protokollierungsskripts</span><span class="sxs-lookup"><span data-stu-id="049d2-114">Review and Generate Supplemental Logging Scripts</span></span>](review-and-generate-supplemental-logging-scripts.md)  
  
  
