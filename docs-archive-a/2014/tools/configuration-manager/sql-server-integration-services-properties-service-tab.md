---
title: Eigenschaften von SQL Server Integration Services (Registerkarte „Dienst“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 37f0acd9-c96f-48fd-9b53-2ca0097af242
author: stevestein
ms.author: sstein
ms.openlocfilehash: a752bdeab3c99ac97445e3281d3165a2d8f79866
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621756"
---
# <a name="sql-server-integration-services-properties-service-tab"></a><span data-ttu-id="ba055-102">Eigenschaften von SQL Server Integration Services (Registerkarte Dienst)</span><span class="sxs-lookup"><span data-stu-id="ba055-102">SQL Server Integration Services Properties (Service Tab)</span></span>
  <span data-ttu-id="ba055-103">Verwenden Sie die Registerkarte **Dienst** im Dialogfeld [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]Eigenschaften**in**, um die folgenden Optionen anzuzeigen oder anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ba055-103">Use the **Service**tab on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] **Properties** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ba055-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ba055-104">Options</span></span>  
 <span data-ttu-id="ba055-105">**Binärpfad**</span><span class="sxs-lookup"><span data-stu-id="ba055-105">**Binary Path**</span></span>  
 <span data-ttu-id="ba055-106">Zeigt den Speicherort der Programmdateien an, die von diesem Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ba055-106">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="ba055-107">**Fehlersteuerung**</span><span class="sxs-lookup"><span data-stu-id="ba055-107">**Error Control**</span></span>  
 <span data-ttu-id="ba055-108">1 steht für `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="ba055-108">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="ba055-109">Wenn der Dienst nicht zusammen mit dem Computer gestartet werden kann, wird der Fehler vom Startprogramm protokolliert und eine Popupmeldung angezeigt, der Startvorgang aber fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="ba055-109">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="ba055-110">Dieser Wert kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ba055-110">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="ba055-111">**Exitcode**</span><span class="sxs-lookup"><span data-stu-id="ba055-111">**Exit Code**</span></span>  
 <span data-ttu-id="ba055-112">Der [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Fehlercode, der alle Probleme definiert, die beim Starten oder Beenden des Dienstes aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="ba055-112">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows error code defining any problems encountered in starting or stopping the service.</span></span> <span data-ttu-id="ba055-113">Diese Eigenschaft wird auf **ERROR_SERVICE_SPECIFIC_ERROR** (1066) festgelegt, wenn der Fehler in Bezug auf den Dienst eindeutig ist, der durch diese Klasse repräsentiert wird, und Informationen zu dem Fehler stehen in der **ServiceSpecificExitCode** -Eigenschaft zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ba055-113">This property is set to **ERROR_SERVICE_SPECIFIC_ERROR** (1066) when the error is unique to the service represented by this class, and information about the error is available in the **ServiceSpecificExitCode** property.</span></span> <span data-ttu-id="ba055-114">Vom Dienst wird dieser Wert bei der Ausführung und erneut bei normaler Beendigung auf NO_ERROR (0) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ba055-114">The service sets this value to NO_ERROR (0) when running, and again upon normal termination.</span></span>  
  
 <span data-ttu-id="ba055-115">**HostName**</span><span class="sxs-lookup"><span data-stu-id="ba055-115">**Host Name**</span></span>  
 <span data-ttu-id="ba055-116">Zeigt den Namen des Computers oder Clusters an, auf dem der [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ba055-116">Displays the name of the computer or cluster running the [!INCLUDE[ssIS](../../includes/ssis-md.md)] service.</span></span>  
  
 <span data-ttu-id="ba055-117">**Name**</span><span class="sxs-lookup"><span data-stu-id="ba055-117">**Name**</span></span>  
 <span data-ttu-id="ba055-118">Zeigt den Anzeigenamen des Dienstes an.</span><span class="sxs-lookup"><span data-stu-id="ba055-118">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="ba055-119">**Prozess-ID**</span><span class="sxs-lookup"><span data-stu-id="ba055-119">**Process ID**</span></span>  
 <span data-ttu-id="ba055-120">Zeigt die Prozess-ID von Windows an.</span><span class="sxs-lookup"><span data-stu-id="ba055-120">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="ba055-121">**SQL-Diensttyp**</span><span class="sxs-lookup"><span data-stu-id="ba055-121">**SQL Service Type**</span></span>  
 <span data-ttu-id="ba055-122">Zeigt den für aufrufende Prozesse bereitgestellten Diensttyp an.</span><span class="sxs-lookup"><span data-stu-id="ba055-122">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="ba055-123">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installiert mehrere Dienste.</span><span class="sxs-lookup"><span data-stu-id="ba055-123">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installs several services.</span></span>  
  
 <span data-ttu-id="ba055-124">**Startmodus**</span><span class="sxs-lookup"><span data-stu-id="ba055-124">**Start Mode**</span></span>  
 <span data-ttu-id="ba055-125">Richten Sie den Dienst mit den folgenden Auswahlmöglichkeiten ein:</span><span class="sxs-lookup"><span data-stu-id="ba055-125">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="ba055-126">Manuell: Dieser Dienst wird nicht automatisch zusammen mit dem Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="ba055-126">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="ba055-127">Zum Starten des Dienstes verwenden Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager oder ein anderes Tool.</span><span class="sxs-lookup"><span data-stu-id="ba055-127">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="ba055-128">Automatisch: Dieser Dienst wird zusammen mit dem Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="ba055-128">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="ba055-129">Deaktiviert: Dieser Dienst kann nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="ba055-129">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="ba055-130">**State**</span><span class="sxs-lookup"><span data-stu-id="ba055-130">**State**</span></span>  
 <span data-ttu-id="ba055-131">Zeigt an, ob dieser Dienst ausgeführt wird, angehalten oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ba055-131">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="ba055-132">„ **…** “ gibt einen ausstehenden Statuswechsel an.</span><span class="sxs-lookup"><span data-stu-id="ba055-132">"**...**" indicates a state change is pending.</span></span>  
  
  
