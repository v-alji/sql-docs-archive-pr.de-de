---
title: Extrahieren von Daten mithilfe der ODBC-Quelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 10f25703-49a2-4d45-abab-6b4da2a57ba5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c05efe2b0479047280fc093ee555e037c77d82e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726113"
---
# <a name="extract-data-by-using-the-odbc-source"></a><span data-ttu-id="68a56-102">Extrahieren von Daten mithilfe der ODBC-Quelle</span><span class="sxs-lookup"><span data-stu-id="68a56-102">Extract Data by Using the ODBC Source</span></span>
  <span data-ttu-id="68a56-103">In diesem Verfahren wird beschrieben, wie Sie Daten mithilfe einer ODBC-Quelle extrahieren.</span><span class="sxs-lookup"><span data-stu-id="68a56-103">This procedure describes how to extract data by using an ODBC source.</span></span> <span data-ttu-id="68a56-104">Um eine ODBC-Quelle hinzuzufügen und zu konfigurieren, muss das Paket bereits mindestens einen Datenflusstask enthalten.</span><span class="sxs-lookup"><span data-stu-id="68a56-104">To add and configure an ODBC source, the package must already include at least one Data Flow task.</span></span>  
  
### <a name="to-extract-data-using-an-odbc-source"></a><span data-ttu-id="68a56-105">So extrahieren Sie Daten mithilfe einer ODBC-Quelle</span><span class="sxs-lookup"><span data-stu-id="68a56-105">To extract data using an ODBC source</span></span>  
  
1.  <span data-ttu-id="68a56-106">Öffnen Sie in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]das gewünschte [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] -Paket.</span><span class="sxs-lookup"><span data-stu-id="68a56-106">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] package you want.</span></span>  
  
2.  <span data-ttu-id="68a56-107">Klicken Sie auf die Registerkarte **Datenfluss** , und ziehen Sie die ODBC-Quelle dann aus der **Toolbox**auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="68a56-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the ODBC source to the design surface.</span></span>  
  
3.  <span data-ttu-id="68a56-108">Doppelklicken Sie auf die ODBC-Quelle.</span><span class="sxs-lookup"><span data-stu-id="68a56-108">Double-click the ODBC source.</span></span>  
  
4.  <span data-ttu-id="68a56-109">Wählen Sie im Dialogfeld **Quellen-Editor für ODBC** auf der Seite **Verbindungs-Manager** einen vorhandenen ODBC-Verbindungs-Manager aus, oder klicken Sie auf **Neu** , um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="68a56-109">In the **ODBC Source Editor** dialog box, on the **Connection Manager** page, select an existing ODBC connection manager or click **New** to create a new connection manager.</span></span>  
  
5.  <span data-ttu-id="68a56-110">Wählen Sie die Datenzugriffsmethode aus.</span><span class="sxs-lookup"><span data-stu-id="68a56-110">Select the data access method.</span></span>  
  
    -   <span data-ttu-id="68a56-111">**Tabellenname**: Wählen Sie in der Datenbank eine Tabelle oder Sicht aus, oder geben Sie einen regulären Ausdruck ein, um die Tabelle zu identifizieren, mit der der ODBC-Verbindungs-Manager eine Verbindung herstellt.</span><span class="sxs-lookup"><span data-stu-id="68a56-111">**Table Name**: Select a table or view in the database or type a regular expression to identify the table to which the ODBC connection manager connects.</span></span>  
  
         <span data-ttu-id="68a56-112">Diese Liste enthält nur die ersten 1000 Tabellen.</span><span class="sxs-lookup"><span data-stu-id="68a56-112">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="68a56-113">Wenn die Datenbank mehr als 1000 Tabellen enthält, können Sie den Anfang eines Tabellennamens eingeben oder das Platzhalterzeichen (\*) verwenden, um einen beliebigen Teil des Namens einzugeben und die gewünschten Tabellen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="68a56-113">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>  
  
    -   <span data-ttu-id="68a56-114">**SQL-Befehl**: Geben Sie einen SQL-Befehl ein, oder klicken Sie auf **Durchsuchen** , um die SQL-Abfrage aus einer Textdatei zu laden.</span><span class="sxs-lookup"><span data-stu-id="68a56-114">**SQL Command**: Type an SQL Command or click **Browse** to load the SQL query from a text file.</span></span>  
  
6.  <span data-ttu-id="68a56-115">Sie können auf **Vorschau** klicken, um bis zu 200 Datenzeilen anzuzeigen, die von der ODBC-Quelle extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="68a56-115">You can click **Preview** to view up to 200 rows of the data extracted by the ODBC source.</span></span>  
  
7.  <span data-ttu-id="68a56-116">Um die Zuordnung zwischen externen Spalten und Ausgabespalten zu aktualisieren, klicken Sie auf **Spalten** und wählen in der Liste **Externe Spalte** verschiedene Spalten aus.</span><span class="sxs-lookup"><span data-stu-id="68a56-116">To update the mapping between external and output columns, click **Columns** and select different columns in the **External Column** list.</span></span>  
  
8.  <span data-ttu-id="68a56-117">Aktualisieren Sie bei Bedarf die Namen von Ausgabespalten, indem Sie Werte in der Liste **Ausgabespalte** bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="68a56-117">If necessary, update the names of output columns by editing values in the **Output Column** list.</span></span>  
  
9. <span data-ttu-id="68a56-118">Klicken Sie auf **Fehlerausgabe**, um die Fehlerausgabe zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="68a56-118">To configure the error output, click **Error Output**.</span></span>  
  
10. <span data-ttu-id="68a56-119">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="68a56-119">Click **OK**.</span></span>  
  
11. <span data-ttu-id="68a56-120">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="68a56-120">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68a56-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="68a56-121">See Also</span></span>  
 <span data-ttu-id="68a56-122">[Quellen-Editor für ODBC &#40;Seite Verbindungs-Manager&#41;](../odbc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="68a56-122">[ODBC Source Editor &#40;Connection Manager Page&#41;](../odbc-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="68a56-123">[Quellen-Editor für ODBC &#40;Seite „Spalten“&#41;](../odbc-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="68a56-123">[ODBC Source Editor &#40;Columns Page&#41;](../odbc-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="68a56-124">Quellen-Editor für ODBC &#40;Seite „Fehlerausgabe“&#41;</span><span class="sxs-lookup"><span data-stu-id="68a56-124">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
  
