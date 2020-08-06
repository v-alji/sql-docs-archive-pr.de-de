---
title: Laden von Daten mithilfe des ODBC-Ziels | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 339ec0a8-922e-48c0-97b3-fc5ee34f95e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e8bf0b30619c2886df6ddb28858cf98bad858421
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700095"
---
# <a name="load-data-by-using-the-odbc-destination"></a><span data-ttu-id="edbd9-102">Laden von Daten mithilfe des ODBC-Ziels</span><span class="sxs-lookup"><span data-stu-id="edbd9-102">Load Data by Using the ODBC Destination</span></span>
  <span data-ttu-id="edbd9-103">In diesem Verfahren wird veranschaulicht, wie Sie Daten mithilfe des ODBC-Ziels laden.</span><span class="sxs-lookup"><span data-stu-id="edbd9-103">This procedure shows how to load data by using the ODBC destination.</span></span> <span data-ttu-id="edbd9-104">Das Paket muss bereits mindestens einen Datenflusstask und eine Quelle enthalten, damit Sie ein ODBC-Ziel hinzufügen und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="edbd9-104">To add and configure an ODBC destination, the package must already include at least one Data Flow task and source.</span></span>  
  
### <a name="to-load-data-using-an-odbc-destination"></a><span data-ttu-id="edbd9-105">So laden Sie Daten mithilfe eines ODBC-Ziels</span><span class="sxs-lookup"><span data-stu-id="edbd9-105">To load data using an ODBC destination</span></span>  
  
1.  <span data-ttu-id="edbd9-106">Öffnen Sie in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]das gewünschte [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket.</span><span class="sxs-lookup"><span data-stu-id="edbd9-106">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package you want.</span></span>  
  
2.  <span data-ttu-id="edbd9-107">Klicken Sie auf die Registerkarte **Datenfluss** , und ziehen Sie dann aus dem Bereich **Toolbox**das ODBC-Ziel auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="edbd9-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the ODBC destination to the design surface.</span></span>  
  
3.  <span data-ttu-id="edbd9-108">Ziehen Sie eine verfügbare Ausgabe einer Datenflusskomponente in den Eingabebereich des ODBC-Ziels.</span><span class="sxs-lookup"><span data-stu-id="edbd9-108">Drag an available output of a data flow component to the input of the ODBC destination.</span></span>  
  
4.  <span data-ttu-id="edbd9-109">Doppelklicken Sie auf das ODBC-Ziel.</span><span class="sxs-lookup"><span data-stu-id="edbd9-109">Double-click the ODBC destination.</span></span>  
  
5.  <span data-ttu-id="edbd9-110">Wählen Sie im Dialogfeld **Ziel-Editor für ODBC** auf der Seite **Verbindungs-Manager** einen vorhandenen ODBC-Verbindungs-Manager aus, oder klicken Sie auf **Neu** , um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="edbd9-110">In the **ODBC Destination Editor** dialog box, on the **Connection Manager** page, select an existing ODBC connection manager or click **New** to create a new connection manager.</span></span>  
  
6.  <span data-ttu-id="edbd9-111">Wählen Sie die Datenzugriffsmethode aus.</span><span class="sxs-lookup"><span data-stu-id="edbd9-111">Select the data access method.</span></span>  
  
    -   <span data-ttu-id="edbd9-112">**Tabellenname – Batch**: Wählen Sie diese Option, um das ODBC-Ziel im Batchmodus zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="edbd9-112">**Table Name - Batch**: Select this option to configure the ODBC destination to work in batch mode.</span></span> <span data-ttu-id="edbd9-113">Wenn Sie diese Option aktivieren, können Sie die **Batchgröße**festlegen.</span><span class="sxs-lookup"><span data-stu-id="edbd9-113">When you select this option, you can set the **Batch size**.</span></span>  
  
    -   <span data-ttu-id="edbd9-114">**Tabellenname – Zeile für Zeile**: Wählen Sie diese Option, um das ODBC-Ziel so zu konfigurieren, dass jede Zeile einzeln in die Zieltabelle eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="edbd9-114">**Table Name - Row by Row**: Select this option to configure the ODBC destination to insert each of the rows into the destination table one at a time.</span></span> <span data-ttu-id="edbd9-115">Wenn Sie diese Option aktivieren, werden die Daten zeilenweise in die Tabelle geladen.</span><span class="sxs-lookup"><span data-stu-id="edbd9-115">When you select this option, the data is loaded into the table one row at a time.</span></span>  
  
7.  <span data-ttu-id="edbd9-116">Wählen Sie in der Liste im Feld **Name der Tabelle oder Sicht** eine verfügbare Tabelle oder Sicht aus der Datenbank aus, oder geben Sie einen regulären Ausdruck zum Identifizieren der Tabelle ein. Diese Liste enthält nur die ersten 1000 Tabellen.</span><span class="sxs-lookup"><span data-stu-id="edbd9-116">In the **Name of the table or the view** field, select an available table or view from the database from the list or type in a regular expression to identify the table.This list contains the first 1000 tables only.</span></span> <span data-ttu-id="edbd9-117">Wenn die Datenbank mehr als 1000 Tabellen enthält, können Sie den Anfang eines Tabellennamens eingeben oder das Platzhalterzeichen (\*) verwenden, um einen beliebigen Teil des Namens einzugeben und die gewünschten Tabellen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="edbd9-117">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>  
  
8.  <span data-ttu-id="edbd9-118">Sie können auf **Vorschau** klicken, um bis zu 200 Zeilen der Daten für die auf dem ODBC-Ziel ausgewählte Tabelle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="edbd9-118">You can click **Preview** to view up to 200 rows of the data from the table selected in the ODBC destination.</span></span>  
  
9. <span data-ttu-id="edbd9-119">Klicken Sie auf **Zuordnungen** , und ordnen Sie Spalten aus der Liste **Verfügbare Eingabespalten** Spalten in der Liste **Verfügbare Zielspalten** zu, indem Sie Spalten von einer Liste in eine andere Liste ziehen.</span><span class="sxs-lookup"><span data-stu-id="edbd9-119">Click **Mappings** and then map columns from the **Available Input Columns** list to columns in the **Available Destination Columns** list by dragging columns from one list to another.</span></span>  
  
10. <span data-ttu-id="edbd9-120">Klicken Sie auf **Fehlerausgabe**, um die Fehlerausgabe zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="edbd9-120">To configure the error output, click **Error Output**.</span></span>  
  
11. <span data-ttu-id="edbd9-121">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="edbd9-121">Click **OK**.</span></span>  
  
12. <span data-ttu-id="edbd9-122">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="edbd9-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edbd9-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="edbd9-123">See Also</span></span>  
 <span data-ttu-id="edbd9-124">[Ziel-Editor für ODBC &#40;Verbindungs-Manager-Seite&#41;](../odbc-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="edbd9-124">[ODBC Destination Editor &#40;Connection Manager Page&#41;](../odbc-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="edbd9-125">[Ziel-Editor für ODBC &#40;Seite „Zuordnungen“&#41;](../odbc-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="edbd9-125">[ODBC Destination Editor &#40;Mappings Page&#41;](../odbc-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="edbd9-126">Quellen-Editor für ODBC &#40;Seite „Fehlerausgabe“&#41;</span><span class="sxs-lookup"><span data-stu-id="edbd9-126">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
  
