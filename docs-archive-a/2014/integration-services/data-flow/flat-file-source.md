---
title: Flatfilequelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesource.f1
helpviewer_keywords:
- sources [Integration Services], Flat File
- text file reading [Integration Services]
- flat files
- Flat File source
ms.assetid: 4a64f7f3-f25d-4db0-93b3-a29496030e58
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b1ca0f38c457256b3f2ed2ddb81bfbd0dc06b6c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726097"
---
# <a name="flat-file-source"></a><span data-ttu-id="62b53-102">Flatfilequelle</span><span class="sxs-lookup"><span data-stu-id="62b53-102">Flat File Source</span></span>
  <span data-ttu-id="62b53-103">Die Flatfilequelle liest Daten aus einer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="62b53-103">The Flat File source reads data from a text file.</span></span> <span data-ttu-id="62b53-104">Die Textdatei kann in einem Format mit Trennzeichen, fester Breite oder einem gemischten Format vorliegen.</span><span class="sxs-lookup"><span data-stu-id="62b53-104">The text file can be in delimited, fixed width, or mixed format.</span></span>  
  
-   <span data-ttu-id="62b53-105">Beim Format mit Trennzeichen werden Spalten und Zeilen mithilfe von Spalten- und Zeilentrennzeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="62b53-105">Delimited format uses column and row delimiters to define columns and rows.</span></span>  
  
-   <span data-ttu-id="62b53-106">Beim Format mit fester Breite werden Spalten und Zeilen mithilfe der Breite definiert.</span><span class="sxs-lookup"><span data-stu-id="62b53-106">Fixed width format uses width to define columns and rows.</span></span> <span data-ttu-id="62b53-107">Dieses Format schließt außerdem ein Zeichen zur Auffüllung der Felder auf die maximale Breite ein.</span><span class="sxs-lookup"><span data-stu-id="62b53-107">This format also includes a character for padding fields to their maximum width.</span></span>  
  
-   <span data-ttu-id="62b53-108">Beim Format mit einem rechten Flatterrand werden mithilfe der Breite alle Spalten definiert, außer der letzten Spalte, die durch das Zeilentrennzeichen getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="62b53-108">Ragged right format uses width to define all columns, except for the last column, which is delimited by the row delimiter.</span></span>  
  
 <span data-ttu-id="62b53-109">Es gibt folgende Möglichkeiten, um die Flatfilequelle zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="62b53-109">You can configure the Flat File source in the following ways:</span></span>  
  
-   <span data-ttu-id="62b53-110">Fügen Sie der Transformationsausgabe eine Zeile hinzu, die den Namen der Textdatei enthält, aus der die Flatfilequelle Daten extrahiert.</span><span class="sxs-lookup"><span data-stu-id="62b53-110">Add a column to the transformation output that contains the name of the text file from which the Flat File source extracts data.</span></span>  
  
-   <span data-ttu-id="62b53-111">Geben Sie an, ob die Flatfilequelle leere Zeichenfolgen in Spalten als NULL-Werte interpretiert.</span><span class="sxs-lookup"><span data-stu-id="62b53-111">Specify whether the Flat File source interprets zero-length strings in columns as null values.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="62b53-112">Für den von der Flatfilequelle verwendeten Verbindungs-Manager für Flatfiles muss die Verwendung eines Formats mit Trennzeichen konfiguriert werden, damit leere Zeichenfolgen als NULL-Werte interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="62b53-112">The Flat File connection manager that the Flat File source uses must be configured to use a delimited format to interpret zero-length strings as nulls.</span></span> <span data-ttu-id="62b53-113">Falls der Verbindungs-Manager ein Format mit fester Breite oder mit einem Flatterrand verwendet, können aus Leerzeichen bestehende Daten nicht als NULL-Werte interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="62b53-113">If the connection manager uses the fixed width or ragged right formats, data that consists of spaces cannot be interpreted as null values.</span></span>  
  
 <span data-ttu-id="62b53-114">Die Ausgabespalte in der Ausgabe der Flatfilequelle schließt die FastParse-Eigenschaft ein.</span><span class="sxs-lookup"><span data-stu-id="62b53-114">The output columns in the output of the Flat File source include the FastParse property.</span></span> <span data-ttu-id="62b53-115">FastParse gibt an, ob die Spalte die schnelleren gebietsschemaneutralen Analyseroutinen von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] oder die gebietsschemabezogenen Standardanalyseroutinen verwendet.</span><span class="sxs-lookup"><span data-stu-id="62b53-115">FastParse indicates whether the column uses the quicker, but locale-insensitive, fast parsing routines that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides or the locale-sensitive standard parsing routines.</span></span> <span data-ttu-id="62b53-116">Weitere Informationen finden Sie unter [Fast Parse](../fast-parse.md) und [Standard Parse](../standard-parse.md).</span><span class="sxs-lookup"><span data-stu-id="62b53-116">For more information, see [Fast Parse](../fast-parse.md) and [Standard Parse](../standard-parse.md).</span></span>  
  
 <span data-ttu-id="62b53-117">Ausgabespalten schließen auch UseBinaryFormat-Eigenschaft ein.</span><span class="sxs-lookup"><span data-stu-id="62b53-117">Output columns also include the UseBinaryFormat property.</span></span> <span data-ttu-id="62b53-118">Sie verwenden diese Eigenschaft, um Unterstützung für binäre Daten in Dateien zu implementieren, wie für Daten mit dem gepackten Dezimalformat.</span><span class="sxs-lookup"><span data-stu-id="62b53-118">You use this property to implement support for binary data, such as data with the packed decimal format, in files.</span></span> <span data-ttu-id="62b53-119">Standardmäßig ist UseBinaryFormat auf festgelegt `false` .</span><span class="sxs-lookup"><span data-stu-id="62b53-119">By default UseBinaryFormat is set to `false`.</span></span> <span data-ttu-id="62b53-120">Wenn Sie ein Binärformat verwenden möchten, legen Sie UseBinaryFormat auf `true` und den Datentyp in der Ausgabe Spalte auf fest `DT_BYTES` .</span><span class="sxs-lookup"><span data-stu-id="62b53-120">If you want to use a binary format, set UseBinaryFormat to `true` and the data type on the output column to `DT_BYTES`.</span></span> <span data-ttu-id="62b53-121">Bei diesem Vorgang überspringt die Flatfilequelle die Datenkonvertierung und leitet die Daten durch die Ausgabespalte, wie sie ist.</span><span class="sxs-lookup"><span data-stu-id="62b53-121">When you do this, the Flat File source skips the data conversion and passes the data to the output column as is.</span></span> <span data-ttu-id="62b53-122">Sie können eine Transformation verwenden, wie Abgeleitete Spalte oder Datenkonvertierung um die `DT_BYTES`-Daten in einen anderen Datentyp umzuwandeln, oder Sie können ein benutzerdefiniertes Skript in eine Skripttransformation schreiben, um die Daten zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="62b53-122">You can then use a transformation such as the Derived Column or Data Conversion to cast the `DT_BYTES` data to a different data type, or you can write custom script in a Script transformation to interpret the data.</span></span> <span data-ttu-id="62b53-123">Sie können auch eine benutzerdefinierte Datenflusskomponente schreiben, um die Daten zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="62b53-123">You can also write a custom data flow component to interpret the data.</span></span> <span data-ttu-id="62b53-124">Weitere Informationen zu den Datentypen, die Sie in umwandeln können `DT_BYTES` , finden Sie unter [Cast &#40;SSIS-Ausdrucks&#41;](../expressions/cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="62b53-124">For more information about which data types you can cast `DT_BYTES` to, see [Cast &#40;SSIS Expression&#41;](../expressions/cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="62b53-125">Diese Quelle verwendet für den Zugriff auf die Textdatei einen Verbindungs-Manager für Flatfiles.</span><span class="sxs-lookup"><span data-stu-id="62b53-125">This source uses a Flat File connection manager to access the text file.</span></span> <span data-ttu-id="62b53-126">Durch Festlegen von Eigenschaften im Verbindungs-Manager für Flatfiles können Sie Informationen zur Datei und zu jeder enthaltenen Spalte bereitstellen und angeben, wie die Flatfilequelle die Daten in der Textdatei behandeln soll.</span><span class="sxs-lookup"><span data-stu-id="62b53-126">By setting properties on the Flat File connection manager, you can provide information about the file and each column in it, and specify how the Flat File source should handle the data in the text file.</span></span> <span data-ttu-id="62b53-127">Beispielsweise können Sie die Zeichen angeben, mit denen Spalten und Zeilen in der Datei getrennt werden, sowie den Datentyp und die Länge jeder Spalte.</span><span class="sxs-lookup"><span data-stu-id="62b53-127">For example, you can specify the characters that delimit columns and rows in the file, and the data type and the length of each column.</span></span> <span data-ttu-id="62b53-128">Weitere Informationen finden Sie unter [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="62b53-128">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="62b53-129">Diese Quelle weist eine Ausgabe und eine Fehlerausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="62b53-129">This source has one output and one error output.</span></span>  
  
## <a name="configuration-of-the-flat-file-source"></a><span data-ttu-id="62b53-130">Konfiguration der Flatfilequelle</span><span class="sxs-lookup"><span data-stu-id="62b53-130">Configuration of the Flat File Source</span></span>  
 <span data-ttu-id="62b53-131">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="62b53-131">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="62b53-132">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Quellen-Editor für Flatfiles** festlegen können:</span><span class="sxs-lookup"><span data-stu-id="62b53-132">For more information about the properties that you can set in the **Flat File Source Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="62b53-133">Quellen-Editor für Flatfiles &#40;Seite „Verbindungs-Manager“&#41;</span><span class="sxs-lookup"><span data-stu-id="62b53-133">Flat File Source Editor &#40;Connection Manager Page&#41;</span></span>](../flat-file-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="62b53-134">Quellen-Editor für Flatfiles &#40;Seite Spalten&#41;</span><span class="sxs-lookup"><span data-stu-id="62b53-134">Flat File Source Editor &#40;Columns Page&#41;</span></span>](../flat-file-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="62b53-135">Quellen-Editor für Flatfiles &#40;Seite Fehlerausgabe&#41;</span><span class="sxs-lookup"><span data-stu-id="62b53-135">Flat File Source Editor &#40;Error Output Page&#41;</span></span>](../flat-file-source-editor-error-output-page.md)  
  
 <span data-ttu-id="62b53-136">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="62b53-136">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="62b53-137">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="62b53-137">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="62b53-138">Common Properties</span><span class="sxs-lookup"><span data-stu-id="62b53-138">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="62b53-139">Benutzerdefinierte Eigenschaften der Flatfile</span><span class="sxs-lookup"><span data-stu-id="62b53-139">Flat File Custom Properties</span></span>](flat-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="62b53-140">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="62b53-140">Related Tasks</span></span>  
 <span data-ttu-id="62b53-141">Weitere Informationen zum Festlegen der Eigenschaften einer Datenflusskomponente finden Sie unter [Festlegen der Eigenschaften einer Datenflusskomponente](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="62b53-141">For details about how to set properties of a data flow component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62b53-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="62b53-142">See Also</span></span>  
 <span data-ttu-id="62b53-143">[Flatfileziel](flat-file-destination.md) </span><span class="sxs-lookup"><span data-stu-id="62b53-143">[Flat File Destination](flat-file-destination.md) </span></span>  
 [<span data-ttu-id="62b53-144">Datenfluss</span><span class="sxs-lookup"><span data-stu-id="62b53-144">Data Flow</span></span>](data-flow.md)  
  
  
