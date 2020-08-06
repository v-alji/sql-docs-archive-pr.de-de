---
title: Eigenschaften von Analysis-Servern (Registerkarte „Dienst“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 8dbe4bc5-6aa9-48ee-857e-0b4ea764b9cb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 91200120d87224c8e7733b0ff41ed423d3086c34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725190"
---
# <a name="analysis-server-properties-service-tab"></a><span data-ttu-id="ff041-102">Analysis-Server-Eigenschaften (Registerkarte Dienst)</span><span class="sxs-lookup"><span data-stu-id="ff041-102">Analysis Server Properties (Service Tab)</span></span>
  <span data-ttu-id="ff041-103">Hierbei handelt es sich um den [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Dienst.</span><span class="sxs-lookup"><span data-stu-id="ff041-103">This service is the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="ff041-104">Dieser Dienst ist für die ordnungsgemäße Ausführung von [!INCLUDE[ssAS](../../includes/ssas-md.md)] zwingend erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ff041-104">This service must be running for [!INCLUDE[ssAS](../../includes/ssas-md.md)] to work properly.</span></span> <span data-ttu-id="ff041-105">Die ausgegrauten Eigenschaftswerte können nicht mithilfe dieser Anwendung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ff041-105">The property values in light gray cannot be changed using this application.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ff041-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ff041-106">Options</span></span>  
 <span data-ttu-id="ff041-107">**Binärpfad**</span><span class="sxs-lookup"><span data-stu-id="ff041-107">**Binary Path**</span></span>  
 <span data-ttu-id="ff041-108">Zeigt den Speicherort der Programmdateien an, die von diesem Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ff041-108">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="ff041-109">**Fehlersteuerung**</span><span class="sxs-lookup"><span data-stu-id="ff041-109">**Error Control**</span></span>  
 <span data-ttu-id="ff041-110">1 steht für `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="ff041-110">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="ff041-111">Wenn der Dienst nicht zusammen mit dem Computer gestartet werden kann, wird der Fehler vom Startprogramm protokolliert und eine Popupmeldung angezeigt, der Startvorgang aber fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="ff041-111">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="ff041-112">Dieser Wert kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ff041-112">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="ff041-113">**Exitcode**</span><span class="sxs-lookup"><span data-stu-id="ff041-113">**Exit Code**</span></span>  
 <span data-ttu-id="ff041-114">Bei einem Fehler wird die dazu gehörende Nummer in diesem Feld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff041-114">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="ff041-115">Verwenden Sie diese Nummer für die Problembehandlung. Stellen Sie die Fehlernummer dem technischen Support zur Verfügung, oder durchsuchen Sie die [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="ff041-115">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="ff041-116">**HostName**</span><span class="sxs-lookup"><span data-stu-id="ff041-116">**Host Name**</span></span>  
 <span data-ttu-id="ff041-117">Zeigt den Namen des Computers oder Clusters an, auf dem [!INCLUDE[ssAS](../../includes/ssas-md.md)]ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ff041-117">Displays the name of the computer or cluster running [!INCLUDE[ssAS](../../includes/ssas-md.md)].</span></span>  
  
 <span data-ttu-id="ff041-118">**Name**</span><span class="sxs-lookup"><span data-stu-id="ff041-118">**Name**</span></span>  
 <span data-ttu-id="ff041-119">Zeigt den Anzeigenamen des Dienstes an.</span><span class="sxs-lookup"><span data-stu-id="ff041-119">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="ff041-120">**Prozess-ID**</span><span class="sxs-lookup"><span data-stu-id="ff041-120">**Process ID**</span></span>  
 <span data-ttu-id="ff041-121">Zeigt die Nummer an, die von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows zum Nachverfolgen der Prozesse dieses Programms verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ff041-121">Displays the number used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows to keep track of this program's processes.</span></span>  
  
 <span data-ttu-id="ff041-122">**SQL-Diensttyp**</span><span class="sxs-lookup"><span data-stu-id="ff041-122">**SQL Service Type**</span></span>  
 <span data-ttu-id="ff041-123">Zeigt den für aufrufende Prozesse bereitgestellten Diensttyp an.</span><span class="sxs-lookup"><span data-stu-id="ff041-123">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="ff041-124">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installiert mehrere Dienste.</span><span class="sxs-lookup"><span data-stu-id="ff041-124">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installs several services.</span></span>  
  
 <span data-ttu-id="ff041-125">**Startmodus**</span><span class="sxs-lookup"><span data-stu-id="ff041-125">**Start Mode**</span></span>  
 <span data-ttu-id="ff041-126">Richten Sie den Dienst mit den folgenden Auswahlmöglichkeiten ein:</span><span class="sxs-lookup"><span data-stu-id="ff041-126">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="ff041-127">Manuell: Dieser Dienst wird nicht automatisch zusammen mit dem Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="ff041-127">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="ff041-128">Zum Starten des Dienstes verwenden Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager oder ein anderes Tool.</span><span class="sxs-lookup"><span data-stu-id="ff041-128">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="ff041-129">Automatisch: Dieser Dienst wird zusammen mit dem Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="ff041-129">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="ff041-130">Deaktiviert: Dieser Dienst kann nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="ff041-130">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="ff041-131">**State**</span><span class="sxs-lookup"><span data-stu-id="ff041-131">**State**</span></span>  
 <span data-ttu-id="ff041-132">Zeigt an, ob dieser Dienst ausgeführt wird, angehalten oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ff041-132">Indicates whether this service is running, stopped, or disabled.</span></span>  
  
  
