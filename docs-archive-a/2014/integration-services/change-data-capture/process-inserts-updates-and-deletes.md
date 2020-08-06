---
title: Verarbeiten von Einfügungen, Updates und Löschungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],processing data
ms.assetid: 13a84d21-2623-4efe-b442-4125a7a2d690
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 67f016aaf4f7f83c0fa506966c4e78f5b8fadef6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608783"
---
# <a name="process-inserts-updates-and-deletes"></a><span data-ttu-id="2e713-102">Verarbeiten von Einfügungen, Updates und Löschungen</span><span class="sxs-lookup"><span data-stu-id="2e713-102">Process Inserts, Updates, and Deletes</span></span>
  <span data-ttu-id="2e713-103">Im Datenfluss eines Integration Services-Pakets, das ein inkrementelles Laden von Änderungsdaten ausführt, werden mit dem zweiten Task Einfügungen, Updates und Löschungen voneinander getrennt.</span><span class="sxs-lookup"><span data-stu-id="2e713-103">In the data flow of an Integration Services package that performs an incremental load of change data, the second task is to separate inserts, updates, and deletes.</span></span> <span data-ttu-id="2e713-104">Dann können Sie entsprechende Befehle verwenden, um sie für das Ziel zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="2e713-104">Then, you can use appropriate commands to apply them to the destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2e713-105">Der erste Task beim Entwerfen des Datenflusses eines Pakets, das ein inkrementelles Laden von Änderungsdaten ausführt, ist die Konfiguration der Quellkomponente, die die Abfrage ausführt, bei der die Änderungsdaten abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2e713-105">The first task in designing the data flow of a package that performs an incremental load of change data is to configure the source component that runs the query that retrieves the change data.</span></span> <span data-ttu-id="2e713-106">Weitere Informationen zu dieser Komponente finden Sie unter [Abrufen und Verstehen der Änderungsdaten](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="2e713-106">For more information about this component, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span> <span data-ttu-id="2e713-107">Eine Beschreibung des Gesamtprozesses zur Erstellung eines Pakets, das ein inkrementelles Laden von Änderungsdaten ausführt, finden Sie unter [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="2e713-107">For a description of the overall process for creating a package that performs an incremental load of change data, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="associating-friendly-values-to-separate-inserts-updates-and-deletes"></a><span data-ttu-id="2e713-108">Zuordnen von benutzerfreundlichen Werten zur Trennung von Einfügungen, Updates und Löschungen</span><span class="sxs-lookup"><span data-stu-id="2e713-108">Associating Friendly Values to Separate Inserts, Updates, and Deletes</span></span>  
 <span data-ttu-id="2e713-109">In der Beispielabfrage, bei der Änderungsdaten abgerufen werden, gibt die **cdc.fn_cdc_get_net_changes_<capture_instance>** -Funktion nur die Metadatenspalte mit der Bezeichnung **__$operation** zurück.</span><span class="sxs-lookup"><span data-stu-id="2e713-109">In the example query that retrieves change data, the **cdc.fn_cdc_get_net_changes_<capture_instance>** function returns only the column of metadata named **__$operation**.</span></span> <span data-ttu-id="2e713-110">Diese Metadatenspalte enthält einen Ordinalwert, der angibt, welcher Vorgang die Änderung verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="2e713-110">This metadata column contains an ordinal value that indicates which operation caused the change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2e713-111">Weitere Informationen zu der Abfrage, die die **cdc.fn_cdc_get_net_changes_<capture_instance>** -Funktion verwendet, finden Sie unter [Erstellen der Funktion zum Abrufen der Änderungsdaten](create-the-function-to-retrieve-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="2e713-111">For more information about the query that uses calls the **cdc.fn_cdc_get_net_changes_<capture_instance>** function, see [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md).</span></span>  
  
 <span data-ttu-id="2e713-112">Das Abgleichen eines Ordinalwerts mit seinem entsprechenden Vorgang ist nicht so einfach wie die Verwendung eines mnemonischen Codes des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="2e713-112">Matching an ordinal value to its corresponding operation is not as easy as using a mnemonic of the operation.</span></span> <span data-ttu-id="2e713-113">Zum Beispiel kann 'D' leicht einen Löschvorgang und 'I' einen Einfügevorgang darstellen.</span><span class="sxs-lookup"><span data-stu-id="2e713-113">For example, 'D' can easily represent a delete operation and 'I' represent an insert operation.</span></span> <span data-ttu-id="2e713-114">Die Beispielabfrage, die im Thema [Erstellen der Funktion zum Abrufen der Änderungsdaten](create-the-function-to-retrieve-the-change-data.md)erstellt wurde, nimmt diese Konvertierung von einem Ordinalwert in einen benutzerfreundlichen Zeichenfolgenwert vor, der in einer neuen Spalte zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2e713-114">The example query that was created in the topic, [Creating the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md), makes this conversion from an ordinal value to a friendly string value that is returned in a new column.</span></span> <span data-ttu-id="2e713-115">Das folgende Codesegment zeigt diese Konvertierung:</span><span class="sxs-lookup"><span data-stu-id="2e713-115">The following segment of code shows this conversion:</span></span>  
  
```  
select   
    ...  
    case __$operation  
        when 1 then 'D'  
        when 2 then 'I'  
        when 4 then 'U'  
        else null  
     end as CDC_OPERATION  
```  
  
## <a name="configuring-a-conditional-split-transformation-to-direct-inserts-updates-and-deletes"></a><span data-ttu-id="2e713-116">Konfigurieren einer Transformation für bedingtes Teilen zur Weiterleitung von Einfügungen, Updates und Löschungen</span><span class="sxs-lookup"><span data-stu-id="2e713-116">Configuring a Conditional Split Transformation to Direct Inserts, Updates, and Deletes</span></span>  
 <span data-ttu-id="2e713-117">Die Transformation für bedingtes Teilen ist ideal zur Weiterleitung von Zeilen mit Änderungsdaten an eine von drei Ausgaben.</span><span class="sxs-lookup"><span data-stu-id="2e713-117">To direct rows of change data to one of three outputs, the Conditional Split transformation is ideal.</span></span> <span data-ttu-id="2e713-118">Die Transformation überprüft den Wert der **CDC_OPERATION** -Spalte in jeder Zeile und bestimmt, ob diese Änderung eine Einfügung, Löschung bzw. ein Update war.</span><span class="sxs-lookup"><span data-stu-id="2e713-118">The transformation just checks the value of the **CDC_OPERATION** column in each row and determines whether that change was an insert, update, or delete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2e713-119">Die Spalte CDC_OPERATION enthält einen benutzerfreundlichen vom numerischen Wert in der **__$operation** -Spalte abgeleiteten Zeichenfolgenwert.</span><span class="sxs-lookup"><span data-stu-id="2e713-119">The CDC_OPERATION column contains a friendly string value derived from the numeric value in the **__$operation** column.</span></span>  
  
#### <a name="to-split-inserts-updates-and-deletes-for-processing-by-using-a-conditional-split-transformation"></a><span data-ttu-id="2e713-120">So teilen Sie Einfügungen, Updates und Löschungen zur Verarbeitung durch Verwendung einer Transformation für bedingtes Teilen</span><span class="sxs-lookup"><span data-stu-id="2e713-120">To split inserts, updates, and deletes for processing by using a Conditional Split transformation</span></span>  
  
1.  <span data-ttu-id="2e713-121">Fügen Sie auf der Registerkarte **Datenfluss** eine Transformation für bedingtes Teilen hinzu.</span><span class="sxs-lookup"><span data-stu-id="2e713-121">On the **Data Flow** tab, add a Conditional Split transformation.</span></span>  
  
2.  <span data-ttu-id="2e713-122">Verbinden Sie die Ausgabe der OLE DB-Quelle mit der Transformation für bedingtes Teilen.</span><span class="sxs-lookup"><span data-stu-id="2e713-122">Connect the output of the OLE DB source to the Conditional Split transformation.</span></span>  
  
3.  <span data-ttu-id="2e713-123">Geben Sie im **Transformations-Editor für bedingtes Teilen**im unteren Bereich des Editors die folgenden drei Zeilen ein, um die drei Ausgaben zu bestimmen</span><span class="sxs-lookup"><span data-stu-id="2e713-123">In the **Conditional Split Transformation Editor**, in the lower pane of the editor, enter the following three lines to designate the three outputs</span></span>  
  
    1.  <span data-ttu-id="2e713-124">Geben Sie eine Zeile mit der Bedingung `CDC_OPERATION == "I"` ein, um eingefügte Zeilen an die Ausgabe für Einfügungen weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="2e713-124">Enter a line with the condition `CDC_OPERATION == "I"` to direct inserted rows to the output for inserts.</span></span>  
  
    2.  <span data-ttu-id="2e713-125">Geben Sie eine Zeile mit der Bedingung `CDC_OPERATION == "U"` ein, um aktualisierte Zeilen an die Ausgabe für Updates weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="2e713-125">Enter a line with the condition `CDC_OPERATION == "U"` to direct updated rows to the output for updates.</span></span>  
  
    3.  <span data-ttu-id="2e713-126">Geben Sie eine Zeile mit der Bedingung `CDC_OPERATION == "D"` ein, um gelöschte Zeilen an die Ausgabe für Löschungen weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="2e713-126">Enter a line with the condition `CDC_OPERATION == "D"` to direct deleted rows to the output for deletes.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="2e713-127">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="2e713-127">Next Step</span></span>  
 <span data-ttu-id="2e713-128">Nachdem Sie die Zeilen zur Verarbeitung geteilt haben, besteht der nächste Schritt darin, die Änderungen auf das Ziel anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="2e713-128">After you split the rows for processing, the next step is to apply the changes to the destination.</span></span>  
  
 <span data-ttu-id="2e713-129">**Nächstes Thema:** [Anwenden der Änderungen auf das Ziel](apply-the-changes-to-the-destination.md)</span><span class="sxs-lookup"><span data-stu-id="2e713-129">**Next topic:** [Apply the Changes to the Destination](apply-the-changes-to-the-destination.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e713-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2e713-130">See Also</span></span>  
 <span data-ttu-id="2e713-131">[Conditional Split Transformation](../data-flow/transformations/conditional-split-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="2e713-131">[Conditional Split Transformation](../data-flow/transformations/conditional-split-transformation.md) </span></span>  
 [<span data-ttu-id="2e713-132">Teilen eines Datasets mithilfe der Transformation für bedingtes Teilen</span><span class="sxs-lookup"><span data-stu-id="2e713-132">Split a Dataset by Using the Conditional Split Transformation</span></span>](../data-flow/transformations/split-a-dataset-by-using-the-conditional-split-transformation.md)  
  
  
