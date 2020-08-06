---
title: Erstellen einer zielgerichteten Mailing-Mining Modellstruktur (Lernprogramm zu Data Mining-Grundlagen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a9c67f29-0c47-4a5a-862b-db0f5213c2c9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 6a27f818b29120e40248044091c78205dad945bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719126"
---
# <a name="creating-a-targeted-mailing-mining-model-structure-basic-data-mining-tutorial"></a><span data-ttu-id="767c0-102">Erstellen der Miningmodellstruktur "Targeted Mailing" (Basic Data Mining-Lernprogramm)</span><span class="sxs-lookup"><span data-stu-id="767c0-102">Creating a Targeted Mailing Mining Model Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="767c0-103">Der erste Schritt beim Erstellen eines Targeted Mailing-Szenarios besteht darin, mit dem Data Mining-Assistenten in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] eine neue Miningstruktur und ein Entscheidungsstruktur-Miningmodell zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="767c0-103">The first step in creating a targeted mailing scenario is to use the Data Mining Wizard in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to create a new mining structure and decision tree mining model.</span></span>  
  
 <span data-ttu-id="767c0-104">In dieser Aufgabe richten Sie eine neue Mining Struktur ein und fügen basierend auf dem Decision Trees-Algorithmus ein ursprüngliches Mining Modell hinzu [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="767c0-104">In this task you will set up a new mining structure, and add an initial mining model based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span> <span data-ttu-id="767c0-105">Um die Struktur zu erstellen, wählen Sie zuerst Tabellen und Sichten aus. Anschließend legen Sie fest, welche Spalten für das Trainieren und welche für das Testen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="767c0-105">To create the structure, you will first select tables and views and then identify which columns will be used for training and which for testing.</span></span>  
  
### <a name="to-create-a-mining-structure-for-the-targeted-mailing-scenario"></a><span data-ttu-id="767c0-106">So erstellen Sie eine Miningstruktur für das Targeted Mailing-Szenario</span><span class="sxs-lookup"><span data-stu-id="767c0-106">To create a mining structure for the targeted mailing scenario</span></span>  
  
1.  <span data-ttu-id="767c0-107">Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf **Mining Strukturen** , und wählen Sie **neue Mining Struktur** , um den Data Mining-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="767c0-107">In Solution Explorer, right-click **Mining Structures** and select **New Mining Structure** to start the Data Mining Wizard.</span></span>  
  
2.  <span data-ttu-id="767c0-108">Klicken Sie auf der Seite **Willkommen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="767c0-108">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="767c0-109">Überprüfen Sie auf der Seite **Definitions Methode auswählen** , ob **aus vorhandener relationaler Datenbank oder Data Warehouse** ausgewählt ist, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="767c0-109">On the **Select the Definition Method** page, verify that **From existing relational database or data warehouse** is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="767c0-110">Wählen Sie auf der Seite **Data Mining-Struktur erstellen** unter **welche Data Mining Technik möchten Sie verwenden?** die Option **Microsoft Decision Trees**aus.</span><span class="sxs-lookup"><span data-stu-id="767c0-110">On the **Create the Data Mining Structure** page, under **Which data mining technique do you want to use?**, select **Microsoft Decision Trees**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="767c0-111">Wenn Sie eine Warnung erhalten, dass keine Data Mining-Algorithmen gefunden werden können, werden die Projekteigenschaften möglicherweise nicht korrekt konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="767c0-111">If you get a warning that no data mining algorithms can be found, the project properties might not be configured correctly.</span></span> <span data-ttu-id="767c0-112">Diese Warnung tritt auf, wenn das Projekt versucht, eine Liste mit Data Mining-Algorithmen vom [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Server abzurufen, und den Server nicht finden kann.</span><span class="sxs-lookup"><span data-stu-id="767c0-112">This warning occurs when the project attempts to retrieve a list of data mining algorithms from the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server and cannot find the server.</span></span> <span data-ttu-id="767c0-113">Standardmäßig [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] verwendet **localhost** als Server.</span><span class="sxs-lookup"><span data-stu-id="767c0-113">By default, [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] will use **localhost** as the server.</span></span> <span data-ttu-id="767c0-114">Wenn Sie eine andere Instanz oder eine benannte Instanz verwenden, müssen die Projekteigenschaften geändert werden.</span><span class="sxs-lookup"><span data-stu-id="767c0-114">If you are using a different instance, or a named instance, you must change the project properties.</span></span> <span data-ttu-id="767c0-115">Weitere Informationen finden Sie unter [Erstellen eines Analysis Services Projekts &#40;Lernprogramm zu Data Mining-Grundlagen&#41;](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="767c0-115">For more information, see [Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md).</span></span>  
  
5.  <span data-ttu-id="767c0-116">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="767c0-116">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="767c0-117">Wählen Sie auf der Seite **Datenquellen Sicht auswählen** im Bereich **Verfügbare Datenquellen Sichten** die Option **Ziel Versand**aus.</span><span class="sxs-lookup"><span data-stu-id="767c0-117">On the **Select Data Source View** page, in the **Available data source views** pane, select **Targeted Mailing**.</span></span> <span data-ttu-id="767c0-118">Sie können auf **Durchsuchen** klicken, um die Tabellen in der Datenquellen Sicht anzuzeigen, und dann auf **Schließen** klicken, um zum Assistenten zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="767c0-118">You can click **Browse** to view the tables in the data source view and then click **Close** to return to the wizard.</span></span>  
  
7.  <span data-ttu-id="767c0-119">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="767c0-119">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="767c0-120">Aktivieren Sie auf der Seite **Tabellentypen angeben** das Kontrollkästchen in der Spalte **Fall** für vTargetMail, um es als Fall Tabelle zu verwenden, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="767c0-120">On the **Specify Table Types** page, select the check box in the **Case** column for vTargetMail to use it as the case table, and then click **Next**.</span></span> <span data-ttu-id="767c0-121">Sie verwenden die ProspectiveBuyer-Tabelle später zum Testen. ignorieren Sie es vorerst.</span><span class="sxs-lookup"><span data-stu-id="767c0-121">You will use the ProspectiveBuyer table later for testing; ignore it for now.</span></span>  
  
9. <span data-ttu-id="767c0-122">Auf der Seite **Trainingsdaten angeben** identifizieren Sie mindestens eine vorhersagbare Spalte, eine Schlüssel Spalte und eine Eingabe Spalte für das Modell.</span><span class="sxs-lookup"><span data-stu-id="767c0-122">On the **Specify the Training Data** page, you will identify at least one predictable column, one key column, and one input column for your model.</span></span> <span data-ttu-id="767c0-123">Aktivieren Sie das Kontrollkästchen in der Spalte **vorhersagbare** Spalte in der Zeile **BikeBuyer** .</span><span class="sxs-lookup"><span data-stu-id="767c0-123">Select the check box in the **Predictable** column in the **BikeBuyer** row.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="767c0-124">Beachten Sie die Warnung am unteren Rand des Fensters.</span><span class="sxs-lookup"><span data-stu-id="767c0-124">Notice the warning at the bottom of the window.</span></span> <span data-ttu-id="767c0-125">Sie können erst zur nächsten Seite navigieren, wenn Sie mindestens eine **Eingabe** und eine **vorhersagbare** Spalte ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="767c0-125">You will not be able to navigate to the next page until you select at least one **Input** and one **Predictable** column.</span></span>  
  
10. <span data-ttu-id="767c0-126">Klicken Sie auf **vorschlagen** , um das Dialogfeld **Verbundene Spalten vorschlagen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="767c0-126">Click **Suggest** to open the **Suggest Related Columns** dialog box.</span></span>  
  
     <span data-ttu-id="767c0-127">Die Schaltfläche **vorschlagen** wird immer dann aktiviert, wenn mindestens ein vorhersagbares Attribut ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="767c0-127">The **Suggest** button is enabled whenever at least one predictable attribute has been selected.</span></span> <span data-ttu-id="767c0-128">Im Dialogfeld verknüpfte **Spalten vorschlagen** werden die Spalten aufgelistet, die am ehesten mit der vorhersagbaren Spalte verknüpft sind, und die Attribute werden nach ihrer Korrelation mit dem vorhersagbaren Attribut sortiert.</span><span class="sxs-lookup"><span data-stu-id="767c0-128">The **Suggest Related Columns** dialog box lists the columns that are most closely related to the predictable column, and orders the attributes by their correlation with the predictable attribute.</span></span> <span data-ttu-id="767c0-129">Spalten mit einer wesentlichen Korrelation (Vertrauen größer als 95 %) werden automatisch für die Aufnahme ins Modell ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="767c0-129">Columns with a significant correlation (confidence greater than 95%) are automatically selected to be included in the model.</span></span>  
  
     <span data-ttu-id="767c0-130">Überprüfen Sie die Vorschläge, und klicken Sie dann auf **Abbrechen** , um die Vorschläge zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="767c0-130">Review the suggestions, and then click **Cancel** toignore the suggestions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="767c0-131">Wenn Sie auf " **OK**" klicken, werden alle aufgeführten Vorschläge im Assistenten als Eingabe Spalten gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="767c0-131">If you click **OK**, all listed suggestions will be marked as input columns in the wizard.</span></span> <span data-ttu-id="767c0-132">Wenn Sie nur einige der Vorschläge übernehmen möchten, müssen Sie die Werte manuell ändern.</span><span class="sxs-lookup"><span data-stu-id="767c0-132">If you agree with only some of the suggestions, you must change the values manually.</span></span>  
  
11. <span data-ttu-id="767c0-133">Vergewissern Sie sich, dass das Kontrollkästchen in der Spalte **Schlüssel** in der Zeile **CustomerKey** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="767c0-133">Verify that the check box in the **Key** column is selected in the **CustomerKey** row.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="767c0-134">Wenn in der Quelltabelle der Datenquellensicht ein Schlüssel angegeben ist, wählt der Data Mining-Assistent automatisch diese Spalte als Schlüssel für das Modell aus.</span><span class="sxs-lookup"><span data-stu-id="767c0-134">If the source table from the data source view indicates a key, the Data Mining Wizard automatically chooses that column as a key for the model.</span></span>  
  
12. <span data-ttu-id="767c0-135">Aktivieren Sie die Kontrollkästchen in der **Eingabe** Spalte in den folgenden Zeilen.</span><span class="sxs-lookup"><span data-stu-id="767c0-135">Select the check boxes in the **Input** column in the following rows.</span></span> <span data-ttu-id="767c0-136">Sie können mehrere Spalten auswählen, indem Sie einen Bereich von Zellen markieren und STRG drücken, während Sie ein Kontrollkästchen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="767c0-136">You can check multiple columns by highlighting a range of cells and pressing CTRL while selecting a check box.</span></span>  
  
    -   <span data-ttu-id="767c0-137">**Age**</span><span class="sxs-lookup"><span data-stu-id="767c0-137">**Age**</span></span>  
  
    -   <span data-ttu-id="767c0-138">**CommuteDistance**</span><span class="sxs-lookup"><span data-stu-id="767c0-138">**CommuteDistance**</span></span>  
  
    -   <span data-ttu-id="767c0-139">**EnglishEducation**</span><span class="sxs-lookup"><span data-stu-id="767c0-139">**EnglishEducation**</span></span>  
  
    -   <span data-ttu-id="767c0-140">**EnglishOccupation**</span><span class="sxs-lookup"><span data-stu-id="767c0-140">**EnglishOccupation**</span></span>  
  
    -   <span data-ttu-id="767c0-141">**Geschlecht**</span><span class="sxs-lookup"><span data-stu-id="767c0-141">**Gender**</span></span>  
  
    -   <span data-ttu-id="767c0-142">**GeographyKey**</span><span class="sxs-lookup"><span data-stu-id="767c0-142">**GeographyKey**</span></span>  
  
    -   <span data-ttu-id="767c0-143">**HouseOwnerFlag**</span><span class="sxs-lookup"><span data-stu-id="767c0-143">**HouseOwnerFlag**</span></span>  
  
    -   <span data-ttu-id="767c0-144">**MaritalStatus**</span><span class="sxs-lookup"><span data-stu-id="767c0-144">**MaritalStatus**</span></span>  
  
    -   <span data-ttu-id="767c0-145">**NumberCarsOwned**</span><span class="sxs-lookup"><span data-stu-id="767c0-145">**NumberCarsOwned**</span></span>  
  
    -   <span data-ttu-id="767c0-146">**NumberChildrenAtHome**</span><span class="sxs-lookup"><span data-stu-id="767c0-146">**NumberChildrenAtHome**</span></span>  
  
    -   <span data-ttu-id="767c0-147">**Region**</span><span class="sxs-lookup"><span data-stu-id="767c0-147">**Region**</span></span>  
  
    -   <span data-ttu-id="767c0-148">**TotalChildren**</span><span class="sxs-lookup"><span data-stu-id="767c0-148">**TotalChildren**</span></span>  
  
    -   <span data-ttu-id="767c0-149">**YearlyIncome**</span><span class="sxs-lookup"><span data-stu-id="767c0-149">**YearlyIncome**</span></span>  
  
13. <span data-ttu-id="767c0-150">Aktivieren Sie in der Spalte ganz links auf der Seite die Kontrollkästchen in den folgenden Zeilen.</span><span class="sxs-lookup"><span data-stu-id="767c0-150">On the far left column of the page, select the check boxes in the following rows.</span></span>  
  
    -   <span data-ttu-id="767c0-151">**AddressLine1**</span><span class="sxs-lookup"><span data-stu-id="767c0-151">**AddressLine1**</span></span>  
  
    -   <span data-ttu-id="767c0-152">**AddressLine2**</span><span class="sxs-lookup"><span data-stu-id="767c0-152">**AddressLine2**</span></span>  
  
    -   <span data-ttu-id="767c0-153">**DateFirstPurchase**</span><span class="sxs-lookup"><span data-stu-id="767c0-153">**DateFirstPurchase**</span></span>  
  
    -   <span data-ttu-id="767c0-154">**EmailAddress**</span><span class="sxs-lookup"><span data-stu-id="767c0-154">**EmailAddress**</span></span>  
  
    -   <span data-ttu-id="767c0-155">**Vorname**</span><span class="sxs-lookup"><span data-stu-id="767c0-155">**FirstName**</span></span>  
  
    -   <span data-ttu-id="767c0-156">**Nachname**</span><span class="sxs-lookup"><span data-stu-id="767c0-156">**LastName**</span></span>  
  
     <span data-ttu-id="767c0-157">Stellen Sie sicher, dass diese Zeilen nur Häkchen in der linken Spalte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="767c0-157">Ensure that these rows have checks only in the left column.</span></span> <span data-ttu-id="767c0-158">Diese Spalten werden der Struktur hinzugefügt, jedoch nicht in das Modell aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="767c0-158">These columns will be added to your structure but will not be included in the model.</span></span> <span data-ttu-id="767c0-159">Nachdem das Modell erstellt wurde, stehen sie jedoch für Drillthrough und Tests zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="767c0-159">However, after the model is built, they will be available for drillthrough and testing.</span></span> <span data-ttu-id="767c0-160">Weitere Informationen zu Drillthrough finden Sie unter [Drillthrough-Abfragen &#40;Data Mining-&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="767c0-160">For more information about drillthrough, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span></span>  
  
14. <span data-ttu-id="767c0-161">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="767c0-161">Click **Next**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="767c0-162">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="767c0-162">Next Task in Lesson</span></span>  
 [<span data-ttu-id="767c0-163">Angeben des Datentyps und des Inhaltstyps &#40;grundlegenden Data Mining-Lernprogramm&#41;</span><span class="sxs-lookup"><span data-stu-id="767c0-163">Specifying the Data Type and Content Type &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-the-data-type-and-content-type-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="767c0-164">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="767c0-164">See Also</span></span>  
 <span data-ttu-id="767c0-165">[Geben Sie die Tabellentypen &#40;Data Mining-Assistenten an&#41;](../../2014/analysis-services/specify-table-types-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="767c0-165">[Specify Table Types &#40;Data Mining Wizard&#41;](../../2014/analysis-services/specify-table-types-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="767c0-166">[Data Mining-Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="767c0-166">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="767c0-167">Microsoft Decision Trees-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="767c0-167">Microsoft Decision Trees Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md)  
  
  
