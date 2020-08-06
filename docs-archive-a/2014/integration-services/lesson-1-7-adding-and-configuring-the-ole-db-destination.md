---
title: 'Schritt 7: Hinzufügen und Konfigurieren des OLE DB-Ziels | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 442c841d-d528-4bf0-8724-7156f909ee50
author: chugugrace
ms.author: chugu
ms.openlocfilehash: da917ccc4ca756c2442e70477976b5a71f7eb56e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618125"
---
# <a name="step-7-adding-and-configuring-the-ole-db-destination"></a><span data-ttu-id="0aa0a-102">Schritt 7: Hinzufügen und Konfigurieren des OLE DB-Ziels</span><span class="sxs-lookup"><span data-stu-id="0aa0a-102">Step 7: Adding and Configuring the OLE DB Destination</span></span>
  <span data-ttu-id="0aa0a-103">Von Ihrem Paket können jetzt Daten aus der Flatfilequelle extrahiert und in ein Format transformiert werden, das mit dem Ziel kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-103">Your package now can extract data from the flat file source and transform that data into a format that is compatible with the destination.</span></span> <span data-ttu-id="0aa0a-104">Die nächste Aufgabe besteht darin, die transformierten Daten tatsächlich in das Ziel zu laden.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-104">The next task is to actually load the transformed data into the destination.</span></span> <span data-ttu-id="0aa0a-105">Um die Daten zu laden, müssen Sie ein OLE DB-Ziel zum Datenfluss hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-105">To load the data, you must add an OLE DB destination to the data flow.</span></span> <span data-ttu-id="0aa0a-106">Vom OLE DB-Ziel kann eine Datenbanktabelle, eine Ansicht oder ein SQL-Befehl verwendet werden, um Daten in verschiedene OLE DB-kompatible Datenbanken zu laden.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-106">The OLE DB destination can use a database table, view, or an SQL command to load data into a variety of OLE DB-compliant databases.</span></span>  
  
 <span data-ttu-id="0aa0a-107">In diesem Vorgang fügen Sie ein OLE DB-Ziel hinzu und konfigurieren es, sodass der OLE DB-Verbindungs-Manager verwendet werden kann, den Sie vorher erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-107">In this procedure, you add and configure an OLE DB destination to use the OLE DB connection manager that you previously created.</span></span>  
  
### <a name="to-add-and-configure-the-sample-ole-db-destination"></a><span data-ttu-id="0aa0a-108">So fügen Sie das Beispiel-OLE DB-Ziel hinzu und konfigurieren es</span><span class="sxs-lookup"><span data-stu-id="0aa0a-108">To add and configure the sample OLE DB destination</span></span>  
  
1.  <span data-ttu-id="0aa0a-109">Erweitern Sie in der **SSIS-Toolbox**die Option **andere Ziele**, und ziehen Sie **OLE DB Ziel** auf die Entwurfs Oberfläche der Registerkarte **Datenfluss** . Platzieren Sie das OLE DB Ziel direkt unterhalb der Transformation **Lookup Date Key** .</span><span class="sxs-lookup"><span data-stu-id="0aa0a-109">In the **SSIS Toolbox**, expand **Other Destinations**, and drag **OLE DB Destination** onto the design surface of the **Data Flow** tab. Place the OLE DB destination directly below the **Lookup Date Key** transformation.</span></span>  
  
2.  <span data-ttu-id="0aa0a-110">Klicken Sie auf die Transformation **Lookup Date Key** , und ziehen Sie den grünen Pfeil zum neu hinzugefügten **OLE DB-Ziel** , um die zwei Komponenten miteinander zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-110">Click the **Lookup Date Key** transformation and drag the green arrow over to the newly added **OLE DB Destination** to connect the two components together.</span></span>  
  
3.  <span data-ttu-id="0aa0a-111">Klicken Sie im Dialogfeld **Eingabe-/Ausgabe-Auswahl** im Listenfeld **Ausgabe** auf **Ausgabe der Suchübereinstimmungen**, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-111">In the **Input Output Selection** dialog box, in the **Output** list box, click **Lookup Match Output**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="0aa0a-112">Klicken Sie auf der Entwurfsoberfläche **Datenfluss** in der neu hinzugefügten **OLE DB-Ziel** -Komponente auf **OLE DB-Ziel** , und ändern Sie den Namen zu **Sample OLE DB Destination**(OLE DB-Beispielziel).</span><span class="sxs-lookup"><span data-stu-id="0aa0a-112">On the **Data Flow** design surface, click **OLE DB Destination** in the newly added **OLE DB Destination** component, and change the name to **Sample OLE DB Destination**.</span></span>  
  
5.  <span data-ttu-id="0aa0a-113">Doppelklicken Sie auf **Sample OLE DB Destination**.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-113">Double-click **Sample OLE DB Destination**.</span></span>  
  
6.  <span data-ttu-id="0aa0a-114">Stellen Sie im Dialogfeld **Ziel-Editor für OLE DB** sicher, dass **localhost.AdventureWorksDW2012** im Feld **OLE DB-Verbindungs-Manager** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-114">In the **OLE DB Destination Editor** dialog box, ensure that **localhost.AdventureWorksDW2012** is selected in the **OLE DB Connection manager** box.</span></span>  
  
7.  <span data-ttu-id="0aa0a-115">Geben Sie im Feld **Name der Tabelle oder Sicht\*\*\*\*[dbo].[FactCurrencyRate]** ein, oder wählen Sie diese Zeichenfolge aus.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-115">In the **Name of the table or the view** box, type or select **[dbo].[FactCurrencyRate]**.</span></span>  
  
8.  <span data-ttu-id="0aa0a-116">Klicken Sie auf die Schaltfläche **Neu** , um eine neue Tabelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-116">Click the **New** button to create a new table.</span></span>  <span data-ttu-id="0aa0a-117">Ändern Sie den Namen der Tabelle im Skript in **NewFactCurrencyRate**.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-117">Change the name of the table in the script to read **NewFactCurrencyRate**.</span></span>  <span data-ttu-id="0aa0a-118">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-118">Click **OK**.</span></span>  
  
9. <span data-ttu-id="0aa0a-119">Nach dem Klicken auf **OK**wird das Dialogfeld geschlossen, und der **Name der Tabelle oder Sicht** wird automatisch in **NewFactCurrencyRate**geändert.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-119">Upon clicking **OK**, the dialog will close and the **Name of the table or the view** will automatically change to **NewFactCurrencyRate**.</span></span>  
  
10. <span data-ttu-id="0aa0a-120">Klicken Sie auf **Zuordnungen**.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-120">Click **Mappings**.</span></span>  
  
11. <span data-ttu-id="0aa0a-121">Überprüfen Sie, ob die Eingabespalten **AverageRate**, **CurrencyKey**, **EndOfDayRate**und **DateKey** den Zielspalten ordnungsgemäß zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-121">Verify that the **AverageRate**, **CurrencyKey**, **EndOfDayRate**, and **DateKey** input columns are mapped correctly to the destination columns.</span></span> <span data-ttu-id="0aa0a-122">Wenn gleichnamige Spalten einander zugeordnet sind, ist die Zuordnung richtig.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-122">If same-named columns are mapped, the mapping is correct.</span></span>  
  
12. <span data-ttu-id="0aa0a-123">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-123">Click **OK**.</span></span>  
  
13. <span data-ttu-id="0aa0a-124">Klicken Sie mit der rechten Maustaste auf das Ziel **Sample OLE DB Destination** und anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-124">Right-click the **Sample OLE DB Destination** destination and click **Properties**.</span></span>  
  
14. <span data-ttu-id="0aa0a-125">Überprüfen Sie im Eigenschaftenfenster, ob die `LocaleID` -Eigenschaft auf **Englisch (USA)** und die- `DefaultCodePage` Eigenschaft auf **1252**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-125">In the Properties window, verify that the `LocaleID` property is set to **English (United States)** and the`DefaultCodePage` property is set to **1252**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="0aa0a-126">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="0aa0a-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="0aa0a-127">Schritt 8: Vereinfachen des Layouts des Pakets aus Lektion 1</span><span class="sxs-lookup"><span data-stu-id="0aa0a-127">Step 8: Making the Lesson 1 Package Easier to Understand</span></span>](lesson-1-8-making-the-lesson-1-package-easier-to-understand.md)  
  
## <a name="see-also"></a><span data-ttu-id="0aa0a-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0aa0a-128">See Also</span></span>  
 [<span data-ttu-id="0aa0a-129">OLE DB-Ziel</span><span class="sxs-lookup"><span data-stu-id="0aa0a-129">OLE DB Destination</span></span>](data-flow/ole-db-destination.md)  
  
  
