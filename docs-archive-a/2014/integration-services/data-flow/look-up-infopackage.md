---
title: InfoPackage suchen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7c0cb7a4-cd07-44cc-85cb-eb1ad91f85fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1e45477e8faeed07faa114850e10a3bc4bbcf170
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700076"
---
# <a name="look-up-infopackage"></a><span data-ttu-id="b749a-102">InfoPackage suchen</span><span class="sxs-lookup"><span data-stu-id="b749a-102">Look Up InfoPackage</span></span>
  <span data-ttu-id="b749a-103">Verwenden Sie das Dialogfeld **InfoPackage suchen** , um ein InfoPackage zu suchen, das im SAP NetWeaver BW-System definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b749a-103">Use the **Look Up InfoPackage** dialog box to look up an InfoPackage that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="b749a-104">Wenn die Liste der InfoPackages angezeigt wird, wählen Sie das gewünschte InfoPackage aus. Daraufhin werden die zugehörigen Optionen vom Ziel mit den erforderlichen Werten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="b749a-104">When the list of InfoPackages appears, select the InfoPackage that you want, and the destination will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="b749a-105">Das SAP BW-Ziel von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW verwendet das Dialogfeld **Prozesskette suchen** .</span><span class="sxs-lookup"><span data-stu-id="b749a-105">The SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW uses the **Look Up Process Chain** dialog box.</span></span> <span data-ttu-id="b749a-106">Weitere Informationen zum SAP BW-Ziel finden Sie unter [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="b749a-106">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b749a-107">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="b749a-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="b749a-108">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="b749a-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="b749a-109">**So öffnen Sie das Dialogfeld "InfoPackage suchen"**</span><span class="sxs-lookup"><span data-stu-id="b749a-109">**To open the Look Up InfoPackage dialog box**</span></span>  
  
1.  <span data-ttu-id="b749a-110">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket, in dem das SAP BW-Ziel enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="b749a-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="b749a-111">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf das SAP BW-Ziel.</span><span class="sxs-lookup"><span data-stu-id="b749a-111">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="b749a-112">Klicken Sie im **Ziel-Editor für SAP BW**auf **Verbindungs-Manager** , um die Seite **Verbindungs-Manager** des Editors zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b749a-112">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="b749a-113">Klicken Sie auf der Seite **Verbindungs-Manager** im Gruppenfeld **InfoPackage/InfoSource** auf **Suchen** , um das Dialogfeld **InfoPackage suchen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b749a-113">On the **Connection Manager** page, in the **InfoPackage/InfoSource** group box, click **Look up** to display the **Look Up InfoPackage** dialog box.</span></span>  
  
## <a name="lookup-options"></a><span data-ttu-id="b749a-114">Suchoptionen</span><span class="sxs-lookup"><span data-stu-id="b749a-114">Lookup Options</span></span>  
 <span data-ttu-id="b749a-115">In den Suchfeldern können Sie Ergebnisse filtern, indem Sie das Platzhalterzeichen (\*) oder eine Teilzeichenfolge in Kombination mit dem Platzhalterzeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b749a-115">In the lookup fields, you can filter results by using the asterisk wildcard character (\*), or by using a partial string in combination with the asterisk wildcard character.</span></span> <span data-ttu-id="b749a-116">Wenn Sie ein Suchfeld leer lassen, werden beim Suchvorgang jedoch nur leere Zeichenfolgen in diesem Feld abgeglichen.</span><span class="sxs-lookup"><span data-stu-id="b749a-116">However, if you leave a lookup field empty, the lookup operation will only match empty strings in that field.</span></span>  
  
 <span data-ttu-id="b749a-117">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="b749a-117">**InfoPackage**</span></span>  
 <span data-ttu-id="b749a-118">Geben Sie den Namen des InfoPackage ein, das Sie suchen möchten, oder geben Sie einen Teilnamen mit dem Platzhalterzeichen (\*) ein.</span><span class="sxs-lookup"><span data-stu-id="b749a-118">Enter the name of the InfoPackage that you want to look up, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="b749a-119">Alternativ können Sie das Platzhalterzeichen alleine verwenden, um alle InfoPackages einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="b749a-119">Or, use the asterisk wildcard character alone to include all InfoPackages.</span></span>  
  
 <span data-ttu-id="b749a-120">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="b749a-120">**InfoSource**</span></span>  
 <span data-ttu-id="b749a-121">Geben Sie den Namen der InfoSource oder einen Teilnamen mit dem Platzhalterzeichen (\*) ein.</span><span class="sxs-lookup"><span data-stu-id="b749a-121">Enter the name of the InfoSource, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="b749a-122">Alternativ können Sie das Platzhalterzeichen alleine verwenden, um alle InfoPackages unabhängig von InfoSource einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="b749a-122">Or, use the asterisk wildcard character alone to include all InfoPackages regardless of InfoSource.</span></span>  
  
 <span data-ttu-id="b749a-123">**Quellsystem**</span><span class="sxs-lookup"><span data-stu-id="b749a-123">**Source system**</span></span>  
 <span data-ttu-id="b749a-124">Geben Sie den Namen des Quellsystems oder einen Teilnamen mit dem Platzhalterzeichen (\*) ein.</span><span class="sxs-lookup"><span data-stu-id="b749a-124">Enter the name of the source system, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="b749a-125">Alternativ können Sie das Platzhalterzeichen alleine verwenden, um alle InfoPackages unabhängig von Quellsystemen einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="b749a-125">Or, use the asterisk wildcard character alone to include all InfoPackages regardless of source systems.</span></span>  
  
 <span data-ttu-id="b749a-126">**Suchen**</span><span class="sxs-lookup"><span data-stu-id="b749a-126">**Look up**</span></span>  
 <span data-ttu-id="b749a-127">Suchen Sie übereinstimmende InfoPackages, die im SAP NetWeaver BW-System definiert sind.</span><span class="sxs-lookup"><span data-stu-id="b749a-127">Look up matching InfoPackages that are defined in the SAP Netweaver BW system.</span></span>  
  
## <a name="lookup-results"></a><span data-ttu-id="b749a-128">Suchergebnisse</span><span class="sxs-lookup"><span data-stu-id="b749a-128">Lookup Results</span></span>  
 <span data-ttu-id="b749a-129">Nachdem Sie auf die Schaltfläche Suchen geklickt haben, wird eine Liste der im SAP NetWeaver BW-System enthaltenen InfoPackages in einer Tabelle angezeigt, die über die folgenden Spaltenüberschriften verfügt.</span><span class="sxs-lookup"><span data-stu-id="b749a-129">After you click the Look up button, a list of the InfoPackages in the SAP Netweaver BW system appears in a table with the following column headings.</span></span>  
  
 <span data-ttu-id="b749a-130">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="b749a-130">**InfoPackage**</span></span>  
 <span data-ttu-id="b749a-131">Zeigt den Namen des InfoPackage an, das im SAP NetWeaver BW-System definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b749a-131">Displays the name of the InfoPackage that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="b749a-132">**Typ**</span><span class="sxs-lookup"><span data-stu-id="b749a-132">**Type**</span></span>  
 <span data-ttu-id="b749a-133">Zeigt den Typ des InfoPackage an.</span><span class="sxs-lookup"><span data-stu-id="b749a-133">Displays the type of the InfoPackage.</span></span> <span data-ttu-id="b749a-134">In der folgenden Tabelle sind die möglichen Werte für den Typ aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="b749a-134">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="b749a-135">value</span><span class="sxs-lookup"><span data-stu-id="b749a-135">Value</span></span>|<span data-ttu-id="b749a-136">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b749a-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b749a-137">Trans.</span><span class="sxs-lookup"><span data-stu-id="b749a-137">Trans.</span></span>|<span data-ttu-id="b749a-138">Transaktionsdaten.</span><span class="sxs-lookup"><span data-stu-id="b749a-138">Transaction data.</span></span>|  
|<span data-ttu-id="b749a-139">Attr.</span><span class="sxs-lookup"><span data-stu-id="b749a-139">Attr.</span></span>|<span data-ttu-id="b749a-140">Attributdaten.</span><span class="sxs-lookup"><span data-stu-id="b749a-140">Attribute data.</span></span>|  
|<span data-ttu-id="b749a-141">Texte</span><span class="sxs-lookup"><span data-stu-id="b749a-141">Texts</span></span>|<span data-ttu-id="b749a-142">Texte.</span><span class="sxs-lookup"><span data-stu-id="b749a-142">Texts.</span></span>|  
  
 <span data-ttu-id="b749a-143">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b749a-143">**Description**</span></span>  
 <span data-ttu-id="b749a-144">Zeigt die Beschreibung des InfoPackage an.</span><span class="sxs-lookup"><span data-stu-id="b749a-144">Displays the description of the InfoPackage.</span></span>  
  
 <span data-ttu-id="b749a-145">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="b749a-145">**InfoSource**</span></span>  
 <span data-ttu-id="b749a-146">Zeigt den Namen der InfoSource an, die dem InfoPackage ggf. zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b749a-146">Displays the name of the InfoSource, if any, that is associated with the InfoPackage.</span></span>  
  
 <span data-ttu-id="b749a-147">**Source System**</span><span class="sxs-lookup"><span data-stu-id="b749a-147">**Source System**</span></span>  
 <span data-ttu-id="b749a-148">Zeigt den Namen des Quellsystems an.</span><span class="sxs-lookup"><span data-stu-id="b749a-148">Displays the name of the source system.</span></span>  
  
 <span data-ttu-id="b749a-149">Wenn die Liste der InfoPackages angezeigt wird, wählen Sie das gewünschte InfoPackage aus. Daraufhin werden die zugehörigen Optionen vom Ziel mit den erforderlichen Werten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="b749a-149">When the list of InfoPackages appears, select the InfoPackage that you want, and the destination will populate the associated options with the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b749a-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b749a-150">See Also</span></span>  
 <span data-ttu-id="b749a-151">[Ziel-Editor für SAP BW &#40;Seite „Verbindungs-Manager“&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="b749a-151">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="b749a-152">F1-Hilfe zu Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="b749a-152">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
