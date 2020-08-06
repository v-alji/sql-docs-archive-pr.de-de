---
title: Task „T-SQL-Anweisung ausführen“ (Wartungsplan) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.tsql.f1
helpviewer_keywords:
- Execute T-SQL Statement Task dialog box
ms.assetid: fef3e259-0c47-4f6e-ade0-aee95e3d6c1a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 63738758ce228a51ab6c75eb11a681eec3b27352
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620355"
---
# <a name="execute-t-sql-statement-task-maintenance-plan"></a><span data-ttu-id="0d87c-102">Task 'T-SQL-Anweisung ausführen' (Wartungsplan)</span><span class="sxs-lookup"><span data-stu-id="0d87c-102">Execute T-SQL Statement Task (Maintenance Plan)</span></span>
  <span data-ttu-id="0d87c-103">Im Dialogfeld **Task 'T-SQL-Anweisung ausführen'** können Sie den Wartungsplan anpassen, indem Sie ihm [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0d87c-103">Use the **Execute T-SQL Statement Task** dialog to customize your maintenance plan by adding [!INCLUDE[tsql](../../includes/tsql-md.md)] statements of your choice to this maintenance plan.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0d87c-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="0d87c-104">Options</span></span>  
 <span data-ttu-id="0d87c-105">**Connection**</span><span class="sxs-lookup"><span data-stu-id="0d87c-105">**Connection**</span></span>  
 <span data-ttu-id="0d87c-106">Wählen Sie die Serververbindung aus, die bei der Ausführung dieses Tasks verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0d87c-106">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="0d87c-107">**Neu**</span><span class="sxs-lookup"><span data-stu-id="0d87c-107">**New**</span></span>  
 <span data-ttu-id="0d87c-108">Erstellen Sie eine neue Serververbindung, die bei der Ausführung dieses Tasks verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0d87c-108">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="0d87c-109">Das Dialogfeld **Neue Verbindung** wird im Folgenden beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0d87c-109">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="0d87c-110">**Ausführungstimeout**</span><span class="sxs-lookup"><span data-stu-id="0d87c-110">**Execution time out**</span></span>  
 <span data-ttu-id="0d87c-111">Zeit (in Sekunden), die bis zum Timeout (Beenden des Tasks) auf die Ausführung des Tasks gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="0d87c-111">Time (seconds) to wait for task completion before timing out (terminating task).</span></span>  
  
 <span data-ttu-id="0d87c-112">**T-SQL-Anweisung**</span><span class="sxs-lookup"><span data-stu-id="0d87c-112">**T-SQL statement**</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="0d87c-113">-Anweisungen zur Ausführung.</span><span class="sxs-lookup"><span data-stu-id="0d87c-113">statements to execute.</span></span>  
  
 <span data-ttu-id="0d87c-114">**T-SQL anzeigen**</span><span class="sxs-lookup"><span data-stu-id="0d87c-114">**View T-SQL**</span></span>  
 <span data-ttu-id="0d87c-115">Zeigt die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen an, die für diesen Task auf dem Server auf Basis der ausgewählten Optionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0d87c-115">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0d87c-116">Wenn die Anzahl der betroffenen Objekte groß ist, kann die Anzeige erhebliche Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="0d87c-116">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="0d87c-117">Neue Verbindung (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="0d87c-117">New Connection Dialog Box</span></span>  
 <span data-ttu-id="0d87c-118">**Verbindungsname**</span><span class="sxs-lookup"><span data-stu-id="0d87c-118">**Connection name**</span></span>  
 <span data-ttu-id="0d87c-119">Geben Sie einen Namen für die neue Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="0d87c-119">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="0d87c-120">**Wählen Sie einen Servernamen aus, oder geben Sie ihn ein.**</span><span class="sxs-lookup"><span data-stu-id="0d87c-120">**Select or enter a server name**</span></span>  
 <span data-ttu-id="0d87c-121">Wählen Sie den Server aus, zu dem bei der Ausführung dieses Tasks eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0d87c-121">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="0d87c-122">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="0d87c-122">**Refresh**</span></span>  
 <span data-ttu-id="0d87c-123">Mithilfe dieser Option aktualisieren Sie die Liste der verfügbaren Server.</span><span class="sxs-lookup"><span data-stu-id="0d87c-123">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="0d87c-124">**Geben Sie Informationen zum Anmelden am Server ein**</span><span class="sxs-lookup"><span data-stu-id="0d87c-124">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="0d87c-125">Legt fest, wie die Authentifizierung gegenüber dem Server stattfindet.</span><span class="sxs-lookup"><span data-stu-id="0d87c-125">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="0d87c-126">**Integrierte Sicherheit von Windows NT verwenden**</span><span class="sxs-lookup"><span data-stu-id="0d87c-126">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="0d87c-127">Stellt mithilfe der [!INCLUDE[msCoName](../../includes/msconame-md.md)]-Windows-Authentifizierung eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="0d87c-127">Connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="0d87c-128">**Bestimmten Benutzernamen und bestimmtes Kennwort verwenden**</span><span class="sxs-lookup"><span data-stu-id="0d87c-128">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="0d87c-129">Stellt mithilfe der [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] -Authentifizierung eine Verbindung zu einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="0d87c-129">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="0d87c-130">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0d87c-130">This option is not available.</span></span>  
  
 <span data-ttu-id="0d87c-131">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="0d87c-131">**User name**</span></span>  
 <span data-ttu-id="0d87c-132">Stellt eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung für den Gebrauch bei der Authentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="0d87c-132">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="0d87c-133">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0d87c-133">This option is not available.</span></span>  
  
 <span data-ttu-id="0d87c-134">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="0d87c-134">**Password**</span></span>  
 <span data-ttu-id="0d87c-135">Stellt ein Kennwort für den Gebrauch bei der Authentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="0d87c-135">Provide a password to use when authenticating.</span></span> <span data-ttu-id="0d87c-136">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0d87c-136">This option is not available.</span></span>  
  
  
