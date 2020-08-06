---
title: Transformations-Editor für Zeichen Zuordnung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.charactermaptransformation.f1
helpviewer_keywords:
- Character Map Transformation Editor
ms.assetid: 3f1dbcf9-9cca-4606-bdcc-7ea6ad48cdf3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c6cdcdba448dafc6ccf03774d4f611dee704b823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615506"
---
# <a name="character-map-transformation-editor"></a><span data-ttu-id="7e4e7-102">Transformations-Editor für Zeichenzuordnung</span><span class="sxs-lookup"><span data-stu-id="7e4e7-102">Character Map Transformation Editor</span></span>
  <span data-ttu-id="7e4e7-103">Im Dialogfeld **Transformations-Editor für Zeichenzuordnung** können Sie die auf Spaltendaten anwendbaren Zeichenfolgenfunktionen auswählen und angeben, ob eine Zuordnung direkt geändert oder als neue Spalte hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7e4e7-103">Use the **Character Map Transformation Editor** dialog box to select the string functions to apply to column data and to specify whether mapping is an in-place change or added as a new column.</span></span>  
  
 <span data-ttu-id="7e4e7-104">Weitere Informationen zur Transformation zum Zuordnen der Zeichen finden Sie unter [Character Map Transformation](data-flow/transformations/character-map-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="7e4e7-104">To learn more about the Character Map transformation, see [Character Map Transformation](data-flow/transformations/character-map-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7e4e7-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="7e4e7-105">Options</span></span>  
 <span data-ttu-id="7e4e7-106">**Verfügbare Eingabespalten**</span><span class="sxs-lookup"><span data-stu-id="7e4e7-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="7e4e7-107">Wählen Sie mithilfe der Kontrollkästchen die Spalten aus, die mithilfe von Zeichenfolgenfunktionen transformiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7e4e7-107">Use the check boxes to select the columns to transform using string functions.</span></span> <span data-ttu-id="7e4e7-108">Die getroffene Auswahl wird in der nachfolgenden Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7e4e7-108">Your selections appear in the table below.</span></span>  
  
 <span data-ttu-id="7e4e7-109">**Eingabespalte**</span><span class="sxs-lookup"><span data-stu-id="7e4e7-109">**Input Column**</span></span>  
 <span data-ttu-id="7e4e7-110">Zeigen Sie die in obiger Tabelle ausgewählten Eingabespalten an.</span><span class="sxs-lookup"><span data-stu-id="7e4e7-110">View input columns selected from the table above.</span></span> <span data-ttu-id="7e4e7-111">Sie können eine Auswahl auch ändern oder entfernen, indem Sie die Liste der verfügbaren Eingabespalten verwenden.</span><span class="sxs-lookup"><span data-stu-id="7e4e7-111">You can also change or remove a selection by using the list of available input columns.</span></span>  
  
 <span data-ttu-id="7e4e7-112">**Ziel**</span><span class="sxs-lookup"><span data-stu-id="7e4e7-112">**Destination**</span></span>  
 <span data-ttu-id="7e4e7-113">Geben Sie an, ob Sie die Ergebnisse der Zeichenfolgenfunktionen direkt in der vorhandenen Spalte speichern möchten, oder ob Sie die geänderten Daten in einer neuen Spalte speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="7e4e7-113">Specify whether to save the results of the string operations in place, using the existing column, or to save the modified data as a new column.</span></span>  
  
|<span data-ttu-id="7e4e7-114">Wert</span><span class="sxs-lookup"><span data-stu-id="7e4e7-114">Value</span></span>|<span data-ttu-id="7e4e7-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7e4e7-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7e4e7-116">Neue Spalte</span><span class="sxs-lookup"><span data-stu-id="7e4e7-116">New column</span></span>|<span data-ttu-id="7e4e7-117">Speichern Sie die Daten in einer neuen Spalte.</span><span class="sxs-lookup"><span data-stu-id="7e4e7-117">Save the data in a new column.</span></span> <span data-ttu-id="7e4e7-118">Weisen Sie der Spalte unter **Ausgabealias**einen Namen zu.</span><span class="sxs-lookup"><span data-stu-id="7e4e7-118">Assign the column name under **Output Alias**.</span></span>|  
|<span data-ttu-id="7e4e7-119">Direkte Änderung</span><span class="sxs-lookup"><span data-stu-id="7e4e7-119">In-place change</span></span>|<span data-ttu-id="7e4e7-120">Speichern Sie die geänderten Daten in der vorhandenen Spalte.</span><span class="sxs-lookup"><span data-stu-id="7e4e7-120">Save the modified data in the existing column.</span></span>|  
  
 <span data-ttu-id="7e4e7-121">**Vorgang**</span><span class="sxs-lookup"><span data-stu-id="7e4e7-121">**Operation**</span></span>  
 <span data-ttu-id="7e4e7-122">Wählen Sie in der Liste die Zeichenfolgenfunktionen aus, die auf Spaltendaten angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7e4e7-122">Select from the list the string functions to apply to column data.</span></span>  
  
|<span data-ttu-id="7e4e7-123">Wert</span><span class="sxs-lookup"><span data-stu-id="7e4e7-123">Value</span></span>|<span data-ttu-id="7e4e7-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7e4e7-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7e4e7-125">Kleinbuchstaben</span><span class="sxs-lookup"><span data-stu-id="7e4e7-125">Lowercase</span></span>|<span data-ttu-id="7e4e7-126">In Kleinschreibung konvertieren.</span><span class="sxs-lookup"><span data-stu-id="7e4e7-126">Convert to lower case.</span></span>|  
|<span data-ttu-id="7e4e7-127">Großbuchstaben</span><span class="sxs-lookup"><span data-stu-id="7e4e7-127">Uppercase</span></span>|<span data-ttu-id="7e4e7-128">In Großschreibung konvertieren.</span><span class="sxs-lookup"><span data-stu-id="7e4e7-128">Convert to upper case.</span></span>|  
|<span data-ttu-id="7e4e7-129">Byteumkehrung</span><span class="sxs-lookup"><span data-stu-id="7e4e7-129">Byte reversal</span></span>|<span data-ttu-id="7e4e7-130">In umgekehrte Bytereihenfolge konvertieren.</span><span class="sxs-lookup"><span data-stu-id="7e4e7-130">Convert by reversing byte order.</span></span>|  
|<span data-ttu-id="7e4e7-131">Hiragana</span><span class="sxs-lookup"><span data-stu-id="7e4e7-131">Hiragana</span></span>|<span data-ttu-id="7e4e7-132">Japanische Katakana-Zeichen in Hiragana-Zeichen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="7e4e7-132">Convert Japanese katakana characters to hiragana.</span></span>|  
|<span data-ttu-id="7e4e7-133">Katakana</span><span class="sxs-lookup"><span data-stu-id="7e4e7-133">Katakana</span></span>|<span data-ttu-id="7e4e7-134">Japanische Hiragana-Zeichen in Katakana-Zeichen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="7e4e7-134">Convert Japanese hiragana characters to katakana.</span></span>|  
|<span data-ttu-id="7e4e7-135">Halbe Breite</span><span class="sxs-lookup"><span data-stu-id="7e4e7-135">Half width</span></span>|<span data-ttu-id="7e4e7-136">Zeichen normaler Breite in Zeichen halber Breite konvertieren.</span><span class="sxs-lookup"><span data-stu-id="7e4e7-136">Convert full-width characters to half width.</span></span>|  
|<span data-ttu-id="7e4e7-137">Normale Breite</span><span class="sxs-lookup"><span data-stu-id="7e4e7-137">Full width</span></span>|<span data-ttu-id="7e4e7-138">Zeichen halber Breite in Zeichen normaler Breite konvertieren.</span><span class="sxs-lookup"><span data-stu-id="7e4e7-138">Convert half-width characters to full width.</span></span>|  
|<span data-ttu-id="7e4e7-139">Linguistische Schreibweise</span><span class="sxs-lookup"><span data-stu-id="7e4e7-139">Linguistic casing</span></span>|<span data-ttu-id="7e4e7-140">Wenden Sie statt der Systemregeln die Regeln der linguistischen Schreibweise an (die mit Unicode bereitgestellte einfache Zuordnung der Schreibweise für Türkisch und andere Gebietsschemas).</span><span class="sxs-lookup"><span data-stu-id="7e4e7-140">Apply linguistic rules of casing (Unicode simple case mapping for Turkic and other locales) instead of the system rules.</span></span>|  
|<span data-ttu-id="7e4e7-141">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="7e4e7-141">Simplified Chinese</span></span>|<span data-ttu-id="7e4e7-142">Konvertieren Sie traditionelle chinesische Zeichen in vereinfachte chinesische Zeichen.</span><span class="sxs-lookup"><span data-stu-id="7e4e7-142">Convert traditional Chinese characters to simplified Chinese.</span></span>|  
|<span data-ttu-id="7e4e7-143">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="7e4e7-143">Traditional Chinese</span></span>|<span data-ttu-id="7e4e7-144">Konvertieren Sie vereinfachte chinesische Zeichen in traditionelle chinesische Zeichen.</span><span class="sxs-lookup"><span data-stu-id="7e4e7-144">Convert simplified Chinese characters to traditional Chinese.</span></span>|  
  
 <span data-ttu-id="7e4e7-145">**Ausgabealias**</span><span class="sxs-lookup"><span data-stu-id="7e4e7-145">**Output Alias**</span></span>  
 <span data-ttu-id="7e4e7-146">Geben Sie einen Alias für jede Spalte ein.</span><span class="sxs-lookup"><span data-stu-id="7e4e7-146">Type an alias for each output column.</span></span> <span data-ttu-id="7e4e7-147">Der Standard lautet **Copy of** , gefolgt vom Namen der Eingabespalte. Sie können jedoch auch einen eindeutigen, beschreibenden Namen auswählen.</span><span class="sxs-lookup"><span data-stu-id="7e4e7-147">The default is **Copy of** followed by the input column name; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="7e4e7-148">**Konfigurieren der Fehlerausgabe**</span><span class="sxs-lookup"><span data-stu-id="7e4e7-148">**Configure Error Output**</span></span>  
 <span data-ttu-id="7e4e7-149">Im Dialogfeld [Fehlerausgabe konfigurieren](../../2014/integration-services/configure-error-output.md) können Sie für die Transformation verfügbare Optionen zur Fehlerbehandlung angeben.</span><span class="sxs-lookup"><span data-stu-id="7e4e7-149">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling options for this transformation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e4e7-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7e4e7-150">See Also</span></span>  
 [<span data-ttu-id="7e4e7-151">Fehler- und Meldungsreferenz von Integration Services</span><span class="sxs-lookup"><span data-stu-id="7e4e7-151">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
