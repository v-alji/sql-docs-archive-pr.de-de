---
title: Benutzerdefinierte Eigenschaften der Flatfile | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7f2caeab-784c-4b0c-9b3e-6a88d1ccdbf9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b906e9268bf3a74ffcf5661953397ad7a24b77a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726101"
---
# <a name="flat-file-custom-properties"></a><span data-ttu-id="32254-102">Benutzerdefinierte Eigenschaften der Flatfile</span><span class="sxs-lookup"><span data-stu-id="32254-102">Flat File Custom Properties</span></span>
  <span data-ttu-id="32254-103">**Benutzerdefinierte Eigenschaften von Quellen**</span><span class="sxs-lookup"><span data-stu-id="32254-103">**Source Custom Properties**</span></span>  
  
 <span data-ttu-id="32254-104">Die Flatfilequelle verfügt sowohl über benutzerdefinierte Eigenschaften als auch über die Eigenschaften, die allen Datenflusskomponenten gemeinsam sind.</span><span class="sxs-lookup"><span data-stu-id="32254-104">The Flat File source has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="32254-105">In der folgenden Tabelle werden die benutzerdefinierten Eigenschaften der Flatfilequelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="32254-105">The following table describes the custom properties of the Flat File source.</span></span> <span data-ttu-id="32254-106">Alle Eigenschaften weisen Lese-/Schreibzugriff auf.</span><span class="sxs-lookup"><span data-stu-id="32254-106">All properties are read/write.</span></span>  
  
|<span data-ttu-id="32254-107">Eigenschaftenname</span><span class="sxs-lookup"><span data-stu-id="32254-107">Property name</span></span>|<span data-ttu-id="32254-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="32254-108">Data Type</span></span>|<span data-ttu-id="32254-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="32254-109">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="32254-110">FileNameColumnName</span><span class="sxs-lookup"><span data-stu-id="32254-110">FileNameColumnName</span></span>|<span data-ttu-id="32254-111">String</span><span class="sxs-lookup"><span data-stu-id="32254-111">String</span></span>|<span data-ttu-id="32254-112">Der Name einer Ausgabespalte, die den Dateinamen enthält.</span><span class="sxs-lookup"><span data-stu-id="32254-112">The name of an output column that contains the file name.</span></span> <span data-ttu-id="32254-113">Wenn kein Name angegeben wird, wird keine Ausgabespalte generiert, die den Dateinamen enthält.</span><span class="sxs-lookup"><span data-stu-id="32254-113">If no name is specified, no output column containing the file name will be generated.</span></span><br /><br /> <span data-ttu-id="32254-114">Hinweis: Diese Eigenschaft ist nicht im **Quellen-Editor für Flatfiles**verfügbar, kann jedoch mit dem Dialogfeld **Erweiterter Editor**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="32254-114">Note: This property is not available in the **Flat File Source Editor**, but can be set by using the **Advanced Editor**.</span></span>|  
|<span data-ttu-id="32254-115">RetainNulls</span><span class="sxs-lookup"><span data-stu-id="32254-115">RetainNulls</span></span>|<span data-ttu-id="32254-116">Boolean</span><span class="sxs-lookup"><span data-stu-id="32254-116">Boolean</span></span>|<span data-ttu-id="32254-117">Ein Wert, der angibt, ob NULL-Werte aus der Quelldatei als NULL-Werte beibehalten werden sollen, wenn die Daten von der Data Transformation-Pipeline-Engine verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="32254-117">A value that specifies whether to retain Null values from the source file as Null values when the data is processed by the Data Transformation Pipeline engine.</span></span> <span data-ttu-id="32254-118">Der Standardwert dieser Eigenschaft ist `False`.</span><span class="sxs-lookup"><span data-stu-id="32254-118">The default value of this property is `False`.</span></span>|  
  
 <span data-ttu-id="32254-119">Die Ausgabe der Flatfilequelle verfügt nicht über benutzerdefinierte Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="32254-119">The output of the Flat File source has no custom properties.</span></span>  
  
 <span data-ttu-id="32254-120">Die folgende Tabelle beschreibt die benutzerdefinierten Eigenschaften der Ausgabespalten der Flatfilequelle.</span><span class="sxs-lookup"><span data-stu-id="32254-120">The following table describes the custom properties of the output columns of the Flat File source.</span></span> <span data-ttu-id="32254-121">Alle Eigenschaften weisen Lese-/Schreibzugriff auf.</span><span class="sxs-lookup"><span data-stu-id="32254-121">All properties are read/write.</span></span>  
  
|<span data-ttu-id="32254-122">Eigenschaftenname</span><span class="sxs-lookup"><span data-stu-id="32254-122">Property name</span></span>|<span data-ttu-id="32254-123">Datentyp</span><span class="sxs-lookup"><span data-stu-id="32254-123">Data Type</span></span>|<span data-ttu-id="32254-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="32254-124">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="32254-125">FastParse</span><span class="sxs-lookup"><span data-stu-id="32254-125">FastParse</span></span>|<span data-ttu-id="32254-126">Boolean</span><span class="sxs-lookup"><span data-stu-id="32254-126">Boolean</span></span>|<span data-ttu-id="32254-127">Ein Wert, der angibt, ob die Spalte die schnelleren gebietsschemaneutralen Analyseroutinen von DTS oder die gebietsschemabezogenen Standardanalyseroutinen verwendet.</span><span class="sxs-lookup"><span data-stu-id="32254-127">A value that indicates whether the column uses the quicker, but locale-insensitive, fast parsing routines that DTS provides or the locale-sensitive standard parsing routines.</span></span> <span data-ttu-id="32254-128">Weitere Informationen finden Sie unter [Fast Parse](../fast-parse.md) und [Standard Parse](../standard-parse.md).</span><span class="sxs-lookup"><span data-stu-id="32254-128">For more information, see [Fast Parse](../fast-parse.md) and [Standard Parse](../standard-parse.md).</span></span> <span data-ttu-id="32254-129">Der Standardwert dieser Eigenschaft ist `False`.</span><span class="sxs-lookup"><span data-stu-id="32254-129">The default value of this property is `False`.</span></span><br /><br /> <span data-ttu-id="32254-130">Hinweis: Diese Eigenschaft ist nicht im **Quellen-Editor für Flatfiles**verfügbar, kann jedoch mit dem Dialogfeld **Erweiterter Editor**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="32254-130">Note: This property is not available in the **Flat File Source Editor**, but can be set by using the **Advanced Editor**.</span></span>|  
  
 <span data-ttu-id="32254-131">Weitere Informationen finden Sie unter [Flat File Source](flat-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="32254-131">For more information, see [Flat File Source](flat-file-source.md).</span></span>  
  
 <span data-ttu-id="32254-132">**Benutzerdefinierte Eigenschaften von Zielen**</span><span class="sxs-lookup"><span data-stu-id="32254-132">**Destination Custom Properties**</span></span>  
  
 <span data-ttu-id="32254-133">Das Flatfileziel verfügt sowohl über benutzerdefinierte Eigenschaften als auch über die Eigenschaften, die allen Datenflusskomponenten gemeinsam sind.</span><span class="sxs-lookup"><span data-stu-id="32254-133">The Flat File destination has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="32254-134">Die folgende Tabelle beschreibt die benutzerdefinierten Eigenschaften des Flatfileziels.</span><span class="sxs-lookup"><span data-stu-id="32254-134">The following table describes the custom properties of the Flat File destination.</span></span> <span data-ttu-id="32254-135">Alle Eigenschaften weisen Lese-/Schreibzugriff auf.</span><span class="sxs-lookup"><span data-stu-id="32254-135">All properties are read/write.</span></span>  
  
|<span data-ttu-id="32254-136">Eigenschaftenname</span><span class="sxs-lookup"><span data-stu-id="32254-136">Property name</span></span>|<span data-ttu-id="32254-137">Datentyp</span><span class="sxs-lookup"><span data-stu-id="32254-137">Data Type</span></span>|<span data-ttu-id="32254-138">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="32254-138">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="32254-139">Header</span><span class="sxs-lookup"><span data-stu-id="32254-139">Header</span></span>|<span data-ttu-id="32254-140">String</span><span class="sxs-lookup"><span data-stu-id="32254-140">String</span></span>|<span data-ttu-id="32254-141">Ein Textblock, der in die Datei eingefügt wird, bevor Daten geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="32254-141">A block of text that is inserted in the file before any data is written.</span></span><br /><br /> <span data-ttu-id="32254-142">Der Wert dieser Eigenschaft kann mithilfe eines Eigenschaftsausdrucks angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="32254-142">The value of this property can be specified by using a property expression.</span></span>|  
|<span data-ttu-id="32254-143">Overwrite</span><span class="sxs-lookup"><span data-stu-id="32254-143">Overwrite</span></span>|<span data-ttu-id="32254-144">Boolean</span><span class="sxs-lookup"><span data-stu-id="32254-144">Boolean</span></span>|<span data-ttu-id="32254-145">Ein Wert, der angibt, ob eine vorhandene Zieldatei mit demselben Namen überschrieben werden soll oder ob an diese Datei angehängt werden soll.</span><span class="sxs-lookup"><span data-stu-id="32254-145">A value that specifies whether to overwrite or append to an existing destination file that has the same name.</span></span> <span data-ttu-id="32254-146">Der Standardwert dieser Eigenschaft ist `True`.</span><span class="sxs-lookup"><span data-stu-id="32254-146">The default value of this property is `True`.</span></span>|  
  
 <span data-ttu-id="32254-147">Die Eingabe und die Eingabespalten des Flatfileziels verfügen nicht über benutzerdefinierte Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="32254-147">The input and the input columns of the Flat File destination have no custom properties.</span></span>  
  
 <span data-ttu-id="32254-148">Weitere Informationen finden Sie unter [Flat File Destination](flat-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="32254-148">For more information, see [Flat File Destination](flat-file-destination.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32254-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="32254-149">See Also</span></span>  
 [<span data-ttu-id="32254-150">Common Properties</span><span class="sxs-lookup"><span data-stu-id="32254-150">Common Properties</span></span>](../common-properties.md)  
  
  
