---
title: InfoSource für Masterdaten erstellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b52a9a89-8380-4a02-8a83-dcfb46ae860e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bb90bc5cf27f37dc89df236b765db98088a5804a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695925"
---
# <a name="create-infosource-for-master-data"></a><span data-ttu-id="002a4-102">InfoSource für Masterdaten erstellen</span><span class="sxs-lookup"><span data-stu-id="002a4-102">Create InfoSource for Master Data</span></span>
  <span data-ttu-id="002a4-103">Verwenden Sie das Dialogfeld **InfoSource für Masterdaten erstellen** , um eine neue InfoSource für Masterdaten im SAP NetWeaver BW-System zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="002a4-103">Use the **Create InfoSource for Master Data** dialog box to create a new InfoSource for master data in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="002a4-104">Sie können das Dialogfeld **InfoSource für Masterdaten erstellen** im **Ziel-Editor für SAP BW** auf der Seite **Verbindungs-Manager**öffnen.</span><span class="sxs-lookup"><span data-stu-id="002a4-104">You can open the **Create InfoSource for Master Data** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="002a4-105">Weitere Informationen zum SAP BW-Ziel finden Sie unter [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="002a4-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="002a4-106">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="002a4-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="002a4-107">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="002a4-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="002a4-108">**So öffnen Sie das Dialogfeld "InfoSource für Masterdaten erstellen"**</span><span class="sxs-lookup"><span data-stu-id="002a4-108">**To open the Create InfoSource for Master Data dialog box**</span></span>  
  
1.  <span data-ttu-id="002a4-109">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket, in dem das SAP BW-Ziel enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="002a4-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="002a4-110">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf das SAP BW-Ziel.</span><span class="sxs-lookup"><span data-stu-id="002a4-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="002a4-111">Klicken Sie im **Ziel-Editor für SAP BW**auf **Verbindungs-Manager** , um die Seite **Verbindungs-Manager** des Editors zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="002a4-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="002a4-112">Wählen Sie auf der Seite **Verbindungs-Manager** im Gruppenfeld **SAP BW-Objekte erstellen** die Option **InfoSource**aus, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="002a4-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoSource**, and then click **Create**.</span></span>  
  
5.  <span data-ttu-id="002a4-113">Wählen Sie im Dialogfeld **InfoSource erstellen** die Option **Masterdaten**aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="002a4-113">In the **Create InfoSource** dialog box, select **Master data**, and then click **OK**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="002a4-114">Tastatur</span><span class="sxs-lookup"><span data-stu-id="002a4-114">Options</span></span>  
 <span data-ttu-id="002a4-115">**InfoObject-Name**</span><span class="sxs-lookup"><span data-stu-id="002a4-115">**InfoObject name**</span></span>  
 <span data-ttu-id="002a4-116">Geben Sie den Namen des InfoObject ein, auf dem die neue InfoSource basieren soll.</span><span class="sxs-lookup"><span data-stu-id="002a4-116">Enter the name of the InfoObject on which the new InfoSource should be based.</span></span>  
  
 <span data-ttu-id="002a4-117">**Suchen**</span><span class="sxs-lookup"><span data-stu-id="002a4-117">**Look up**</span></span>  
 <span data-ttu-id="002a4-118">Suchen Sie das InfoObject.</span><span class="sxs-lookup"><span data-stu-id="002a4-118">Look up the InfoObject.</span></span> <span data-ttu-id="002a4-119">Mit dieser Option wird das Dialogfeld **InfoObject suchen** geöffnet, in dem Sie das InfoObject auswählen können.</span><span class="sxs-lookup"><span data-stu-id="002a4-119">This option opens the **Look Up InfoObject** dialog box in which you can select the InfoObject.</span></span> <span data-ttu-id="002a4-120">Weitere Informationen zu diesem Dialogfeld finden Sie unter [Look Up InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="002a4-120">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="002a4-121">Nachdem Sie ein InfoObject ausgewählt haben, wird das Textfeld **InfoObject-Name** mit dem Namen des ausgewählten InfoObject aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="002a4-121">After you select an InfoObject, the component populates the **InfoObject name** text box with the name of the selected InfoObject.</span></span>  
  
 <span data-ttu-id="002a4-122">**Neu**</span><span class="sxs-lookup"><span data-stu-id="002a4-122">**New**</span></span>  
 <span data-ttu-id="002a4-123">Erstellen Sie ein neues InfoObject.</span><span class="sxs-lookup"><span data-stu-id="002a4-123">Create a new InfoObject.</span></span> <span data-ttu-id="002a4-124">Mit dieser Option wird das Dialogfeld **Neues InfoObject erstellen** geöffnet, in dem Sie das neue InfoObject erstellen können.</span><span class="sxs-lookup"><span data-stu-id="002a4-124">This option opens the **Create New InfoObject** dialog box in which you can create the new InfoObject.</span></span> <span data-ttu-id="002a4-125">Weitere Informationen zu diesem Dialogfeld finden Sie unter [Create New InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="002a4-125">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>  
  
 <span data-ttu-id="002a4-126">Nachdem Sie ein InfoObject erstellt haben, wird das Textfeld **InfoObject-Name** mit dem Namen des neuen InfoObject aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="002a4-126">After you create an InfoObject, the component populates the **InfoObject name** text box with the name of the new InfoObject.</span></span>  
  
 <span data-ttu-id="002a4-127">**Kurzbeschreibung**</span><span class="sxs-lookup"><span data-stu-id="002a4-127">**Short description**</span></span>  
 <span data-ttu-id="002a4-128">Geben Sie eine kurze Beschreibung für die neue InfoSource ein.</span><span class="sxs-lookup"><span data-stu-id="002a4-128">Enter a short description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="002a4-129">**Lange Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="002a4-129">**Long description**</span></span>  
 <span data-ttu-id="002a4-130">Geben Sie eine lange Beschreibung für die neue InfoSource ein.</span><span class="sxs-lookup"><span data-stu-id="002a4-130">Enter a long description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="002a4-131">**Quellsystem**</span><span class="sxs-lookup"><span data-stu-id="002a4-131">**Source system**</span></span>  
 <span data-ttu-id="002a4-132">Wählen Sie das Quellsystem aus, das der neuen InfoSource zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="002a4-132">Select the source system to be associated with the new InfoSource.</span></span>  
  
 <span data-ttu-id="002a4-133">**Anwendung**</span><span class="sxs-lookup"><span data-stu-id="002a4-133">**Application**</span></span>  
 <span data-ttu-id="002a4-134">Geben Sie den Namen der Anwendung ein, die der neuen InfoSource zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="002a4-134">Enter the name of the application to be associated with the new InfoSource.</span></span>  
  
 <span data-ttu-id="002a4-135">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="002a4-135">**Attributes**</span></span>  
 <span data-ttu-id="002a4-136">Gibt an, dass sich die Masterdaten aus Attributen zusammensetzen.</span><span class="sxs-lookup"><span data-stu-id="002a4-136">Indicates that the master data consists of attributes.</span></span>  
  
 <span data-ttu-id="002a4-137">**Texte**</span><span class="sxs-lookup"><span data-stu-id="002a4-137">**Texts**</span></span>  
 <span data-ttu-id="002a4-138">Gibt an, dass sich die Masterdaten aus Attributen zusammensetzen.</span><span class="sxs-lookup"><span data-stu-id="002a4-138">Indicates that the master data consists of attributes.</span></span>  
  
 <span data-ttu-id="002a4-139">**Speichern und aktivieren**</span><span class="sxs-lookup"><span data-stu-id="002a4-139">**Save & Activate**</span></span>  
 <span data-ttu-id="002a4-140">Speichern und aktivieren Sie die neue InfoSource.</span><span class="sxs-lookup"><span data-stu-id="002a4-140">Save and activate the new InfoSource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="002a4-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="002a4-141">See Also</span></span>  
 <span data-ttu-id="002a4-142">[InfoSource erstellen](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="002a4-142">[Create InfoSource](create-infosource.md) </span></span>  
 [<span data-ttu-id="002a4-143">F1-Hilfe zu Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="002a4-143">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
