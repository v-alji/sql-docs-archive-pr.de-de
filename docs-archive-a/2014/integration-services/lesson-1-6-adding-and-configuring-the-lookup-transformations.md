---
title: 'Schritt 6: Hinzufügen und Konfigurieren von Suchtransformationen | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5c59f723-9707-4407-80ae-f05f483cf65f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 96b0a848508c19eb24cf1538244a39fcec57361a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618126"
---
# <a name="step-6-adding-and-configuring-the-lookup-transformations"></a><span data-ttu-id="7e269-102">Schritt 6: Hinzufügen und Konfigurieren der Transformationen zum Suchen</span><span class="sxs-lookup"><span data-stu-id="7e269-102">Step 6: Adding and Configuring the Lookup Transformations</span></span>
  <span data-ttu-id="7e269-103">Nach dem Konfigurieren der Flatfilequelle zum Extrahieren von Daten aus der Quelldatei besteht die nächste Aufgabe darin, die Suchtransformationen zu definieren, die zum Abrufen der Werte für **CurrencyKey** und **DateKey**erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="7e269-103">After you have configured the Flat File source to extract data from the source file, the next task is to define the Lookup transformations needed to obtain the values for the **CurrencyKey** and **DateKey**.</span></span> <span data-ttu-id="7e269-104">Von einer Transformation zum Suchen wird eine Suche durchgeführt, indem Daten in der angegebenen Eingabespalte mit einer Spalte in einem referenzierten Dataset verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="7e269-104">A Lookup transformation performs a lookup by joining data in the specified input column to a column in a reference dataset.</span></span> <span data-ttu-id="7e269-105">Bei dem Verweisdataset kann es sich um eine vorhandene Tabelle oder Sicht, eine neue Tabelle oder das Ergebnis einer SQL-Anweisung handeln.</span><span class="sxs-lookup"><span data-stu-id="7e269-105">The reference dataset can be an existing table or view, a new table, or the result of an SQL statement.</span></span> <span data-ttu-id="7e269-106">In diesem Lernprogramm stellt die Transformation für Suche stellt mithilfe eines OLE DB-Verbindungs-Managers eine Verbindung mit der Datenbank her, die die Daten enthält, die als Quelle des Verweisdatasets dienen.</span><span class="sxs-lookup"><span data-stu-id="7e269-106">In this tutorial, the Lookup transformation uses an OLE DB connection manager to connect to the database that contains the data that is the source of the reference dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7e269-107">Sie können die Transformation für Suche auch so konfigurieren, dass sie eine Verbindung mit einem Cache herstellt, der das Verweisdataset enthält.</span><span class="sxs-lookup"><span data-stu-id="7e269-107">You can also configure the Lookup transformation to connect to a cache that contains the reference dataset.</span></span> <span data-ttu-id="7e269-108">Weitere Informationen finden Sie unter [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="7e269-108">For more information, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
 <span data-ttu-id="7e269-109">Für dieses Lernprogramm fügen Sie die folgenden zwei Transformationskomponenten zum Suchen zu dem Paket hinzu und konfigurieren sie:</span><span class="sxs-lookup"><span data-stu-id="7e269-109">For this tutorial, you will add and configure the following two Lookup transformation components to the package:</span></span>  
  
-   <span data-ttu-id="7e269-110">Eine Transformation zum Ausführen einer Suche nach Werten aus der **CurrencyKey** -Spalte der **DimCurrency** -Dimensionstabelle basierend auf übereinstimmenden **CurrencyID** -Spaltenwerten aus der Flatfile.</span><span class="sxs-lookup"><span data-stu-id="7e269-110">One transformation to perform a lookup of values from the **CurrencyKey** column of the **DimCurrency** dimension table based on matching **CurrencyID** column values from the flat file.</span></span>  
  
-   <span data-ttu-id="7e269-111">Eine Transformation zum Ausführen einer Suche nach Werten in der **DateKey** -Spalte der **DimDate** -Dimensionstabelle basierend auf übereinstimmenden **CurrencyDate** -Spaltenwerten aus der Flatfile.</span><span class="sxs-lookup"><span data-stu-id="7e269-111">One transformation to perform a lookup of values from the **DateKey** column of the **DimDate** dimension table based on matching **CurrencyDate** column values from the flat file.</span></span>  
  
 <span data-ttu-id="7e269-112">In beiden Fällen verwendet die Suchtransformation den OLE DB-Verbindungs-Manager, den Sie zuvor erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="7e269-112">In both cases, the Lookup transformation will utilize the OLE DB connection manager that you previously created.</span></span>  
  
### <a name="to-add-and-configure-the-lookup-currency-key-transformation"></a><span data-ttu-id="7e269-113">So fügen Sie die Lookup Currency Key-Transformation hinzu und konfigurieren sie</span><span class="sxs-lookup"><span data-stu-id="7e269-113">To add and configure the Lookup Currency Key transformation</span></span>  
  
1.  <span data-ttu-id="7e269-114">Erweitern Sie in der **SSIS-Toolbox**die Option **Allgemein**, und ziehen **Sie dann Suche** auf die Entwurfs Oberfläche der Registerkarte **Datenfluss** . Platzieren Sie die Suche direkt unterhalb der **Extract Sample Currency Data** -Quelle.</span><span class="sxs-lookup"><span data-stu-id="7e269-114">In the **SSIS Toolbox**, expand **Common**, and then drag **Lookup** onto the design surface of the **Data Flow** tab. Place Lookup directly below the **Extract Sample Currency Data** source.</span></span>  
  
2.  <span data-ttu-id="7e269-115">Klicken Sie auf die **Extract Sample Currency Data** -Flatfilequelle, und ziehen Sie den grünen Pfeil auf die neu hinzugefügte Transformation **Suche** , um die zwei Komponenten zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="7e269-115">Click the **Extract Sample Currency Data** flat file source and drag the green arrow onto the newly added **Lookup** transformation to connect the two components.</span></span>  
  
3.  <span data-ttu-id="7e269-116">Klicken Sie auf der **Datenfluss** -Entwurfsoberfläche auf **Suche** in der Transformation **Suche** , und ändern Sie den Namen in **Lookup Currency Key**.</span><span class="sxs-lookup"><span data-stu-id="7e269-116">On the **Data Flow** design surface, click **Lookup** in the **Lookup** transformation, and change the name to **Lookup Currency Key**.</span></span>  
  
4.  <span data-ttu-id="7e269-117">Doppelklicken Sie auf die Transformation **Lookup Currency Key** , um den Transformations-Editor für Suche anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7e269-117">Double-click the **Lookup CurrencyKey** transformation to display the Lookup Transformation Editor.</span></span>  
  
5.  <span data-ttu-id="7e269-118">Wählen Sie auf der Seite **Allgemein** die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="7e269-118">On the **General** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="7e269-119">Wählen Sie **Vollcache**aus.</span><span class="sxs-lookup"><span data-stu-id="7e269-119">Select **Full cache**.</span></span>  
  
    2.  <span data-ttu-id="7e269-120">Wählen Sie im Bereich **Verbindungstyp** **OLE DB-Verbindungs-Manager**aus.</span><span class="sxs-lookup"><span data-stu-id="7e269-120">In the **Connection type** area, select **OLE DB connection manager**.</span></span>  
  
6.  <span data-ttu-id="7e269-121">Wählen Sie auf der Seite **Verbindung** die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="7e269-121">On the **Connection** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="7e269-122">Stellen Sie im **OLE DB-Verbindungs-Manager** sicher, dass **localhost.AdventureWorksDW2012** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7e269-122">In the **OLE DB connection manager** dialog box, ensure that **localhost.AdventureWorksDW2012** is displayed.</span></span>  
  
    2.  <span data-ttu-id="7e269-123">Wählen Sie **Ergebnisse einer SQL-Abfrage verwenden**aus, und geben Sie anschließend die folgende SQL-Anweisung ein, oder kopieren Sie diese:</span><span class="sxs-lookup"><span data-stu-id="7e269-123">Select **Use results of an SQL query**, and then type or copy the following SQL statement:</span></span>  
  
        ```  
        select * from (select * from [dbo].[DimCurrency]) as refTable  
        where [refTable].[CurrencyAlternateKey] = 'ARS'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'AUD'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'BRL'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'CAD'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'CNY'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'DEM'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'EUR'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'FRF'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'GBP'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'JPY'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'MXN'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'SAR'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'USD'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'VEB'  
        ```  
  
7.  <span data-ttu-id="7e269-124">Wählen Sie auf der Seite **Spalten** die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="7e269-124">On the **Columns** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="7e269-125">Ziehen Sie aus dem Bereich **Verfügbare Eingabespalten** den Spaltennamen **CurrencyID** in den Bereich **Verfügbare Suchspalten** auf **CurrencyAlternateKey**.</span><span class="sxs-lookup"><span data-stu-id="7e269-125">In the **Available Input Columns** panel, drag **CurrencyID** to the **Available Lookup Columns** panel and drop it on **CurrencyAlternateKey**.</span></span>  
  
    2.  <span data-ttu-id="7e269-126">Aktivieren Sie in der Liste **Verfügbare Suchspalten** das Kontrollkästchen links neben **CurrencyKey**.</span><span class="sxs-lookup"><span data-stu-id="7e269-126">In the **Available Lookup Columns** list, select the check box to the left of **CurrencyKey**.</span></span>  
  
8.  <span data-ttu-id="7e269-127">Klicken Sie auf **OK** , um zur Entwurfsoberfläche **Datenfluss** zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="7e269-127">Click **OK** to return to the **Data Flow** design surface.</span></span>  
  
9. <span data-ttu-id="7e269-128">Klicken Sie mit der rechten Maustaste auf die Lookup Currency Key-Transformation, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="7e269-128">Right-click the Lookup Currency Key transformation, click **Properties**.</span></span>  
  
10. <span data-ttu-id="7e269-129">Überprüfen Sie im Eigenschaftenfenster, ob die `LocaleID` -Eigenschaft auf **Englisch (USA)** und die **DefaultCodePage** -Eigenschaft auf **1252**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7e269-129">In the Properties window, verify that the `LocaleID` property is set to **English (United States)** and the **DefaultCodePage** property is set to **1252**.</span></span>  
  
### <a name="to-add-and-configure-the--lookup-datekey-transformation"></a><span data-ttu-id="7e269-130">So fügen Sie die Lookup DateKey-Transformation hinzu und konfigurieren sie</span><span class="sxs-lookup"><span data-stu-id="7e269-130">To add and configure the  Lookup DateKey transformation</span></span>  
  
1.  <span data-ttu-id="7e269-131">Ziehen Sie in der **SSIS-Toolbox**die Option **Suche** auf die **Datenfluss** -Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="7e269-131">In the **SSIS Toolbox**, drag **Lookup** onto the **Data Flow** design surface.</span></span> <span data-ttu-id="7e269-132">Legen Sie „Suche“ direkt unterhalb der Transformation **Lookup Currency Key** ab.</span><span class="sxs-lookup"><span data-stu-id="7e269-132">Place Lookup directly below the **Lookup Currency Key** transformation.</span></span>  
  
2.  <span data-ttu-id="7e269-133">Klicken Sie auf die **Lookup Currency Key** -Transformation, und ziehen Sie den grünen Pfeil auf die neu hinzugefügte **Suche** -Transformation, um die zwei Komponenten zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="7e269-133">Click the **Lookup Currency Key** transformation and drag the green arrow onto the newly added **Lookup** transformation to connect the two components.</span></span>  
  
3.  <span data-ttu-id="7e269-134">Klicken Sie im Dialogfeld **Eingabe-/Ausgabe-Auswahl** im Listenfeld **Ausgabe** auf **Ausgabe der Suchübereinstimmungen** , und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7e269-134">In the **Input Output Selection** dialog box, click **Lookup Match Output** in the **Output** list box, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="7e269-135">Klicken Sie auf der Entwurfsoberfläche **Datenfluss** in der neu hinzugefügten Transformation **Suche** auf **Suche** , und ändern Sie den Namen in **Lookup Date Key**.</span><span class="sxs-lookup"><span data-stu-id="7e269-135">On the **Data Flow** design surface, click **Lookup** in the newly added **Lookup** transformation, and change the name to **Lookup Date Key**.</span></span>  
  
5.  <span data-ttu-id="7e269-136">Doppelklicken Sie auf die Transformation **Lookup Date Key** .</span><span class="sxs-lookup"><span data-stu-id="7e269-136">Double-click the **Lookup Date Key** transformation.</span></span>  
  
6.  <span data-ttu-id="7e269-137">Wählen Sie auf der Seite **Allgemein** die Option **Teilcache**aus.</span><span class="sxs-lookup"><span data-stu-id="7e269-137">On the **General** page, select **Partial cache**.</span></span>  
  
7.  <span data-ttu-id="7e269-138">Wählen Sie auf der Seite **Verbindung** die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="7e269-138">On the **Connection** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="7e269-139">Stellen Sie im **OLE DB-Verbindungs-Manager** sicher, dass **localhost.AdventureWorksDW2012** angezeigt wird.rd.</span><span class="sxs-lookup"><span data-stu-id="7e269-139">In the **OLEDB connection manager** dialog box, ensure that **localhost.AdventureWorksDW2012** is displayed.</span></span>  
  
    2.  <span data-ttu-id="7e269-140">Geben Sie im Feld **Tabelle oder Sicht verwenden** den Eintrag **[dbo].[DimDate]** ein, oder wählen Sie diesen Eintrag aus.</span><span class="sxs-lookup"><span data-stu-id="7e269-140">In the **Use a table or view** box, type or select **[dbo].[DimDate]**.</span></span>  
  
8.  <span data-ttu-id="7e269-141">Wählen Sie auf der Seite **Spalten** die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="7e269-141">On the **Columns** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="7e269-142">Ziehen Sie aus dem Bereich **Verfügbare Eingabespalten** den Spaltennamen **CurrencyDate** in den Bereich **Verfügbare Suchspalten** auf **FullDateAlternateKey**.</span><span class="sxs-lookup"><span data-stu-id="7e269-142">In the **Available Input Columns** panel, drag **CurrencyDate** to the **Available Lookup Columns** panel and drop it on **FullDateAlternateKey**.</span></span>  
  
    2.  <span data-ttu-id="7e269-143">Aktivieren Sie in der Liste **Verfügbare Suchspalten** das Kontrollkästchen links neben **DateKey**.</span><span class="sxs-lookup"><span data-stu-id="7e269-143">In the **Available Lookup Columns** list, select the check box to the left of **DateKey**.</span></span>  
  
9. <span data-ttu-id="7e269-144">Überprüfen Sie auf der Seite **Erweitert** die Optionen für die Zwischenspeicherung.</span><span class="sxs-lookup"><span data-stu-id="7e269-144">On the **Advanced** page, review the caching options.</span></span>  
  
10. <span data-ttu-id="7e269-145">Klicken Sie auf **OK** , um zur Entwurfsoberfläche **Datenfluss** zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="7e269-145">Click **OK** to return to the **Data Flow** design surface.</span></span>  
  
11. <span data-ttu-id="7e269-146">Klicken Sie mit der rechten Maustaste auf die Lookup Date Key-Transformation, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="7e269-146">Right-click the Lookup Date Key transformation and click **Properties.**</span></span>  
  
12. <span data-ttu-id="7e269-147">Überprüfen Sie im Eigenschaftenfenster, ob die `LocaleID` -Eigenschaft auf **Englisch (USA)** und die **DefaultCodePage** -Eigenschaft auf **1252**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7e269-147">In the Properties window, verify that the `LocaleID` property is set to **English (United States)** and the **DefaultCodePage** property is set to **1252**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="7e269-148">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="7e269-148">Next Task in Lesson</span></span>  
 [<span data-ttu-id="7e269-149">Schritt 7: Hinzufügen und Konfigurieren des OLE DB-Ziels</span><span class="sxs-lookup"><span data-stu-id="7e269-149">Step 7: Adding and Configuring the OLE DB Destination</span></span>](lesson-1-7-adding-and-configuring-the-ole-db-destination.md)  
  
## <a name="see-also"></a><span data-ttu-id="7e269-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7e269-150">See Also</span></span>  
 [<span data-ttu-id="7e269-151">Suchtransformation</span><span class="sxs-lookup"><span data-stu-id="7e269-151">Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
