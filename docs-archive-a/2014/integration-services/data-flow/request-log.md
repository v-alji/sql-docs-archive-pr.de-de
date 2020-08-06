---
title: Anforderungsprotokoll | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 165d3833-0493-490c-9f63-8a134a7fafb8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 024012878ae94c5ba6276648e289e6e6f7c93d7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615457"
---
# <a name="request-log"></a><span data-ttu-id="a1fb3-102">Anforderungsprotokoll</span><span class="sxs-lookup"><span data-stu-id="a1fb3-102">Request Log</span></span>
  <span data-ttu-id="a1fb3-103">Verwenden Sie das Dialogfeld **Anforderungsprotokoll** , um die Ereignisse anzuzeigen, die protokolliert werden, während Beispieldaten vom SAP NetWeaver BW-System angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="a1fb3-103">Use the **Request Log** dialog box to view the events that are logged during the request that is made to the SAP Netweaver BW system for sample data.</span></span> <span data-ttu-id="a1fb3-104">Diese Informationen können hilfreich sein, um Konfigurationsprobleme mit der SAP BW-Quelle zu beheben.</span><span class="sxs-lookup"><span data-stu-id="a1fb3-104">This information can be useful if you have to troubleshoot your configuration of the SAP BW source.</span></span>  
  
 <span data-ttu-id="a1fb3-105">Weitere Informationen zur SAP BW-Quellkomponente von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW finden Sie unter [SAP BW-Quelle](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="a1fb3-105">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a1fb3-106">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="a1fb3-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="a1fb3-107">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="a1fb3-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a1fb3-108">Das Extrahieren von Daten aus SAP NetWeaver BW erfordert zusätzliche SAP-Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="a1fb3-108">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="a1fb3-109">Stimmen Sie diese Anforderungen mit SAP ab.</span><span class="sxs-lookup"><span data-stu-id="a1fb3-109">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="a1fb3-110">**So öffnen Sie das Dialogfeld "Anforderungsprotokoll"**</span><span class="sxs-lookup"><span data-stu-id="a1fb3-110">**To open the Request Log dialog box**</span></span>  
  
1.  <span data-ttu-id="a1fb3-111">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket, in dem die SAP BW-Quelle enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="a1fb3-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="a1fb3-112">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf die SAP BW-Quelle.</span><span class="sxs-lookup"><span data-stu-id="a1fb3-112">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="a1fb3-113">Klicken Sie im **Quellen-Editor für SAP BW**auf **Verbindungs-Manager** , um die Seite **Verbindungs-Manager** des Editors zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a1fb3-113">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="a1fb3-114">Nachdem Sie die SAP BW-Quelle konfiguriert haben, klicken Sie auf **Vorschau** , um die Ereignisse im Dialogfeld **Anforderungsprotokoll** in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a1fb3-114">After you configure the SAP BW source, click **Preview** to preview the events in the **Request Log** dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a1fb3-115">Wenn Sie auf **Vorschau** klicken, wird auch das Dialogfeld **Vorschau** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a1fb3-115">Clicking **Preview** also opens the **Preview** dialog box.</span></span> <span data-ttu-id="a1fb3-116">Weitere Informationen zu diesem Dialogfeld finden Sie unter [Preview](preview.md).</span><span class="sxs-lookup"><span data-stu-id="a1fb3-116">For more information about this dialog box, see [Preview](preview.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a1fb3-117">Tastatur</span><span class="sxs-lookup"><span data-stu-id="a1fb3-117">Options</span></span>  
 <span data-ttu-id="a1fb3-118">**Time**</span><span class="sxs-lookup"><span data-stu-id="a1fb3-118">**Time**</span></span>  
 <span data-ttu-id="a1fb3-119">Zeigt die Uhrzeit an, zu der das Ereignis protokolliert wurde.</span><span class="sxs-lookup"><span data-stu-id="a1fb3-119">Displays the time that the event that was logged.</span></span>  
  
 <span data-ttu-id="a1fb3-120">**Typ**</span><span class="sxs-lookup"><span data-stu-id="a1fb3-120">**Type**</span></span>  
 <span data-ttu-id="a1fb3-121">Zeigt den Typ des protokollierten Ereignisses an.</span><span class="sxs-lookup"><span data-stu-id="a1fb3-121">Displays the type of the event that was logged.</span></span> <span data-ttu-id="a1fb3-122">In der folgenden Tabelle sind die möglichen Ereignistypen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="a1fb3-122">The following table lists the possible event types.</span></span>  
  
|<span data-ttu-id="a1fb3-123">value</span><span class="sxs-lookup"><span data-stu-id="a1fb3-123">Value</span></span>|<span data-ttu-id="a1fb3-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a1fb3-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a1fb3-125">E</span><span class="sxs-lookup"><span data-stu-id="a1fb3-125">S</span></span>|<span data-ttu-id="a1fb3-126">Eine Erfolgsmeldung.</span><span class="sxs-lookup"><span data-stu-id="a1fb3-126">Success message.</span></span>|  
|<span data-ttu-id="a1fb3-127">E</span><span class="sxs-lookup"><span data-stu-id="a1fb3-127">E</span></span>|<span data-ttu-id="a1fb3-128">Fehlermeldung</span><span class="sxs-lookup"><span data-stu-id="a1fb3-128">Error message</span></span>|  
|<span data-ttu-id="a1fb3-129">W</span><span class="sxs-lookup"><span data-stu-id="a1fb3-129">W</span></span>|<span data-ttu-id="a1fb3-130">Warnmeldung.</span><span class="sxs-lookup"><span data-stu-id="a1fb3-130">Warning message.</span></span>|  
|<span data-ttu-id="a1fb3-131">I</span><span class="sxs-lookup"><span data-stu-id="a1fb3-131">I</span></span>|<span data-ttu-id="a1fb3-132">Informationsmeldung.</span><span class="sxs-lookup"><span data-stu-id="a1fb3-132">Informational message.</span></span>|  
|<span data-ttu-id="a1fb3-133">Ein</span><span class="sxs-lookup"><span data-stu-id="a1fb3-133">A</span></span>|<span data-ttu-id="a1fb3-134">Der Vorgang wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="a1fb3-134">The operation was aborted.</span></span>|  
  
 <span data-ttu-id="a1fb3-135">**Meldung**</span><span class="sxs-lookup"><span data-stu-id="a1fb3-135">**Message**</span></span>  
 <span data-ttu-id="a1fb3-136">Zeigt den Meldungstext an, der dem protokollierten Ereignis zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a1fb3-136">Displays the message text that is associated with the logged event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1fb3-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a1fb3-137">See Also</span></span>  
 <span data-ttu-id="a1fb3-138">[Quellen-Editor für SAP BW &#40;Seite „Verbindungs-Manager“&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="a1fb3-138">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="a1fb3-139">F1-Hilfe zu Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="a1fb3-139">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
