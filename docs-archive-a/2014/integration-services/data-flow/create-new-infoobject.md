---
title: Neues InfoObject erstellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3587a633-1c0b-4d63-a22a-6b2b93923c3a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 022f2d1e3fe10ae037ea379a02a18845b3a36107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621613"
---
# <a name="create-new-infoobject"></a><span data-ttu-id="12674-102">Neues InfoObject erstellen</span><span class="sxs-lookup"><span data-stu-id="12674-102">Create New InfoObject</span></span>
  <span data-ttu-id="12674-103">Verwenden Sie das Dialogfeld **Neues InfoObject erstellen** , um ein neues InfoObject im SAP NetWeaver BW-System zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="12674-103">Use the **Create New InfoObject** dialog box to create a new InfoObject in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="12674-104">Sie können das Dialogfeld **InfoObject erstellen** über die Seite **Verbindungs-Manager** im **Ziel-Editor für SAP BW**öffnen.</span><span class="sxs-lookup"><span data-stu-id="12674-104">You can open the **Create InfoObject** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="12674-105">Weitere Informationen zum SAP BW-Ziel finden Sie unter [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="12674-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="12674-106">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="12674-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="12674-107">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="12674-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="12674-108">**So öffnen Sie das Dialogfeld "Neues InfoObject erstellen"**</span><span class="sxs-lookup"><span data-stu-id="12674-108">**To open the Create New InfoObject dialog box**</span></span>  
  
1.  <span data-ttu-id="12674-109">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket, in dem das SAP BW-Ziel enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="12674-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="12674-110">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf das SAP BW-Ziel.</span><span class="sxs-lookup"><span data-stu-id="12674-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="12674-111">Klicken Sie im **Ziel-Editor für SAP BW**auf **Verbindungs-Manager** , um die Seite **Verbindungs-Manager** des Editors zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="12674-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="12674-112">Führen Sie auf der Seite **Verbindungs-Manager** im Gruppenfeld **SAP BW-Objekte erstellen** einen der folgenden Schritte aus, um ein InfoObject zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="12674-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, do one of the following steps to create an InfoObject:</span></span>  
  
    1.  <span data-ttu-id="12674-113">Um ein InfoObject direkt zu erstellen, wählen Sie **InfoObject**aus, und klicken Sie dann auf **Erstellen** , um das Dialogfeld **Neues InfoObject erstellen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="12674-113">To create an InfoObject directly, select **InfoObject**, and then click **Create** to open the **Create New InfoObject** dialog box.</span></span>  
  
    2.  <span data-ttu-id="12674-114">Um ein InfoObject beim Erstellen eines InfoCube anzulegen, wählen Sie **InfoCube**aus und klicken dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="12674-114">To create an InfoObject while creating an InfoCube, select **InfoCube**, and then click **Create**.</span></span> <span data-ttu-id="12674-115">Wählen Sie im Dialogfeld **InfoCube für Transaktionsdaten erstellen** in der Spalte **IObject** für eine der Zeilen in der Liste **Erstellen** aus, um das Dialogfeld **Neues InfoObject erstellen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="12674-115">In the **Create InfoCube for Transaction Data** dialog box, in the **IObject** column for one of the rows in the list, select **Create** to open the **Create New InfoObject** dialog box.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="12674-116">Jede Zeile in der Tabelle stellt eine Spalte im Datenfluss des Pakets dar.</span><span class="sxs-lookup"><span data-stu-id="12674-116">Each row in the table represents a column in the data flow of the package.</span></span>  
  
    3.  <span data-ttu-id="12674-117">Um ein InfoObject zu erstellen, während eine InfoSouce für Transaktionsdaten erstellt wird, wählen Sie **InfoSource**aus und klicken dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="12674-117">To create an InfoObject while creating an InfoSouce for transactional data, select **InfoSource**, and then click **Create**.</span></span> <span data-ttu-id="12674-118">Wählen Sie im Dialogfeld **InfoSource erstellen** die Option **Transaktionsdaten**aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="12674-118">In the **Create InfoSource** dialog box, select **Transaction Data**, and then click **OK**.</span></span> <span data-ttu-id="12674-119">Wählen Sie im Dialogfeld **InfoSource für Transaktionsdaten erstellen** in der Spalte **IObject** für eine der Zeilen in der Liste **Erstellen** aus, um das Dialogfeld **Neues InfoObject erstellen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="12674-119">In the **Create InfoSource for Transaction Data** dialog box, in the **IObject** column for one of the rows in the list, select **Create** to open the **Create New InfoObject** dialog box.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="12674-120">Jede Zeile in der Tabelle stellt eine Spalte im Datenfluss des Pakets dar.</span><span class="sxs-lookup"><span data-stu-id="12674-120">Each row in the table represents a column in the data flow of the package.</span></span>  
  
    4.  <span data-ttu-id="12674-121">Um ein InfoObject zu erstellen, während eine InfoSouce für Masterdaten erstellt wird, wählen Sie **InfoSource**aus und klicken dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="12674-121">To create an InfoObject while creating an InfoSource for master data, select **InfoSource**, and then click **Create**.</span></span> <span data-ttu-id="12674-122">Wählen Sie im Dialogfeld **InfoSource erstellen** die Option **Masterdaten**aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="12674-122">In the **Create InfoSource** dialog box, select **Master Data**, and then click **OK**.</span></span> <span data-ttu-id="12674-123">Klicken Sie im Dialogfeld **InfoSource für Masterdaten erstellen** auf **Neu** , um das Dialogfeld **Neues InfoObject erstellen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="12674-123">In the **Create InfoSource for Master Data** dialog box, click **New** to open the **Create New InfoObject** dialog box.</span></span>  
  
 <span data-ttu-id="12674-124">Sie können das Dialogfeld **Neues InfoObject erstellen** auch öffnen, indem Sie im Abschnitt **Attribute** des Dialogfelds **Neues InfoObject erstellen** auf **Neu** klicken.</span><span class="sxs-lookup"><span data-stu-id="12674-124">You can also open the **Create New InfoObject** dialog box by clicking **New** in the **Attributes** section of the **Create New InfoObject** dialog box.</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="12674-125">Allgemeine Optionen</span><span class="sxs-lookup"><span data-stu-id="12674-125">General Options</span></span>  
 <span data-ttu-id="12674-126">**Merkmal**</span><span class="sxs-lookup"><span data-stu-id="12674-126">**Characteristic**</span></span>  
 <span data-ttu-id="12674-127">Erstellen Sie ein InfoObject, das die Dimensionsdaten darstellt.</span><span class="sxs-lookup"><span data-stu-id="12674-127">Create an InfoObject that represents dimension data.</span></span>  
  
 <span data-ttu-id="12674-128">**Kennzahl**</span><span class="sxs-lookup"><span data-stu-id="12674-128">**Key figure**</span></span>  
 <span data-ttu-id="12674-129">Erstellen Sie ein InfoObject, das die Faktendaten darstellt.</span><span class="sxs-lookup"><span data-stu-id="12674-129">Create an InfoObject that represents fact data.</span></span>  
  
 <span data-ttu-id="12674-130">**InfoObject-Name**</span><span class="sxs-lookup"><span data-stu-id="12674-130">**InfoObject name**</span></span>  
 <span data-ttu-id="12674-131">Geben Sie einen Namen für das InfoObject ein.</span><span class="sxs-lookup"><span data-stu-id="12674-131">Enter a name for the InfoObject.</span></span>  
  
 <span data-ttu-id="12674-132">**Kurzbeschreibung**</span><span class="sxs-lookup"><span data-stu-id="12674-132">**Short description**</span></span>  
 <span data-ttu-id="12674-133">Geben Sie eine kurze Beschreibung für das InfoObject ein.</span><span class="sxs-lookup"><span data-stu-id="12674-133">Enter a short description for the InfoObject.</span></span>  
  
 <span data-ttu-id="12674-134">**Lange Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="12674-134">**Long description**</span></span>  
 <span data-ttu-id="12674-135">Geben Sie eine lange Beschreibung für das InfoObject ein.</span><span class="sxs-lookup"><span data-stu-id="12674-135">Enter a long description for the InfoObject.</span></span>  
  
 <span data-ttu-id="12674-136">**Verfügt über Masterdaten**</span><span class="sxs-lookup"><span data-stu-id="12674-136">**Has master data**</span></span>  
 <span data-ttu-id="12674-137">Geben Sie an, dass das InfoObject Masterdaten in Form von Attributen, Texten oder Hierarchien enthält.</span><span class="sxs-lookup"><span data-stu-id="12674-137">Indicate that the InfoObject contains master data in the form of attributes, texts, or hierarchies.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12674-138">Wählen Sie diese Option aus, wenn das InfoObject Dimensionsdaten darstellt und Sie die Option **Merkmal** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="12674-138">Select this option if the InfoObject represents dimensional data and you have selected the **Characteristic** option.</span></span>  
  
 <span data-ttu-id="12674-139">**Kleinbuchstaben zulassen**</span><span class="sxs-lookup"><span data-stu-id="12674-139">**Allow lower-case characters**</span></span>  
 <span data-ttu-id="12674-140">Lassen Sie Kleinbuchstaben in den InfoObject-Daten zu.</span><span class="sxs-lookup"><span data-stu-id="12674-140">Allow lower-case characters in the InfoObject data.</span></span>  
  
 <span data-ttu-id="12674-141">**Speichern und aktivieren**</span><span class="sxs-lookup"><span data-stu-id="12674-141">**Save & Activate**</span></span>  
 <span data-ttu-id="12674-142">Speichern und aktivieren Sie das neue InfoObject.</span><span class="sxs-lookup"><span data-stu-id="12674-142">Save and active the new InfoObject.</span></span>  
  
## <a name="data-type-options"></a><span data-ttu-id="12674-143">Optionen für "Datentyp"</span><span class="sxs-lookup"><span data-stu-id="12674-143">Data Type Options</span></span>  
 <span data-ttu-id="12674-144">**CHAR - Zeichenfolge**</span><span class="sxs-lookup"><span data-stu-id="12674-144">**CHAR - Character String**</span></span>  
 <span data-ttu-id="12674-145">Gibt an, dass das InfoObject Zeichendaten enthält.</span><span class="sxs-lookup"><span data-stu-id="12674-145">Indicates that the InfoObject contains character data.</span></span>  
  
 <span data-ttu-id="12674-146">**NUMC - Numerische Zeichenfolge**</span><span class="sxs-lookup"><span data-stu-id="12674-146">**NUMC - Numeric String**</span></span>  
 <span data-ttu-id="12674-147">Gibt an, dass das InfoObject numerische Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="12674-147">Indicates that the InfoObject contains numeric data.</span></span>  
  
 <span data-ttu-id="12674-148">**DATS - Datum (JJJJMMTT)**</span><span class="sxs-lookup"><span data-stu-id="12674-148">**DATS - Date (YYYYMMDD)**</span></span>  
 <span data-ttu-id="12674-149">Gibt an, dass das InfoObject Datumsangaben enthält.</span><span class="sxs-lookup"><span data-stu-id="12674-149">Indicates that the InfoObject contains date data.</span></span>  
  
 <span data-ttu-id="12674-150">**TIMS - Zeit (HHMMSS)**</span><span class="sxs-lookup"><span data-stu-id="12674-150">**TIMS - Time (HHMMSS)**</span></span>  
 <span data-ttu-id="12674-151">Gibt an, dass das InfoObject Uhrzeitdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="12674-151">Indicates that the InfoObject contains time data.</span></span>  
  
 <span data-ttu-id="12674-152">**Länge**</span><span class="sxs-lookup"><span data-stu-id="12674-152">**Length**</span></span>  
 <span data-ttu-id="12674-153">Geben Sie die Länge der Daten ein.</span><span class="sxs-lookup"><span data-stu-id="12674-153">Enter the length of the data.</span></span>  
  
## <a name="text-options"></a><span data-ttu-id="12674-154">Optionen für "Text"</span><span class="sxs-lookup"><span data-stu-id="12674-154">Text Options</span></span>  
 <span data-ttu-id="12674-155">**Mit Texten**</span><span class="sxs-lookup"><span data-stu-id="12674-155">**With Texts**</span></span>  
 <span data-ttu-id="12674-156">Gibt an, dass das InfoObject Texte enthält.</span><span class="sxs-lookup"><span data-stu-id="12674-156">Indicate that the InfoObject contains texts.</span></span>  
  
 <span data-ttu-id="12674-157">**Kurzer Text**</span><span class="sxs-lookup"><span data-stu-id="12674-157">**Short Text**</span></span>  
 <span data-ttu-id="12674-158">Gibt an, dass das InfoObject kurze Texte enthält.</span><span class="sxs-lookup"><span data-stu-id="12674-158">Indicates that the InfoObject contains short texts.</span></span>  
  
 <span data-ttu-id="12674-159">**Mittellanger Text**</span><span class="sxs-lookup"><span data-stu-id="12674-159">**Medium Text**</span></span>  
 <span data-ttu-id="12674-160">Gibt an, dass das InfoObject mittellange Texte enthält.</span><span class="sxs-lookup"><span data-stu-id="12674-160">Indicates that the InfoObject contains medium texts.</span></span>  
  
 <span data-ttu-id="12674-161">**Langer Text**</span><span class="sxs-lookup"><span data-stu-id="12674-161">**Long Text**</span></span>  
 <span data-ttu-id="12674-162">Gibt an, dass das InfoObject lange Texte enthält.</span><span class="sxs-lookup"><span data-stu-id="12674-162">Indicates that the InfoObject contains long texts.</span></span>  
  
 <span data-ttu-id="12674-163">**Sprachenabhängiger Text**</span><span class="sxs-lookup"><span data-stu-id="12674-163">**Text Language-Dependent**</span></span>  
 <span data-ttu-id="12674-164">Gibt an, dass die Texte sprachabhängig sind.</span><span class="sxs-lookup"><span data-stu-id="12674-164">Indicates that the texts are language-dependent.</span></span>  
  
 <span data-ttu-id="12674-165">**Zeitabhängiger Text**</span><span class="sxs-lookup"><span data-stu-id="12674-165">**Text Time-Dependent**</span></span>  
 <span data-ttu-id="12674-166">Gibt an, dass die Texte zeitabhängig sind.</span><span class="sxs-lookup"><span data-stu-id="12674-166">Indicates that the texts are time-dependent.</span></span>  
  
## <a name="attributes-section"></a><span data-ttu-id="12674-167">Abschnitt "Attribute"</span><span class="sxs-lookup"><span data-stu-id="12674-167">Attributes Section</span></span>  
 <span data-ttu-id="12674-168">Der Abschnitt **Attribute** enthält eine Liste der Attribute für das InfoObject sowie die Optionen, mit denen Sie Listenattribute hinzufügen und entfernen können.</span><span class="sxs-lookup"><span data-stu-id="12674-168">The **Attributes** section consists of a list of attributes for the InfoObject, and the options that let you add and remove attributes from the list.</span></span>  
  
### <a name="attributes-list"></a><span data-ttu-id="12674-169">Liste "Attribute"</span><span class="sxs-lookup"><span data-stu-id="12674-169">Attributes List</span></span>  
 <span data-ttu-id="12674-170">Die Liste **Attribute** zeigt die Attribute des erstellten InfoObject an.</span><span class="sxs-lookup"><span data-stu-id="12674-170">The **Attributes** list displays the attributes of the InfoObject that you are creating.</span></span> <span data-ttu-id="12674-171">Die Liste **Attribute** verfügt über die folgenden Spaltenüberschriften:</span><span class="sxs-lookup"><span data-stu-id="12674-171">The **Attributes** list has the following column headings:</span></span>  
  
 <span data-ttu-id="12674-172">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="12674-172">**InfoObject**</span></span>  
 <span data-ttu-id="12674-173">Zeigt den InfoObject-Namen an.</span><span class="sxs-lookup"><span data-stu-id="12674-173">View the name of the InfoObject.</span></span>  
  
 <span data-ttu-id="12674-174">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="12674-174">**Description**</span></span>  
 <span data-ttu-id="12674-175">Zeigt die InfoObject-Beschreibung an.</span><span class="sxs-lookup"><span data-stu-id="12674-175">View the description of the InfoObject.</span></span>  
  
 <span data-ttu-id="12674-176">**InfoObject-Typ**</span><span class="sxs-lookup"><span data-stu-id="12674-176">**InfoObject Type**</span></span>  
 <span data-ttu-id="12674-177">Zeigt den InfoObject-Typ an.</span><span class="sxs-lookup"><span data-stu-id="12674-177">View the type of the InfoObject.</span></span> <span data-ttu-id="12674-178">In der folgenden Tabelle sind die möglichen Werte für den Typ aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="12674-178">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="12674-179">value</span><span class="sxs-lookup"><span data-stu-id="12674-179">Value</span></span>|<span data-ttu-id="12674-180">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="12674-180">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="12674-181">CHA</span><span class="sxs-lookup"><span data-stu-id="12674-181">CHA</span></span>|<span data-ttu-id="12674-182">Merkmale</span><span class="sxs-lookup"><span data-stu-id="12674-182">Characteristics</span></span>|  
|<span data-ttu-id="12674-183">KYF</span><span class="sxs-lookup"><span data-stu-id="12674-183">KYF</span></span>|<span data-ttu-id="12674-184">Kennzahlen</span><span class="sxs-lookup"><span data-stu-id="12674-184">Key figures</span></span>|  
|<span data-ttu-id="12674-185">UNI</span><span class="sxs-lookup"><span data-stu-id="12674-185">UNI</span></span>|<span data-ttu-id="12674-186">Units</span><span class="sxs-lookup"><span data-stu-id="12674-186">Units</span></span>|  
|<span data-ttu-id="12674-187">TIM</span><span class="sxs-lookup"><span data-stu-id="12674-187">TIM</span></span>|<span data-ttu-id="12674-188">Zeitmerkmale</span><span class="sxs-lookup"><span data-stu-id="12674-188">Time characteristics</span></span>|  
  
### <a name="attributes-options"></a><span data-ttu-id="12674-189">Optionen für "Attribute"</span><span class="sxs-lookup"><span data-stu-id="12674-189">Attributes Options</span></span>  
 <span data-ttu-id="12674-190">Verwenden Sie die folgenden Optionen, um Attribute für ein erstelltes InfoObject hinzuzufügen und zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="12674-190">Use the following options to add and remove attributes for the InfoObject that you are creating:</span></span>  
  
 <span data-ttu-id="12674-191">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="12674-191">**Add**</span></span>  
 <span data-ttu-id="12674-192">Fügen Sie ein bestehendes InfoObject als Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="12674-192">Add an existing InfoObject as an attribute.</span></span>  
  
 <span data-ttu-id="12674-193">Um ein vorhandenes InfoObject hinzuzufügen, klicken Sie auf Hinzufügen und verwenden dann das Dialogfeld **InfoObject suchen** für die Suche nach dem InfoObject.</span><span class="sxs-lookup"><span data-stu-id="12674-193">To add an existing InfoObject, click Add, and then use the **Look Up InfoObject** dialog box to find the InfoObject.</span></span> <span data-ttu-id="12674-194">Weitere Informationen zu diesem Dialogfeld finden Sie unter [Look Up InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="12674-194">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="12674-195">**Neu**</span><span class="sxs-lookup"><span data-stu-id="12674-195">**New**</span></span>  
 <span data-ttu-id="12674-196">Fügt ein neues InfoObject als Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="12674-196">Add a new InfoObject as an attribute.</span></span>  
  
 <span data-ttu-id="12674-197">Um ein neues InfoObject zu erstellen und hinzuzufügen, klicken Sie auf Neu und verwenden dann eine neue Instanz des Dialogfelds **Neues InfoObject erstellen** , um das neue InfoObject zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="12674-197">To create and add a new InfoObject, click New, and then use a new instance of the **Create New InfoObject** dialog box to create the new InfoObject.</span></span>  
  
 <span data-ttu-id="12674-198">**Remove**</span><span class="sxs-lookup"><span data-stu-id="12674-198">**Remove**</span></span>  
 <span data-ttu-id="12674-199">Entfernt das ausgewählte InfoObject aus der Liste **Attribute** .</span><span class="sxs-lookup"><span data-stu-id="12674-199">Remove the selected InfoObject from the **Attributes** list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12674-200">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="12674-200">See Also</span></span>  
 <span data-ttu-id="12674-201">[InfoCube für Transaktionsdaten erstellen](create-infocube-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="12674-201">[Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md) </span></span>  
 <span data-ttu-id="12674-202">[InfoSource erstellen](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="12674-202">[Create InfoSource](create-infosource.md) </span></span>  
 <span data-ttu-id="12674-203">[InfoSource für Transaktionsdaten erstellen](create-infosource-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="12674-203">[Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) </span></span>  
 <span data-ttu-id="12674-204">[InfoSource für Masterdaten erstellen](create-infosource-for-master-data.md) </span><span class="sxs-lookup"><span data-stu-id="12674-204">[Create InfoSource for Master Data](create-infosource-for-master-data.md) </span></span>  
 [<span data-ttu-id="12674-205">F1-Hilfe zu Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="12674-205">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
