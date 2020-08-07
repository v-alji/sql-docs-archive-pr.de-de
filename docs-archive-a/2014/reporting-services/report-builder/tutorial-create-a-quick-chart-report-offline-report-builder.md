---
title: 'Tutorial: Schnelles Erstellen eines Diagrammberichts offline (Berichts-Generator) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports, creating
- tutorials, getting started
- creating reports
ms.assetid: 6b1db67a-cf75-494c-b70c-09f1e6a8d414
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 51a9e648550a0108f47e3d93d75267ab0c1c24f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615821"
---
# <a name="tutorial-create-a-quick-chart-report-offline-report-builder"></a><span data-ttu-id="2bd21-102">Lernprogramm: Erstellen eines Quick-Diagrammberichts offline (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="2bd21-102">Tutorial: Create a Quick Chart Report Offline (Report Builder)</span></span>
  <span data-ttu-id="2bd21-103">In diesem Lernprogramm erstellen Sie ein Kreisdiagramm mithilfe eines Assistenten. Danach nehmen Sie eine kleine Änderung an diesem Diagramm vor, damit Sie eine Vorstellung von den Bearbeitungsmöglichkeiten erhalten.</span><span class="sxs-lookup"><span data-stu-id="2bd21-103">In this tutorial, you'll create a pie chart by using a wizard, and then you'll modify it a little, just to get an idea of what's possible.</span></span> <span data-ttu-id="2bd21-104">Dieses Lernprogramm kann auf zwei unterschiedliche Arten absolviert werden.</span><span class="sxs-lookup"><span data-stu-id="2bd21-104">You can do this tutorial two different ways.</span></span> <span data-ttu-id="2bd21-105">Beide Methoden haben dasselbe Ergebnis: ein Kreis Diagramm wie das in der folgenden Abbildung:</span><span class="sxs-lookup"><span data-stu-id="2bd21-105">Both methods have the same outcome-a pie chart like the one in the following illustration:</span></span>

 <span data-ttu-id="2bd21-106">!["Mein erstes Kreisdiagramm" in der Ansicht "Ausführen"](../media/rs-my1stpierunview.gif "Mein erstes Kreis Diagramm in der Ansicht "ausführen"")</span><span class="sxs-lookup"><span data-stu-id="2bd21-106">!["My First Pie Chart" in Run view](../media/rs-my1stpierunview.gif "My First Pie Chart in Run view")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2bd21-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2bd21-107">Prerequisites</span></span>
 <span data-ttu-id="2bd21-108">Sowohl bei Verwendung von XML-Daten als auch bei einer [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Abfrage benötigen Sie Zugriff auf [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] Berichts-Generator.</span><span class="sxs-lookup"><span data-stu-id="2bd21-108">Whether you use XML data or a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query, you need to have access to [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] Report Builder.</span></span> <span data-ttu-id="2bd21-109">Sie können die eigenständige Version oder die ClickOnce-Version ausführen, die im Berichts-Manager oder auf einer SharePoint-Website verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="2bd21-109">You can run the stand-alone version or the ClickOnce version available from Report Manager or a SharePoint site.</span></span> <span data-ttu-id="2bd21-110">Bei der ClickOnce-Version ist lediglich der erste Schritt anders, also das Öffnen des Berichts-Generators.</span><span class="sxs-lookup"><span data-stu-id="2bd21-110">Only the first step, how to open Report Builder, is different for ClickOnce versions.</span></span> <span data-ttu-id="2bd21-111">Weitere Informationen finden Sie [unter Installieren, deinstallieren und Berichts-Generator-Unterstützung](../install-uninstall-and-report-builder-support.md).</span><span class="sxs-lookup"><span data-stu-id="2bd21-111">For more information, see [Install, Uninstall, and Report Builder Support](../install-uninstall-and-report-builder-support.md).</span></span>

##  <a name="two-ways-to-do-this-tutorial"></a><a name="TwoWays"></a> <span data-ttu-id="2bd21-112">Zwei Möglichkeiten zum Absolvieren des Lernprogramms</span><span class="sxs-lookup"><span data-stu-id="2bd21-112">Two Ways To Do This Tutorial</span></span>

-   [<span data-ttu-id="2bd21-113">Erstellen des Kreisdiagramms mit XML-Daten</span><span class="sxs-lookup"><span data-stu-id="2bd21-113">Create the pie chart with XML data</span></span>](#CreatePieChartXML)

-   [<span data-ttu-id="2bd21-114">Erstellen des Kreis Diagramms mit einer Transact-SQL-Abfrage, die Daten enthält</span><span class="sxs-lookup"><span data-stu-id="2bd21-114">Create the pie chart with a Transact-SQL query that contains data</span></span>](#CreatePieQueryData)

### <a name="using-xml-data-for-this-tutorial"></a><span data-ttu-id="2bd21-115">Verwenden von XML-Daten für dieses Lernprogramm</span><span class="sxs-lookup"><span data-stu-id="2bd21-115">Using XML data for this tutorial</span></span>
 <span data-ttu-id="2bd21-116">Sie können XML-Daten verwenden, die Sie aus diesem Thema kopieren und in den Assistenten einfügen.</span><span class="sxs-lookup"><span data-stu-id="2bd21-116">You can use XML data that you copy from this topic and paste into the wizard.</span></span> <span data-ttu-id="2bd21-117">Es muss keine Verbindung mit einem Berichtsserver oder einem Berichtsserver im integrierten SharePoint-Modus bestehen, und Sie müssen auf keine Instanz von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] zugreifen.</span><span class="sxs-lookup"><span data-stu-id="2bd21-117">You don't need to be connected to a report server or a report server in SharePoint integrated mode, and you don't need access to an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>

 [<span data-ttu-id="2bd21-118">Erstellen des Kreisdiagramms mit XML-Daten</span><span class="sxs-lookup"><span data-stu-id="2bd21-118">Create the pie chart with XML data</span></span>](#CreatePieChartXML)

### <a name="using-a-transact-sql-query-that-contains-data-for-this-tutorial"></a><span data-ttu-id="2bd21-119">Verwenden einer Transact-SQL-Abfrage mit Daten für dieses Lernprogramm</span><span class="sxs-lookup"><span data-stu-id="2bd21-119">Using a Transact-SQL query that contains data for this tutorial</span></span>
 <span data-ttu-id="2bd21-120">Sie können aus diesem Thema eine Abfrage mit Daten kopieren und diese in den Assistenten einfügen.</span><span class="sxs-lookup"><span data-stu-id="2bd21-120">You can copy a query with data included in it from this topic and paste it into the wizard.</span></span> <span data-ttu-id="2bd21-121">Sie benötigen den Namen einer Instanz von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] sowie Anmeldeinformationen für den schreibgeschützten Zugriff auf eine beliebige Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2bd21-121">You will need the name of an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] and credentials sufficient for read-only access to any database.</span></span> <span data-ttu-id="2bd21-122">Von der Datasetabfrage im Lernprogramm werden zwar Literaldaten verwendet, die Abfrage muss jedoch durch eine Instanz von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] verarbeitet werden, um die für ein Berichtsdataset erforderlichen Metadaten zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="2bd21-122">The dataset query in the tutorial uses literal data, but the query must be processed by an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] to return the metadata that is required for a report dataset.</span></span>

 <span data-ttu-id="2bd21-123">Der Vorteil der Verwendung der [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Abfrage besteht darin, dass in allen anderen Lernprogrammen für Berichts-Generator die gleiche Methode verwendet wird und Sie beim Ausführen der anderen Lernprogramme bereits mit der Vorgehensweise vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="2bd21-123">The advantage of using the [!INCLUDE[tsql](../../../includes/tsql-md.md)] query is that all the other Report Builder tutorials use the same method, so when you do the other tutorials, you will already know what to do.</span></span>

 <span data-ttu-id="2bd21-124">Für die [!INCLUDE[tsql](../../../includes/tsql-md.md)] -Abfrage müssen noch einige andere Voraussetzungen erfüllt sein.</span><span class="sxs-lookup"><span data-stu-id="2bd21-124">The [!INCLUDE[tsql](../../../includes/tsql-md.md)] query does require a few other prerequisites.</span></span> <span data-ttu-id="2bd21-125">Weitere Informationen finden Sie unter [Voraussetzungen für Lernprogramme &#40;Berichts-Generator&#41;](../report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="2bd21-125">For more information, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md).</span></span>

 [<span data-ttu-id="2bd21-126">Erstellen des Kreis Diagramms mit einer Transact-SQL-Abfrage, die Daten enthält</span><span class="sxs-lookup"><span data-stu-id="2bd21-126">Create the pie chart with a Transact-SQL query that contains data</span></span>](#CreatePieQueryData)

## <a name="also-in-this-article"></a><span data-ttu-id="2bd21-127">Auch in diesem Artikel</span><span class="sxs-lookup"><span data-stu-id="2bd21-127">Also in This Article</span></span>
 [<span data-ttu-id="2bd21-128">Nach dem Ausführen des Assistenten</span><span class="sxs-lookup"><span data-stu-id="2bd21-128">After You Run the Wizard</span></span>](#AfterWizard)

 [<span data-ttu-id="2bd21-129">Was kommt als nächstes</span><span class="sxs-lookup"><span data-stu-id="2bd21-129">What's Next</span></span>](#WhatsNext)

##  <a name="creating-the-pie-chart-with-xml-data"></a><a name="CreatePieChartXML"></a><span data-ttu-id="2bd21-130">Erstellen des Kreis Diagramms mit XML-Daten</span><span class="sxs-lookup"><span data-stu-id="2bd21-130">Creating the pie chart with XML data</span></span>

#### <a name="to-create-the-pie-chart-with-xml-data"></a><span data-ttu-id="2bd21-131">So erstellen Sie das Kreisdiagramm mit XML-Daten</span><span class="sxs-lookup"><span data-stu-id="2bd21-131">To create the pie chart with XML data</span></span>

1.  <span data-ttu-id="2bd21-132">Klicken Sie auf **Start**, zeigen Sie auf **Programme**, zeigen Sie auf **Microsoft SQL Server 2012 Berichts-Generator**, und klicken Sie dann auf **Berichts-Generator**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-132">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>

     <span data-ttu-id="2bd21-133">Das Dialogfeld " **Getting Started** " wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2bd21-133">The **Getting Started** dialog box appears.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="2bd21-134">Wenn das Dialogfeld " **Getting Started** " nicht angezeigt wird, klicken Sie auf der Schaltfläche " **Berichts-Generator** " auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-134">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>

2.  <span data-ttu-id="2bd21-135">Vergewissern Sie sich im linken Bereich, dass der **Bericht** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="2bd21-135">In the left pane, verify that **Report** is selected.</span></span>

3.  <span data-ttu-id="2bd21-136">Klicken Sie im rechten Bereich auf **Diagramm-Assistent**und anschließend auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-136">In the right pane, click **Chart Wizard**, and then click **Create**.</span></span>

4.  <span data-ttu-id="2bd21-137">Klicken Sie auf der Seite **Dataset auswählen** auf **Dataset erstellen**und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-137">In the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>

5.  <span data-ttu-id="2bd21-138">Klicken Sie auf der Seite **Verbindung mit einer Datenquelle auswählen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-138">In the **Choose a connection to a data source** page, click **New**.</span></span>

     <span data-ttu-id="2bd21-139">Das Dialogfeld **Datenquelleneigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2bd21-139">The **Data Source Properties** dialog box opens.</span></span>

6.  <span data-ttu-id="2bd21-140">Sie können jedes gewünschte Element als Datenquelle bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="2bd21-140">You can name a data source anything you want.</span></span> <span data-ttu-id="2bd21-141">Geben Sie im Feld **Name** den Namen **MyPieChart**ein.</span><span class="sxs-lookup"><span data-stu-id="2bd21-141">In the **Name** box, type **MyPieChart**.</span></span>

7.  <span data-ttu-id="2bd21-142">Klicken Sie im Feld **Verbindungstyp auswählen** auf **XML.**</span><span class="sxs-lookup"><span data-stu-id="2bd21-142">In the **Select connection type** box, click **XML.**</span></span>

8.  <span data-ttu-id="2bd21-143">Klicken Sie auf der Registerkarte **Anmelde** Informationen auf **aktuellen Windows-Benutzer verwenden. Möglicherweise ist eine Kerberos-Delegierung erforderlich**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-143">Click the **Credentials** tab, select **Use current Windows user. Kerberos delegation may be required**, and then click **OK**.</span></span>

9. <span data-ttu-id="2bd21-144">Klicken Sie auf der Seite **Verbindung mit einer Datenquelle auswählen** auf **MyPieChart**und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-144">In the **Choose a connection to a data source** page, click **MyPieChart**, and then click **Next**.</span></span>

10. <span data-ttu-id="2bd21-145">Kopieren Sie den folgenden Text, und fügen Sie ihn in das große Feld in der Mitte der Seite **Abfrage entwerfen ein** .</span><span class="sxs-lookup"><span data-stu-id="2bd21-145">Copy the following text and paste it in the large box in the center of the **Design a query** page.</span></span>

    ```
    <Query>
    <ElementPath>Root /S  {@Sales (Integer)} /C {@FullName} </ElementPath>
    <XmlData>
    <Root>
    <S Sales="150">
      <C FullName="Jae Pak" />
    </S>
    <S Sales="350">
      <C FullName="Jillian  Carson" />
    </S>
    <S Sales="250">
      <C FullName="Linda C Mitchell" />
    </S>
    <S Sales="500">
      <C FullName="Michael Blythe" />
    </S>
    <S Sales="450">
      <C FullName="Ranjit Varkey" />
    </S>
    </Root>
    </XmlData>
    </Query>
    ```

11. <span data-ttu-id="2bd21-146">(Optional) Klicken Sie auf die Schaltfläche Ausführen (**!**), um die Daten anzuzeigen, auf denen das Diagramm basiert.</span><span class="sxs-lookup"><span data-stu-id="2bd21-146">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>

12. <span data-ttu-id="2bd21-147">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-147">Click **Next**.</span></span>

13. <span data-ttu-id="2bd21-148">Klicken Sie auf der Seite **Diagrammtyp auswählen** auf **Kreisdiagramm**. Danach klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-148">In the **Choose a chart type** page, click **Pie**, and then click **Next**.</span></span>

14. <span data-ttu-id="2bd21-149">Doppelklicken Sie auf der Seite **Diagrammfelder anordnen** auf das Feld **Vertrieb** im Feld **Verfügbare Felder**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-149">In the **Arrange chart fields** page, double-click the **Sales** field in the **Available fields** box.</span></span>

     <span data-ttu-id="2bd21-150">Beachten Sie, dass der Wert automatisch in das Feld **Werte** verschoben wird, da es sich um einen numerischen Wert handelt.</span><span class="sxs-lookup"><span data-stu-id="2bd21-150">Note that it automatically moves to the **Values** box, because it is a numerical value.</span></span>

15. <span data-ttu-id="2bd21-151">Ziehen Sie das Feld **FullName** aus dem Feld **Verfügbare Felder** in das Feld **Kategorien** (oder doppelklicken Sie auf das Feld, damit es in das Feld **Kategorien** verschoben wird). Klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-151">Drag the **FullName** field from the **Available fields** box to the **Categories** box (or double-click it; it will go to the **Categories** box), and then click **Next**.</span></span>

16. <span data-ttu-id="2bd21-152">Auf der Seite Format **auswählen** ist **Ozean** standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="2bd21-152">In the **Choose a style** page, **Ocean** is selected by default.</span></span> <span data-ttu-id="2bd21-153">Klicken Sie auf die anderen Formate, um deren Darstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2bd21-153">Click the other styles to see what they look like.</span></span>

17. <span data-ttu-id="2bd21-154">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-154">Click **Finish**.</span></span>

     <span data-ttu-id="2bd21-155">Nun sehen Sie den neuen Kreisdiagrammbericht auf der Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="2bd21-155">You're now looking at your new pie chart report on the design surface.</span></span> <span data-ttu-id="2bd21-156">Was Sie sehen, ist symbolisch.</span><span class="sxs-lookup"><span data-stu-id="2bd21-156">What you see is representational.</span></span> <span data-ttu-id="2bd21-157">Anstelle der Namen der Vertriebsmitarbeiter enthält die Legende "Full Name 1", "Full Name 2" usw.; außerdem ist die Größe der Kreissegmente nicht exakt.</span><span class="sxs-lookup"><span data-stu-id="2bd21-157">The legend reads Full Name 1, Full Name 2, etc., rather than the salespeople's names, and the size of the slices of pie are not accurate.</span></span> <span data-ttu-id="2bd21-158">Diese Darstellung soll nur eine Vorstellung vom Aussehen des Berichts vermitteln.</span><span class="sxs-lookup"><span data-stu-id="2bd21-158">This is just to give you an idea of what your report will look like.</span></span>

18. <span data-ttu-id="2bd21-159">Klicken Sie auf der Registerkarte **Home** des Menübands auf **Ausführen** , um das tatsächliche Kreisdiagramm anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2bd21-159">To see your actual pie chart, click **Run** on the **Home** tab of the Ribbon.</span></span>

 <span data-ttu-id="2bd21-160">![Pfeilsymbol mit dem Link "zurück zum Anfang](../../2014-toc/media/uparrow16x16.gif "Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird") " [zurück zum Anfang](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="2bd21-160">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

##  <a name="creating-the-pie-chart-with-a-tsql-query"></a><a name="CreatePieQueryData"></a> <span data-ttu-id="2bd21-161">Erstellen des Kreisdiagramms mit einer [!INCLUDE[tsql](../../../includes/tsql-md.md)] -Abfrage</span><span class="sxs-lookup"><span data-stu-id="2bd21-161">Creating the pie chart with a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query</span></span>

#### <a name="to-create-the-pie-chart-with-a-tsql-query-that-contains-data"></a><span data-ttu-id="2bd21-162">So erstellen Sie das Kreisdiagramm mit einer [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Abfrage, die Daten enthält</span><span class="sxs-lookup"><span data-stu-id="2bd21-162">To create the pie chart with a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query that contains data</span></span>

1.  <span data-ttu-id="2bd21-163">Klicken Sie auf **Start**, zeigen Sie auf **Programme**, zeigen Sie auf **Microsoft SQL Server 2012 Berichts-Generator**, und klicken Sie dann auf **Berichts-Generator**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-163">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>

2.  <span data-ttu-id="2bd21-164">Überprüfen Sie im Dialogfeld **neuer Bericht oder DataSet** , ob im linken Bereich **Bericht** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="2bd21-164">In the **New report or dataset** dialog box, verify that **Report** is selected in the left pane.</span></span>

3.  <span data-ttu-id="2bd21-165">Klicken Sie im rechten Bereich auf **Diagramm-Assistent**und anschließend auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-165">In the right pane, click **Chart Wizard**, and then click **Create**.</span></span>

4.  <span data-ttu-id="2bd21-166">Klicken Sie auf der Seite **Dataset auswählen** auf **Dataset erstellen**und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-166">In the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>

5.  <span data-ttu-id="2bd21-167">Wählen Sie auf der Seite **Verbindung mit einer Datenquelle auswählen** eine vorhandene Datenquelle aus, oder navigieren Sie zum Berichtsserver, und wählen Sie eine Datenquelle aus. Klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-167">In the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="2bd21-168">Möglicherweise müssen Benutzername und Kennwort eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2bd21-168">You may need to enter a user name and password.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="2bd21-169">Welche Datenquelle Sie auswählen, ist unwichtig, solange Sie über ausreichende Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="2bd21-169">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="2bd21-170">Aus der Datenquelle werden keine Daten abgerufen.</span><span class="sxs-lookup"><span data-stu-id="2bd21-170">You will not be getting data from the data source.</span></span> <span data-ttu-id="2bd21-171">Weitere Informationen finden Sie unter [Voraussetzungen für Lernprogramme &#40;Berichts-Generator&#41;](../report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="2bd21-171">For more information, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md).</span></span>

6.  <span data-ttu-id="2bd21-172">Klicken Sie auf der Seite **Abfrage entwerfen** auf **als Text bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-172">On the **Design a Query** page, click **Edit as Text**.</span></span>

7.  <span data-ttu-id="2bd21-173">Fügen Sie die folgende Abfrage in den Abfragebereich ein:</span><span class="sxs-lookup"><span data-stu-id="2bd21-173">Paste the following query into the query pane:</span></span>

    ```
    SELECT 150 AS Sales, 'Jae Pak' AS FullName 
    UNION SELECT 350 AS Sales, 'Jillian Carson' AS FullName 
    UNION SELECT 250 AS Sales, 'Linda C Mitchell' AS FullName 
    UNION SELECT 500 AS Sales, 'Michael Blythe' AS FullName 
    UNION SELECT 450 AS Sales, 'Ranjit Varkey' AS FullName 
    ```

8.  <span data-ttu-id="2bd21-174">(Optional) Klicken Sie auf die Schaltfläche Ausführen (**!**), um die Daten anzuzeigen, auf denen das Diagramm basiert.</span><span class="sxs-lookup"><span data-stu-id="2bd21-174">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>

9. <span data-ttu-id="2bd21-175">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-175">Click **Next**.</span></span>

10. <span data-ttu-id="2bd21-176">Klicken Sie auf der Seite **Diagrammtyp auswählen** auf **Kreisdiagramm**. Danach klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-176">In the **Choose a chart type** page, click **Pie**, and then click **Next**.</span></span>

11. <span data-ttu-id="2bd21-177">Doppelklicken Sie auf der Seite **Diagrammfelder anordnen** auf das Feld **Vertrieb** im Feld **Verfügbare Felder**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-177">In the **Arrange chart fields** page, double-click the **Sales** field in the **Available fields** box.</span></span>

     <span data-ttu-id="2bd21-178">Beachten Sie, dass der Wert automatisch in das Feld **Werte** verschoben wird, da er ein numerischer Wert ist.</span><span class="sxs-lookup"><span data-stu-id="2bd21-178">Note that it automatically moves to the **Values** box, because it's a numerical value.</span></span>

12. <span data-ttu-id="2bd21-179">Ziehen Sie das Feld **FullName** aus dem Feld **Verfügbare Felder** in das Feld **Kategorien** (oder doppelklicken Sie auf das Feld, damit es in das Feld **Kategorien** verschoben wird). Klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-179">Drag the **FullName** field from the **Available fields** box to the **Categories** box (or double-click it; it will go to the **Categories** box), and then click **Next**.</span></span>

13. <span data-ttu-id="2bd21-180">Auf der Seite Format **auswählen** ist Ozean standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="2bd21-180">In the **Choose a style** page, Ocean is selected by default.</span></span> <span data-ttu-id="2bd21-181">Klicken Sie auf die anderen Formate, um deren Darstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2bd21-181">Click the other styles to see what they look like.</span></span>

14. <span data-ttu-id="2bd21-182">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-182">Click **Finish**.</span></span>

     <span data-ttu-id="2bd21-183">Nun sehen Sie den neuen Kreisdiagrammbericht auf der Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="2bd21-183">You're now looking at your new pie chart report on the design surface.</span></span> <span data-ttu-id="2bd21-184">Was Sie sehen, ist symbolisch.</span><span class="sxs-lookup"><span data-stu-id="2bd21-184">What you see is representational.</span></span> <span data-ttu-id="2bd21-185">Anstelle der Namen der Vertriebsmitarbeiter enthält die Legende "Full Name 1", "Full Name 2" usw.; außerdem ist die Größe der Kreissegmente nicht exakt.</span><span class="sxs-lookup"><span data-stu-id="2bd21-185">The legend reads Full Name 1, Full Name 2, etc., rather than the salespeople's names, and the size of the slices of pie are not accurate.</span></span> <span data-ttu-id="2bd21-186">Diese Darstellung soll nur eine Vorstellung vom Aussehen des Berichts vermitteln.</span><span class="sxs-lookup"><span data-stu-id="2bd21-186">This is just to give you an idea of what your report will look like.</span></span>

15. <span data-ttu-id="2bd21-187">Klicken Sie auf der Registerkarte **Home** des Menübands auf **Ausführen** , um das tatsächliche Kreisdiagramm anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2bd21-187">To see your actual pie chart, click **Run** on the **Home** tab of the Ribbon.</span></span>

 <span data-ttu-id="2bd21-188">![Pfeilsymbol mit dem Link "zurück zum Anfang](../../2014-toc/media/uparrow16x16.gif "Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird") " [zurück zum Anfang](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="2bd21-188">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

##  <a name="after-you-run-the-wizard"></a><a name="AfterWizard"></a><span data-ttu-id="2bd21-189">Nach dem Ausführen des Assistenten</span><span class="sxs-lookup"><span data-stu-id="2bd21-189">After You Run the Wizard</span></span>
 <span data-ttu-id="2bd21-190">Nachdem Sie den Kreisdiagrammbericht erstellt haben, können Sie etwas experimentieren.</span><span class="sxs-lookup"><span data-stu-id="2bd21-190">Now that you have your pie chart report, you can play with it.</span></span> <span data-ttu-id="2bd21-191">Klicken Sie auf der Registerkarte **Ausführen** des Menübands auf **Entwurf**, um das Diagramm weiter ändern zu können.</span><span class="sxs-lookup"><span data-stu-id="2bd21-191">On the **Run** tab of the Ribbon, click **Design**, so you can continue modifying it.</span></span>

### <a name="make-the-chart-bigger"></a><span data-ttu-id="2bd21-192">Vergrößern des Diagramms</span><span class="sxs-lookup"><span data-stu-id="2bd21-192">Make the chart bigger</span></span>
 <span data-ttu-id="2bd21-193">Das Kreisdiagramm muss unter Umständen vergrößert werden.</span><span class="sxs-lookup"><span data-stu-id="2bd21-193">You may want the pie chart to be bigger.</span></span> <span data-ttu-id="2bd21-194">Klicken Sie auf das Diagramm, um es auszuwählen. Klicken Sie dabei jedoch nicht auf ein Element des Diagramms. Ziehen Sie anschließend die rechte untere Ecke, um die Größe zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2bd21-194">Click the chart, but not on any element in the chart, to select it and drag the lower-right corner to resize it.</span></span>

### <a name="add-a-report-title"></a><span data-ttu-id="2bd21-195">Hinzufügen eines Berichtstitels</span><span class="sxs-lookup"><span data-stu-id="2bd21-195">Add a report title</span></span>
 <span data-ttu-id="2bd21-196">Markieren Sie am oberen Rand des Diagramms den Text **Diagrammtitel** , und geben Sie anschließend einen Titel (beispielsweise **Sales Pie Chart**) ein.</span><span class="sxs-lookup"><span data-stu-id="2bd21-196">Select the words **Chart title** at the top of the chart, and then type a title, such as **Sales Pie Chart**.</span></span>

### <a name="add-percentages"></a><span data-ttu-id="2bd21-197">Hinzufügen von Prozentsätzen</span><span class="sxs-lookup"><span data-stu-id="2bd21-197">Add percentages</span></span>

##### <a name="to-display-percentage-values-as-labels-on-a-pie-chart"></a><span data-ttu-id="2bd21-198">So zeigen Sie Prozentwerte als Bezeichnungen in einem Kreisdiagramm an</span><span class="sxs-lookup"><span data-stu-id="2bd21-198">To display percentage values as labels on a pie chart</span></span>

1.  <span data-ttu-id="2bd21-199">Klicken Sie mit der rechten Maustaste auf das Kreis Diagramm, und wählen Sie **Daten Bezeichnungen anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="2bd21-199">Right-click on the pie chart and select **Show Data Labels**.</span></span> <span data-ttu-id="2bd21-200">Die Datenbezeichnungen sollten innerhalb jedes Segments des Kreisdiagramms angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2bd21-200">The data labels should appear within each slice on the pie chart.</span></span>

2.  <span data-ttu-id="2bd21-201">Klicken Sie mit der rechten Maustaste auf die Bezeichnungen, und wählen Sie Reihen Bezeichnungs **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="2bd21-201">Right-click on the labels and select **Series Label Properties**.</span></span> <span data-ttu-id="2bd21-202">Das Dialogfeld **Reihenbezeichnungseigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2bd21-202">The **Series Label Properties** dialog box appears.</span></span>

3.  <span data-ttu-id="2bd21-203">Geben Sie `#PERCENT{P0}` für die Option Bezeichnungs **Daten** ein.</span><span class="sxs-lookup"><span data-stu-id="2bd21-203">Type `#PERCENT{P0}` for the **Label data** option.</span></span>

     <span data-ttu-id="2bd21-204">Mit `{P0}` erhalten Sie den Prozentsatz ohne Dezimalstellen.</span><span class="sxs-lookup"><span data-stu-id="2bd21-204">The `{P0}` gives you the percentage without decimal places.</span></span> <span data-ttu-id="2bd21-205">Falls Sie nur `#PERCENT` eingeben, erhalten Ihre Zahlen zwei Dezimalstellen.</span><span class="sxs-lookup"><span data-stu-id="2bd21-205">If you type just `#PERCENT`, your numbers will have two decimal places.</span></span> <span data-ttu-id="2bd21-206">`#PERCENT` ist ein Schlüsselwort, das eine Berechnung oder eine Funktion für Sie ausführt. Dies ist nur ein Beispiel unter vielen.</span><span class="sxs-lookup"><span data-stu-id="2bd21-206">`#PERCENT` is a keyword that performs a calculation or function for you; there are many others.</span></span>

 <span data-ttu-id="2bd21-207">Weitere Informationen zum Anpassen von Diagrammbezeichnungen und -legenden finden Sie unter [Anzeigen von Prozentwerten in einem Kreisdiagramm &#40;Berichts-Generator und SSRS&#41;](../report-design/display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) sowie unter [Ändern des Texts eines Legendenelements &#40;Berichts-Generator und SSRS&#41;](../report-design/chart-legend-change-item-text-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="2bd21-207">For more information about customizing chart labels and legends, see [Display Percentage Values on a Pie Chart &#40;Report Builder and SSRS&#41;](../report-design/display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) and [Change the Text of a Legend Item &#40;Report Builder and SSRS&#41;](../report-design/chart-legend-change-item-text-report-builder.md).</span></span>

 <span data-ttu-id="2bd21-208">![Pfeilsymbol mit dem Link "zurück zum Anfang](../../2014-toc/media/uparrow16x16.gif "Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird") " [zurück zum Anfang](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="2bd21-208">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

##  <a name="whats-next"></a><a name="WhatsNext"></a><span data-ttu-id="2bd21-209">Was kommt als nächstes?</span><span class="sxs-lookup"><span data-stu-id="2bd21-209">What's Next?</span></span>
 <span data-ttu-id="2bd21-210">Nachdem Sie nun Ihren ersten Bericht im Berichts-Generator erstellt haben, können Sie die anderen Lernprogramme ausführen und die ersten Berichte mit Ihren eigenen Daten erstellen.</span><span class="sxs-lookup"><span data-stu-id="2bd21-210">Now that you have created your first report in Report Builder, you are ready to try the other tutorials and to start creating reports from your own data.</span></span> <span data-ttu-id="2bd21-211">Um Berichts-Generator auszuführen, benötigen Sie die Berechtigung für den Zugriff auf Ihre Datenquellen, z. b. Datenbanken, mit einer *Verbindungs Zeichenfolge*, die Sie tatsächlich mit der Datenquelle verbindet.</span><span class="sxs-lookup"><span data-stu-id="2bd21-211">To run Report Builder, you need permission to access your data sources, such as databases, with a *connection string*, which actually connects you to the data source.</span></span> <span data-ttu-id="2bd21-212">Der Systemadministrator hat diese Informationen und kann Ihnen bei der Einrichtung helfen.</span><span class="sxs-lookup"><span data-stu-id="2bd21-212">Your system administrator will have this information and can set you up.</span></span>

 <span data-ttu-id="2bd21-213">Zum Absolvieren der anderen Lernprogramme benötigen Sie den Namen einer Instanz von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] sowie Anmeldeinformationen für den schreibgeschützten Zugriff auf eine beliebige Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2bd21-213">To work through the other tutorials, you need the name of an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] and credentials sufficient for read-only access to any database.</span></span> <span data-ttu-id="2bd21-214">Auch dabei können Sie sich an den Systemadministrator wenden.</span><span class="sxs-lookup"><span data-stu-id="2bd21-214">Your system administrator can also set that up for you.</span></span>

 <span data-ttu-id="2bd21-215">Schließlich benötigen Sie die URL und die Berechtigungen, um die Berichte auf einem Berichtsserver oder einer SharePoint-Website zu speichern, die mit einem Berichtsserver integriert ist.</span><span class="sxs-lookup"><span data-stu-id="2bd21-215">Finally, to save your reports to a report server or a SharePoint site that is integrated with a report server, you need the URL and permissions.</span></span> <span data-ttu-id="2bd21-216">Sie können jeden Bericht, den Sie erstellen, direkt auf Ihrem Computer ausführen. Berichte haben jedoch mehr Funktionalität, wenn sie vom Berichtsserver oder von einer SharePoint-Website aus ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2bd21-216">You can run any report you create directly from your computer, but reports have more functionality when run from the report server or SharePoint site.</span></span> <span data-ttu-id="2bd21-217">Sie benötigen Berechtigungen zum Ausführen Ihrer Berichte oder anderer Berichte auf dem Berichtsserver oder einer SharePoint-Website, auf der sie veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="2bd21-217">You need permissions to run your reports or others from the report server or SharePoint site where they are published.</span></span> <span data-ttu-id="2bd21-218">Wenden Sie sich an den Systemadministrator, um Zugriff zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2bd21-218">Talk to your system administrator to obtain access.</span></span>

 <span data-ttu-id="2bd21-219">Außerdem sollten Sie sich zunächst mit einigen Grundlagen und Begriffen vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="2bd21-219">It may help to read about some of the concepts and terms before you get started.</span></span> <span data-ttu-id="2bd21-220">Weitere Informationen finden Sie unter [Konzepte der Berichterstellung &#40;Berichts-Generator und SSRS&#41;](../report-design/report-authoring-concepts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2bd21-220">For more information, see [Report Authoring Concepts &#40;Report Builder and SSRS&#41;](../report-design/report-authoring-concepts-report-builder-and-ssrs.md).</span></span> <span data-ttu-id="2bd21-221">Außerdem sollten Sie das Erstellen Ihres ersten Berichts sorgfältig planen.</span><span class="sxs-lookup"><span data-stu-id="2bd21-221">Also, spend some time planning, before you create your first report.</span></span> <span data-ttu-id="2bd21-222">Der Aufwand lohnt sich.</span><span class="sxs-lookup"><span data-stu-id="2bd21-222">It will be time well spent.</span></span> <span data-ttu-id="2bd21-223">Weitere Informationen finden Sie unter [Planning a Report &#40;Berichts-Generator&#41;](../report-design/planning-a-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="2bd21-223">For more information, see [Planning a Report &#40;Report Builder&#41;](../report-design/planning-a-report-report-builder.md).</span></span>

 <span data-ttu-id="2bd21-224">![Pfeilsymbol mit dem Link "zurück zum Anfang](../../2014-toc/media/uparrow16x16.gif "Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird") " [zurück zum Anfang](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="2bd21-224">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

## <a name="see-also"></a><span data-ttu-id="2bd21-225">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2bd21-225">See Also</span></span>
 <span data-ttu-id="2bd21-226">Lernprogramme [&#40;Berichts-Generator&#41;](../report-builder-tutorials.md) [Berichts-Generator in SQL Server 2014](report-builder-in-sql-server-2016.md)</span><span class="sxs-lookup"><span data-stu-id="2bd21-226">[Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md) [Report Builder in SQL Server 2014](report-builder-in-sql-server-2016.md)</span></span>


