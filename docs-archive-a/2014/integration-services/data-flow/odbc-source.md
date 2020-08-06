---
title: ODBC-Quelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.f1
ms.assetid: abcf34eb-9140-4100-82e6-b85bccd22abe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 792557839d60f34bdf944dab150959d4df7cb8cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615481"
---
# <a name="odbc-source"></a><span data-ttu-id="106c0-102">ODBC-Quelle</span><span class="sxs-lookup"><span data-stu-id="106c0-102">ODBC Source</span></span>
  <span data-ttu-id="106c0-103">Die ODBC-Quelle extrahiert Daten mithilfe einer Datenbanktabelle, Sicht oder SQL-Anweisung aus einer Datenbank mit ODBC-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="106c0-103">The ODBC source extracts data from ODBC-supported database by using a database table, a view, or an SQL statement.</span></span>  
  
 <span data-ttu-id="106c0-104">Die ODBC-Quelle verfügt über die folgenden Datenzugriffsmodi zum Extrahieren von Daten:</span><span class="sxs-lookup"><span data-stu-id="106c0-104">The ODBC source has the following data access modes for extracting data:</span></span>  
  
-   <span data-ttu-id="106c0-105">Eine Tabelle oder Sicht.</span><span class="sxs-lookup"><span data-stu-id="106c0-105">A table or view.</span></span>  
  
-   <span data-ttu-id="106c0-106">Die Ergebnisse einer SQL-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="106c0-106">The results of an SQL statement.</span></span>  
  
 <span data-ttu-id="106c0-107">Die Quelle verwendet einen ODBC-Verbindungs-Manager, der den zu verwendenden Anbieter angibt.</span><span class="sxs-lookup"><span data-stu-id="106c0-107">The source uses an ODBC connection manager, which specifies the provider to use.</span></span>  
  
 <span data-ttu-id="106c0-108">Eine ODBC-Quelle enthält die Ausgabespalten für Quelldaten.</span><span class="sxs-lookup"><span data-stu-id="106c0-108">An ODBC source includes the source data output columns.</span></span> <span data-ttu-id="106c0-109">Wenn Ausgabespalten auf dem ODBC-Ziel den Zielspalten zugeordnet werden, treten möglicherweise Fehler auf, wenn den Zielspalten keine Ausgabespalten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="106c0-109">When output columns are mapped in the ODBC destination to the destination columns, errors may occur if no output columns are mapped to the destination columns.</span></span> <span data-ttu-id="106c0-110">Es können Spalten mit verschiedenen Typen zugeordnet werden. Wenn die Ausgabedaten mit dem Ziel jedoch nicht kompatibel sind, tritt zur Laufzeit ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="106c0-110">Columns of different types can be mapped, however if the output data is not compatible for the destination then an error occurs at runtime.</span></span> <span data-ttu-id="106c0-111">Je nach Einstellung des Fehlerverhaltens wird der Fehler ignoriert, ein Fehler verursacht oder die Zeile zurück an die Fehlerausgabe gesendet.</span><span class="sxs-lookup"><span data-stu-id="106c0-111">Depending on the error behavior, setting the error will be ignored, cause a failure, or the row is sent to the error output.</span></span>  
  
 <span data-ttu-id="106c0-112">Die ODBC-Quelle weist eine reguläre Ausgabe und eine Fehlerausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="106c0-112">The ODBC source has one regular output and one error output.</span></span>  
  
## <a name="error-handling"></a><span data-ttu-id="106c0-113">Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="106c0-113">Error Handling</span></span>  
 <span data-ttu-id="106c0-114">Die ODBC-Quelle verfügt über eine Fehlerausgabe.</span><span class="sxs-lookup"><span data-stu-id="106c0-114">The ODBC source has an error output.</span></span> <span data-ttu-id="106c0-115">Die Komponentenfehlerausgabe enthält die folgenden Ausgabespalten:</span><span class="sxs-lookup"><span data-stu-id="106c0-115">The component error output includes the following output columns:</span></span>  
  
-   <span data-ttu-id="106c0-116">**Fehlercode**: Ruft die Zahl ab, die dem aktuellen Fehler entspricht.</span><span class="sxs-lookup"><span data-stu-id="106c0-116">**Error Code**: The number that corresponds to the current error.</span></span> <span data-ttu-id="106c0-117">Eine Liste der Fehler finden Sie in der Dokumentation zur Datenbank mit ODBC-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="106c0-117">See the documentation for the ODBC-supported database you are using for a list of errors.</span></span> <span data-ttu-id="106c0-118">Eine Liste der SSIS-Fehlercodes finden Sie in der SSIS-Fehler- und Meldungsreferenz.</span><span class="sxs-lookup"><span data-stu-id="106c0-118">For a list of SSIS error codes, see the SSIS Error Code and Message Reference.</span></span>  
  
-   <span data-ttu-id="106c0-119">**Fehlerspalte**: Die Quellspalte, die den Fehler verursacht (für Konvertierungsfehler).</span><span class="sxs-lookup"><span data-stu-id="106c0-119">**Error Column**: The source column causing the error (for conversion errors).</span></span>  
  
-   <span data-ttu-id="106c0-120">Die Spalten mit den Standardausgabedaten.</span><span class="sxs-lookup"><span data-stu-id="106c0-120">The standard output data columns.</span></span>  
  
 <span data-ttu-id="106c0-121">Je nach Einstellung des Fehlerverhaltens unterstützt die ODBC-Quelle das Zurückgeben von Fehlern (Datenkonvertierung, Abschneiden), die während des Extraktionsprozesses in der Fehlerausgabe auftreten.</span><span class="sxs-lookup"><span data-stu-id="106c0-121">Depending on the error behavior setting, the ODBC source supports returning errors (data conversion, truncation) that occur during the extraction process in the error output.</span></span> <span data-ttu-id="106c0-122">Weitere Informationen finden Sie unter [Ziel-Editor für ODBC &#40;Seite „Verbindungs-Manager“&#41;](../odbc-destination-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="106c0-122">For more information, see [ODBC Destination Editor &#40;Connection Manager Page&#41;](../odbc-destination-editor-connection-manager-page.md).</span></span>  
  
## <a name="data-type-support"></a><span data-ttu-id="106c0-123">Datentypunterstützung</span><span class="sxs-lookup"><span data-stu-id="106c0-123">Data Type Support</span></span>  
 <span data-ttu-id="106c0-124">Informationen zu den Datentypen, die von der ODBC-Quelle unterstützt werden, finden Sie unter Konnektor für Open Database Connectivity (ODBC) von Attunity.</span><span class="sxs-lookup"><span data-stu-id="106c0-124">For information about the data types supported by the ODBC source, see Connector for Open Database Connectivity (ODBC) by Attunity.</span></span>  
  
## <a name="extract-options"></a><span data-ttu-id="106c0-125">Extrahierungsoptionen</span><span class="sxs-lookup"><span data-stu-id="106c0-125">Extract Options</span></span>  
 <span data-ttu-id="106c0-126">Die ODBC-Quelle arbeitet entweder im Modus **Batch** oder **Zeile für Zeile** .</span><span class="sxs-lookup"><span data-stu-id="106c0-126">The ODBC source operates in either **Batch** or **Row-by-Row** mode.</span></span> <span data-ttu-id="106c0-127">Der verwendete Modus wird mithilfe der **FetchMethod** -Eigenschaft bestimmt.</span><span class="sxs-lookup"><span data-stu-id="106c0-127">The mode used is determined by the **FetchMethod** property.</span></span> <span data-ttu-id="106c0-128">Die Modi werden in der folgenden Liste beschrieben:</span><span class="sxs-lookup"><span data-stu-id="106c0-128">The following list describes the modes.</span></span>  
  
-   <span data-ttu-id="106c0-129">**Batch**: Die Komponente versucht, basierend auf den erkannten Funktionen des ODBC-Anbieters die effizienteste Abrufmethode zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="106c0-129">**Batch**: The component attempts to use the most efficient fetch method based on the perceived ODBC provider capabilities.</span></span> <span data-ttu-id="106c0-130">Für die meisten modernen ODBC-Anbieter ist dies SQLFetchScroll mit Arraybindung (wobei die Arraygröße von der **BatchSize** -Eigenschaft bestimmt wird).</span><span class="sxs-lookup"><span data-stu-id="106c0-130">For most modern ODBC providers, this is SQLFetchScroll with array binding (where the array size is determined by the **BatchSize** property).</span></span> <span data-ttu-id="106c0-131">Wenn Sie **Batch** auswählen und der Anbieter diese Methode nicht unterstützt, wechselt das ODBC-Ziel automatisch zum Modus **Zeile für Zeile** .</span><span class="sxs-lookup"><span data-stu-id="106c0-131">If you select **Batch** and the provider does not support this method, the ODBC destination automatically switches to the **Row-by-row** mode.</span></span>  
  
-   <span data-ttu-id="106c0-132">**Zeile für Zeile**: Die Komponente ruft die Zeilen mithilfe von SQLFetch einzeln ab.</span><span class="sxs-lookup"><span data-stu-id="106c0-132">**Row-by Row**: The component uses SQLFetch to retrieve the rows one at a time.</span></span>  
  
 <span data-ttu-id="106c0-133">Weitere Informationen zur **FetchMethod** -Eigenschaft finden Sie unter [ODBC Source Custom Properties](odbc-source-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="106c0-133">For more information about the **FetchMethod** property, see [ODBC Source Custom Properties](odbc-source-custom-properties.md).</span></span>  
  
## <a name="parallelism"></a><span data-ttu-id="106c0-134">Parallelität</span><span class="sxs-lookup"><span data-stu-id="106c0-134">Parallelism</span></span>  
 <span data-ttu-id="106c0-135">Es gilt keine Einschränkung in Bezug auf die Anzahl von ODBC-Quellkomponenten, die parallel für dieselbe Tabelle oder verschiedene Tabellen, auf demselben Computer oder auf unterschiedlichen Computern ausgeführt werden können (mit Ausnahme normaler Einschränkungen für globale Sitzungen).</span><span class="sxs-lookup"><span data-stu-id="106c0-135">There is no limitation on the number of ODBC source components that can run in parallel against the same table or different tables, on the same machine or on different machines (other than normal global session limits).</span></span>  
  
 <span data-ttu-id="106c0-136">Aufgrund von Einschränkungen in Verbindung mit dem verwendeten ODBC-Anbieter kann die Anzahl gleichzeitiger Verbindungen über den Anbieter möglicherweise trotzdem eingeschränkt sein.</span><span class="sxs-lookup"><span data-stu-id="106c0-136">However, limitations of the ODBC provider being used may restrict the number of concurrent connections through the provider.</span></span> <span data-ttu-id="106c0-137">Diese Einschränkungen begrenzen die Anzahl der unterstützten parallelen Instanzen, die für die ODBC-Quelle möglich sind.</span><span class="sxs-lookup"><span data-stu-id="106c0-137">These limitations limit the number of supported parallel instances possible for the ODBC source.</span></span> <span data-ttu-id="106c0-138">Der SSIS-Entwickler muss sich über die Einschränkungen im Klaren sein, die für verwendete ODBC-Anbieter gelten, und diese beim Erstellen von SSIS-Paketen beachten.</span><span class="sxs-lookup"><span data-stu-id="106c0-138">The SSIS developer must be aware of the limitations of any ODBC provider being used and take them into consideration when building SSIS packages.</span></span>  
  
## <a name="troubleshooting-the-odbc-source"></a><span data-ttu-id="106c0-139">Problembehandlung der ODBC-Quelle</span><span class="sxs-lookup"><span data-stu-id="106c0-139">Troubleshooting the ODBC Source</span></span>  
 <span data-ttu-id="106c0-140">Sie können die von der ODBC-Quelle an externe Datenanbieter gerichteten Aufrufe protokollieren.</span><span class="sxs-lookup"><span data-stu-id="106c0-140">You can log the calls that the ODBC source makes to external data providers.</span></span> <span data-ttu-id="106c0-141">Mithilfe dieser Protokollierungsfunktion können Sie Probleme beim Laden von Daten aus externen Datenquellen durch die ODBC-Quelle behandeln.</span><span class="sxs-lookup"><span data-stu-id="106c0-141">You can use this logging capability to troubleshoot the loading of data from external data sources that the ODBC source performs.</span></span> <span data-ttu-id="106c0-142">Aktivieren Sie die Ablaufverfolgung für den ODBC-Treiber-Manager, um die Aufrufe zu protokollieren, die von der ODBC-Quelle an externe Datenanbieter gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="106c0-142">To log the calls that the ODBC source makes to external data providers, enable the ODBC driver manager trace.</span></span> <span data-ttu-id="106c0-143">Weitere Informationen finden Sie in der Microsoft-Dokumentation unter *Generieren einer ODBC-Ablaufverfolgung mit dem ODBC-Datenquellen-Administrator*.</span><span class="sxs-lookup"><span data-stu-id="106c0-143">For more information, see the Microsoft documentation on *How To Generate an ODBC Trace with ODBC the Data Source Administrator.*</span></span>  
  
## <a name="configuring-the-odbc-source"></a><span data-ttu-id="106c0-144">Konfigurieren der ODBC-Quelle</span><span class="sxs-lookup"><span data-stu-id="106c0-144">Configuring the ODBC Source</span></span>  
 <span data-ttu-id="106c0-145">Sie können die ODBC-Quelle programmgesteuert oder mit dem SSIS-Designer konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="106c0-145">You can configure the ODBC source programmatically or through the SSIS Designer.</span></span>  
  
 <span data-ttu-id="106c0-146">Weitere Informationen finden Sie in einem der folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="106c0-146">For more information, see one of the following topics:</span></span>  
  
-   [<span data-ttu-id="106c0-147">Quellen-Editor für ODBC &#40;Seite „Verbindungs-Manager“&#41;</span><span class="sxs-lookup"><span data-stu-id="106c0-147">ODBC Source Editor &#40;Connection Manager Page&#41;</span></span>](../odbc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="106c0-148">Quellen-Editor für ODBC &#40;Seite „Spalten“&#41;</span><span class="sxs-lookup"><span data-stu-id="106c0-148">ODBC Source Editor &#40;Columns Page&#41;</span></span>](../odbc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="106c0-149">Quellen-Editor für ODBC &#40;Seite „Fehlerausgabe“&#41;</span><span class="sxs-lookup"><span data-stu-id="106c0-149">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
 <span data-ttu-id="106c0-150">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="106c0-150">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
 <span data-ttu-id="106c0-151">So öffnen Sie das Dialogfeld **Erweiterter Editor** :</span><span class="sxs-lookup"><span data-stu-id="106c0-151">To open the **Advanced Editor** dialog box:</span></span>  
  
-   <span data-ttu-id="106c0-152">Klicken Sie auf dem Bildschirm **Datenfluss** des [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] -Projekts mit der rechten Maustaste auf die ODBC-Quelle, und wählen Sie **Erweiterten Editor anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="106c0-152">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the ODBC source and select **Show Advanced Editor**.</span></span>  
  
 <span data-ttu-id="106c0-153">Weitere Informationen zu den Eigenschaften, die Sie im Dialogfeld Erweiterter Editor festlegen können, finden Sie unter [ODBC Source Custom Properties](odbc-source-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="106c0-153">For more information about the properties that you can set in the Advanced Editor dialog box, see [ODBC Source Custom Properties](odbc-source-custom-properties.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="106c0-154">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="106c0-154">In This Section</span></span>  
  
-   [<span data-ttu-id="106c0-155">Quellen-Editor für ODBC &#40;Seite „Fehlerausgabe“&#41;</span><span class="sxs-lookup"><span data-stu-id="106c0-155">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="106c0-156">Quellen-Editor für ODBC &#40;Seite „Spalten“&#41;</span><span class="sxs-lookup"><span data-stu-id="106c0-156">ODBC Source Editor &#40;Columns Page&#41;</span></span>](../odbc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="106c0-157">Quellen-Editor für ODBC &#40;Seite „Verbindungs-Manager“&#41;</span><span class="sxs-lookup"><span data-stu-id="106c0-157">ODBC Source Editor &#40;Connection Manager Page&#41;</span></span>](../odbc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="106c0-158">Extrahieren von Daten mithilfe der ODBC-Quelle</span><span class="sxs-lookup"><span data-stu-id="106c0-158">Extract Data by Using the ODBC Source</span></span>](odbc-source.md)  
  
-   [<span data-ttu-id="106c0-159">ODBC Source Custom Properties</span><span class="sxs-lookup"><span data-stu-id="106c0-159">ODBC Source Custom Properties</span></span>](odbc-source-custom-properties.md)  
  
  
