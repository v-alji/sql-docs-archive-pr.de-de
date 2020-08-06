---
title: Eigenschaften von NS $- &lt; Dienst Name &gt; (Registerkarte "Dienst") | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 57c6b791-1663-4a01-9de2-cf1bdd8adb2c
author: stevestein
ms.author: sstein
ms.openlocfilehash: ddd80cf1c84e3fe7acc538e6aa65230b45870219
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722093"
---
# <a name="nsltservice-namegt-properties-service-tab"></a><span data-ttu-id="80994-102">NS$&lt;Dienstname&gt;-Eigenschaften (Registerkarte „Dienst“)</span><span class="sxs-lookup"><span data-stu-id="80994-102">NS$&lt;service name&gt; Properties (Service Tab)</span></span>
  <span data-ttu-id="80994-103">Hierbei handelt es sich um den [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNS](../../includes/ssns-md.md)]-Dienst.</span><span class="sxs-lookup"><span data-stu-id="80994-103">This service is the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNS](../../includes/ssns-md.md)] service.</span></span> <span data-ttu-id="80994-104">Die ausgegrauten Eigenschaftswerte können nicht mithilfe dieser Anwendung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="80994-104">The property values in light gray cannot be changed using this application.</span></span>  
  
## <a name="options"></a><span data-ttu-id="80994-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="80994-105">Options</span></span>  
 <span data-ttu-id="80994-106">**Binärpfad**</span><span class="sxs-lookup"><span data-stu-id="80994-106">**Binary Path**</span></span>  
 <span data-ttu-id="80994-107">Zeigt den Speicherort der Programmdateien an, die von diesem Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="80994-107">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="80994-108">**Fehlersteuerung**</span><span class="sxs-lookup"><span data-stu-id="80994-108">**Error Control**</span></span>  
 <span data-ttu-id="80994-109">1 steht für `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="80994-109">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="80994-110">Wenn der Dienst nicht zusammen mit dem Computer gestartet werden kann, wird der Fehler vom Startprogramm protokolliert und eine Popupmeldung angezeigt, der Startvorgang aber fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="80994-110">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="80994-111">Dieser Wert kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="80994-111">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="80994-112">**Exitcode**</span><span class="sxs-lookup"><span data-stu-id="80994-112">**Exit Code**</span></span>  
 <span data-ttu-id="80994-113">Bei einem Fehler wird die dazu gehörende Nummer in diesem Feld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="80994-113">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="80994-114">Verwenden Sie diese Nummer für die Problembehandlung. Stellen Sie die Fehlernummer dem technischen Support zur Verfügung, oder durchsuchen Sie die [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="80994-114">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="80994-115">**HostName**</span><span class="sxs-lookup"><span data-stu-id="80994-115">**Host Name**</span></span>  
 <span data-ttu-id="80994-116">Zeigt den Namen des Computers oder Clusters an, auf dem die Volltextsuche ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="80994-116">Displays the name of the computer or cluster running the full text search.</span></span>  
  
 <span data-ttu-id="80994-117">**Name**</span><span class="sxs-lookup"><span data-stu-id="80994-117">**Name**</span></span>  
 <span data-ttu-id="80994-118">Zeigt den Anzeigenamen des Dienstes an.</span><span class="sxs-lookup"><span data-stu-id="80994-118">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="80994-119">**Prozess-ID**</span><span class="sxs-lookup"><span data-stu-id="80994-119">**Process ID**</span></span>  
 <span data-ttu-id="80994-120">Zeigt die Prozess-ID von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows an.</span><span class="sxs-lookup"><span data-stu-id="80994-120">Displays the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows process ID.</span></span>  
  
 <span data-ttu-id="80994-121">**SQL-Diensttyp**</span><span class="sxs-lookup"><span data-stu-id="80994-121">**SQL Service Type**</span></span>  
 <span data-ttu-id="80994-122">Der für aufrufende Prozesse bereitgestellte Diensttyp.</span><span class="sxs-lookup"><span data-stu-id="80994-122">Type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="80994-123">werden mehrere Dienste installiert.</span><span class="sxs-lookup"><span data-stu-id="80994-123">installs several services.</span></span>  
  
 <span data-ttu-id="80994-124">**Startmodus**</span><span class="sxs-lookup"><span data-stu-id="80994-124">**Start Mode**</span></span>  
 <span data-ttu-id="80994-125">Richten Sie den Dienst mit den folgenden Auswahlmöglichkeiten ein:</span><span class="sxs-lookup"><span data-stu-id="80994-125">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="80994-126">Manuell: Dieser Dienst wird nicht automatisch zusammen mit dem Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="80994-126">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="80994-127">Zum Starten des Dienstes verwenden Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager oder ein anderes Tool.</span><span class="sxs-lookup"><span data-stu-id="80994-127">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="80994-128">Automatisch: Dieser Dienst wird zusammen mit dem Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="80994-128">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="80994-129">Deaktiviert: Dieser Dienst kann nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="80994-129">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="80994-130">**State**</span><span class="sxs-lookup"><span data-stu-id="80994-130">**State**</span></span>  
 <span data-ttu-id="80994-131">Zeigt an, ob dieser Dienst ausgeführt wird, angehalten oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="80994-131">Indicates whether this service is running, stopped, or disabled.</span></span>  
  
  
