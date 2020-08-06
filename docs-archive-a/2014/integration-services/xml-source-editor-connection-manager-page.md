---
title: Quellen-Editor für XML (Seite Verbindungs-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.xmlsourceadapter.connectionmanager.f1
helpviewer_keywords:
- XML Source Editor
ms.assetid: e6507403-a3ce-4b6f-91fc-a7de9f7b6283
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0e40ca6ef2d8fbcd10b756a2ce15f33730c367d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622205"
---
# <a name="xml-source-editor-connection-manager-page"></a><span data-ttu-id="39454-102">Quellen-Editor für XML (Seite Verbindungs-Manager)</span><span class="sxs-lookup"><span data-stu-id="39454-102">XML Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="39454-103">Mithilfe der Seite **Verbindungs-Manager** in **Quellen-Editor für XML** können Sie eine XML-Datei und die XML-Schemadefinition (XSD) angeben, mit der die XML-Daten transformiert werden.</span><span class="sxs-lookup"><span data-stu-id="39454-103">Use the **Connection Manager** page of the **XML Source Editor** to specify an XML file and the XSD that transforms the XML data.</span></span>  
  
 <span data-ttu-id="39454-104">Weitere Informationen zur XML-Quelle finden Sie unter [XML Source](data-flow/xml-source.md).</span><span class="sxs-lookup"><span data-stu-id="39454-104">For more information about the XML source, see [XML Source](data-flow/xml-source.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="39454-105">Statische Optionen</span><span class="sxs-lookup"><span data-stu-id="39454-105">Static Options</span></span>  
 <span data-ttu-id="39454-106">**Datenzugriffsmodus**</span><span class="sxs-lookup"><span data-stu-id="39454-106">**Data access mode**</span></span>  
 <span data-ttu-id="39454-107">Geben Sie die Methode für die Auswahl von Daten aus der Quelle an.</span><span class="sxs-lookup"><span data-stu-id="39454-107">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="39454-108">Wert</span><span class="sxs-lookup"><span data-stu-id="39454-108">Value</span></span>|<span data-ttu-id="39454-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="39454-109">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="39454-110">XML-Dateispeicherort</span><span class="sxs-lookup"><span data-stu-id="39454-110">XML file location</span></span>|<span data-ttu-id="39454-111">Ruft Daten aus einer XML-Datei ab.</span><span class="sxs-lookup"><span data-stu-id="39454-111">Retrieve data from an XML file.</span></span>|  
|<span data-ttu-id="39454-112">XML-Datei aus Variable</span><span class="sxs-lookup"><span data-stu-id="39454-112">XML file from variable</span></span>|<span data-ttu-id="39454-113">Gibt den XML-Dateinamen in einer Variablen an.</span><span class="sxs-lookup"><span data-stu-id="39454-113">Specify the XML file name in a variable.</span></span><br /><br /> <span data-ttu-id="39454-114">**Verwandte Informationen**: [Verwenden von Variablen in Paketen](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="39454-114">**Related information**: [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="39454-115">XML-Daten aus Variable</span><span class="sxs-lookup"><span data-stu-id="39454-115">XML data from variable</span></span>|<span data-ttu-id="39454-116">Ruft XML-Daten aus einer Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="39454-116">Retrieve XML data from a variable.</span></span>|  
  
 <span data-ttu-id="39454-117">**Inlineschema verwenden**</span><span class="sxs-lookup"><span data-stu-id="39454-117">**Use inline schema**</span></span>  
 <span data-ttu-id="39454-118">Gibt an, ob die XML-Quelldaten das XSD-Schema enthalten, mit dem die Struktur und die Daten definiert und überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="39454-118">Specify whether the XML source data itself contains the XSD schema that defines and validates its structure and data.</span></span>  
  
 <span data-ttu-id="39454-119">**XSD-Speicherort**</span><span class="sxs-lookup"><span data-stu-id="39454-119">**XSD location**</span></span>  
 <span data-ttu-id="39454-120">Geben Sie den Pfad und den Dateinamen der XSD-Schemadatei ein, oder suchen Sie die Datei, indem Sie auf die Schaltfläche **Durchsuchen**klicken.</span><span class="sxs-lookup"><span data-stu-id="39454-120">Type the path and file name of the XSD schema file, or locate the file by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="39454-121">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="39454-121">**Browse**</span></span>  
 <span data-ttu-id="39454-122">Mithilfe des Dialogfelds **Öffnen** können Sie die XSD-Schemadatei suchen.</span><span class="sxs-lookup"><span data-stu-id="39454-122">Use the **Open** dialog box to locate the XSD schema file.</span></span>  
  
 <span data-ttu-id="39454-123">**XSD-Code generieren**</span><span class="sxs-lookup"><span data-stu-id="39454-123">**Generate XSD**</span></span>  
 <span data-ttu-id="39454-124">Mithilfe des Dialogfelds **Speichern unter** können Sie einen Speicherort für die automatisch generierte XSD-Schemadatei auswählen.</span><span class="sxs-lookup"><span data-stu-id="39454-124">Use the **Save As** dialog box to select a location for the auto-generated XSD schema file.</span></span> <span data-ttu-id="39454-125">Der Editor leitet das Schema aus der Struktur der XML-Daten ab.</span><span class="sxs-lookup"><span data-stu-id="39454-125">The editor infers the schema from the structure of the XML data.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="39454-126">Dynamische Optionen (Datenzugriffsmodus)</span><span class="sxs-lookup"><span data-stu-id="39454-126">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--xml-file-location"></a><span data-ttu-id="39454-127">Datenzugriffsmodus = Speicherort der XML-Datei</span><span class="sxs-lookup"><span data-stu-id="39454-127">Data access mode = XML file location</span></span>  
 <span data-ttu-id="39454-128">**XML-Speicherort**</span><span class="sxs-lookup"><span data-stu-id="39454-128">**XML location**</span></span>  
 <span data-ttu-id="39454-129">Geben Sie den Pfad und den Dateinamen der XML-Datendatei ein, oder suchen Sie die Datei, indem Sie auf die Schaltfläche **Durchsuchen**klicken.</span><span class="sxs-lookup"><span data-stu-id="39454-129">Type the path and file name of the XML data file, or locate the file by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="39454-130">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="39454-130">**Browse**</span></span>  
 <span data-ttu-id="39454-131">Mithilfe des Dialogfelds **Öffnen** können Sie die XML-Datendatei suchen.</span><span class="sxs-lookup"><span data-stu-id="39454-131">Use the **Open** dialog box to locate the XML data file.</span></span>  
  
### <a name="data-access-mode--xml-file-from-variable"></a><span data-ttu-id="39454-132">Datenzugriffsmodus = XML-Datei aus Variable</span><span class="sxs-lookup"><span data-stu-id="39454-132">Data access mode = XML file from variable</span></span>  
 <span data-ttu-id="39454-133">**Variablenname**</span><span class="sxs-lookup"><span data-stu-id="39454-133">**Variable name**</span></span>  
 <span data-ttu-id="39454-134">Wählt die Variable aus, die den Pfad und den Dateinamen der XML-Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="39454-134">Select the variable that contains the path and file name of the XML file.</span></span>  
  
### <a name="data-access-mode--xml-data-from-variable"></a><span data-ttu-id="39454-135">Datenzugriffsmodus = XML-Daten aus Variable</span><span class="sxs-lookup"><span data-stu-id="39454-135">Data access mode = XML data from variable</span></span>  
 <span data-ttu-id="39454-136">**Variablenname**</span><span class="sxs-lookup"><span data-stu-id="39454-136">**Variable name**</span></span>  
 <span data-ttu-id="39454-137">Wählt die Variable aus, die die XML-Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="39454-137">Select the variable that contains the XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39454-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="39454-138">See Also</span></span>  
 <span data-ttu-id="39454-139">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="39454-139">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="39454-140">[Der Quellen-Editor für XML-&#40;Spalten&#41;](../../2014/integration-services/xml-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="39454-140">[XML Source Editor &#40;Columns Page&#41;](../../2014/integration-services/xml-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="39454-141">[Quellen-Editor für XML-&#40;Seite Fehlerausgabe&#41;](../../2014/integration-services/xml-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="39454-141">[XML Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/xml-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="39454-142">Extrahieren von Daten mithilfe der XML-Quelle</span><span class="sxs-lookup"><span data-stu-id="39454-142">Extract Data by Using the XML Source</span></span>](data-flow/extract-data-by-using-the-xml-source.md)  
  
  
