---
title: Excel-Ziel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.exceldest.f1
helpviewer_keywords:
- destinations [Integration Services], Excel
- Excel [Integration Services]
ms.assetid: 37c07446-1264-4814-b4f5-9c66d333bb24
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3e959f14e52fc045cb0cbc2ba0255d20bd0356d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726125"
---
# <a name="excel-destination"></a><span data-ttu-id="d7dcf-102">Excel-Ziel</span><span class="sxs-lookup"><span data-stu-id="d7dcf-102">Excel Destination</span></span>
  <span data-ttu-id="d7dcf-103">Das Excel-Ziel lädt Daten in Arbeitsblätter oder Bereiche in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel-Arbeitsmappen.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-103">The Excel destination loads data into worksheets or ranges in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel workbooks.</span></span>  
  
## <a name="access-modes"></a><span data-ttu-id="d7dcf-104">Zugriffsmodi</span><span class="sxs-lookup"><span data-stu-id="d7dcf-104">Access Modes</span></span>  
 <span data-ttu-id="d7dcf-105">Das Excel-Ziel stellt drei verschiedene Datenzugriffsmodi zum Laden von Daten bereit:</span><span class="sxs-lookup"><span data-stu-id="d7dcf-105">The Excel destination provides three different data access modes for loading data:</span></span>  
  
-   <span data-ttu-id="d7dcf-106">Eine Tabelle oder Sicht.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-106">A table or view.</span></span>  
  
-   <span data-ttu-id="d7dcf-107">Eine in einer Variablen angegebene Tabelle oder Sicht.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-107">A table or view specified in a variable.</span></span>  
  
-   <span data-ttu-id="d7dcf-108">Die Ergebnisse einer SQL-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-108">The results of an SQL statement.</span></span> <span data-ttu-id="d7dcf-109">Bei der Abfrage kann es sich um eine parametrisierte Abfrage handeln.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-109">The query can be a parameterized query.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d7dcf-110">In Excel entspricht ein Arbeitsblatt oder ein Bereich einer Tabelle oder Sicht.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-110">In Excel, a worksheet or range is the equivalent of a table or view.</span></span> <span data-ttu-id="d7dcf-111">In den Listen der verfügbaren Tabellen im Quellen-Editor und Ziel-Editor für Excel werden nur vorhandene Arbeitsblätter (identifiziert durch das an den Arbeitsblattnamen angefügte $-Zeichen, wie z. B. Sheet1$) und benannte Bereiche (identifiziert durch das Fehlen des $-Zeichens, wie z. B. MyRange) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-111">The lists of available tables in the Excel Source and Destination editors display only existing worksheets (identified by the $ sign appended to the worksheet name, such as Sheet1$) and named ranges (identified by the absence of the $ sign, such as MyRange).</span></span>  
  
## <a name="usage-considerations"></a><span data-ttu-id="d7dcf-112">Überlegungen zur Verwendung</span><span class="sxs-lookup"><span data-stu-id="d7dcf-112">Usage Considerations</span></span>  
 <span data-ttu-id="d7dcf-113">Der Excel-Verbindungs-Manager verwendet den [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB-Anbieter für Jet 4.0 und den unterstützenden Excel-ISAM-Treiber (Indexed Sequential Access Method, indizierte sequenzielle Zugriffsmethode), um sich mit Excel-Datenquellen zu verbinden und diese zu lesen und in sie zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-113">The Excel Connection Manager uses the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for Jet 4.0 and its supporting Excel ISAM (Indexed Sequential Access Method) driver to connect and read and write data to Excel data sources.</span></span>  
  
 <span data-ttu-id="d7dcf-114">In vielen [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base-Artikeln ist das Verhalten dieses Anbieters und Treibers dokumentiert. Diese Artikel beziehen sich zwar nicht speziell auf [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] oder die Vorgängerversion Data Transformation Services, aber Sie sollten bestimmte Verhaltensweisen kennen, die zu unerwarteten Ergebnissen führen können.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-114">Many existing [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base articles document the behavior of this provider and driver, and although these articles are not specific to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] or its predecessor Data Transformation Services, you may want to know about certain behaviors that can lead to unexpected results.</span></span> <span data-ttu-id="d7dcf-115">Allgemeine Informationen zu Verwendung und Verhalten des Excel-Treibers finden Sie unter [SO WIRD'S GEMACHT: Verwenden von ADO mit Excel-Daten von Visual Basic oder VBA](https://support.microsoft.com/kb/257819).</span><span class="sxs-lookup"><span data-stu-id="d7dcf-115">For general information on the use and behavior of the Excel driver, see [HOWTO: Use ADO with Excel Data from Visual Basic or VBA](https://support.microsoft.com/kb/257819).</span></span>  
  
 <span data-ttu-id="d7dcf-116">Die folgenden Verhaltensweisen des im Excel-Treiber enthaltenen Jet-Anbieters können zu unerwarteten Ergebnissen führen, wenn Daten in ein Excel-Ziel gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-116">The following behaviors of the Jet provider that is included with the Excel driver can lead to unexpected results when saving data to an Excel destination.</span></span>  
  
-   <span data-ttu-id="d7dcf-117">**Speichern von Textdaten**.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-117">**Saving text data**.</span></span> <span data-ttu-id="d7dcf-118">Wenn der Excel-Treiber Textdatenwerte in ein Excel-Ziel speichert, wird vor den Text jeder Zelle das einfache Anführungszeichen (') gesetzt, um sicherzustellen, dass die gespeicherten Werte als Textwerte interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-118">When the Excel driver saves text data values to an Excel destination, the driver precedes the text in each cell with the single quote character (') to ensure that the saved values will be interpreted as text values.</span></span> <span data-ttu-id="d7dcf-119">Wenn Sie andere Anwendungen verwenden bzw. entwickeln, die die gespeicherten Daten lesen oder verarbeiten, kann eine spezielle Verarbeitung des vor jedem Textwert gesetzten einfachen Anführungszeichens erforderlich sein.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-119">If you have or develop other applications that read or process the saved data, you may need to include special handling for the single quote character that precedes each text value.</span></span>  
  
     <span data-ttu-id="d7dcf-120">Informationen dazu, wie Sie das Einschließen des einfachen Anführungszeichens vermeiden, finden Sie in diesem Blogpost: [Single quote is appended to all strings when data is transformed to excel when using Excel destination data flow component in SSIS package](https://go.microsoft.com/fwlink/?LinkId=400876)(Einzelnes Anführungszeichen wird an alle Zeichenfolgen angehängt, wenn Daten für Excel umgewandelt werden und die Excel-Ziel-Datenflusskomponente in SSIS verwendet wird), auf msdn.com.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-120">For information on how to avoid including the single quote, see this blog post, [Single quote is appended to all strings when data is transformed to excel when using Excel destination data flow component in SSIS package](https://go.microsoft.com/fwlink/?LinkId=400876), on msdn.com.</span></span>  
  
-   <span data-ttu-id="d7dcf-121">**Speichern von Memodaten (ntext)**</span><span class="sxs-lookup"><span data-stu-id="d7dcf-121">**Saving memo (ntext) da**ta.</span></span> <span data-ttu-id="d7dcf-122">Zum erfolgreichen Speichern von Zeichenfolgen mit mehr als 255 Zeichen in einer Excel-Spalte muss der Treiber den Datentyp der Zielspalte als **memo** und nicht als **string**erkennen.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-122">Before you can successfully save strings longer than 255 characters to an Excel column, the driver must recognize the data type of the destination column as **memo** and not **string**.</span></span> <span data-ttu-id="d7dcf-123">Wenn die Zieltabelle bereits Datenzeilen enthält, müssen die ersten Zeilen, die vom Treiber als Stichprobe genommen werden, mindestens eine Instanz eines Werts mit mehr als 255 Zeichen in der Memospalte enthalten.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-123">If the destination table already contains rows of data, then the first few rows that are sampled by the driver must contain at least one instance of a value longer than 255 characters in the memo column.</span></span> <span data-ttu-id="d7dcf-124">Wenn die Ziel Tabelle während des Paket Entwurfs oder zur Laufzeit erstellt wird, muss für die CREATE TABLE-Anweisung LONGTEXT (oder eines der Synonyme) als Datentyp der Memo Spalte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-124">If the destination table is created during package design or at run time, then the CREATE TABLE statement must use LONGTEXT (or one of its synonyms) as the data type of the memo column.</span></span>  
  
-   <span data-ttu-id="d7dcf-125">**Datentypen**.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-125">**Data types**.</span></span> <span data-ttu-id="d7dcf-126">Der Excel-Treiber erkennt nur einen begrenzten Satz von Datentypen.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-126">The Excel driver recognizes only a limited set of data types.</span></span> <span data-ttu-id="d7dcf-127">Beispielsweise werden alle numerischen Spalten als Werte mit doppelter Genauigkeit (DT_R8) interpretiert, und alle Zeichenfolgenspalten (außer Memospalten) werden als Unicode-Zeichenfolgen mit 255 Zeichen (DT_WSTR) interpretiert.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-127">For example, all numeric columns are interpreted as doubles (DT_R8), and all string columns (other than memo columns) are interpreted as 255-character Unicode strings (DT_WSTR).</span></span> [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="d7dcf-128">werden die Excel-Datentypen folgendermaßen zugeordnet:</span><span class="sxs-lookup"><span data-stu-id="d7dcf-128">maps the Excel data types as follows:</span></span>  
  
    -   <span data-ttu-id="d7dcf-129">Numerisch – Gleitkommawert mit doppelter Genauigkeit (DT_R8)</span><span class="sxs-lookup"><span data-stu-id="d7dcf-129">Numeric    double-precision float (DT_R8)</span></span>  
  
    -   <span data-ttu-id="d7dcf-130">Währung – Währung (DT_CY)</span><span class="sxs-lookup"><span data-stu-id="d7dcf-130">Currency     currency (DT_CY)</span></span>  
  
    -   <span data-ttu-id="d7dcf-131">Boolesch – Boolesch (DT_BOOL)</span><span class="sxs-lookup"><span data-stu-id="d7dcf-131">Boolean     Boolean (DT_BOOL)</span></span>  
  
    -   <span data-ttu-id="d7dcf-132">Datum/Uhrzeit `datetime` (DT_DATE)</span><span class="sxs-lookup"><span data-stu-id="d7dcf-132">Date/time     `datetime` (DT_DATE)</span></span>  
  
    -   <span data-ttu-id="d7dcf-133">Zeichenfolge – Unicode-Zeichenfolge, Länge 255 (DT_WSTR)</span><span class="sxs-lookup"><span data-stu-id="d7dcf-133">String     Unicode string, length 255 (DT_WSTR)</span></span>  
  
    -   <span data-ttu-id="d7dcf-134">Memo – Unicode-Textstream (DT_NTEXT)</span><span class="sxs-lookup"><span data-stu-id="d7dcf-134">Memo     Unicode text stream (DT_NTEXT)</span></span>  
  
-   <span data-ttu-id="d7dcf-135">**Datentyp-und Längen Konvertierungen**.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-135">**Data type and length conversions**.</span></span> [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="d7dcf-136">werden Datentypen nicht implizit konvertiert.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-136">does not implicitly convert data types.</span></span> <span data-ttu-id="d7dcf-137">Daher müssen Sie eventuell die Transformationen für abgeleitete Spalten und für die Datenkonvertierung verwenden, um Excel-Daten vor dem Laden in ein Nicht-Excel-Ziel explizit zu konvertieren bzw. um Nicht-Excel-Daten vor dem Laden in ein Excel-Ziel zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-137">As a result, you may need to use the Derived Column or Data Conversion transformations to convert Excel data explicitly before loading it into a non-Excel destination, or to convert non-Excel data before loading it into an Excel destination.</span></span> <span data-ttu-id="d7dcf-138">In diesem Fall kann es nützlich sein, das erste Paket mit dem Import/Export-Assistenten zu erstellen, mit dem die Konfiguration notwendiger Konvertierungen vorgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-138">In this case, it may be useful to create the initial package by using the Import and Export Wizard, which configures the necessary conversions for you.</span></span> <span data-ttu-id="d7dcf-139">Im Folgenden finden Sie einige Beispiele für ggf. erforderliche Konvertierungen:</span><span class="sxs-lookup"><span data-stu-id="d7dcf-139">Some examples of the conversions that may be required include the following:</span></span>  
  
    -   <span data-ttu-id="d7dcf-140">Konvertierung zwischen Unicode-Excel-Zeichenfolgenspalten und Nicht-Unicode-Zeichenfolgenspalten mit bestimmten Codepages.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-140">Conversion between Unicode Excel string columns and non-Unicode string columns with specific codepages.</span></span>  
  
    -   <span data-ttu-id="d7dcf-141">Konvertierung zwischen Excel-Zeichenfolgenspalten mit 255 Zeichen und Zeichenfolgenspalten anderer Längen.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-141">Conversion between 255-character Excel string columns and string columns of different lengths.</span></span>  
  
    -   <span data-ttu-id="d7dcf-142">Konvertierung zwischen numerischen Excel-Spalten mit doppelter Genauigkeit und numerischen Spalten anderer Typen.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-142">Conversion between double-precision Excel numeric columns and numeric columns of other types.</span></span>  
  
## <a name="configuration-of-the-excel-destination"></a><span data-ttu-id="d7dcf-143">Konfiguration des Excel-Ziels</span><span class="sxs-lookup"><span data-stu-id="d7dcf-143">Configuration of the Excel Destination</span></span>  
 <span data-ttu-id="d7dcf-144">Das Excel-Ziel verwendet einen Excel-Verbindungs-Manager zum Herstellen einer Verbindung mit einer Datenquelle. Dieser Verbindungs-Manager gibt die zu verwendende Arbeitsmappendatei an.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-144">The Excel destination uses an Excel connection manager to connect to a data source, and the connection manager specifies the workbook file to use.</span></span> <span data-ttu-id="d7dcf-145">Weitere Informationen finden Sie unter [Excel Connection Manager](../connection-manager/excel-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="d7dcf-145">For more information, see [Excel Connection Manager](../connection-manager/excel-connection-manager.md).</span></span>  
  
 <span data-ttu-id="d7dcf-146">Das Excel-Ziel weist eine reguläre Eingabe und eine Fehlerausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-146">The Excel destination has one regular input and one error output.</span></span>  
  
 <span data-ttu-id="d7dcf-147">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-147">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="d7dcf-148">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Ziel-Editor für Excel** festlegen können:</span><span class="sxs-lookup"><span data-stu-id="d7dcf-148">For more information about the properties that you can set in the **Excel Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="d7dcf-149">Ziel-Editor für Excel &#40;Seite Verbindungs-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="d7dcf-149">Excel Destination Editor &#40;Connection Manager Page&#41;</span></span>](../excel-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="d7dcf-150">Ziel-Editor für Excel &#40;Seite Zuordnungen&#41;</span><span class="sxs-lookup"><span data-stu-id="d7dcf-150">Excel Destination Editor &#40;Mappings Page&#41;</span></span>](../excel-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="d7dcf-151">Ziel-Editor für Excel &#40;Seite Fehlerausgabe&#41;</span><span class="sxs-lookup"><span data-stu-id="d7dcf-151">Excel Destination Editor &#40;Error Output Page&#41;</span></span>](../excel-destination-editor-error-output-page.md)  
  
 <span data-ttu-id="d7dcf-152">Das Dialogfeld **Erweiterter Editor** enthält alle Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="d7dcf-152">The **Advanced Editor** dialog box reflects all the properties that can be set programmatically.</span></span> <span data-ttu-id="d7dcf-153">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="d7dcf-153">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="d7dcf-154">Common Properties</span><span class="sxs-lookup"><span data-stu-id="d7dcf-154">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="d7dcf-155">Benutzerdefinierte Eigenschaften von Excel</span><span class="sxs-lookup"><span data-stu-id="d7dcf-155">Excel Custom Properties</span></span>](excel-custom-properties.md)  
  
 <span data-ttu-id="d7dcf-156">Weitere Informationen zum Festlegen der Eigenschaften finden Sie unter [Festlegen der Eigenschaften einer Datenflusskomponente](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="d7dcf-156">For more information about how to set properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="d7dcf-157">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="d7dcf-157">Related Tasks</span></span>  
  
-   [<span data-ttu-id="d7dcf-158">Laden von Daten aus oder in Excel mit SQL Server Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="d7dcf-158">Import data from Excel or export data to Excel with SQL Server Integration Services (SSIS)</span></span>](../load-data-to-from-excel-with-ssis.md)  
  
-   [<span data-ttu-id="d7dcf-159">Schleife durch Excel-Dateien und Tabellen mit einem Foreach-Schleifencontainer</span><span class="sxs-lookup"><span data-stu-id="d7dcf-159">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](../control-flow/foreach-loop-container.md)  
  
-   [<span data-ttu-id="d7dcf-160">Festlegen der Eigenschaften einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="d7dcf-160">Set the Properties of a Data Flow Component</span></span>](set-the-properties-of-a-data-flow-component.md)  
  
## <a name="see-also"></a><span data-ttu-id="d7dcf-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d7dcf-161">See Also</span></span>  
 <span data-ttu-id="d7dcf-162">[Excel-Quelle](excel-source.md) </span><span class="sxs-lookup"><span data-stu-id="d7dcf-162">[Excel Source](excel-source.md) </span></span>  
 <span data-ttu-id="d7dcf-163">[Integration Services-Variablen &#40;SSIS&#41;](../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="d7dcf-163">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="d7dcf-164">[Datenfluss](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="d7dcf-164">[Data Flow](data-flow.md) </span></span>  
 [<span data-ttu-id="d7dcf-165">Arbeiten mit Excel-Dateien mit dem Skripttask</span><span class="sxs-lookup"><span data-stu-id="d7dcf-165">Working with Excel Files with the Script Task</span></span>](../extending-packages-scripting-task-examples/working-with-excel-files-with-the-script-task.md)  
  
  
