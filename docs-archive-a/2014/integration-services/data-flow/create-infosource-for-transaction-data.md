---
title: InfoSource für Transaktionsdaten erstellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ab5f23e2-cd4e-4507-83d9-ac5ef721c171
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3e3a60bb93da17e79087982473e92c35fa0856d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695917"
---
# <a name="create-infosource-for-transaction-data"></a><span data-ttu-id="1ee4d-102">InfoSource für Transaktionsdaten erstellen</span><span class="sxs-lookup"><span data-stu-id="1ee4d-102">Create InfoSource for Transaction Data</span></span>
  <span data-ttu-id="1ee4d-103">Verwenden Sie das Dialogfeld **InfoSource für Transaktionsdaten erstellen** , um eine neue InfoSource für Transaktionsdaten im SAP NetWeaver BW-System zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-103">Use the **Create InfoSource for Transaction Data** dialog box to create a new InfoSource for transaction data in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="1ee4d-104">Sie können das Dialogfeld **InfoSource für Transaktionsdaten erstellen** im **Ziel-Editor für SAP BW** auf der Seite **Verbindungs-Manager**öffnen.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-104">You can open the **Create InfoSource for Transaction Data** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="1ee4d-105">Weitere Informationen zum SAP BW-Ziel finden Sie unter [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="1ee4d-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1ee4d-106">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="1ee4d-107">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="1ee4d-108">**So öffnen Sie das Dialogfeld "InfoSource für Transaktionsdaten erstellen"**</span><span class="sxs-lookup"><span data-stu-id="1ee4d-108">**To open the Create InfoSource for Transaction Data dialog box**</span></span>  
  
1.  <span data-ttu-id="1ee4d-109">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket, in dem das SAP BW-Ziel enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="1ee4d-110">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf das SAP BW-Ziel.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="1ee4d-111">Klicken Sie im **Ziel-Editor für SAP BW**auf **Verbindungs-Manager** , um die Seite **Verbindungs-Manager** des Editors zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="1ee4d-112">Wählen Sie auf der Seite **Verbindungs-Manager** im Gruppenfeld **SAP BW-Objekte erstellen** die Option **InfoSource**aus, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoSource**, and then click **Create**.</span></span>  
  
5.  <span data-ttu-id="1ee4d-113">Wählen Sie im Dialogfeld **InfoSource erstellen** die Option **Transaktionsdaten**aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-113">In the **Create InfoSource** dialog box, select **Transaction data**, and then click **OK**.</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="1ee4d-114">Allgemeine Optionen</span><span class="sxs-lookup"><span data-stu-id="1ee4d-114">General Options</span></span>  
 <span data-ttu-id="1ee4d-115">**InfoSource-Name**</span><span class="sxs-lookup"><span data-stu-id="1ee4d-115">**InfoSource name**</span></span>  
 <span data-ttu-id="1ee4d-116">Geben Sie einen Namen für die neue InfoSource ein.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-116">Enter a name for the new InfoSource.</span></span>  
  
 <span data-ttu-id="1ee4d-117">**Kurzbeschreibung**</span><span class="sxs-lookup"><span data-stu-id="1ee4d-117">**Short description**</span></span>  
 <span data-ttu-id="1ee4d-118">Geben Sie eine kurze Beschreibung für die neue InfoSource ein.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-118">Enter a short description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="1ee4d-119">**Lange Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1ee4d-119">**Long description**</span></span>  
 <span data-ttu-id="1ee4d-120">Geben Sie eine lange Beschreibung für die neue InfoSource ein.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-120">Enter a long description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="1ee4d-121">**Quellsystem**</span><span class="sxs-lookup"><span data-stu-id="1ee4d-121">**Source system**</span></span>  
 <span data-ttu-id="1ee4d-122">Wählen Sie das Quellsystem aus, das der InfoSource zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-122">Select the source system associated with the InfoSource.</span></span>  
  
 <span data-ttu-id="1ee4d-123">**Speichern und aktivieren**</span><span class="sxs-lookup"><span data-stu-id="1ee4d-123">**Save & Activate**</span></span>  
 <span data-ttu-id="1ee4d-124">Speichern und aktivieren Sie die neue InfoSource.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-124">Save and activate the new InfoSource.</span></span>  
  
## <a name="infosource-transfer-structure-options"></a><span data-ttu-id="1ee4d-125">Optionen für die "InfoSource-Übergangsstruktur"</span><span class="sxs-lookup"><span data-stu-id="1ee4d-125">InfoSource Transfer Structure Options</span></span>  
 <span data-ttu-id="1ee4d-126">Mithilfe der InfoSource-Übergangsstruktur können Sie InfoSources Datenflussspalten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-126">The InfoSource transfer structure lets you associate data flow columns to InfoSources.</span></span>  
  
 <span data-ttu-id="1ee4d-127">**PipelineElement**</span><span class="sxs-lookup"><span data-stu-id="1ee4d-127">**PipelineElement**</span></span>  
 <span data-ttu-id="1ee4d-128">Zeigt die Spalte in der Ausgabe des Datenflusses an, der mit dem SAP BW-Ziel verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-128">Displays the column in the output of the data flow that is connected to the SAP BW destination.</span></span>  
  
 <span data-ttu-id="1ee4d-129">**PipelineDataType**</span><span class="sxs-lookup"><span data-stu-id="1ee4d-129">**PipelineDataType**</span></span>  
 <span data-ttu-id="1ee4d-130">Zeigt den [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Datentyp der Datenflussspalte an.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-130">Displays the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data type of the data flow column.</span></span>  
  
 <span data-ttu-id="1ee4d-131">**Iobject - Suchen**</span><span class="sxs-lookup"><span data-stu-id="1ee4d-131">**Iobject - Search**</span></span>  
 <span data-ttu-id="1ee4d-132">Ordnen Sie der Datenflussspalte in der aktuellen Zeile ein vorhandenes InfoObject zu.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-132">Associate an existing InfoObject to the data flow column in the current row.</span></span> <span data-ttu-id="1ee4d-133">Um diese Zuordnung zu erstellen, klicken Sie auf **Suchen**und verwenden dann das Dialogfeld **InfoObject suchen** , um das vorhandene InfoObject auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-133">To make this association, click **Search**, and then use the **Look Up InfoObject** dialog box to select the existing InfoObject.</span></span> <span data-ttu-id="1ee4d-134">Weitere Informationen zu diesem Dialogfeld finden Sie unter [Look Up InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="1ee4d-134">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="1ee4d-135">Nachdem Sie ein vorhandenes InfoObject ausgewählt haben, werden die Spalten **InfoObject** und **Typ** von der Komponente mit den ausgewählten Werten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-135">After you select an existing InfoObject, the component populates the **InfoObject** and **Type** columns with the selected values.</span></span>  
  
 <span data-ttu-id="1ee4d-136">**Iobject - Neu**</span><span class="sxs-lookup"><span data-stu-id="1ee4d-136">**Iobject - New**</span></span>  
 <span data-ttu-id="1ee4d-137">Erstellen Sie ein neues InfoObject, und ordnen Sie dieses neue InfoObject der Datenflussspalte in der aktuellen Zeile zu.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-137">Create a new InfoObject and associate this new InfoObect to the data flow column in the current row.</span></span> <span data-ttu-id="1ee4d-138">Um das neue InfoObject zu erstellen, klicken Sie auf **Neu**und erstellen dann das InfoObject im Dialogfeld **Neues InfoObject erstellen** .</span><span class="sxs-lookup"><span data-stu-id="1ee4d-138">To create the new InfoObject, click **New**, and then use the **Create New InfoObject** dialog box to create the InfoObject.</span></span> <span data-ttu-id="1ee4d-139">Weitere Informationen zu diesem Dialogfeld finden Sie unter [Create New InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="1ee4d-139">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>  
  
 <span data-ttu-id="1ee4d-140">Nachdem Sie ein neues InfoObject erstellt haben, werden die Spalten **InfoObject** und **Typ** mit den neuen Werten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-140">After you create a new InfoObject, the component populates the **InfoObject** and **Type** columns with the new values.</span></span>  
  
 <span data-ttu-id="1ee4d-141">**Iobject - Entfernen**</span><span class="sxs-lookup"><span data-stu-id="1ee4d-141">**Iobject - Remove**</span></span>  
 <span data-ttu-id="1ee4d-142">Heben Sie die Zuordnung zwischen dem InfoObject und der Datenflussspalte für die aktuelle Zeile auf.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-142">Remove the association between the InfoObject and the data flow column for the current row.</span></span> <span data-ttu-id="1ee4d-143">Um die Zuordnung aufzuheben, klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-143">To remove this association, click **Remove**.</span></span>  
  
 <span data-ttu-id="1ee4d-144">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="1ee4d-144">**InfoObject**</span></span>  
 <span data-ttu-id="1ee4d-145">Zeigt den Namen des InfoObject an, das der Datenflussspalte zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-145">Displays the name of the InfoObject that is associated with the data flow column.</span></span>  
  
 <span data-ttu-id="1ee4d-146">**Typ**</span><span class="sxs-lookup"><span data-stu-id="1ee4d-146">**Type**</span></span>  
 <span data-ttu-id="1ee4d-147">Zeigt den Typ des InfoObject an, das der Datenflussspalte zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-147">Displays the type of the InfoObject that is associated with the data flow column.</span></span> <span data-ttu-id="1ee4d-148">In der folgenden Tabelle sind die möglichen Werte für den Typ aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-148">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="1ee4d-149">value</span><span class="sxs-lookup"><span data-stu-id="1ee4d-149">Value</span></span>|<span data-ttu-id="1ee4d-150">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1ee4d-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1ee4d-151">CHA</span><span class="sxs-lookup"><span data-stu-id="1ee4d-151">CHA</span></span>|<span data-ttu-id="1ee4d-152">Merkmale</span><span class="sxs-lookup"><span data-stu-id="1ee4d-152">Characteristics</span></span>|  
|<span data-ttu-id="1ee4d-153">UNI</span><span class="sxs-lookup"><span data-stu-id="1ee4d-153">UNI</span></span>|<span data-ttu-id="1ee4d-154">Units</span><span class="sxs-lookup"><span data-stu-id="1ee4d-154">Units</span></span>|  
|<span data-ttu-id="1ee4d-155">KYF</span><span class="sxs-lookup"><span data-stu-id="1ee4d-155">KYF</span></span>|<span data-ttu-id="1ee4d-156">Kennzahlen</span><span class="sxs-lookup"><span data-stu-id="1ee4d-156">Key figures</span></span>|  
|<span data-ttu-id="1ee4d-157">TIM</span><span class="sxs-lookup"><span data-stu-id="1ee4d-157">TIM</span></span>|<span data-ttu-id="1ee4d-158">Zeitmerkmale</span><span class="sxs-lookup"><span data-stu-id="1ee4d-158">Time characteristics</span></span>|  
  
 <span data-ttu-id="1ee4d-159">**Einheitenfeld**</span><span class="sxs-lookup"><span data-stu-id="1ee4d-159">**Unit Field**</span></span>  
 <span data-ttu-id="1ee4d-160">Geben Sie die Einheiten an, die vom InfoObject verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1ee4d-160">Specify the units that the InfoObject will use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ee4d-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ee4d-161">See Also</span></span>  
 <span data-ttu-id="1ee4d-162">[InfoSource erstellen](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="1ee4d-162">[Create InfoSource](create-infosource.md) </span></span>  
 [<span data-ttu-id="1ee4d-163">F1-Hilfe zu Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="1ee4d-163">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
