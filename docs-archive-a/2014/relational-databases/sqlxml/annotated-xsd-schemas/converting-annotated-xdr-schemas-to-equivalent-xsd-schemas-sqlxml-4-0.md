---
title: Umrechnen von XDR-Schemas mit Anmerkungen in entsprechende XSD-Schemas (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XDR schemas, converting schemas
- annotated XSD schemas, converting schemas
- XDR to XSD Converter tool [SQLXML]
- XDR schemas [SQLXML], converting
- converting annotated schemas
- mapping schema [SQLXML], conversions
- XSD schemas [SQLXML], converting schemas
ms.assetid: 151c94a8-66d3-4c46-a5ff-a22df456940a
author: rothja
ms.author: jroth
ms.openlocfilehash: c36eb17aacb61a47fad0f389de9a3c216202827d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619727"
---
# <a name="converting-annotated-xdr-schemas-to-equivalent-xsd-schemas-sqlxml-40"></a><span data-ttu-id="d6f64-102">Konvertieren von XDR-Schemas mit Anmerkungen in gleichbedeutende XSD-Schemas (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="d6f64-102">Converting Annotated XDR Schemas to Equivalent XSD Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="d6f64-103">Die XSD-Sprache (XML Schema Definition) ist Nachfolger der XDR-Sprache (XML-Data Reduced) für Schemadefinitionen.</span><span class="sxs-lookup"><span data-stu-id="d6f64-103">The XML Schema Definition (XSD) language is the successor to the XML-Data Reduced (XDR) schema definition language.</span></span> <span data-ttu-id="d6f64-104">Nachdem XSD ab [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 unterstützt wird, wird davon ausgegangen, dass neue Schemas mit Anmerkungen mit XSD erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d6f64-104">With the introduction of XSD support in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, it is assumed that new annotated schemas are created using XSD.</span></span> <span data-ttu-id="d6f64-105">SQLXML 4.0 umfasst ein Konvertierungstool für die Umwandlung von XDR in XSD, das die Konvertierung vorhandener XDR-Schemas mit Anmerkungen in entsprechende XSD-Schemas erleichtern soll.</span><span class="sxs-lookup"><span data-stu-id="d6f64-105">SQLXML 4.0 includes an XDR to XSD converter tool that is designed to help you convert your existing annotated XDR schemas to equivalent XSD schemas.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d6f64-106">Verwenden Sie dieses Tool nur, wenn Sie XDR-Schemas mit Anmerkungen in mit SQLXML 4.0 zu verwendendes XSD konvertieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d6f64-106">Use this tool only when you want to convert annotated XDR schemas to XSD for use with SQLXML 4.0.</span></span> <span data-ttu-id="d6f64-107">Dies ist kein universelles XDR-in-XSD-Konvertierungstool.</span><span class="sxs-lookup"><span data-stu-id="d6f64-107">This is not a general purpose XDR to XSD converter tool.</span></span> <span data-ttu-id="d6f64-108">Die konvertierten XSD-Schemas verhalten sich unter Umständen anders als die ursprünglichen XDR-Schemas, wenn sie in anderen Umgebungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6f64-108">The converted XSD schemas may not behave the same as the original XDR schemas when used in other environments.</span></span>  
  
 <span data-ttu-id="d6f64-109">Wenn in der XDR-Eingabedatei die Codierung innerhalb der XML-Deklaration angegeben wird, dann wird diese Codierung für die generierte XSD-Ausgabedatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6f64-109">If the input XDR file specifies the encoding within the XML declaration, this becomes the encoding of the XSD output file that is generated.</span></span>  
  
 <span data-ttu-id="d6f64-110">Das Konvertierungstool (Cvtschema.exe) wird im Ordner Programme\SQLXML 4.0\bin installiert und an der Eingabeaufforderung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d6f64-110">The converter tool (Cvtschema.exe) is installed in the Program Files\SQLXML 4.0\bin folder and is executed at the command prompt.</span></span>  
  
 <span data-ttu-id="d6f64-111">Das ist die allgemeine Syntax:</span><span class="sxs-lookup"><span data-stu-id="d6f64-111">This is the general syntax:</span></span>  
  
```  
cvtschema XDRFileName, [-y], [-w] [-?]  
```  
  
 <span data-ttu-id="d6f64-112">Hierbei gilt:</span><span class="sxs-lookup"><span data-stu-id="d6f64-112">Where:</span></span>  
  
 <span data-ttu-id="d6f64-113">XDRFileName</span><span class="sxs-lookup"><span data-stu-id="d6f64-113">XDRFileName</span></span>  
 <span data-ttu-id="d6f64-114">Der Name der XDR-Datei, die in XSD konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d6f64-114">Is the name of the XDR file that is to be converted to XSD.</span></span> <span data-ttu-id="d6f64-115">Das Tool liest die XDR-Eingabedatei und erstellt im aktuellen Arbeitsverzeichnis eine XSD-Ausgabedatei.</span><span class="sxs-lookup"><span data-stu-id="d6f64-115">The tool reads the input XDR file and creates an XSD output file in the current working directory.</span></span> <span data-ttu-id="d6f64-116">Wenn die Eingabedatei über die Namenerweiterung .XDR oder .XML verfügt, wird eine XSD-Ausgabedatei gleichen Namens mit der Erweiterung .XSD erstellt.</span><span class="sxs-lookup"><span data-stu-id="d6f64-116">If the input file has an .xdr or .xml extension, the output XSD file is created with the same name but with an .xsd extension.</span></span> <span data-ttu-id="d6f64-117">Wenn die Eingabedatei eine andere Namenerweiterung als .XDR oder .XML hat (oder die Erweiterung fehlt), wird eine Ausgabedatei erstellt, die den gleichen Namen wie die Eingabedatei trägt, und dieser Dateiname wird zusätzlich mit der Erweiterung .XSD versehen.</span><span class="sxs-lookup"><span data-stu-id="d6f64-117">If the input file extension is other than .xml or .xdr (or if the extension is missing), the output file is created with the same name and the .xsd extension is appended to the input file name.</span></span> <span data-ttu-id="d6f64-118">Wenn der Name der XDR-Eingabedatei beispielsweise SampleFile.abc lautet, wird das resultierende XSD unter dem Namen SampleFile.abc.xsd gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d6f64-118">For example, if the input XDR file name is SampleFile.abc, the resulting XSD is saved as SampleFile.abc.xsd.</span></span>  
  
 <span data-ttu-id="d6f64-119">-y</span><span class="sxs-lookup"><span data-stu-id="d6f64-119">-y</span></span>  
 <span data-ttu-id="d6f64-120">(Optional) Überschreibt die vorhandene XSD-Datei mit der XSD-Datei, die vom Konvertierungstool generiert wird.</span><span class="sxs-lookup"><span data-stu-id="d6f64-120">(Optional) Overwrites the existing XSD file with the XSD file that is generated by the converter tool.</span></span> <span data-ttu-id="d6f64-121">Wenn dieses Flag nicht angegeben wird, fordert Sie das Tool auf anzugeben, ob die vorhandene XSD-Datei überschrieben werden soll, und gibt Ihnen die Möglichkeit, den Namen der Ausgabedatei zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d6f64-121">If the flag is not specified, the tool prompts you to specify whether you want to overwrite the existing XSD file and gives you the option to change the output file name.</span></span>  
  
 <span data-ttu-id="d6f64-122">-w</span><span class="sxs-lookup"><span data-stu-id="d6f64-122">-w</span></span>  
 <span data-ttu-id="d6f64-123">(Optional) Gibt im Konvertierungsprozess des Tools generierte Warnungen zurück, die nicht schwerwiegend sind.</span><span class="sxs-lookup"><span data-stu-id="d6f64-123">(Optional) Returns nonfatal warnings that are generated in the conversion process by the tool.</span></span> <span data-ttu-id="d6f64-124">Standardmäßig zeigt das Tool nur Meldungen für schwerwiegende Fehler an.</span><span class="sxs-lookup"><span data-stu-id="d6f64-124">By default, the tool displays messages only for fatal errors.</span></span>  
  
 <span data-ttu-id="d6f64-125">-?</span><span class="sxs-lookup"><span data-stu-id="d6f64-125">-?</span></span>  
 <span data-ttu-id="d6f64-126">Gibt eine Liste der Optionen, die Sie für `cvtschema` angeben können, und Erläuterungen dieser Optionen zurück.</span><span class="sxs-lookup"><span data-stu-id="d6f64-126">Returns a list of options that you can specify with `cvtschema`, along with an explanation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6f64-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6f64-127">See Also</span></span>  
 <span data-ttu-id="d6f64-128">[Zuordnung von XSD-Datentypen zu XPath-Datentypen &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="d6f64-128">[Mapping XSD Data Types to XPath Data Types &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="d6f64-129">XSD-Anmerkungen &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d6f64-129">XSD Annotations &#40;SQLXML 4.0&#41;</span></span>](../../sqlxml-annotated-xsd-schemas-using/xsd-annotations-sqlxml-4-0.md)  
  
  
