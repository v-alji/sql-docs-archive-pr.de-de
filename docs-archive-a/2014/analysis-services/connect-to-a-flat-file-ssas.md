---
title: Herstellen einer Verbindung mit einer Flatfile (SSAS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connflatfile.f1
ms.assetid: a365991e-eded-4cd8-89c0-0daf6d658d15
author: minewiskan
ms.author: owend
ms.openlocfilehash: e6bee3c8f7f4b255e6985e8d783365bc8a47599e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610226"
---
# <a name="connect-to-a-flat-file-ssas"></a><span data-ttu-id="0095e-102">Mit einer Flatfile verbinden (SSAS)</span><span class="sxs-lookup"><span data-stu-id="0095e-102">Connect to a Flat File (SSAS)</span></span>
  <span data-ttu-id="0095e-103">Auf dieser Seite des **Tabellenimport-Assistenten** können Sie eine Verbindung mit einer Flatfile (.txt), einer durch Tabstopps getrennten Datei (.tab) oder einer durch Trennzeichen getrennten Datei (.csv) herstellen.</span><span class="sxs-lookup"><span data-stu-id="0095e-103">This page of the **Table Import Wizard** enables you to connect to a flat file (.txt), tab-separated file (.tab), or a comma-separated file (.csv).</span></span> <span data-ttu-id="0095e-104">Um im [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf den Assistenten zuzugreifen, klicken Sie im Menü **Modell** auf **Aus Datenquelle importieren**.</span><span class="sxs-lookup"><span data-stu-id="0095e-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="0095e-105">Der ACE-Anbieter muss auf dem Computer installiert sein, um eine Verbindung mit einer Flatfile herzustellen.</span><span class="sxs-lookup"><span data-stu-id="0095e-105">To connect to a flat file, you must have the ACE provider installed on your computer.</span></span> <span data-ttu-id="0095e-106">Weitere Informationen finden Sie unter [Unterstützte Datenquellen &#40;SSAS – tabellarisch&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="0095e-106">For more information, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0095e-107">Beim Auswählen einer Datei auf dieser Seite werden die Anmeldeinformationen des aktuellen Benutzers verwendet.</span><span class="sxs-lookup"><span data-stu-id="0095e-107">The credentials of the current user are used when selecting a file in this page.</span></span> <span data-ttu-id="0095e-108">Der Import ist jedoch nicht erfolgreich, wenn der auf der Seite Identitätswechselinformationen angegebene Benutzer nicht über ausreichend Berechtigungen zum Lesen aus der ausgewählten Datei verfügt.</span><span class="sxs-lookup"><span data-stu-id="0095e-108">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected file.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="0095e-109">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="0095e-109">UI element list</span></span>  
 <span data-ttu-id="0095e-110">**Anzeigename der Verbindung**</span><span class="sxs-lookup"><span data-stu-id="0095e-110">**Friendly connection name**</span></span>  
 <span data-ttu-id="0095e-111">Geben Sie einen eindeutigen Namen für diese Datenquellenverbindung ein.</span><span class="sxs-lookup"><span data-stu-id="0095e-111">Type a unique name for this data source connection.</span></span> <span data-ttu-id="0095e-112">Dies ist ein Pflichtfeld.</span><span class="sxs-lookup"><span data-stu-id="0095e-112">This is a required field.</span></span>  
  
 <span data-ttu-id="0095e-113">**Dateipfad**</span><span class="sxs-lookup"><span data-stu-id="0095e-113">**File Path**</span></span>  
 <span data-ttu-id="0095e-114">Geben Sie den vollständigen Pfad der Datei an.</span><span class="sxs-lookup"><span data-stu-id="0095e-114">Specify a full path for the file.</span></span>  
  
 <span data-ttu-id="0095e-115">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="0095e-115">**Browse**</span></span>  
 <span data-ttu-id="0095e-116">Navigieren Sie zu einem Speicherort, an dem eine Datei verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0095e-116">Navigate to a location where a file is available.</span></span>  
  
 <span data-ttu-id="0095e-117">**Spalten Trennzeichen**</span><span class="sxs-lookup"><span data-stu-id="0095e-117">**Column Separator**</span></span>  
 <span data-ttu-id="0095e-118">Wählen Sie eine Option aus der Liste der verfügbaren Spaltentrennzeichen aus.</span><span class="sxs-lookup"><span data-stu-id="0095e-118">Select from a list of available column separators.</span></span> <span data-ttu-id="0095e-119">Dabei sollten Sie ein Spaltentrennzeichen auswählen, dessen Auftreten als Zeichen im Text unwahrscheinlich ist.</span><span class="sxs-lookup"><span data-stu-id="0095e-119">Choose a separator that is not likely to occur in the text.</span></span>  
  
|<span data-ttu-id="0095e-120">Wert</span><span class="sxs-lookup"><span data-stu-id="0095e-120">Value</span></span>|<span data-ttu-id="0095e-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0095e-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0095e-122">Tabulator (t)</span><span class="sxs-lookup"><span data-stu-id="0095e-122">Tab (t)</span></span>|<span data-ttu-id="0095e-123">Als Trennzeichen für Spalten dient ein Tabulator (t).</span><span class="sxs-lookup"><span data-stu-id="0095e-123">Columns are separated by a tab (t).</span></span>|  
|<span data-ttu-id="0095e-124">Komma (,)</span><span class="sxs-lookup"><span data-stu-id="0095e-124">Comma (,)</span></span>|<span data-ttu-id="0095e-125">Als Trennzeichen für Spalten dient ein Komma (,).</span><span class="sxs-lookup"><span data-stu-id="0095e-125">Columns are separated by a comma (,).</span></span>|  
|<span data-ttu-id="0095e-126">Semikolon (;)</span><span class="sxs-lookup"><span data-stu-id="0095e-126">Semicolon (;)</span></span>|<span data-ttu-id="0095e-127">Als Trennzeichen für Spalten dient ein Semikolon (;).</span><span class="sxs-lookup"><span data-stu-id="0095e-127">Columns are separated by a semicolon (;).</span></span>|  
|<span data-ttu-id="0095e-128">Leerzeichen ( )</span><span class="sxs-lookup"><span data-stu-id="0095e-128">Space ( )</span></span>|<span data-ttu-id="0095e-129">Als Trennzeichen für Spalten dient ein Leerzeichen ( ).</span><span class="sxs-lookup"><span data-stu-id="0095e-129">Columns are separated by a space ( ).</span></span>|  
|<span data-ttu-id="0095e-130">Doppelpunkt (:)</span><span class="sxs-lookup"><span data-stu-id="0095e-130">Colon (:)</span></span>|<span data-ttu-id="0095e-131">Als Trennzeichen für Spalten dient ein Doppelpunkt (:).</span><span class="sxs-lookup"><span data-stu-id="0095e-131">Columns are separated by a colon (:).</span></span>|  
|<span data-ttu-id="0095e-132">Senkrechter Strich (&#124;)</span><span class="sxs-lookup"><span data-stu-id="0095e-132">Vertical Bar (&#124;)</span></span>|<span data-ttu-id="0095e-133">Als Trennzeichen für Spalten dient ein senkrechter Strich (&#124;).</span><span class="sxs-lookup"><span data-stu-id="0095e-133">Columns are separated by a vertical bar (&#124;).</span></span>|  
  
 <span data-ttu-id="0095e-134">**Erweitert**</span><span class="sxs-lookup"><span data-stu-id="0095e-134">**Advanced**</span></span>  
 <span data-ttu-id="0095e-135">Geben Sie die Codierung und die Gebietsschemaoptionen für die Flatfile an.</span><span class="sxs-lookup"><span data-stu-id="0095e-135">Specify the encoding and locale options for the flat file.</span></span>  
  
 <span data-ttu-id="0095e-136">**Erste Zeile als Spaltenüberschriften verwenden**</span><span class="sxs-lookup"><span data-stu-id="0095e-136">**Use first row as column headers**</span></span>  
 <span data-ttu-id="0095e-137">Geben Sie an, ob die erste Datenzeile für die Spaltenüberschriften der Zieltabelle verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0095e-137">Specify whether to use the first data row as the column headers of the destination table.</span></span>  
  
 <span data-ttu-id="0095e-138">**Datenvorschau**</span><span class="sxs-lookup"><span data-stu-id="0095e-138">**Data preview**</span></span>  
 <span data-ttu-id="0095e-139">Zeigen Sie die Daten in der ausgewählten Datei in einer Vorschau an, und verwenden Sie die folgenden Optionen zum Ändern des Datenimports.</span><span class="sxs-lookup"><span data-stu-id="0095e-139">Preview the data in the selected file, and use the following options to modify the data import.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0095e-140">Nur die ersten 50 Zeilen in der Datei werden in dieser Vorschau angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0095e-140">Only the first 50 rows in the file are displayed in this preview.</span></span>  
  
|<span data-ttu-id="0095e-141">Option</span><span class="sxs-lookup"><span data-stu-id="0095e-141">Option</span></span>|<span data-ttu-id="0095e-142">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0095e-142">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="0095e-143">**Kontrollkästchen in der Spaltenüberschrift**</span><span class="sxs-lookup"><span data-stu-id="0095e-143">**Checkbox in the column header**</span></span>|<span data-ttu-id="0095e-144">Aktivieren Sie das Kontrollkästchen, um die Spalte in den Datenimport einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="0095e-144">Select the checkbox to include the column in the data import.</span></span> <span data-ttu-id="0095e-145">Deaktivieren Sie das Kontrollkästchen, um die Spalte aus dem Datenimport zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="0095e-145">Clear the checkbox to remove the column from the data import.</span></span>|  
|<span data-ttu-id="0095e-146">**Schaltfläche mit Abwärtspfeil in der Spaltenüberschrift**</span><span class="sxs-lookup"><span data-stu-id="0095e-146">**Down-arrow button in the column header**</span></span>|<span data-ttu-id="0095e-147">Sortieren und filtern Sie die Daten in der Spalte.</span><span class="sxs-lookup"><span data-stu-id="0095e-147">Sort and filter data in the column.</span></span>|  
  
 <span data-ttu-id="0095e-148">**Zeilenfilter löschen**</span><span class="sxs-lookup"><span data-stu-id="0095e-148">**Clear Row Filters**</span></span>  
 <span data-ttu-id="0095e-149">Entfernen Sie alle Filter, die auf die Daten in den Spalten angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="0095e-149">Remove all filters that were applied to the data in the columns.</span></span>  
  
  
