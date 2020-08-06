---
title: Berichtsserver-Eigenschaften (Registerkarte „Dienst“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 2a2e1dbf-02b9-4893-aaf0-c0e4a2c9b4f9
author: stevestein
ms.author: sstein
ms.openlocfilehash: a8d223234e5f53eb087650d0634eb09b520cd21e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619466"
---
# <a name="report-server-properties-service-tab"></a><span data-ttu-id="14dba-102">Berichtsserver-Eigenschaften (Registerkarte Dienst)</span><span class="sxs-lookup"><span data-stu-id="14dba-102">Report Server Properties (Service Tab)</span></span>
  <span data-ttu-id="14dba-103">Hierbei handelt es sich um den [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Berichtsserverdienst.</span><span class="sxs-lookup"><span data-stu-id="14dba-103">This service is the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Report Server service.</span></span> <span data-ttu-id="14dba-104">Die ausgegrauten Eigenschaftswerte können nicht mithilfe dieser Anwendung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="14dba-104">The property values in light gray cannot be changed by using this application.</span></span>  
  
## <a name="options"></a><span data-ttu-id="14dba-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="14dba-105">Options</span></span>  
 <span data-ttu-id="14dba-106">**Binärpfad**</span><span class="sxs-lookup"><span data-stu-id="14dba-106">**Binary Path**</span></span>  
 <span data-ttu-id="14dba-107">Zeigt den Speicherort der Programmdateien an, die von diesem Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="14dba-107">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="14dba-108">**Fehlersteuerung**</span><span class="sxs-lookup"><span data-stu-id="14dba-108">**Error Control**</span></span>  
 <span data-ttu-id="14dba-109">1 gibt "SERVICE_ERROR_NORMAL" an.</span><span class="sxs-lookup"><span data-stu-id="14dba-109">1 indicates "SERVICE_ERROR_NORMAL".</span></span> <span data-ttu-id="14dba-110">Wenn der Dienst nicht zusammen mit dem Computer gestartet werden kann, wird der Fehler vom Startprogramm protokolliert und eine Popupmeldung angezeigt, der Startvorgang aber fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="14dba-110">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="14dba-111">Dieser Wert kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="14dba-111">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="14dba-112">**Exitcode**</span><span class="sxs-lookup"><span data-stu-id="14dba-112">**Exit Code**</span></span>  
 <span data-ttu-id="14dba-113">Bei einem Fehler wird die dazu gehörende Nummer in diesem Feld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="14dba-113">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="14dba-114">Verwenden Sie diese Nummer für die Problembehandlung. Stellen Sie die Fehlernummer dem technischen Support zur Verfügung, oder durchsuchen Sie die [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="14dba-114">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="14dba-115">**HostName**</span><span class="sxs-lookup"><span data-stu-id="14dba-115">**Host Name**</span></span>  
 <span data-ttu-id="14dba-116">Zeigt den Namen des Computers oder Clusters an, auf dem die Volltextsuche ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="14dba-116">Displays the name of the computer or cluster running the full text search.</span></span>  
  
 <span data-ttu-id="14dba-117">**Name**</span><span class="sxs-lookup"><span data-stu-id="14dba-117">**Name**</span></span>  
 <span data-ttu-id="14dba-118">Zeigt den Anzeigenamen des Dienstes an.</span><span class="sxs-lookup"><span data-stu-id="14dba-118">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="14dba-119">**Prozess-ID**</span><span class="sxs-lookup"><span data-stu-id="14dba-119">**Process ID**</span></span>  
 <span data-ttu-id="14dba-120">Zeigt die Prozess-ID von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows an.</span><span class="sxs-lookup"><span data-stu-id="14dba-120">Displays the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows process ID.</span></span>  
  
 <span data-ttu-id="14dba-121">**SQL-Diensttyp**</span><span class="sxs-lookup"><span data-stu-id="14dba-121">**SQL Service Type**</span></span>  
 <span data-ttu-id="14dba-122">Der für aufrufende Prozesse bereitgestellte Diensttyp.</span><span class="sxs-lookup"><span data-stu-id="14dba-122">Type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="14dba-123">werden mehrere Dienste installiert.</span><span class="sxs-lookup"><span data-stu-id="14dba-123">installs several services.</span></span>  
  
 <span data-ttu-id="14dba-124">**Startmodus**</span><span class="sxs-lookup"><span data-stu-id="14dba-124">**Start Mode**</span></span>  
 <span data-ttu-id="14dba-125">Richten Sie den Dienst mit den folgenden Auswahlmöglichkeiten ein:</span><span class="sxs-lookup"><span data-stu-id="14dba-125">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="14dba-126">Manuell: Dieser Dienst wird nicht automatisch zusammen mit dem Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="14dba-126">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="14dba-127">Zum Starten des Dienstes verwenden Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager oder ein anderes Tool.</span><span class="sxs-lookup"><span data-stu-id="14dba-127">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="14dba-128">Automatisch: Dieser Dienst wird zusammen mit dem Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="14dba-128">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="14dba-129">Deaktiviert: Dieser Dienst kann nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="14dba-129">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="14dba-130">**State**</span><span class="sxs-lookup"><span data-stu-id="14dba-130">**State**</span></span>  
 <span data-ttu-id="14dba-131">Zeigt an, ob dieser Dienst ausgeführt wird, angehalten oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="14dba-131">Indicates whether this service is running, stopped, or disabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14dba-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="14dba-132">See Also</span></span>  
 [<span data-ttu-id="14dba-133">SQL Server-Dienste</span><span class="sxs-lookup"><span data-stu-id="14dba-133">SQL Server Services</span></span>](../../../2014/tools/configuration-manager/sql-server-services.md)  
  
  
