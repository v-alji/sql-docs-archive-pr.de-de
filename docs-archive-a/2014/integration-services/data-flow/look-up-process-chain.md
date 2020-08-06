---
title: Prozesskette suchen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f6303ea4-fbbf-4cba-bc60-828df62be8c2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2e0d3743071d018a8a82f60eeaf04fd86dec3e63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700071"
---
# <a name="look-up-process-chain"></a><span data-ttu-id="9c385-102">Prozesskette suchen</span><span class="sxs-lookup"><span data-stu-id="9c385-102">Look Up Process Chain</span></span>
  <span data-ttu-id="9c385-103">Verwenden Sie das Dialogfeld **Prozesskette suchen** , um eine Prozesskette suchen, die im SAP NetWeaver BW-System definiert ist.</span><span class="sxs-lookup"><span data-stu-id="9c385-103">Use the **Look Up Process Chain** dialog box to look up a process chain that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="9c385-104">Wenn die Liste der verfügbaren Prozessketten angezeigt wird, wählen Sie die gewünschte Kette aus. Daraufhin werden die zugehörigen Optionen von der Quelle mit den erforderlichen Werten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="9c385-104">When the list of available process chains appears, select the chain that you want, and the source will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="9c385-105">Die SAP BW-Quelle von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW verwendet das Dialogfeld **Prozesskette suchen** .</span><span class="sxs-lookup"><span data-stu-id="9c385-105">The SAP BW source of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW uses the **Look Up Process Chain** dialog box.</span></span> <span data-ttu-id="9c385-106">Weitere Informationen zur SAP BW-Quelle finden Sie unter [SAP BW Source](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="9c385-106">To learn more about the SAP BW source, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9c385-107">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="9c385-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="9c385-108">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="9c385-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="9c385-109">**So öffnen Sie das Dialogfeld "Prozesskette suchen"**</span><span class="sxs-lookup"><span data-stu-id="9c385-109">**To open the Look Up Process Chain dialog box**</span></span>  
  
1.  <span data-ttu-id="9c385-110">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket, in dem die SAP BW-Quelle enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="9c385-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="9c385-111">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf die SAP BW-Quelle.</span><span class="sxs-lookup"><span data-stu-id="9c385-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="9c385-112">Klicken Sie im **Quellen-Editor für SAP BW**auf **Verbindungs-Manager** , um die Seite **Verbindungs-Manager** des Editors zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9c385-112">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="9c385-113">Klicken Sie im Gruppenfeld **Prozesskette** auf **Suchen** , um das Dialogfeld **Prozesskette suchen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9c385-113">In the **Process Chain** group box, click **Look up** to display the **Look Up Process Chain** dialog box.</span></span>  
  
     <span data-ttu-id="9c385-114">Das Gruppenfeld **Prozesskette** wird nur angezeigt, wenn der Wert für **Ausführungsmodus** auf **P - Prozesskette auslösen**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9c385-114">The **Process Chain** group box appears only if the value for **Execution mode** is **P - Trigger process chain**.</span></span>  
  
## <a name="lookup-options"></a><span data-ttu-id="9c385-115">Suchoptionen</span><span class="sxs-lookup"><span data-stu-id="9c385-115">Lookup Options</span></span>  
 <span data-ttu-id="9c385-116">In den Suchfeldern können Sie Ergebnisse filtern, indem Sie das Platzhalterzeichen (\*) oder eine Teilzeichenfolge in Kombination mit dem Platzhalterzeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="9c385-116">In the lookup fields, you can filter results by using the asterisk wildcard character (\*), or by using a partial string in combination with the asterisk wildcard character.</span></span> <span data-ttu-id="9c385-117">Wenn Sie ein Suchfeld leer lassen, werden beim Suchvorgang jedoch nur leere Zeichenfolgen in diesem Feld abgeglichen.</span><span class="sxs-lookup"><span data-stu-id="9c385-117">However, if you leave a lookup field empty, the lookup operation will only match empty strings in that field.</span></span>  
  
 <span data-ttu-id="9c385-118">**Prozesskette**</span><span class="sxs-lookup"><span data-stu-id="9c385-118">**Process chain**</span></span>  
 <span data-ttu-id="9c385-119">Geben Sie den Namen der gesuchten Prozesskette oder einen Teilnamen mit dem Platzhalterzeichen (\*) ein.</span><span class="sxs-lookup"><span data-stu-id="9c385-119">Enter the name of the process chain that you want to look up, or enter a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="9c385-120">Alternativ können Sie das Platzhalterzeichen (\*) alleine verwenden, um alle Prozessketten einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="9c385-120">Or, use the asterisk wildcard character alone to include all process chains.</span></span>  
  
 <span data-ttu-id="9c385-121">**Suchen**</span><span class="sxs-lookup"><span data-stu-id="9c385-121">**Look up**</span></span>  
 <span data-ttu-id="9c385-122">Suchen Sie übereinstimmende Prozessketten, die im SAP NetWeaver BW-System definiert sind.</span><span class="sxs-lookup"><span data-stu-id="9c385-122">Look up matching process chains that are defined in the SAP Netweaver BW system.</span></span>  
  
## <a name="lookup-results"></a><span data-ttu-id="9c385-123">Suchergebnisse</span><span class="sxs-lookup"><span data-stu-id="9c385-123">Lookup Results</span></span>  
 <span data-ttu-id="9c385-124">Nachdem Sie auf die Schaltfläche Suchen geklickt haben, wird eine Liste der im SAP NetWeaver BW-System enthaltenen Prozessketten in einer Tabelle angezeigt, die über die folgenden Spaltenüberschriften verfügt.</span><span class="sxs-lookup"><span data-stu-id="9c385-124">After you click the Look up button, a list of the process chains in the SAP Netweaver BW system appears in a table with the following column headings:</span></span>  
  
 <span data-ttu-id="9c385-125">**Prozesskette**</span><span class="sxs-lookup"><span data-stu-id="9c385-125">**Process Chain**</span></span>  
 <span data-ttu-id="9c385-126">Zeigt den Namen der Prozesskette an, die im SAP NetWeaver BW-System definiert ist.</span><span class="sxs-lookup"><span data-stu-id="9c385-126">Displays the name of the process chain that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="9c385-127">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="9c385-127">**Description**</span></span>  
 <span data-ttu-id="9c385-128">Zeigt die Beschreibung der Prozesskette an.</span><span class="sxs-lookup"><span data-stu-id="9c385-128">Displays the description of the process chain.</span></span>  
  
 <span data-ttu-id="9c385-129">Wenn die Liste der verfügbaren Prozessketten angezeigt wird, wählen Sie die gewünschte Kette aus. Daraufhin werden die zugehörigen Optionen von der Quelle mit den erforderlichen Werten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="9c385-129">When the list of available process chains appears, select the chain that you want, and the source will populate the associated options with the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c385-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9c385-130">See Also</span></span>  
 <span data-ttu-id="9c385-131">[Quellen-Editor für SAP BW &#40;Seite „Verbindungs-Manager“&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="9c385-131">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="9c385-132">F1-Hilfe zu Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="9c385-132">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
