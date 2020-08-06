---
title: DMX-Vorlagen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2a577e52-821d-4bd3-ba35-075a6be285c9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 79c8615933baf4fa3d80974daae91b4d1c7fa101
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621252"
---
# <a name="dmx-templates"></a><span data-ttu-id="88082-102">DMX-Vorlagen</span><span class="sxs-lookup"><span data-stu-id="88082-102">DMX Templates</span></span>
  <span data-ttu-id="88082-103">Die Data Mining-Vorlagen ermöglichen Ihnen das schnelle Erstellen komplexer Abfragen.</span><span class="sxs-lookup"><span data-stu-id="88082-103">The data mining templates help you quickly build sophisticated queries.</span></span> <span data-ttu-id="88082-104">Die allgemeine Syntax für DMX-Abfragen ist zwar umfassend dokumentiert, die Vorlagen erleichtern es Ihnen jedoch, Abfragen durch Klicken und Zeigen auf Argumente und Datenquellen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="88082-104">Although the general syntax for DMX queries is well documented, using the templates makes it easier to build queries by clicking and pointing to arguments and data sources.</span></span>  
  
## <a name="using-the-templates"></a><span data-ttu-id="88082-105">Verwenden der Vorlagen</span><span class="sxs-lookup"><span data-stu-id="88082-105">Using the Templates</span></span>  
  
1.  <span data-ttu-id="88082-106">Klicken Sie im Data Mining-Client für Excel auf **Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="88082-106">In the Data Mining Client for Excel, click **Query**.</span></span>  
  
2.  <span data-ttu-id="88082-107">Klicken Sie auf der **Start** Seite des Assistenten auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="88082-107">On the wizard **Start** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="88082-108">**Wählen Sie**auf der Seite Modell aus, und klicken Sie auf **erweitert**.</span><span class="sxs-lookup"><span data-stu-id="88082-108">On the page, **Select Model**, click **Advanced**.</span></span>  
  
     <span data-ttu-id="88082-109">**Tipp:** Wenn Sie eine Vorhersage Abfrage für ein Modell erstellen, können Sie zuerst das Modell auswählen und dann auf **erweitert**klicken, um die Vorlage vorab mit dem Modellnamen aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="88082-109">**Tip:** If you are going to create a prediction query on a model, you can select the model first, and then click **Advanced**, to prepopulate the template with the model name.</span></span>  
  
4.  <span data-ttu-id="88082-110">Klicken Sie im **erweiterten Data Mining-Abfrage-Editor**auf **DMX-Vorlagen**, und wählen Sie eine Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="88082-110">In the **Data Mining Advanced Query Editor**, click **DMX Templates**, and select a template.</span></span>  
  
5.  <span data-ttu-id="88082-111">Drücken Sie die EINGABETASTE, um die Vorlage im Bereich DMX-Abfrage zu laden.</span><span class="sxs-lookup"><span data-stu-id="88082-111">Press ENTER to load the template into the DMX Query pane.</span></span>  
  
6.  <span data-ttu-id="88082-112">Fahren Sie fort, indem Sie auf die Links in der Vorlage klicken. Wählen Sie im angezeigten Dialogfeld eine entsprechende Ausgabe, ein Modell oder einen Parameter aus.</span><span class="sxs-lookup"><span data-stu-id="88082-112">Continue clicking the links in the template, and as the dialog box appears, select an appropriate output, model, or parameter.</span></span>  
  
     <span data-ttu-id="88082-113">Wählen Sie für Vorhersageabfragen zuerst das Eingabedataset aus, und ordnen Sie dann die Spalten zu.</span><span class="sxs-lookup"><span data-stu-id="88082-113">For prediction queries, choose the input dataset first, and then map the columns.</span></span>  
  
7.  <span data-ttu-id="88082-114">Klicken Sie auf **Abfrage bearbeiten** , um zur Text-Editor-Ansicht zu wechseln und die Abfrage manuell zu ändern.</span><span class="sxs-lookup"><span data-stu-id="88082-114">Click **Edit Query** to switch to text editor view and manually change the query.</span></span>  
  
     <span data-ttu-id="88082-115">Beachten Sie jedoch Folgendes: Wenn Sie beim Arbeiten im Abfrage-Editor zwischen Sichten wechseln, werden alle Informationen aus der vorherigen Sicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="88082-115">Be aware, however, that if you switch views when working in the query editor, any information that you had in the previous view will be cleared.</span></span> <span data-ttu-id="88082-116">Speichern Sie daher vor dem Wechseln der Ansicht Ihre Arbeit, indem Sie die DMX-Anweisungen in eine separate Datei kopieren und diese speichern.</span><span class="sxs-lookup"><span data-stu-id="88082-116">Before changing views, save your work by copying and pasting the DMX statements to a separate file.</span></span>  
  
8.  <span data-ttu-id="88082-117">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="88082-117">Click **Finish**.</span></span> <span data-ttu-id="88082-118">Geben Sie im Dialogfeld **Ziel auswählen** an, wo das Ergebnis gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="88082-118">In the **Choose Destination** dialog  box, specify where you want the result saved.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="88082-119">Wenn Sie eine-Anweisung erfolgreich ausgeführt haben, wird die DMX-Anweisung, die Sie an den Server gesendet haben, auch im Ablauf **Verfolgungs** Fenster aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="88082-119">If you executed a statement successfully, the DMX statement that you sent to the server is also recorded in the **Trace** window.</span></span> <span data-ttu-id="88082-120">Weitere Informationen zum Verwenden der Ablauf Verfolgungs Funktion finden Sie unter Ablauf [Verfolgung &#40;Data Mining-Client für Excel&#41;](trace-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="88082-120">For more information about how to use the Trace feature, see [Trace &#40;Data Mining Client for Excel&#41;](trace-data-mining-client-for-excel.md).</span></span>  
  
 <span data-ttu-id="88082-121">Weitere Informationen zur Verwendung des erweiterten Data Mining-Abfrage-Editors finden Sie unter [Abfrage &#40;SQL Server Data Mining-Add-ins&#41;](query-sql-server-data-mining-add-ins.md) und erweiterter [Data Mining-Abfrage-Editor](advanced-data-mining-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="88082-121">For more information about how to use the Data Mining Advanced Query Editor, see [Query &#40;SQL Server Data Mining Add-ins&#41;](query-sql-server-data-mining-add-ins.md) and [Advanced Data Mining Query Editor](advanced-data-mining-query-editor.md).</span></span>  
  
## <a name="list-of-dmx-templates"></a><span data-ttu-id="88082-122">Liste von DMX-Vorlagen</span><span class="sxs-lookup"><span data-stu-id="88082-122">List of DMX Templates</span></span>  
 <span data-ttu-id="88082-123">Die folgenden DMX-Vorlagen sind im Data Mining-Client für Excel enthalten.</span><span class="sxs-lookup"><span data-stu-id="88082-123">The following DMX templates are included in the Data Mining Client for Excel.</span></span>  
  
 <span data-ttu-id="88082-124">**Vorhersage**</span><span class="sxs-lookup"><span data-stu-id="88082-124">**Prediction**</span></span>  
  
 <span data-ttu-id="88082-125">Erstellen Sie mithilfe dieser Vorlagen erweiterte Vorhersageabfragen, u. a. Abfragen, die von den Assistenten der Add-Ins nicht unterstützt werden, z. B. Abfragen, in denen geschachtelte Tabellen oder externe Datenquellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="88082-125">Use these templates to create advanced prediction queries, including queries not supported by the wizards in the add-ins, such as queries that use nested tables or external data sources.</span></span>  
  
-   <span data-ttu-id="88082-126">Gefilterte Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="88082-126">Filtered predictions</span></span>  
  
-   <span data-ttu-id="88082-127">Gefilterte geschachtelte Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="88082-127">Filtered nested predictions</span></span>  
  
-   <span data-ttu-id="88082-128">Geschachtelte Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="88082-128">Nested predictions</span></span>  
  
-   <span data-ttu-id="88082-129">Singleton-Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="88082-129">Singleton predictions</span></span>  
  
-   <span data-ttu-id="88082-130">Standardvorhersagen</span><span class="sxs-lookup"><span data-stu-id="88082-130">Standard predictions</span></span>  
  
-   <span data-ttu-id="88082-131">Zeitreihen Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="88082-131">Time series predictions</span></span>  
  
-   <span data-ttu-id="88082-132">TOP-Vorhersageabfrage</span><span class="sxs-lookup"><span data-stu-id="88082-132">TOP prediction query</span></span>  
  
-   <span data-ttu-id="88082-133">TOP-Vorhersageabfrage für geschachtelte Tabelle</span><span class="sxs-lookup"><span data-stu-id="88082-133">TOP prediction query on nested table</span></span>  
  
 <span data-ttu-id="88082-134">**Erstellen**</span><span class="sxs-lookup"><span data-stu-id="88082-134">**Create**</span></span>  
  
 <span data-ttu-id="88082-135">Erstellen Sie mit diesen Vorlagen benutzerdefinierte Modelle oder Datenstrukturen.</span><span class="sxs-lookup"><span data-stu-id="88082-135">Use these templates to build custom models or data structures.</span></span> <span data-ttu-id="88082-136">Sie sind nicht auf die Modelle beschränkt, die von den Assistenten unterstützt werden. Sie können jeden beliebigen Data Mining Algorithmus verwenden, der von der Instanz von unterstützt wird [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , mit der Sie verbunden sind, einschließlich Plug-in-Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="88082-136">You are not limited to the models supported by the wizards - you can use any data mining algorithm supported by the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you are connected to, including plug-in algorithms.</span></span>  
  
-   <span data-ttu-id="88082-137">Mining Modell</span><span class="sxs-lookup"><span data-stu-id="88082-137">Mining model</span></span>  
  
-   <span data-ttu-id="88082-138">Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="88082-138">Mining structure</span></span>  
  
-   <span data-ttu-id="88082-139">Miningstruktur mit zurückgehaltenen Daten</span><span class="sxs-lookup"><span data-stu-id="88082-139">Mining structure with holdout</span></span>  
  
-   <span data-ttu-id="88082-140">Temporäres Modell</span><span class="sxs-lookup"><span data-stu-id="88082-140">Temporary model</span></span>  
  
-   <span data-ttu-id="88082-141">Temporäre Struktur</span><span class="sxs-lookup"><span data-stu-id="88082-141">Temporary structure</span></span>  
  
 <span data-ttu-id="88082-142">**Modell Eigenschaften**</span><span class="sxs-lookup"><span data-stu-id="88082-142">**Model Properties**</span></span>  
  
 <span data-ttu-id="88082-143">Erstellen Sie mit diesen Vorlagen Abfragen, mit denen Metadaten zum Modell und zum Trainingssatz abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="88082-143">Use these templates to create queries that get metadata about the model and the training set.</span></span> <span data-ttu-id="88082-144">Sie können auch Details aus dem Modellinhalt abrufen oder ein statistisches Profil der Trainingsdaten abrufen.</span><span class="sxs-lookup"><span data-stu-id="88082-144">You can also retrieve details from the model content, or get a statistical profile of the training data.</span></span>  
  
-   <span data-ttu-id="88082-145">Mining Modell Inhalt</span><span class="sxs-lookup"><span data-stu-id="88082-145">Mining model content</span></span>  
  
-   <span data-ttu-id="88082-146">Minimale und maximale Spaltenwerte</span><span class="sxs-lookup"><span data-stu-id="88082-146">Minimum and maximum column values</span></span>  
  
-   <span data-ttu-id="88082-147">Test-/Trainingsfälle der Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="88082-147">Mining structure test/training cases</span></span>  
  
-   <span data-ttu-id="88082-148">Diskrete Spaltenwerte</span><span class="sxs-lookup"><span data-stu-id="88082-148">Discrete column values</span></span>  
  
 <span data-ttu-id="88082-149">**Verwaltung**</span><span class="sxs-lookup"><span data-stu-id="88082-149">**Management**</span></span>  
  
 <span data-ttu-id="88082-150">Führen Sie mit diesen Vorlagen beliebige von DMX unterstützte Verwaltungsaufgaben aus; hierzu zählen das Importieren und Exportieren von Modellen, das Löschen von Modellen sowie das Leeren von Modellen oder Datenstrukturen.</span><span class="sxs-lookup"><span data-stu-id="88082-150">Use these templates to perform any management task supported by DMX, which includes importing and exporting models, deleting models, and clearing models or data structures.</span></span>  
  
-   <span data-ttu-id="88082-151">Miningmodell entfernen</span><span class="sxs-lookup"><span data-stu-id="88082-151">Clear mining model</span></span>  
  
-   <span data-ttu-id="88082-152">Struktur und Modelle löschen</span><span class="sxs-lookup"><span data-stu-id="88082-152">Clear structure and models</span></span>  
  
-   <span data-ttu-id="88082-153">Miningstruktur entfernen</span><span class="sxs-lookup"><span data-stu-id="88082-153">Clear mining structure</span></span>  
  
-   <span data-ttu-id="88082-154">Miningmodell löschen</span><span class="sxs-lookup"><span data-stu-id="88082-154">Delete mining model</span></span>  
  
-   <span data-ttu-id="88082-155">Miningstruktur löschen</span><span class="sxs-lookup"><span data-stu-id="88082-155">Delete mining structure</span></span>  
  
-   <span data-ttu-id="88082-156">Miningmodell umbenennen</span><span class="sxs-lookup"><span data-stu-id="88082-156">Rename mining model</span></span>  
  
-   <span data-ttu-id="88082-157">Miningstruktur umbenennen</span><span class="sxs-lookup"><span data-stu-id="88082-157">Rename mining structure</span></span>  
  
-   <span data-ttu-id="88082-158">Miningmodell trainieren</span><span class="sxs-lookup"><span data-stu-id="88082-158">Train mining model</span></span>  
  
-   <span data-ttu-id="88082-159">Geschachtelte Miningstruktur trainieren</span><span class="sxs-lookup"><span data-stu-id="88082-159">Train nested mining structure</span></span>  
  
-   <span data-ttu-id="88082-160">Miningstruktur trainieren</span><span class="sxs-lookup"><span data-stu-id="88082-160">Train mining structure</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="88082-161">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="88082-161">Requirements</span></span>  
 <span data-ttu-id="88082-162">In Abhängigkeit der von Ihnen verwendeten Vorlage benötigen Sie möglicherweise Administratorrechte, um auf den [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Server zugreifen und eine Abfrage ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="88082-162">Depending on which template you are using, you might need administrative permissions to access the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server and execute the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88082-163">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="88082-163">See Also</span></span>  
 [<span data-ttu-id="88082-164">Erstellen eines Data Mining-Modells</span><span class="sxs-lookup"><span data-stu-id="88082-164">Creating a Data Mining Model</span></span>](creating-a-data-mining-model.md)  
  
  
