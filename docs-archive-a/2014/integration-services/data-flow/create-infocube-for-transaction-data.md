---
title: InfoCube für Transaktionsdaten erstellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 673cea01-a260-4fce-a1a0-f73839289805
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a20fe051cfdd3e6afe285279996fcf696a83c21b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695933"
---
# <a name="create-infocube-for-transaction-data"></a><span data-ttu-id="33bc4-102">InfoCube für Transaktionsdaten erstellen</span><span class="sxs-lookup"><span data-stu-id="33bc4-102">Create InfoCube for Transaction Data</span></span>
  <span data-ttu-id="33bc4-103">Verwenden Sie das Dialogfeld **InfoCube für Transaktionsdaten erstellen** , um einen neuen InfoCube für Transaktionsdaten im SAP NetWeaver BW-System zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="33bc4-103">Use the **Create InfoCube for Transaction Data** dialog box to create a new InfoCube for transaction data in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="33bc4-104">Sie können das Dialogfeld **InfoCube für Transaktionsdaten erstellen** im **Ziel-Editor für SAP BW** auf der Seite **Verbindungs-Manager**öffnen.</span><span class="sxs-lookup"><span data-stu-id="33bc4-104">You can open the **Create InfoCube for Transaction Data** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="33bc4-105">Weitere Informationen zum SAP BW-Ziel finden Sie unter [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="33bc4-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="33bc4-106">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="33bc4-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="33bc4-107">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="33bc4-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="33bc4-108">**So öffnen Sie das Dialogfeld "InfoCube für Transaktionsdaten erstellen"**</span><span class="sxs-lookup"><span data-stu-id="33bc4-108">**To open the Create InfoCube for Transaction Data dialog box**</span></span>  
  
1.  <span data-ttu-id="33bc4-109">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket, in dem das SAP BW-Ziel enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="33bc4-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="33bc4-110">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf das SAP BW-Ziel.</span><span class="sxs-lookup"><span data-stu-id="33bc4-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="33bc4-111">Klicken Sie im **Ziel-Editor für SAP BW**auf **Verbindungs-Manager** , um die Seite **Verbindungs-Manager** des Editors zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="33bc4-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="33bc4-112">Wählen Sie auf der Seite **Verbindungs-Manager** im Gruppenfeld **SAP BW-Objekte erstellen** die Option **InfoCube**aus, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="33bc4-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoCube**, and then click **Create**.</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="33bc4-113">Allgemeine Optionen</span><span class="sxs-lookup"><span data-stu-id="33bc4-113">General Options</span></span>  
 <span data-ttu-id="33bc4-114">**InfoCube-Name**</span><span class="sxs-lookup"><span data-stu-id="33bc4-114">**InfoCube name**</span></span>  
 <span data-ttu-id="33bc4-115">Geben Sie einen Namen für den neuen InfoCube ein.</span><span class="sxs-lookup"><span data-stu-id="33bc4-115">Enter a name for the new InfoCube.</span></span>  
  
 <span data-ttu-id="33bc4-116">**Lange Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="33bc4-116">**Long description**</span></span>  
 <span data-ttu-id="33bc4-117">Geben Sie eine Beschreibung für den neuen InfoCube ein.</span><span class="sxs-lookup"><span data-stu-id="33bc4-117">Enter a description for the new InfoCube.</span></span>  
  
 <span data-ttu-id="33bc4-118">**Speichern und aktivieren**</span><span class="sxs-lookup"><span data-stu-id="33bc4-118">**Save & Activate**</span></span>  
 <span data-ttu-id="33bc4-119">Speichern und aktivieren Sie den neuen InfoCube.</span><span class="sxs-lookup"><span data-stu-id="33bc4-119">Save and activate the new InfoCube.</span></span>  
  
## <a name="infocube-transfer-structure-options"></a><span data-ttu-id="33bc4-120">Optionen für die InfoCube-Übergangsstruktur</span><span class="sxs-lookup"><span data-stu-id="33bc4-120">InfoCube Transfer Structure Options</span></span>  
 <span data-ttu-id="33bc4-121">Im Abschnitt für die InfoCube-Übergangsstruktur können Sie InfoObjects Datenflussspalten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="33bc4-121">The InfoCube transfer structure section lets you associate data flow columns to InfoObjects.</span></span>  
  
 <span data-ttu-id="33bc4-122">**PipelineElement**</span><span class="sxs-lookup"><span data-stu-id="33bc4-122">**PipelineElement**</span></span>  
 <span data-ttu-id="33bc4-123">Zeigt die Spalte in der Ausgabe des Datenflusses an, der mit dem SAP BW-Ziel verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="33bc4-123">Displays the column in the output of the data flow that is connected to the SAP BW destination.</span></span>  
  
 <span data-ttu-id="33bc4-124">**PipelineDataType**</span><span class="sxs-lookup"><span data-stu-id="33bc4-124">**PipelineDataType**</span></span>  
 <span data-ttu-id="33bc4-125">Zeigt den Datentyp der Datenflussspalte an.</span><span class="sxs-lookup"><span data-stu-id="33bc4-125">Displays the data type of the data flow column.</span></span>  
  
 <span data-ttu-id="33bc4-126">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="33bc4-126">**InfoObject**</span></span>  
 <span data-ttu-id="33bc4-127">Zeigt den Namen des InfoObject an, das der Datenflussspalte zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="33bc4-127">Displays the name of the InfoObject that is associated with the data flow column.</span></span>  
  
 <span data-ttu-id="33bc4-128">**Typ**</span><span class="sxs-lookup"><span data-stu-id="33bc4-128">**Type**</span></span>  
 <span data-ttu-id="33bc4-129">Zeigt den Typ des InfoObject an, das der Datenflussspalte zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="33bc4-129">Displays the type of the InfoObject that is associated with the data flow column.</span></span> <span data-ttu-id="33bc4-130">In der folgenden Tabelle sind die möglichen Werte für den Typ aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="33bc4-130">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="33bc4-131">value</span><span class="sxs-lookup"><span data-stu-id="33bc4-131">Value</span></span>|<span data-ttu-id="33bc4-132">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="33bc4-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="33bc4-133">CHA</span><span class="sxs-lookup"><span data-stu-id="33bc4-133">CHA</span></span>|<span data-ttu-id="33bc4-134">Merkmale</span><span class="sxs-lookup"><span data-stu-id="33bc4-134">Characteristics</span></span>|  
|<span data-ttu-id="33bc4-135">UNI</span><span class="sxs-lookup"><span data-stu-id="33bc4-135">UNI</span></span>|<span data-ttu-id="33bc4-136">Units</span><span class="sxs-lookup"><span data-stu-id="33bc4-136">Units</span></span>|  
|<span data-ttu-id="33bc4-137">KYF</span><span class="sxs-lookup"><span data-stu-id="33bc4-137">KYF</span></span>|<span data-ttu-id="33bc4-138">Kennzahlen</span><span class="sxs-lookup"><span data-stu-id="33bc4-138">Key figures</span></span>|  
|<span data-ttu-id="33bc4-139">TIM</span><span class="sxs-lookup"><span data-stu-id="33bc4-139">TIM</span></span>|<span data-ttu-id="33bc4-140">Zeitmerkmale</span><span class="sxs-lookup"><span data-stu-id="33bc4-140">Time characteristics</span></span>|  
  
 <span data-ttu-id="33bc4-141">**Iobject - Suchen**</span><span class="sxs-lookup"><span data-stu-id="33bc4-141">**Iobject - Search**</span></span>  
 <span data-ttu-id="33bc4-142">Ordnen Sie der Datenflussspalte der aktuellen Zeile ein vorhandenes InfoObject zu.</span><span class="sxs-lookup"><span data-stu-id="33bc4-142">Associate an existing InfoObject to the data flow column for the current row.</span></span> <span data-ttu-id="33bc4-143">Um diese Zuordnung zu erstellen, klicken Sie auf **Suchen**und verwenden dann das Dialogfeld **InfoObject suchen** , um das vorhandene InfoObject auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="33bc4-143">To make this association, click **Search**, and then use the **Look Up InfoObject** dialog box to select the existing InfoObject.</span></span> <span data-ttu-id="33bc4-144">Weitere Informationen zu diesem Dialogfeld finden Sie unter [Look Up InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="33bc4-144">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="33bc4-145">Nachdem Sie ein vorhandenes InfoObject ausgewählt haben, werden die Spalten **InfoObject** und **Typ** von der Komponente mit den ausgewählten Werten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="33bc4-145">After you select an existing InfoObject, the component populates the **InfoObject** and **Type** columns with the selected values.</span></span>  
  
 <span data-ttu-id="33bc4-146">**Iobject - Neu**</span><span class="sxs-lookup"><span data-stu-id="33bc4-146">**Iobject - New**</span></span>  
 <span data-ttu-id="33bc4-147">Erstellen Sie ein neues InfoObject, und ordnen Sie dieses neue InfoObject der Datenflussspalte in der aktuellen Zeile zu.</span><span class="sxs-lookup"><span data-stu-id="33bc4-147">Create a new InfoObject and associate this new InfoObject to the data flow column in the current row.</span></span> <span data-ttu-id="33bc4-148">Um das neue InfoObject zu erstellen, klicken Sie auf **Neu**und erstellen dann das InfoObject im Dialogfeld **Neues InfoObject erstellen** .</span><span class="sxs-lookup"><span data-stu-id="33bc4-148">To create the new InfoObject, click **New**, and then use the **Create New InfoObject** dialog box to create the InfoObject.</span></span> <span data-ttu-id="33bc4-149">Weitere Informationen zu diesem Dialogfeld finden Sie unter [Create New InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="33bc4-149">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>  
  
 <span data-ttu-id="33bc4-150">Nachdem Sie ein neues InfoObject erstellt haben, werden die Spalten **InfoObject** und **Typ** mit den neuen Werten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="33bc4-150">After you create a new InfoObject, the component populates the **InfoObject** and **Type** columns with the new values.</span></span>  
  
 <span data-ttu-id="33bc4-151">**Iobject - Entfernen**</span><span class="sxs-lookup"><span data-stu-id="33bc4-151">**Iobject - Remove**</span></span>  
 <span data-ttu-id="33bc4-152">Heben Sie die Zuordnung zwischen dem InfoObject und der Datenflussspalte für die aktuelle Zeile auf.</span><span class="sxs-lookup"><span data-stu-id="33bc4-152">Remove the association between the InfoObject and the data flow column for the current row.</span></span> <span data-ttu-id="33bc4-153">Um die Zuordnung aufzuheben, klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="33bc4-153">To remove this association, click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33bc4-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="33bc4-154">See Also</span></span>  
 [<span data-ttu-id="33bc4-155">F1-Hilfe zu Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="33bc4-155">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
