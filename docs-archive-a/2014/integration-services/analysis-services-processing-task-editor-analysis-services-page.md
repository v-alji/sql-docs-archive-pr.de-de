---
title: Editor für den Analysis Services Verarbeitungs Task (Seite Analysis Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.asprocessingtask.as.f1
helpviewer_keywords:
- Analysis Services Processing Task Editor
ms.assetid: 5612be78-57cf-4e4e-92cf-6bfa9f971040
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aabcfe286b40f58b429227654107d58e8a4ee837
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615523"
---
# <a name="analysis-services-processing-task-editor-analysis-services-page"></a><span data-ttu-id="188da-102">Editor für den Analysis Services-Verarbeitungstask (Seite Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="188da-102">Analysis Services Processing Task Editor (Analysis Services Page)</span></span>
  <span data-ttu-id="188da-103">Auf der Seite **Analysis Services** des Dialogfelds **Editor für den Analysis Services-Verarbeitungstask** können Sie den Analysis Services-Verbindungs-Manager angeben, die zu verarbeitenden Analyseobjekte auswählen und die Verarbeitungs- und Fehlerbehandlungsoptionen festlegen.</span><span class="sxs-lookup"><span data-stu-id="188da-103">Use the **Analysis Services** page of the **Analysis Services Processing Task Editor** dialog box to specify an Analysis Services connection manager, select the analytic objects to process, and set processing and error handling options.</span></span>  
  
 <span data-ttu-id="188da-104">Beim Verarbeiten von tabellarischen Modellen müssen Sie Folgendes berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="188da-104">When processing tabular models, keep the following in mind:</span></span>  
  
1.  <span data-ttu-id="188da-105">Sie können keine Auswirkungsanalyse auf tabellarische Modelle ausführen.</span><span class="sxs-lookup"><span data-stu-id="188da-105">You cannot perform impact analysis on tabular models.</span></span>  
  
2.  <span data-ttu-id="188da-106">Einige Verarbeitungsoptionen für den tabellarischen Modus werden nicht verfügbar gemacht, z. B. "Defragmentierung verarbeiten" und "Neuberechnung verarbeiten".</span><span class="sxs-lookup"><span data-stu-id="188da-106">Some processing options for tabular mode are not exposed, such as Process Defrag and Process Recalc.</span></span> <span data-ttu-id="188da-107">Sie können diese Funktionen mithilfe des Execute DDL-Tasks ausführen.</span><span class="sxs-lookup"><span data-stu-id="188da-107">You can perform these functions by using the Execute DDL task.</span></span>  
  
3.  <span data-ttu-id="188da-108">Einige bereitgestellte Verarbeitungsoptionen, beispielsweise Verarbeitungsindizes, eignen sich nicht für tabellarische Modelle und sollten daher nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="188da-108">Some processing options provided, such as process indexes, are not appropriate for tabular models and should not be used.</span></span>  
  
4.  <span data-ttu-id="188da-109">Batcheinstellungen werden für tabellarische Modelle ignoriert.</span><span class="sxs-lookup"><span data-stu-id="188da-109">Batch settings are ignored for tabular models.</span></span>  
  
 <span data-ttu-id="188da-110">Informationen, um sich mit diesem Thema vertraut zu machen, finden Sie unter [Analysis Services Processing Task](control-flow/analysis-services-processing-task.md).</span><span class="sxs-lookup"><span data-stu-id="188da-110">To learn about this task, see [Analysis Services Processing Task](control-flow/analysis-services-processing-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="188da-111">Tastatur</span><span class="sxs-lookup"><span data-stu-id="188da-111">Options</span></span>  
 <span data-ttu-id="188da-112">**Analysis Services Verbindungs-Manager**</span><span class="sxs-lookup"><span data-stu-id="188da-112">**Analysis Services connection manager**</span></span>  
 <span data-ttu-id="188da-113">Wählen Sie einen vorhandenen Analysis Services-Verbindungs-Manager aus der Liste aus, oder klicken Sie auf **Neu** , um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="188da-113">Select an existing Analysis Services connection manager in the list or click **New** to create a new connection manager.</span></span>  
  
 <span data-ttu-id="188da-114">**Neu**</span><span class="sxs-lookup"><span data-stu-id="188da-114">**New**</span></span>  
 <span data-ttu-id="188da-115">Erstellen Sie einen neuen Analysis Services-Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="188da-115">Create a new Analysis Services connection manager.</span></span>  
  
 <span data-ttu-id="188da-116">**Verwandte Themen:** [Analysis Services Connection Manager](connection-manager/analysis-services-connection-manager.md), [Referenz zur Benutzeroberfläche des Dialogfelds „Analysis Services-Verbindungs-Manager hinzufügen“](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md)</span><span class="sxs-lookup"><span data-stu-id="188da-116">**Related Topics:** [Analysis Services Connection Manager](connection-manager/analysis-services-connection-manager.md), [Add Analysis Services Connection Manager Dialog Box UI Reference](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md)</span></span>  
  
 <span data-ttu-id="188da-117">**Objektliste**</span><span class="sxs-lookup"><span data-stu-id="188da-117">**Object list**</span></span>  
 |<span data-ttu-id="188da-118">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="188da-118">Property</span></span>|<span data-ttu-id="188da-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="188da-119">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="188da-120">**Objektnamen**</span><span class="sxs-lookup"><span data-stu-id="188da-120">**Object Name**</span></span>|<span data-ttu-id="188da-121">Listet die angegebenen Objektnamen auf.</span><span class="sxs-lookup"><span data-stu-id="188da-121">Lists the specified object names.</span></span>|  
|<span data-ttu-id="188da-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="188da-122">**Type**</span></span>|<span data-ttu-id="188da-123">Listet die Typen der angegebenen Objekte auf.</span><span class="sxs-lookup"><span data-stu-id="188da-123">Lists the types of the specified objects.</span></span>|  
|<span data-ttu-id="188da-124">**Verarbeitungsoptionen**</span><span class="sxs-lookup"><span data-stu-id="188da-124">**Process Options**</span></span>|<span data-ttu-id="188da-125">Wählen Sie eine Verarbeitungsoption in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="188da-125">Select a processing option in the list.</span></span><br /><br /> <span data-ttu-id="188da-126">**Verwandte Themen**: [Verarbeitung von mehrdimensionalen Modell Objekten](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-a-multidimensional-model-analysis-services)</span><span class="sxs-lookup"><span data-stu-id="188da-126">**Related Topics**: [Multidimensional Model Object Processing](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-a-multidimensional-model-analysis-services)</span></span>|  
|<span data-ttu-id="188da-127">**Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="188da-127">**Settings**</span></span>|<span data-ttu-id="188da-128">Listet die Verarbeitungseinstellungen für die angegebenen Objekte auf.</span><span class="sxs-lookup"><span data-stu-id="188da-128">Lists processing settings for the specified objects.</span></span>|  
  
 <span data-ttu-id="188da-129">**Add**</span><span class="sxs-lookup"><span data-stu-id="188da-129">**Add**</span></span>  
 <span data-ttu-id="188da-130">Fügen Sie der Liste ein [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="188da-130">Add an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object to the list.</span></span>  
  
 <span data-ttu-id="188da-131">**Entfernen**</span><span class="sxs-lookup"><span data-stu-id="188da-131">**Remove**</span></span>  
 <span data-ttu-id="188da-132">Wählen Sie ein Objekt aus, und klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="188da-132">Select an object, and then click **Delete**.</span></span>  
  
 <span data-ttu-id="188da-133">**Auswirkungsanalyse**</span><span class="sxs-lookup"><span data-stu-id="188da-133">**Impact Analysis**</span></span>  
 <span data-ttu-id="188da-134">Führen Sie für das ausgewählte Objekt eine Auswirkungsanalyse aus.</span><span class="sxs-lookup"><span data-stu-id="188da-134">Perform impact analysis on the selected object.</span></span>  
  
 <span data-ttu-id="188da-135">**Verwandte Themen:** [Dialogfeld „Auswirkungsanalyse“ &#40;Analysis Services – Mehrdimensionale Daten&#41;](../../2014/analysis-services/impact-analysis-dialog-box-analysis-services-multidimensional-data.md)</span><span class="sxs-lookup"><span data-stu-id="188da-135">**Related Topics:** [Impact Analysis Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](../../2014/analysis-services/impact-analysis-dialog-box-analysis-services-multidimensional-data.md)</span></span>  
  
 <span data-ttu-id="188da-136">**Zusammenfassung der Batcheinstellungen**</span><span class="sxs-lookup"><span data-stu-id="188da-136">**Batch Settings Summary**</span></span>  
 |<span data-ttu-id="188da-137">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="188da-137">Property</span></span>|<span data-ttu-id="188da-138">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="188da-138">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="188da-139">**Verarbeitungsreihenfolge**</span><span class="sxs-lookup"><span data-stu-id="188da-139">**Processing order**</span></span>|<span data-ttu-id="188da-140">Gibt an, ob die Objekte nacheinander oder als Batch verarbeitet werden; bei Verwendung der parallelen Verarbeitung wird die Anzahl der gleichzeitig verarbeiteten Objekte angegeben.</span><span class="sxs-lookup"><span data-stu-id="188da-140">Specifies whether objects are processed sequentially or in a batch; if parallel processing is used, specifies the number of objects to process concurrently.</span></span>|  
|<span data-ttu-id="188da-141">**Transaktionsmodus**</span><span class="sxs-lookup"><span data-stu-id="188da-141">**Transaction mode**</span></span>|<span data-ttu-id="188da-142">Gibt den Transaktionsmodus für die sequenzielle Verarbeitung an.</span><span class="sxs-lookup"><span data-stu-id="188da-142">Specifies the transaction mode for sequential processing.</span></span>|  
|<span data-ttu-id="188da-143">**Dimensionsfehler**</span><span class="sxs-lookup"><span data-stu-id="188da-143">**Dimension errors**</span></span>|<span data-ttu-id="188da-144">Gibt das Verhalten des Tasks bei Auftreten eines Fehlers an.</span><span class="sxs-lookup"><span data-stu-id="188da-144">Specifies the task behavior when errors occur.</span></span>|  
|<span data-ttu-id="188da-145">**Fehlerprotokollpfad für Dimensionsschlüssel**</span><span class="sxs-lookup"><span data-stu-id="188da-145">**Dimension key error log path**</span></span>|<span data-ttu-id="188da-146">Gibt den Pfad der Datei an, in der Fehler protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="188da-146">Specifies the path of the file to which errors are logged.</span></span>|  
|<span data-ttu-id="188da-147">**Betroffene Objekte verarbeiten**</span><span class="sxs-lookup"><span data-stu-id="188da-147">**Process affected objects**</span></span>|<span data-ttu-id="188da-148">Kennzeichnet, ob abhängige oder betroffene Objekte auch verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="188da-148">Indicates whether dependent or affected objects are also processed.</span></span>|  
  
 <span data-ttu-id="188da-149">**Einstellungen ändern**</span><span class="sxs-lookup"><span data-stu-id="188da-149">**Change Settings**</span></span>  
 <span data-ttu-id="188da-150">Ändern Sie die Verarbeitungsoptionen und die Fehlerbehandlung bei Dimensionsschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="188da-150">Change the processing options and the handling of errors in dimension keys.</span></span>  
  
 <span data-ttu-id="188da-151">**Verwandte Themen:** [Dialogfeld „Einstellungen ändern“ &#40;Analysis Services – Mehrdimensionale Daten&#41;](../../2014/analysis-services/change-settings-dialog-box-analysis-services-multidimensional-data.md)</span><span class="sxs-lookup"><span data-stu-id="188da-151">**Related Topics:** [Change Settings Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](../../2014/analysis-services/change-settings-dialog-box-analysis-services-multidimensional-data.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="188da-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="188da-152">See Also</span></span>  
 <span data-ttu-id="188da-153">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="188da-153">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="188da-154">[Analysis Services Verarbeitungs Task-Editor &#40;Seite Allgemein&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="188da-154">[Analysis Services Processing Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="188da-155">DDL ausführen (Analysis Services-Task)</span><span class="sxs-lookup"><span data-stu-id="188da-155">Analysis Services Execute DDL Task</span></span>](control-flow/analysis-services-execute-ddl-task.md)  
  
  
