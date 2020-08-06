---
title: Eigenschaften von SQL Server (Registerkarte „Dienst“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: e4ae0c6b-6fd8-4325-b54e-1758fc659958
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5822a02d5631e0d0e9318b20a1dcee87b8a4ded1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724317"
---
# <a name="sql-server-properties-service-tab"></a><span data-ttu-id="40e7b-102">SQL-Server-Eigenschaften (Registerkarte Dienst)</span><span class="sxs-lookup"><span data-stu-id="40e7b-102">SQL Server Properties (Service Tab)</span></span>
  <span data-ttu-id="40e7b-103">Verwenden Sie im Dialogfeld **MSSQLSERVER-Eigenschaften**die Registerkarte **Dienst** , um die folgenden Optionen anzuzeigen oder anzugeben.</span><span class="sxs-lookup"><span data-stu-id="40e7b-103">Use the **Service**tab on the **MSSQLSERVER Properties** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="40e7b-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="40e7b-104">Options</span></span>  
 <span data-ttu-id="40e7b-105">**Binärpfad**</span><span class="sxs-lookup"><span data-stu-id="40e7b-105">**Binary Path**</span></span>  
 <span data-ttu-id="40e7b-106">Führt den Speicherort der Programmdateien auf, die von diesem Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="40e7b-106">Lists the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="40e7b-107">**Fehlersteuerung**</span><span class="sxs-lookup"><span data-stu-id="40e7b-107">**Error Control**</span></span>  
 <span data-ttu-id="40e7b-108">1 steht für `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="40e7b-108">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="40e7b-109">Wenn der Dienst nicht zusammen mit dem Computer gestartet werden kann, wird der Fehler vom Startprogramm protokolliert und eine Popupmeldung angezeigt, der Startvorgang aber fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="40e7b-109">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="40e7b-110">Dieser Wert kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="40e7b-110">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="40e7b-111">**Exitcode**</span><span class="sxs-lookup"><span data-stu-id="40e7b-111">**Exit Code**</span></span>  
 <span data-ttu-id="40e7b-112">Bei einem Fehler wird die dazu gehörende Nummer in diesem Feld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="40e7b-112">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="40e7b-113">Verwenden Sie diese Nummer für die Problembehandlung. Stellen Sie die Fehlernummer dem technischen Support zur Verfügung, oder durchsuchen Sie die [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="40e7b-113">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="40e7b-114">**HostName**</span><span class="sxs-lookup"><span data-stu-id="40e7b-114">**Host Name**</span></span>  
 <span data-ttu-id="40e7b-115">Zeigt den Namen des Computers oder Clusters an, auf dem der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienst ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="40e7b-115">Displays the name of the computer or cluster running the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
 <span data-ttu-id="40e7b-116">**Name**</span><span class="sxs-lookup"><span data-stu-id="40e7b-116">**Name**</span></span>  
 <span data-ttu-id="40e7b-117">Zeigt den Anzeigenamen des Dienstes an.</span><span class="sxs-lookup"><span data-stu-id="40e7b-117">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="40e7b-118">**Prozess-ID**</span><span class="sxs-lookup"><span data-stu-id="40e7b-118">**Process ID**</span></span>  
 <span data-ttu-id="40e7b-119">Zeigt die Prozess-ID von Windows an.</span><span class="sxs-lookup"><span data-stu-id="40e7b-119">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="40e7b-120">**Diensttyp**</span><span class="sxs-lookup"><span data-stu-id="40e7b-120">**Service Type**</span></span>  
 <span data-ttu-id="40e7b-121">Zeigt den für aufrufende Prozesse bereitgestellten Diensttyp an.</span><span class="sxs-lookup"><span data-stu-id="40e7b-121">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="40e7b-122">werden mehrere Dienste installiert.</span><span class="sxs-lookup"><span data-stu-id="40e7b-122">installs several services.</span></span>  
  
 <span data-ttu-id="40e7b-123">**Startmodus**</span><span class="sxs-lookup"><span data-stu-id="40e7b-123">**Start Mode**</span></span>  
 <span data-ttu-id="40e7b-124">Richten Sie den Dienst mit den folgenden Auswahlmöglichkeiten ein:</span><span class="sxs-lookup"><span data-stu-id="40e7b-124">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="40e7b-125">Manuell: Dieser Dienst wird nicht automatisch zusammen mit dem Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="40e7b-125">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="40e7b-126">Zum Starten des Dienstes verwenden Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager oder ein anderes Tool.</span><span class="sxs-lookup"><span data-stu-id="40e7b-126">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="40e7b-127">Automatisch: Dieser Dienst wird zusammen mit dem Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="40e7b-127">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="40e7b-128">Deaktiviert: Dieser Dienst kann nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="40e7b-128">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="40e7b-129">**State**</span><span class="sxs-lookup"><span data-stu-id="40e7b-129">**State**</span></span>  
 <span data-ttu-id="40e7b-130">Zeigt an, ob dieser Dienst ausgeführt wird, angehalten oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="40e7b-130">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="40e7b-131">„ **…** “ gibt einen ausstehenden Statuswechsel an.</span><span class="sxs-lookup"><span data-stu-id="40e7b-131">"**...**" indicates a state change is pending.</span></span>  
  
  
