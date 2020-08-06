---
title: Transformation zum Zuordnen der Zeichen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.charactertrans.f1
helpviewer_keywords:
- mutually exclusive mapping [Integration Services]
- mapping data [Integration Services]
- string functions
- Character Map transformation [Integration Services]
ms.assetid: e0f50eb6-b893-400f-bb8c-fb3072cc2620
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b5fc31e1a3500a7a7b023e43a968e70e5b438dec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619244"
---
# <a name="character-map-transformation"></a><span data-ttu-id="b569b-102">Transformation zum Zuordnen der Zeichen</span><span class="sxs-lookup"><span data-stu-id="b569b-102">Character Map Transformation</span></span>
  <span data-ttu-id="b569b-103">Die Transformation zum Zuordnen der Zeichen wendet Zeichenfolgenfunktionen, wie z. B. die Konvertierung von Klein- in Großbuchstaben, auf Zeichendaten an.</span><span class="sxs-lookup"><span data-stu-id="b569b-103">The Character Map transformation applies string functions, such as conversion from lowercase to uppercase, to character data.</span></span> <span data-ttu-id="b569b-104">Diese Transformation betrifft nur Spaltendaten mit einem Zeichenfolgen-Datentyp.</span><span class="sxs-lookup"><span data-stu-id="b569b-104">This transformation operates only on column data with a string data type.</span></span>  
  
 <span data-ttu-id="b569b-105">Die Transformation zum Zuordnen der Zeichen kann Spaltendaten direkt konvertieren oder der Transformationsausgabe eine Spalte hinzufügen und die konvertierten Daten in die neue Spalte einfügen.</span><span class="sxs-lookup"><span data-stu-id="b569b-105">The Character Map transformation can convert column data in place or add a column to the transformation output and put the converted data in the new column.</span></span> <span data-ttu-id="b569b-106">Sie können auf eine Eingabespalte verschiedene Zuordnungsvorgänge anwenden und die Ergebnisse verschiedenen Spalten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b569b-106">You can apply different sets of mapping operations to the same input column and put the results in different columns.</span></span> <span data-ttu-id="b569b-107">Konvertieren Sie z. B. eine Spalte in Groß- und Kleinbuchstaben, und fügen Sie die Ergebnisse zwei unterschiedlichen Spalten hinzu.</span><span class="sxs-lookup"><span data-stu-id="b569b-107">For example, you can convert the same column to uppercase and lowercase and put the results in two different columns.</span></span>  
  
 <span data-ttu-id="b569b-108">Die Zuordnung kann unter bestimmten Umständen das Abschneiden von Daten verursachen.</span><span class="sxs-lookup"><span data-stu-id="b569b-108">Mapping can, under some circumstances, cause data to be truncated.</span></span> <span data-ttu-id="b569b-109">Beispielsweise, wenn Einzelbytezeichen Zeichen mit einer Multibytedarstellung zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="b569b-109">For example, truncation can occur when single-byte characters are mapped to characters with a multibyte representation.</span></span> <span data-ttu-id="b569b-110">Die Transformation zum Zuordnen der Zeichen schließt eine Fehlerausgabe ein, mit der abgeschnittene Daten an eine separate Ausgabe weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="b569b-110">The Character Map transformation includes an error output, which can be used to direct truncated data to separate output.</span></span> <span data-ttu-id="b569b-111">Weitere Informationen finden Sie unter [Fehlerbehandlung in Daten](../error-handling-in-data.md).</span><span class="sxs-lookup"><span data-stu-id="b569b-111">For more information, see [Error Handling in Data](../error-handling-in-data.md).</span></span>  
  
 <span data-ttu-id="b569b-112">Diese Transformation weist eine Eingabe, eine Ausgabe und eine Fehlerausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="b569b-112">This transformation has one input, one output, and one error output.</span></span>  
  
## <a name="mapping-operations"></a><span data-ttu-id="b569b-113">Zuordnungsvorgänge</span><span class="sxs-lookup"><span data-stu-id="b569b-113">Mapping Operations</span></span>  
 <span data-ttu-id="b569b-114">In der folgenden Tabelle sind die Zuordnungsvorgänge beschrieben, die von der Transformation zum Zuordnen der Zeichen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="b569b-114">The following table describes the mapping operations that the Character Map transformation supports.</span></span>  
  
|<span data-ttu-id="b569b-115">Vorgang</span><span class="sxs-lookup"><span data-stu-id="b569b-115">Operation</span></span>|<span data-ttu-id="b569b-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b569b-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b569b-117">Byteumkehrung</span><span class="sxs-lookup"><span data-stu-id="b569b-117">Byte reversal</span></span>|<span data-ttu-id="b569b-118">Kehrt die Bytereihenfolge um.</span><span class="sxs-lookup"><span data-stu-id="b569b-118">Reverses byte order.</span></span>|  
|<span data-ttu-id="b569b-119">Normale Breite</span><span class="sxs-lookup"><span data-stu-id="b569b-119">Full width</span></span>|<span data-ttu-id="b569b-120">Ordnet Zeichen halber Breite Zeichen normaler Breite zu.</span><span class="sxs-lookup"><span data-stu-id="b569b-120">Maps half-width characters to full-width characters.</span></span>|  
|<span data-ttu-id="b569b-121">Halbe Breite</span><span class="sxs-lookup"><span data-stu-id="b569b-121">Half width</span></span>|<span data-ttu-id="b569b-122">Ordnet Zeichen normaler Breite Zeichen halber Breite zu.</span><span class="sxs-lookup"><span data-stu-id="b569b-122">Maps full-width characters to half-width characters.</span></span>|  
|<span data-ttu-id="b569b-123">Hiragana</span><span class="sxs-lookup"><span data-stu-id="b569b-123">Hiragana</span></span>|<span data-ttu-id="b569b-124">Ordnet Katakanazeichen Hiraganazeichen zu.</span><span class="sxs-lookup"><span data-stu-id="b569b-124">Maps katakana characters to hiragana characters.</span></span>|  
|<span data-ttu-id="b569b-125">Katakana</span><span class="sxs-lookup"><span data-stu-id="b569b-125">Katakana</span></span>|<span data-ttu-id="b569b-126">Ordnet Hiraganazeichen Katakanazeichen zu.</span><span class="sxs-lookup"><span data-stu-id="b569b-126">Maps hiragana characters to katakana characters.</span></span>|  
|<span data-ttu-id="b569b-127">Linguistische Schreibweise</span><span class="sxs-lookup"><span data-stu-id="b569b-127">Linguistic casing</span></span>|<span data-ttu-id="b569b-128">Wendet die linguistische Schreibweise anstelle der Systemregeln an.</span><span class="sxs-lookup"><span data-stu-id="b569b-128">Applies linguistic casing instead of the system rules.</span></span> <span data-ttu-id="b569b-129">Die linguistische Schreibweise bezieht sich auf die Funktionalität der Win32 API für die einfache Unicode-Schreibweisenzuordnung von Türkisch und anderen Gebietsschemas.</span><span class="sxs-lookup"><span data-stu-id="b569b-129">Linguistic casing refers to functionality provided by the Win32 API for Unicode simple case mapping of Turkic and other locales.</span></span>|  
|<span data-ttu-id="b569b-130">Kleinbuchstaben</span><span class="sxs-lookup"><span data-stu-id="b569b-130">Lowercase</span></span>|<span data-ttu-id="b569b-131">Konvertiert Zeichen in Kleinbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="b569b-131">Converts characters to lowercase.</span></span>|  
|<span data-ttu-id="b569b-132">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="b569b-132">Simplified Chinese</span></span>|<span data-ttu-id="b569b-133">Ordnet Zeichen in traditionellem Chinesisch Zeichen in vereinfachtem Chinesisch zu.</span><span class="sxs-lookup"><span data-stu-id="b569b-133">Maps traditional Chinese characters to simplified Chinese characters.</span></span>|  
|<span data-ttu-id="b569b-134">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="b569b-134">Traditional Chinese</span></span>|<span data-ttu-id="b569b-135">Ordnet Zeichen in vereinfachtem Chinesisch Zeichen in traditionellem Chinesisch zu.</span><span class="sxs-lookup"><span data-stu-id="b569b-135">Maps simplified Chinese characters to traditional Chinese characters.</span></span>|  
|<span data-ttu-id="b569b-136">Großbuchstaben</span><span class="sxs-lookup"><span data-stu-id="b569b-136">Uppercase</span></span>|<span data-ttu-id="b569b-137">Konvertiert Zeichen in Großbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="b569b-137">Converts characters to uppercase.</span></span>|  
  
## <a name="mutually-exclusive-mapping-operations"></a><span data-ttu-id="b569b-138">Zuordnungsvorgänge, die sich gegenseitig ausschließen</span><span class="sxs-lookup"><span data-stu-id="b569b-138">Mutually Exclusive Mapping Operations</span></span>  
 <span data-ttu-id="b569b-139">In einer Transformation können mehrere Vorgänge ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b569b-139">More than one operation can be performed in a transformation.</span></span> <span data-ttu-id="b569b-140">Manche Zuordnungsvorgänge schließen sich jedoch gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="b569b-140">However, some mapping operations are mutually exclusive.</span></span> <span data-ttu-id="b569b-141">In der folgenden Tabelle sind die Einschränkungen aufgeführt, die bei der Verwendung mehrerer Vorgänge in derselben Spalte gelten.</span><span class="sxs-lookup"><span data-stu-id="b569b-141">The following table lists restrictions that apply when you use multiple operations on the same column.</span></span> <span data-ttu-id="b569b-142">Vorgänge in den Spalten Vorgang A und Vorgang B schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="b569b-142">Operations in the columns Operation A and Operation B are mutually exclusive.</span></span>  
  
|<span data-ttu-id="b569b-143">Vorgang A</span><span class="sxs-lookup"><span data-stu-id="b569b-143">Operation A</span></span>|<span data-ttu-id="b569b-144">Vorgang B</span><span class="sxs-lookup"><span data-stu-id="b569b-144">Operation B</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="b569b-145">Kleinbuchstaben</span><span class="sxs-lookup"><span data-stu-id="b569b-145">Lowercase</span></span>|<span data-ttu-id="b569b-146">Großbuchstaben</span><span class="sxs-lookup"><span data-stu-id="b569b-146">Uppercase</span></span>|  
|<span data-ttu-id="b569b-147">Hiragana</span><span class="sxs-lookup"><span data-stu-id="b569b-147">Hiragana</span></span>|<span data-ttu-id="b569b-148">Katakana</span><span class="sxs-lookup"><span data-stu-id="b569b-148">Katakana</span></span>|  
|<span data-ttu-id="b569b-149">Halbe Breite</span><span class="sxs-lookup"><span data-stu-id="b569b-149">Half width</span></span>|<span data-ttu-id="b569b-150">Normale Breite</span><span class="sxs-lookup"><span data-stu-id="b569b-150">Full width</span></span>|  
|<span data-ttu-id="b569b-151">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="b569b-151">Traditional Chinese</span></span>|<span data-ttu-id="b569b-152">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="b569b-152">Simplified Chinese</span></span>|  
|<span data-ttu-id="b569b-153">Kleinbuchstaben</span><span class="sxs-lookup"><span data-stu-id="b569b-153">Lowercase</span></span>|<span data-ttu-id="b569b-154">Hiragana, Katakana, halbe Breite, normale Breite</span><span class="sxs-lookup"><span data-stu-id="b569b-154">Hiragana, katakana, half width, full width</span></span>|  
|<span data-ttu-id="b569b-155">Großbuchstaben</span><span class="sxs-lookup"><span data-stu-id="b569b-155">Uppercase</span></span>|<span data-ttu-id="b569b-156">Hiragana, Katakana, halbe Breite, normale Breite</span><span class="sxs-lookup"><span data-stu-id="b569b-156">Hiragana, katakana, half width, full width</span></span>|  
  
## <a name="configuration-of-the-character-map-transformation"></a><span data-ttu-id="b569b-157">Konfiguration der Transformation zum Zuordnen der Zeichen</span><span class="sxs-lookup"><span data-stu-id="b569b-157">Configuration of the Character Map Transformation</span></span>  
 <span data-ttu-id="b569b-158">Es gibt folgende Möglichkeiten, um die Transformation zum Zuordnen der Zeichen zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="b569b-158">You configure the Character Map transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="b569b-159">Geben Sie die zu konvertierenden Spalten an.</span><span class="sxs-lookup"><span data-stu-id="b569b-159">Specify the columns to convert.</span></span>  
  
-   <span data-ttu-id="b569b-160">Geben Sie die auf jede Spalte anzuwendenden Vorgänge an.</span><span class="sxs-lookup"><span data-stu-id="b569b-160">Specify the operations to apply to each column.</span></span>  
  
 <span data-ttu-id="b569b-161">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="b569b-161">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="b569b-162">Weitere Informationen zu den Eigenschaften, die Sie im Dialogfeld **Transformations-Editor für Zeichenzuordnung** festlegen können, finden Sie unter [Character Map Transformation Editor](../../character-map-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="b569b-162">For more information about the properties that you can set in the **Character Map Transformation Editor** dialog box, see [Character Map Transformation Editor](../../character-map-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="b569b-163">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="b569b-163">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="b569b-164">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="b569b-164">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="b569b-165">Common Properties</span><span class="sxs-lookup"><span data-stu-id="b569b-165">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="b569b-166">Benutzerdefinierte Eigenschaften von Transformationen</span><span class="sxs-lookup"><span data-stu-id="b569b-166">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="b569b-167">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zum Festlegen von Eigenschaften anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="b569b-167">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="b569b-168">Festlegen der Eigenschaften einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="b569b-168">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
-   [<span data-ttu-id="b569b-169">Sortieren von Daten für die Transformationen für Zusammenführen und Zusammenführungsjoin</span><span class="sxs-lookup"><span data-stu-id="b569b-169">Sort Data for the Merge and Merge Join Transformations</span></span>](sort-data-for-the-merge-and-merge-join-transformations.md)  
  
  
