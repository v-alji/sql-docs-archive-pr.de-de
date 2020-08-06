---
title: Kopieren und Einfügen von Daten (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.pastepreviewdb.f1
ms.assetid: 2f8d8b3d-810b-4c31-98f2-341015e13da8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30df733377f3cb6f7583d380fbb8e92a0ea69e88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610197"
---
# <a name="copy-and-paste-data-ssas-tabular"></a><span data-ttu-id="67bab-102">Kopieren und Einfügen von Daten (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="67bab-102">Copy and Paste Data (SSAS Tabular)</span></span>
  <span data-ttu-id="67bab-103">Sie können Tabellendaten aus externen Anwendungen kopieren und sie in eine neue oder vorhandene Tabelle im Modell-Designer einfügen.</span><span class="sxs-lookup"><span data-stu-id="67bab-103">You can copy table data from external applications and paste it into a new or existing table in the model designer.</span></span> <span data-ttu-id="67bab-104">Die Daten, die Sie aus der Zwischenablage einfügen, müssen im HTML-Format vorliegen, z. B. Daten, die aus Excel oder Word kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="67bab-104">The data that you paste from the Clipboard must be in HTML format, for example, data that is copied from Excel or Word.</span></span> <span data-ttu-id="67bab-105">Der Modell-Designer erkennt automatisch Datentypen und wenden sie auf die eingefügten Daten an.</span><span class="sxs-lookup"><span data-stu-id="67bab-105">The model designer will automatically detect and apply data types to the pasted data.</span></span> <span data-ttu-id="67bab-106">Sie können den Datentyp auch manuell ändern oder die Formatierung einer Spalte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="67bab-106">You can also manually modify the data type or display formatting of a column.</span></span>  
  
 <span data-ttu-id="67bab-107">Im Unterschied zu Tabellen mit einer Datenquellenverbindung verfügen eingefügte Tabellen über keine ConnectionName-Eigenschaft oder SourceData-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="67bab-107">Unlike tables with a data source connection, pasted tables do not have a Connection Name or Source Data property.</span></span> <span data-ttu-id="67bab-108">Eingefügte Daten werden in der Datei Model.bim beibehalten.</span><span class="sxs-lookup"><span data-stu-id="67bab-108">Pasted data is persisted in the Model.bim file.</span></span> <span data-ttu-id="67bab-109">Beim Speichern des Projekts oder der Datei Model.bim werden die eingefügten Daten ebenfalls gespeichert.</span><span class="sxs-lookup"><span data-stu-id="67bab-109">When the project or Model.bim file is saved, the pasted data is also saved.</span></span>  
  
 <span data-ttu-id="67bab-110">Bei der Modellbereitstellung werden die eingefügten Daten mit dem Modell bereitgestellt, und zwar unabhängig davon, ob das Modell mit der Bereitstellung verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="67bab-110">When a model is deployed, pasted data will also be deployed with it regardless if the model is processed with the deployment.</span></span>  
  
 <span data-ttu-id="67bab-111">Abschnitte in diesem Thema:</span><span class="sxs-lookup"><span data-stu-id="67bab-111">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="67bab-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="67bab-112">Prerequisites</span></span>](#bkmk_prerequisites)  
  
-   [<span data-ttu-id="67bab-113">Einfügen von Daten</span><span class="sxs-lookup"><span data-stu-id="67bab-113">Paste Data</span></span>](#bkmk_paste_data)  
  
-   [<span data-ttu-id="67bab-114">Vorschau einfügen (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="67bab-114">Paste Preview Dialog Box</span></span>](#bkmk_paste_preview)  
  
##  <a name="prerequisites"></a><a name="bkmk_prerequisites"></a> <span data-ttu-id="67bab-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="67bab-115">Prerequisites</span></span>  
 <span data-ttu-id="67bab-116">Beim Einfügen von Daten müssen verschiedene Einschränkungen beachtet werden:</span><span class="sxs-lookup"><span data-stu-id="67bab-116">There are some restrictions when pasting data:</span></span>  
  
-   <span data-ttu-id="67bab-117">Eingefügte Tabellen dürfen maximal 10.000 Zeilen enthalten.</span><span class="sxs-lookup"><span data-stu-id="67bab-117">Pasted tables cannot have more than 10,000 rows.</span></span>  
  
-   <span data-ttu-id="67bab-118">Eingefügte Tabellen können nicht partitioniert werden.</span><span class="sxs-lookup"><span data-stu-id="67bab-118">Pasted tables cannot be partitioned.</span></span>  
  
-   <span data-ttu-id="67bab-119">Eingefügte Tabellen werden nicht im DirectQuery-Modus unterstützt.</span><span class="sxs-lookup"><span data-stu-id="67bab-119">Pasted tables are not supported in DirectQuery mode.</span></span>  
  
-   <span data-ttu-id="67bab-120">Beim Arbeiten mit einer Tabelle, die anfänglich durch Einfügen von Daten aus der Zwischenablage erstellt wurde, sind nur die Optionen **Am Ende einfügen** und **Am Ende ersetzen** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="67bab-120">The **Paste Append** and **Paste Replace** options are only available when working with a table that was initially created by pasting data from the Clipboard.</span></span> <span data-ttu-id="67bab-121">Sie können **Am Ende einfügen** oder **Am Ende ersetzen** nicht verwenden, um einer Tabelle, die importierte Daten enthält, Daten aus einem anderen Datenquellentyp hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="67bab-121">You cannot use **Paste Append** or **Paste Replace** to add data into a table of imported data from another type of data source.</span></span>  
  
-   <span data-ttu-id="67bab-122">Wenn Sie **Am Ende einfügen** oder **Am Ende ersetzen**verwenden, müssen in den neuen Daten genau die gleiche Anzahl von Spalten wie in den ursprünglichen Daten enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="67bab-122">When you use **Paste Append** or **Paste Replace**, the new data must contain exactly the same number of columns as the original data.</span></span> <span data-ttu-id="67bab-123">Idealerweise sollten die Datenspalten, die Sie einfügen oder anfügen, denselben oder einen mit den Spalten in der Zieltabelle kompatiblen Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="67bab-123">Preferably, the columns of data that you paste or append should also be of the same or compatible data type as those in the destination table.</span></span> <span data-ttu-id="67bab-124">In einigen Fällen können Sie einen anderen Datentyp verwenden, dabei kann jedoch ein **Typenkonflikt** -Fehler angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="67bab-124">In some cases you can use a different data type, but a **Type mismatch** error may be displayed.</span></span>  
  
##  <a name="paste-data"></a><a name="bkmk_paste_data"></a> <span data-ttu-id="67bab-125">Einfügen von Daten</span><span class="sxs-lookup"><span data-stu-id="67bab-125">Paste Data</span></span>  
  
#### <a name="to-paste-data-into-the-designer"></a><span data-ttu-id="67bab-126">So fügen Sie Daten in den Designer ein</span><span class="sxs-lookup"><span data-stu-id="67bab-126">To paste data into the designer</span></span>  
  
-   <span data-ttu-id="67bab-127">Klicken Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]auf das Menü **Bearbeiten** , und klicken Sie dann auf eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="67bab-127">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Edit** menu, and then clicke of the following:</span></span>  
  
    -   <span data-ttu-id="67bab-128">Klicken Sie auf **Einfügen** , um den Inhalt der Zwischenablage in eine neue Tabelle einzufügen.</span><span class="sxs-lookup"><span data-stu-id="67bab-128">Click **Paste** to paste the contents of the Clipboard into a new table.</span></span>  
  
    -   <span data-ttu-id="67bab-129">Klicken Sie auf **Am Ende einfügen** , um den Inhalt der Zwischenablage als zusätzliche Zeilen in die ausgewählte Tabelle einzufügen.</span><span class="sxs-lookup"><span data-stu-id="67bab-129">Click **Paste Append** to paste the contents of the Clipboard as additional rows into the selected table.</span></span> <span data-ttu-id="67bab-130">Die neuen Zeilen werden am Ende der Tabelle hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="67bab-130">The new rows will be added to the end of the table.</span></span>  
  
    -   <span data-ttu-id="67bab-131">Klicken Sie auf **Am Ende ersetzen** , um die ausgewählte Tabelle durch den Inhalt der Zwischenablage zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="67bab-131">Click **Paste Replace** to replace the selected table with the contents of the Clipboard.</span></span> <span data-ttu-id="67bab-132">Alle vorhandenen Namen von Spaltenüberschriften bleiben in der Tabelle, und Beziehungen werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="67bab-132">All existing column header names will remain in the table, and relationships are preserved.</span></span>  
  
##  <a name="paste-preview-dialog-box"></a><a name="bkmk_paste_preview"></a><span data-ttu-id="67bab-133">Vorschau einfügen (Dialog Feld)</span><span class="sxs-lookup"><span data-stu-id="67bab-133">Paste Preview Dialog Box</span></span>  
 <span data-ttu-id="67bab-134">Im Dialogfeld **Vorschau einfügen** können Sie eine Vorschau der in das Designer-Fenster kopierten Daten anzeigen und sicherstellen, dass die Daten ordnungsgemäß kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="67bab-134">The **Paste Preview** dialog box enables you to see a preview of data that is copied into the designer window and to ensure that the data is copied correctly.</span></span> <span data-ttu-id="67bab-135">Kopieren Sie zum Öffnen des Dialogfelds tabellenbasierte Daten im HTML-Format in die Zwischenablage, und klicken Sie anschließend im Designer auf das Menü **Bearbeiten** . Klicken Sie anschließend auf **Einfügen**, **Am Ende anfügen**oder **Beim Einfügen ersetzen**.</span><span class="sxs-lookup"><span data-stu-id="67bab-135">To access this dialog box, copy table-based data in the HTML format to the clipboard, and then in the designer, click on the **Edit** menu, and then click **Paste**, **Paste Append**, or **Paste Replace**.</span></span> <span data-ttu-id="67bab-136">Die Optionen **Am Ende einfügen** und **Am Ende ersetzen** sind nur verfügbar, wenn Sie Daten in einer Tabelle hinzufügen oder ersetzen, die durch das Kopieren und Einfügen aus der Zwischenablage erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="67bab-136">The **Paste Append** and **Paste Replace** options are only available when you add or replace data in a table that was created by copying and pasting from the Clipboard.</span></span> <span data-ttu-id="67bab-137">Sie können **Am Ende einfügen** oder **Am Ende ersetzen** nicht verwenden, um Daten einer Tabelle mit importierten Daten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="67bab-137">You cannot use **Paste Append** or **Paste Replace** to add data into a table of imported data.</span></span>  
  
 <span data-ttu-id="67bab-138">Die Optionen in diesem Dialogfeld unterscheiden sich abhängig davon, ob Sie Daten in eine vollkommen neue Tabelle einfügen, Daten in eine vorhandene Tabelle einfügen und die vorhandenen Daten durch die neuen Daten ersetzen oder Daten an eine vorhandene Tabelle anfügen.</span><span class="sxs-lookup"><span data-stu-id="67bab-138">The options for this dialog box are different depending on whether you paste data into a completely new table, paste data into an existing table and then replace the existing data with the new data, or whether you append data to an existing table.</span></span>  
  
### <a name="paste-to-new-table"></a><span data-ttu-id="67bab-139">In neue Tabelle einfügen</span><span class="sxs-lookup"><span data-stu-id="67bab-139">Paste to New Table</span></span>  
 <span data-ttu-id="67bab-140">**Tabellenname**</span><span class="sxs-lookup"><span data-stu-id="67bab-140">**Table name**</span></span>  
 <span data-ttu-id="67bab-141">Geben Sie den Namen der Tabelle an, die im Designer erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="67bab-141">Specify the name of the table that will be created in the designer.</span></span>  
  
 <span data-ttu-id="67bab-142">**Einzufügende Daten**</span><span class="sxs-lookup"><span data-stu-id="67bab-142">**Data to be pasted**</span></span>  
 <span data-ttu-id="67bab-143">Zeigt ein Beispiel für den Inhalt der Zwischenablage an, der der Zieltabelle hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="67bab-143">Shows a sample of the Clipboard contents that will be added to the destination table.</span></span>  
  
### <a name="paste-append"></a><span data-ttu-id="67bab-144">Am Ende einfügen</span><span class="sxs-lookup"><span data-stu-id="67bab-144">Paste Append</span></span>  
 <span data-ttu-id="67bab-145">**Vorhandene Daten in der Tabelle**</span><span class="sxs-lookup"><span data-stu-id="67bab-145">**Existing data in the table**</span></span>  
 <span data-ttu-id="67bab-146">Zeigt ein Beispiel der vorhandenen Daten in der Tabelle an, damit Sie die Spalten, Datentypen usw. überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="67bab-146">Shows a sample of the existing data in the table so that you can verify the columns, data types, etc.</span></span>  
  
 <span data-ttu-id="67bab-147">**Einzufügende Daten**</span><span class="sxs-lookup"><span data-stu-id="67bab-147">**Data to be pasted**</span></span>  
 <span data-ttu-id="67bab-148">Zeigt ein Beispiel für den Inhalt der Zwischenablage an.</span><span class="sxs-lookup"><span data-stu-id="67bab-148">Shows a sample of the Clipboard contents.</span></span> <span data-ttu-id="67bab-149">Diese Daten werden an die vorhandenen Daten angefügt.</span><span class="sxs-lookup"><span data-stu-id="67bab-149">The existing data will be appended by this data.</span></span>  
  
### <a name="paste-replace"></a><span data-ttu-id="67bab-150">Am Ende ersetzen</span><span class="sxs-lookup"><span data-stu-id="67bab-150">Paste Replace</span></span>  
 <span data-ttu-id="67bab-151">**Vorhandene Daten in der Tabelle**</span><span class="sxs-lookup"><span data-stu-id="67bab-151">**Existing data in the table**</span></span>  
 <span data-ttu-id="67bab-152">Zeigt ein Beispiel der vorhandenen Daten in der Tabelle an, damit Sie die Spalten, Datentypen usw. überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="67bab-152">Shows a sample of the existing data in the table so that you can verify the columns, data types, etc.</span></span>  
  
 <span data-ttu-id="67bab-153">**Einzufügende Daten**</span><span class="sxs-lookup"><span data-stu-id="67bab-153">**Data to be pasted**</span></span>  
 <span data-ttu-id="67bab-154">Zeigt ein Beispiel für den Inhalt der Zwischenablage an.</span><span class="sxs-lookup"><span data-stu-id="67bab-154">Shows a sample of the Clipboard contents.</span></span> <span data-ttu-id="67bab-155">Die vorhandenen Daten in der Zieltabelle werden gelöscht, und die neuen Zeilen werden in die Tabelle eingefügt.</span><span class="sxs-lookup"><span data-stu-id="67bab-155">The existing data in the destination table will be deleted and the new rows will be inserted into the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67bab-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="67bab-156">See Also</span></span>  
 <span data-ttu-id="67bab-157">[Importieren von Daten &#40;tabellarischen SSAS-&#41;](import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="67bab-157">[Import Data &#40;SSAS Tabular&#41;](import-data-ssas-tabular.md) </span></span>  
 <span data-ttu-id="67bab-158">[Unterstützte Datenquellen &#40;tabellarischen SSAS-&#41;](tabular-models/data-sources-supported-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="67bab-158">[Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="67bab-159">Festlegen des Datentyps einer Spalte &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="67bab-159">Set the Data Type of a Column &#40;SSAS Tabular&#41;</span></span>](tabular-models/set-the-data-type-of-a-column-ssas-tabular.md)  
  
  
