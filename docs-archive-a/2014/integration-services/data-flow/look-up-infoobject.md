---
title: InfoObject suchen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e7f4c132-a5ec-49d8-a964-45775432731f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1616b4fcb368afc9e3f1157a3fc2511d4a7e8cce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700077"
---
# <a name="look-up-infoobject"></a><span data-ttu-id="fdde8-102">InfoObject suchen</span><span class="sxs-lookup"><span data-stu-id="fdde8-102">Look Up InfoObject</span></span>
  <span data-ttu-id="fdde8-103">Verwenden Sie das Dialogfeld **InfoObject suchen** , um ein InfoObject zu suchen, das im SAP NetWeaver BW-System definiert ist.</span><span class="sxs-lookup"><span data-stu-id="fdde8-103">Use the **Look Up InfoObject** dialog box to look up an InfoObject that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="fdde8-104">Wenn die Liste der verfügbaren InfoObjects angezeigt wird, wählen Sie das gewünschte InfoObject aus. Daraufhin werden die zugehörigen Optionen vom SAP BW-Ziel mit den erforderlichen Werten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="fdde8-104">When the list of available InfoObjects appears, select the InfoObject that you want, and the SAP BW destination will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="fdde8-105">Das SAP BW-Ziel von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW verwendet das Dialogfeld **InfoObject suchen** .</span><span class="sxs-lookup"><span data-stu-id="fdde8-105">The SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW uses the **Look Up InfoObject** dialog box.</span></span> <span data-ttu-id="fdde8-106">Weitere Informationen zum SAP BW-Ziel finden Sie unter [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="fdde8-106">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fdde8-107">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="fdde8-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="fdde8-108">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="fdde8-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="fdde8-109">**So öffnen Sie das Dialogfeld "InfoObject suchen"**</span><span class="sxs-lookup"><span data-stu-id="fdde8-109">**To open the Look Up InfoObject dialog box**</span></span>  
  
1.  <span data-ttu-id="fdde8-110">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket, in dem das SAP BW-Ziel enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="fdde8-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="fdde8-111">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf das SAP BW-Ziel.</span><span class="sxs-lookup"><span data-stu-id="fdde8-111">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="fdde8-112">Klicken Sie im **Ziel-Editor für SAP BW**auf **Verbindungs-Manager** , um die Seite **Verbindungs-Manager** des Editors zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fdde8-112">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="fdde8-113">Wählen Sie auf der Seite **Verbindungs-Manager** im Gruppenfeld **SAP BW-Objekte erstellen** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="fdde8-113">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select one of the following options:</span></span>  
  
    1.  <span data-ttu-id="fdde8-114">Wählen Sie **InfoCube**aus.</span><span class="sxs-lookup"><span data-stu-id="fdde8-114">Select **InfoCube**.</span></span> <span data-ttu-id="fdde8-115">Klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="fdde8-115">Then, click **Create**.</span></span> <span data-ttu-id="fdde8-116">Klicken Sie im Dialogfeld **InfoCube für Transaktionsdaten erstellen** in der Spalte **IObject** für eine der Zeilen in der Liste auf **Suchen** .</span><span class="sxs-lookup"><span data-stu-id="fdde8-116">In the **Create InfoCube for Transaction Data** dialog box, click **Search** in the **IObject** column for one of the rows in the list.</span></span> <span data-ttu-id="fdde8-117">Jede Zeile stellt eine Spalte im Datenfluss des Pakets dar.</span><span class="sxs-lookup"><span data-stu-id="fdde8-117">Each row represents a column in the data flow of the package.</span></span>  
  
    2.  <span data-ttu-id="fdde8-118">Wählen Sie **InfoSource**aus.</span><span class="sxs-lookup"><span data-stu-id="fdde8-118">Select **InfoSource**.</span></span> <span data-ttu-id="fdde8-119">Klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="fdde8-119">Then click **Create**.</span></span> <span data-ttu-id="fdde8-120">Wählen Sie im Dialogfeld **InfoSource erstellen** die Option **Transaktionsdaten**aus.</span><span class="sxs-lookup"><span data-stu-id="fdde8-120">In the **Create InfoSource** dialog box, select **Transaction data**.</span></span> <span data-ttu-id="fdde8-121">Klicken Sie im Dialogfeld **InfoSource für Transaktionsdaten erstellen** in der Spalte **IObject** für eine der Zeilen in der Liste auf **Suchen** .</span><span class="sxs-lookup"><span data-stu-id="fdde8-121">In the **Create InfoSource for Transaction Data** dialog box, click **Search** in the **IObject** column for one of the rows in the list.</span></span> <span data-ttu-id="fdde8-122">Jede Zeile stellt eine Spalte im Datenfluss des Pakets dar.</span><span class="sxs-lookup"><span data-stu-id="fdde8-122">Each row represents a column in the data flow of the package.</span></span>  
  
    3.  <span data-ttu-id="fdde8-123">Wählen Sie **InfoSource**aus.</span><span class="sxs-lookup"><span data-stu-id="fdde8-123">Select **InfoSource**.</span></span> <span data-ttu-id="fdde8-124">Klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="fdde8-124">Then click **Create**.</span></span> <span data-ttu-id="fdde8-125">Wählen Sie im Dialogfeld **InfoSource erstellen** die Option **Masterdaten**aus.</span><span class="sxs-lookup"><span data-stu-id="fdde8-125">In the **Create InfoSource** dialog box, select **Master data**.</span></span> <span data-ttu-id="fdde8-126">Klicken Sie im Dialogfeld **InfoSource für Masterdaten erstellen** auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="fdde8-126">In the **Create InfoSource for Master Data** dialog box, click **Look up**.</span></span>  
  
 <span data-ttu-id="fdde8-127">Sie können das Dialogfeld **InfoObject suchen** auch öffnen, indem Sie im Abschnitt **Attribute** des Dialogfelds **Neues InfoObject erstellen** auf **Hinzufügen** klicken.</span><span class="sxs-lookup"><span data-stu-id="fdde8-127">You can also open the **Look Up InfoObject** dialog box by clicking **Add** in the **Attributes** section of the **Create New InfoObject** dialog box.</span></span>  
  
## <a name="lookup-options"></a><span data-ttu-id="fdde8-128">Suchoptionen</span><span class="sxs-lookup"><span data-stu-id="fdde8-128">Lookup Options</span></span>  
 <span data-ttu-id="fdde8-129">In den Suchtextfeldern können Sie Ergebnisse filtern, indem Sie das Platzhalterzeichen (\*) oder eine Teilzeichenfolge in Kombination mit dem Platzhalterzeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="fdde8-129">In the lookup field text boxes, you can filter results by using the asterisk wildcard character (\*), or by using a partial string in combination with the asterisk wildcard character.</span></span> <span data-ttu-id="fdde8-130">Wenn Sie ein Suchfeld jedoch leer lassen, werden beim Suchvorgang nur leere Zeichenfolgen in diesem Feld abgeglichen.</span><span class="sxs-lookup"><span data-stu-id="fdde8-130">However, if you leave a lookup field empty, the lookup process will only match empty strings in that field.</span></span>  
  
 <span data-ttu-id="fdde8-131">**Merkmale**</span><span class="sxs-lookup"><span data-stu-id="fdde8-131">**Characteristics**</span></span>  
 <span data-ttu-id="fdde8-132">Suchen Sie die InfoObjects, die die Eigenschaften darstellen.</span><span class="sxs-lookup"><span data-stu-id="fdde8-132">Look up InfoObjects that represent characteristics.</span></span>  
  
 <span data-ttu-id="fdde8-133">**Einheiten**</span><span class="sxs-lookup"><span data-stu-id="fdde8-133">**Units**</span></span>  
 <span data-ttu-id="fdde8-134">Suchen Sie die InfoObjects, die die Einheiten darstellen.</span><span class="sxs-lookup"><span data-stu-id="fdde8-134">Look up InfoObjects that represent units.</span></span>  
  
 <span data-ttu-id="fdde8-135">**Kennzahlen**</span><span class="sxs-lookup"><span data-stu-id="fdde8-135">**Key figures**</span></span>  
 <span data-ttu-id="fdde8-136">Suchen Sie die InfoObjects, die die Kennzahlen darstellen.</span><span class="sxs-lookup"><span data-stu-id="fdde8-136">Look up InfoObjects that represent key figures.</span></span>  
  
 <span data-ttu-id="fdde8-137">**Zeitmerkmale**</span><span class="sxs-lookup"><span data-stu-id="fdde8-137">**Time characteristics**</span></span>  
 <span data-ttu-id="fdde8-138">Suchen Sie die InfoObjects, die die Zeitmerkmale darstellen.</span><span class="sxs-lookup"><span data-stu-id="fdde8-138">Look up InfoObjects that represent time characteristics.</span></span>  
  
 <span data-ttu-id="fdde8-139">**Name**</span><span class="sxs-lookup"><span data-stu-id="fdde8-139">**Name**</span></span>  
 <span data-ttu-id="fdde8-140">Geben Sie den Namen des InfoObject ein, das Sie suchen möchten, oder geben Sie einen Teilnamen mit dem Platzhalterzeichen (\*) ein.</span><span class="sxs-lookup"><span data-stu-id="fdde8-140">Enter the name of the InfoObject that you want to look up, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="fdde8-141">Alternativ können Sie das Platzhalterzeichen alleine verwenden, um alle InfoObjects einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="fdde8-141">Or, use the asterisk wildcard character alone to include all InfoObjects.</span></span>  
  
 <span data-ttu-id="fdde8-142">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="fdde8-142">**Description**</span></span>  
 <span data-ttu-id="fdde8-143">Geben Sie die Beschreibung oder eine teilweise Beschreibung mit dem Platzhalterzeichen (\*) ein.</span><span class="sxs-lookup"><span data-stu-id="fdde8-143">Enter the description, or a partial description with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="fdde8-144">Alternativ können Sie das Platzhalterzeichen alleine verwenden, um alle InfoObjects unabhängig von der Beschreibung einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="fdde8-144">Or, use the asterisk wildcard character alone to include all InfoObjects regardless of description.</span></span>  
  
 <span data-ttu-id="fdde8-145">**Suchen**</span><span class="sxs-lookup"><span data-stu-id="fdde8-145">**Look up**</span></span>  
 <span data-ttu-id="fdde8-146">Suchen Sie übereinstimmende InfoObjects, die im SAP NetWeaver BW-System definiert sind.</span><span class="sxs-lookup"><span data-stu-id="fdde8-146">Look up matching InfoObjects that are defined in the SAP Netweaver BW system.</span></span>  
  
## <a name="lookup-results"></a><span data-ttu-id="fdde8-147">Suchergebnisse</span><span class="sxs-lookup"><span data-stu-id="fdde8-147">Lookup Results</span></span>  
 <span data-ttu-id="fdde8-148">Nachdem Sie auf die Schaltfläche Suchen geklickt haben, wird eine Liste der im SAP NetWeaver BW-System enthaltenen InfoObjects in einer Tabelle angezeigt, die über die folgenden Spaltenüberschriften verfügt.</span><span class="sxs-lookup"><span data-stu-id="fdde8-148">After you click the Look up button, a list of the InfoObjects in the SAP Netweaver BW system appears in a table with the following column headings.</span></span>  
  
 <span data-ttu-id="fdde8-149">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="fdde8-149">**InfoObject**</span></span>  
 <span data-ttu-id="fdde8-150">Zeigt den Namen des InfoObject an, das im SAP NetWeaver BW-System definiert ist.</span><span class="sxs-lookup"><span data-stu-id="fdde8-150">Displays the name of the InfoObject that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="fdde8-151">**Text (kurz)**</span><span class="sxs-lookup"><span data-stu-id="fdde8-151">**Text (short)**</span></span>  
 <span data-ttu-id="fdde8-152">Zeigt den kurzen Text an, der dem InfoObject zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="fdde8-152">Displays the short text that is associated with the InfoObject.</span></span>  
  
 <span data-ttu-id="fdde8-153">Wenn die Liste der verfügbaren InfoObjects angezeigt wird, wählen Sie das gewünschte InfoObject aus. Daraufhin werden die zugehörigen Optionen vom Ziel mit den erforderlichen Werten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="fdde8-153">When the list of available InfoObjects appears, select the InfoObject that you want, and the destination will populate the associated options with the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdde8-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fdde8-154">See Also</span></span>  
 <span data-ttu-id="fdde8-155">[InfoCube für Transaktionsdaten erstellen](create-infocube-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="fdde8-155">[Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md) </span></span>  
 <span data-ttu-id="fdde8-156">[InfoSource erstellen](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="fdde8-156">[Create InfoSource](create-infosource.md) </span></span>  
 <span data-ttu-id="fdde8-157">[InfoSource für Transaktionsdaten erstellen](create-infosource-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="fdde8-157">[Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) </span></span>  
 <span data-ttu-id="fdde8-158">[InfoSource für Masterdaten erstellen](create-infosource-for-master-data.md) </span><span class="sxs-lookup"><span data-stu-id="fdde8-158">[Create InfoSource for Master Data](create-infosource-for-master-data.md) </span></span>  
 <span data-ttu-id="fdde8-159">[Neues InfoObject erstellen](create-new-infoobject.md) </span><span class="sxs-lookup"><span data-stu-id="fdde8-159">[Create New InfoObject](create-new-infoobject.md) </span></span>  
 <span data-ttu-id="fdde8-160">[Ziel-Editor für SAP BW &#40;Seite „Verbindungs-Manager“&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="fdde8-160">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="fdde8-161">F1-Hilfe zu Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="fdde8-161">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
