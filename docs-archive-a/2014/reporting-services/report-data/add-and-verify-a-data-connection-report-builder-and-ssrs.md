---
title: Hinzufügen und Überprüfen einer Datenverbindung oder Datenquelle (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1d3b2573-e29d-480d-9dde-d26379c86618
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d86b3e6598c12545f0e24ef1d162eeb1131bd15d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608347"
---
# <a name="add-and-verify-a-data-connection-or-data-source-report-builder-and-ssrs"></a><span data-ttu-id="7bfbb-102">Hinzufügen und Prüfen einer Datenverbindung oder Datenquelle (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="7bfbb-102">Add and Verify a Data Connection or Data Source (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7bfbb-103">Im Berichts-Generator können Sie eine freigegebene Datenquelle des Berichtsservers hinzufügen oder eine eingebettete Datenquelle für Ihren Bericht erstellen.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-103">In Report Builder, you can add a shared data source from the report server or create an embedded data source for your report.</span></span> <span data-ttu-id="7bfbb-104">Im Berichts-Designer können Sie eine freigegebene Datenquelle oder eine eingebettete Datenquelle erstellen und sie auf einem Berichtsserver bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-104">In Report Designer, you can create a shared data source or an embedded data source and deploy it to a report server.</span></span>  
  
 <span data-ttu-id="7bfbb-105">Navigieren Sie zu einem Berichtsserver, und wählen Sie eine freigegebene Datenquelle aus, um diese in den Bericht aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-105">To add a shared data source to your report, browse to a report server and select a shared data source.</span></span> <span data-ttu-id="7bfbb-106">Die freigegebene Datenquelle im Bericht verweist auf die freigegebene Datenquellendefinition auf dem Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-106">The shared data source in your report points to the shared data source definition on the report server.</span></span>  
  
 <span data-ttu-id="7bfbb-107">Zum Erstellen einer eingebetteten Datenquelle benötigen Sie Informationen über die Verbindung mit der externen Datenquelle, und Sie müssen wissen, welche Berechtigungen für den Zugriff auf die Daten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-107">To create an embedded data source, you must have connection information to the external source of data and you must know which permissions you need to access the data.</span></span> <span data-ttu-id="7bfbb-108">Diese Informationen erhalten Sie normalerweise vom Besitzer der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-108">This information usually comes from the owner of the data source.</span></span> <span data-ttu-id="7bfbb-109">Sie können die Verbindung testen, um zu überprüfen, ob die angegebenen Anmeldeinformationen ausreichend sind.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-109">You can test the connection to verify that the credentials that are specified are sufficient.</span></span>  
  
 <span data-ttu-id="7bfbb-110">Weitere Informationen finden Sie unter [Datenverbindungen, Datenquellen und Verbindungszeichenfolgen im Berichts-Generator](../data-connections-data-sources-and-connection-strings-in-report-builder.md) und [Angeben von Anmeldeinformationen im Berichts-Generator](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="7bfbb-110">For more information, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md) and [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-create-a-reference-to-a-shared-data-source"></a><span data-ttu-id="7bfbb-111">So erstellen Sie einen Verweis auf eine freigegebene Datenquelle</span><span class="sxs-lookup"><span data-stu-id="7bfbb-111">To create a reference to a shared data source</span></span>  
  
1.  <span data-ttu-id="7bfbb-112">Klicken Sie im Berichtsdatenbereich auf der Symbolleiste auf **Neu** und anschließend auf **Datenquelle**.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-112">On the toolbar in the Report Data pane, click **New,** and then click **Data Source**.</span></span> <span data-ttu-id="7bfbb-113">Das Dialogfeld **Datenquelleneigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-113">The **Data Source Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="7bfbb-114">Geben Sie in das Textfeld **Name** einen Namen für die Datenquelle ein.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-114">In the **Name** text box, type a name for the data source.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7bfbb-115">Dieser Name wird in der lokalen Berichtsdefinition gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-115">This name is saved in the local report definition.</span></span> <span data-ttu-id="7bfbb-116">Der Name entspricht nicht dem Namen der freigegebenen Datenquelle auf dem Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-116">This name is not the name of the shared data source on the report server.</span></span>  
  
3.  <span data-ttu-id="7bfbb-117">Wählen Sie **Freigegebene Verbindung oder Berichtsmodell verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-117">Select **Use a shared connection or report model**.</span></span> <span data-ttu-id="7bfbb-118">Die Liste der zuletzt verwendeten freigegebenen Datenquellen und Berichtsmodelle wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-118">The list of recently used shared data sources and report models appears.</span></span> <span data-ttu-id="7bfbb-119">Klicken Sie zum Auswählen einer Datenquelle auf **Durchsuchen** , und suchen Sie den Ordner auf dem Berichtsserver mit den freigegebenen Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-119">To select one from a report server, click **Browse** and browse to the folder on the report server where shared data sources are available.</span></span>  
  
4.  <span data-ttu-id="7bfbb-120">Wählen Sie die freigegebene Datenquelle aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-120">Select the shared data source and then click **Open**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="7bfbb-121">Die Datenquelle wird im Berichtsdatenbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-121">The data source appears in the Report Data pane.</span></span>  
  
### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="7bfbb-122">So erstellen Sie eine eingebettete Datenquelle</span><span class="sxs-lookup"><span data-stu-id="7bfbb-122">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="7bfbb-123">Klicken Sie im Berichtsdaten Bereich auf der Symbolleiste auf **neu**, und klicken Sie dann auf **Datenquelle**.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-123">On the toolbar in the Report Data pane, click **New**, and then click **Data Source**.</span></span> <span data-ttu-id="7bfbb-124">Das Dialogfeld **Datenquelleneigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-124">The **Data Source Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="7bfbb-125">Geben Sie im Textfeld **Name** einen Namen für die Datenquelle ein, oder übernehmen Sie den Standardnamen.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-125">In the **Name** text box, type a name for the data source or accept the default.</span></span>  
  
3.  <span data-ttu-id="7bfbb-126">Stellen Sie sicher, dass die Option **In Bericht eingebettete Verbindung verwenden** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-126">Verify that **Use a connection embedded in my report** is selected.</span></span>  
  
    1.  <span data-ttu-id="7bfbb-127">Wählen Sie in der Dropdownliste **Verbindungstyp auswählen** einen Datenquellentyp aus, zum Beispiel **Microsoft SQL Server** oder **OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-127">From the **Select connection type** drop-down list, select a data source type; for example, **Microsoft SQL Server** or **OLE DB**.</span></span>  
  
    2.  <span data-ttu-id="7bfbb-128">Geben Sie eine Verbindungszeichenfolge mit einer der folgenden Möglichkeiten an:</span><span class="sxs-lookup"><span data-stu-id="7bfbb-128">Specify a connection string by using one of the following alternatives:</span></span>  
  
    -   <span data-ttu-id="7bfbb-129">Geben Sie die Verbindungszeichenfolge direkt in das Textfeld **Verbindungszeichenfolge** ein.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-129">Type the connection string directly in the **Connection string** text box.</span></span> <span data-ttu-id="7bfbb-130">Eine Liste von Beispielen für Verbindungszeichenfolgen finden Sie unter [Datenverbindungen, Datenquellen und Verbindungszeichenfolgen in Berichts-Generator](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="7bfbb-130">For a list of example connection strings, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span></span>  
  
    -   <span data-ttu-id="7bfbb-131">Klicken Sie auf die Ausdrucksschaltfläche (**fx)** , um einen Ausdruck zu erstellen, der als Verbindungszeichenfolge ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-131">Click the expression (**fx)** button to create an expression that evaluates to a connection string.</span></span> <span data-ttu-id="7bfbb-132">Geben Sie den Ausdruck im Dialogfeld **Ausdruck** in den Bereich Ausdruck ein.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-132">In the **Expression** dialog box, type the expression in the Expression pane.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    -   <span data-ttu-id="7bfbb-133">Klicken Sie auf **Erstellen** , um das Dialogfeld **Verbindungseigenschaften** für den Datenquellentyp zu öffnen, den Sie in Schritt 2 gewählt haben.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-133">Click **Build** to open the **Connection Properties** dialog box for the data source type that you chose in step 2.</span></span>  
  
         <span data-ttu-id="7bfbb-134">Füllen Sie die Felder im Dialogfeld **Verbindungseigenschaften** gemäß dem jeweiligen Datenquellentyp aus.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-134">Fill in the fields in the **Connection Properties** dialog box as appropriate for the data source type.</span></span> <span data-ttu-id="7bfbb-135">Verbindungseigenschaften enthalten den Typ der Datenquelle, den Namen der Datenquelle und die zu verwendenden Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-135">Connection properties include the type of data source, the name of the data source, and the credentials to use.</span></span> <span data-ttu-id="7bfbb-136">Nachdem Sie in diesem Dialogfeld Werte angegeben haben, klicken Sie auf **Verbindung testen** , um zu überprüfen, ob die Datenquelle verfügbar ist und die angegebenen Anmeldeinformationen richtig sind.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-136">After you specify values in this dialog box, click **Test Connection** to verify that the data source is available and that the credentials you specified are correct.</span></span>  
  
4.  <span data-ttu-id="7bfbb-137">Klicken Sie auf **Anmeldeinformationen**.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-137">Click **Credentials**.</span></span>  
  
     <span data-ttu-id="7bfbb-138">Geben Sie die Anmeldeinformationen für diese Datenquelle an.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-138">Specify the credentials to use for this data source.</span></span> <span data-ttu-id="7bfbb-139">Der Besitzer der Datenquelle wählt den Typ von Anmeldeinformationen aus, die unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-139">The owner of the data source chooses the type of credentials that are supported.</span></span> <span data-ttu-id="7bfbb-140">In einigen Fällen verwaltet der Besitzer der Datenquelle eine freigegebene Datenquelle in einem Berichtsserver und konfiguriert die Datenquelle mit Anmeldeinformationen, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-140">In some cases, the owner of the data source maintains a shared data source on a report server and configures the data source with credentials that you can use.</span></span> <span data-ttu-id="7bfbb-141">Wenden Sie sich an den Datenquellenbesitzer für diese Informationen.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-141">Contact the data source owner for this information.</span></span> <span data-ttu-id="7bfbb-142">Weitere Informationen finden Sie unter [Angeben von Anmeldeinformationen im Berichts-Generator](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="7bfbb-142">For more information, see [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="7bfbb-143">Die Datenquelle wird im Berichtsdatenbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-143">The data source appears in the Report Data pane.</span></span>  
  
### <a name="to-verify-a-data-connection"></a><span data-ttu-id="7bfbb-144">So überprüfen Sie eine Datenverbindung</span><span class="sxs-lookup"><span data-stu-id="7bfbb-144">To verify a data connection</span></span>  
  
1.  <span data-ttu-id="7bfbb-145">Doppelklicken Sie auf der Symbolleiste im Berichtsdatenbereich auf die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-145">On the toolbar in the Report Data pane, double-click the data source.</span></span> <span data-ttu-id="7bfbb-146">Das Dialogfeld **Datenquelleneigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-146">The **Data Source Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="7bfbb-147">Klicken Sie auf **Verbindung testen**.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-147">Click **Test Connection**.</span></span>  
  
3.  <span data-ttu-id="7bfbb-148">Bei einer erfolgreichen Verbindung wird die folgende Meldung angezeigt: "Die Verbindung wurde erfolgreich erstellt".</span><span class="sxs-lookup"><span data-stu-id="7bfbb-148">If the connection is successful, the following message appears: "Connection created successfully".</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="7bfbb-149">Wenn die Verbindung nicht erfolgreich hergestellt werden kann, wird die folgende Meldung angezeigt: "Es konnte keine Verbindung mit der Datenquelle hergestellt werden".</span><span class="sxs-lookup"><span data-stu-id="7bfbb-149">If the connection is not successful, the following message appears: "Unable to connect to the data source."</span></span>  
  
5.  <span data-ttu-id="7bfbb-150">Klicken Sie auf **Details**, und beheben Sie das Problem mithilfe der angezeigten Informationen.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-150">Click **Details**, and use the information to correct the issue.</span></span>  
  
     <span data-ttu-id="7bfbb-151">Weitere Informationen finden Sie unter [Angeben von Anmeldeinformationen im Berichts-Generator](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="7bfbb-151">For more information, see [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7bfbb-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7bfbb-152">See Also</span></span>  
 <span data-ttu-id="7bfbb-153">[Hinzufügen von Daten zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7bfbb-153">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="7bfbb-154">[Melden Sie eingebettete Datasets und freigegebene Datasets &#40;Berichts-Generator und SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7bfbb-154">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7bfbb-155">[Suchen, anzeigen und Verwalten von Berichten &#40;Berichts-Generator und SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7bfbb-155">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7bfbb-156">Datenverbindungen, Datenquellen und Verbindungszeichenfolgen in Berichts-Generator</span><span class="sxs-lookup"><span data-stu-id="7bfbb-156">Data Connections, Data Sources, and Connection Strings in Report Builder</span></span>](../data-connections-data-sources-and-connection-strings-in-report-builder.md)  
  
  
