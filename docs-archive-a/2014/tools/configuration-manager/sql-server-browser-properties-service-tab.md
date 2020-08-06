---
title: Eigenschaften von SQL Server-Browser (Registerkarte „Dienst“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 98ace9b0-72d5-4b72-9b7b-11fbc490981a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 200e45648b94e26c5e808e9a817cfe01866e6a65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608997"
---
# <a name="sql-server-browser-properties-service-tab"></a><span data-ttu-id="7fb6d-102">Eigenschaften von SQL Server-Browser (Registerkarte Dienst)</span><span class="sxs-lookup"><span data-stu-id="7fb6d-102">SQL Server Browser Properties (Service Tab)</span></span>
  <span data-ttu-id="7fb6d-103">Das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browser-Programm wird als Dienst auf dem Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7fb6d-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser program runs as a service on the server.</span></span> <span data-ttu-id="7fb6d-104">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Browser lauscht auf eingehende Anforderungen für [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Ressourcen und stellt Informationen zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanzen zur Verfügung, die auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="7fb6d-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser listens for incoming requests for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
 <span data-ttu-id="7fb6d-105">Verwenden Sie im Dialogfeld **Eigenschaften von SQL Server-Browser** die Registerkarte **Dienst** , um die folgenden Optionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7fb6d-105">Use the **Service** tab on the **SQL Server Browser Properties** dialog box to view the following options.</span></span> <span data-ttu-id="7fb6d-106">Alle Eigenschaften außer **Startmodus** sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="7fb6d-106">All properties except **Start Mode** are read-only.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7fb6d-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="7fb6d-107">Options</span></span>  
 <span data-ttu-id="7fb6d-108">**Binärpfad**</span><span class="sxs-lookup"><span data-stu-id="7fb6d-108">**Binary Path**</span></span>  
 <span data-ttu-id="7fb6d-109">Zeigt den Speicherort der Programmdateien an, die von diesem Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7fb6d-109">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="7fb6d-110">**Fehlersteuerung**</span><span class="sxs-lookup"><span data-stu-id="7fb6d-110">**Error Control**</span></span>  
 <span data-ttu-id="7fb6d-111">1 steht für `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="7fb6d-111">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="7fb6d-112">Wenn der Dienst nicht zusammen mit dem Computer gestartet werden kann, wird der Fehler vom Startprogramm protokolliert und eine Popupmeldung angezeigt, der Startvorgang aber fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="7fb6d-112">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="7fb6d-113">Dieser Wert kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="7fb6d-113">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="7fb6d-114">**Exitcode**</span><span class="sxs-lookup"><span data-stu-id="7fb6d-114">**Exit Code**</span></span>  
 <span data-ttu-id="7fb6d-115">Bei einem Fehler wird die dazu gehörende Nummer in diesem Feld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7fb6d-115">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="7fb6d-116">Verwenden Sie diese Nummer für die Problembehandlung. Stellen Sie die Fehlernummer dem technischen Support zur Verfügung, oder durchsuchen Sie die [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="7fb6d-116">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="7fb6d-117">**HostName**</span><span class="sxs-lookup"><span data-stu-id="7fb6d-117">**Host Name**</span></span>  
 <span data-ttu-id="7fb6d-118">Zeigt den Namen des Computers oder Clusters an, auf dem der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browser-Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7fb6d-118">Displays the name of the computer or cluster running the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="7fb6d-119">**Name**</span><span class="sxs-lookup"><span data-stu-id="7fb6d-119">**Name**</span></span>  
 <span data-ttu-id="7fb6d-120">Zeigt den Anzeigenamen des Dienstes an.</span><span class="sxs-lookup"><span data-stu-id="7fb6d-120">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="7fb6d-121">**Prozess-ID**</span><span class="sxs-lookup"><span data-stu-id="7fb6d-121">**Process ID**</span></span>  
 <span data-ttu-id="7fb6d-122">Zeigt die Prozess-ID von Windows an.</span><span class="sxs-lookup"><span data-stu-id="7fb6d-122">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="7fb6d-123">**Diensttyp**</span><span class="sxs-lookup"><span data-stu-id="7fb6d-123">**Service Type**</span></span>  
 <span data-ttu-id="7fb6d-124">Zeigt den für aufrufende Prozesse bereitgestellten Diensttyp an.</span><span class="sxs-lookup"><span data-stu-id="7fb6d-124">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7fb6d-125">werden mehrere Dienste installiert.</span><span class="sxs-lookup"><span data-stu-id="7fb6d-125">installs several services.</span></span>  
  
 <span data-ttu-id="7fb6d-126">**Startmodus**</span><span class="sxs-lookup"><span data-stu-id="7fb6d-126">**Start Mode**</span></span>  
 <span data-ttu-id="7fb6d-127">Richten Sie den Dienst mit den folgenden Auswahlmöglichkeiten ein:</span><span class="sxs-lookup"><span data-stu-id="7fb6d-127">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="7fb6d-128">Manuell: Dieser Dienst wird nicht automatisch zusammen mit dem Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="7fb6d-128">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="7fb6d-129">Zum Starten des Dienstes verwenden Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager oder ein anderes Tool.</span><span class="sxs-lookup"><span data-stu-id="7fb6d-129">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="7fb6d-130">Automatisch: Dieser Dienst wird zusammen mit dem Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="7fb6d-130">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="7fb6d-131">Deaktiviert: Dieser Dienst kann nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="7fb6d-131">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="7fb6d-132">**State**</span><span class="sxs-lookup"><span data-stu-id="7fb6d-132">**State**</span></span>  
 <span data-ttu-id="7fb6d-133">Zeigt an, ob dieser Dienst ausgeführt wird, angehalten oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="7fb6d-133">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="7fb6d-134">„ **…** “ gibt einen ausstehenden Statuswechsel an.</span><span class="sxs-lookup"><span data-stu-id="7fb6d-134">"**...**" indicates a state change is pending.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fb6d-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7fb6d-135">See Also</span></span>  
 [<span data-ttu-id="7fb6d-136">SQL Server-Browserdienst</span><span class="sxs-lookup"><span data-stu-id="7fb6d-136">SQL Server Browser Service</span></span>](../../../2014/tools/configuration-manager/sql-server-browser-service.md)  
  
  
