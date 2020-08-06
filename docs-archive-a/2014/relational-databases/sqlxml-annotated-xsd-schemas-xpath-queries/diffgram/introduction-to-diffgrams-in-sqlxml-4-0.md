---
title: Einführung in DiffGrams in SQLXML 4,0 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotations [SQLXML]
- DiffGrams [SQLXML], about DiffGrams
ms.assetid: 1902d67f-baf3-46e6-a36c-b24b5ba6f8ea
author: rothja
ms.author: jroth
ms.openlocfilehash: e57d87d064ace47247f342ed002b162b920e627f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618590"
---
# <a name="introduction-to-diffgrams-in-sqlxml-40"></a><span data-ttu-id="ade62-102">Einführung in DiffGrams für SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="ade62-102">Introduction to DiffGrams in SQLXML 4.0</span></span>
  <span data-ttu-id="ade62-103">Dieses Thema bietet eine kurze Einführung in DiffGrams.</span><span class="sxs-lookup"><span data-stu-id="ade62-103">This topic provides a brief introduction to DiffGrams.</span></span>  
  
## <a name="diffgram-format"></a><span data-ttu-id="ade62-104">DiffGram-Format</span><span class="sxs-lookup"><span data-stu-id="ade62-104">DiffGram Format</span></span>  
 <span data-ttu-id="ade62-105">Das allgemeine DiffGram-Format sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="ade62-105">This is the general DiffGram format:</span></span>  
  
```  
<?xml version="1.0"?>  
<diffgr:diffgram   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"  
         xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1"  
         xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
   <DataInstance>  
      ...  
   </DataInstance>  
   [<diffgr:before>  
        ...  
   </diffgr:before>]  
  
   [<diffgr:errors>  
        ...  
   </diffgr:errors>]  
</diffgr:diffgram>  
```  
  
 <span data-ttu-id="ade62-106">Das DiffGram-Format besteht aus den folgenden Blöcken:</span><span class="sxs-lookup"><span data-stu-id="ade62-106">The DiffGram format consists of these blocks:</span></span>  
  
 **\<DataInstance>**  
 <span data-ttu-id="ade62-107">Der Name dieses Elements, **DataInstance**, wird zur Erläuterung in dieser Dokumentation verwendet.</span><span class="sxs-lookup"><span data-stu-id="ade62-107">The name of this element, **DataInstance**, is used for explanation purposes in this documentation.</span></span> <span data-ttu-id="ade62-108">Wenn beispielsweise das DiffGram-Objekt aus einem Dataset im .NET Framework generiert wurde, wird der Wert der **Name** -Eigenschaft des Datasets als Name dieses Elements verwendet.</span><span class="sxs-lookup"><span data-stu-id="ade62-108">For example, if the DiffGram were generated from a dataset in the .NET Framework, the value of the **Name** property of the dataset would be used as the name of this element.</span></span> <span data-ttu-id="ade62-109">Dieser Block enthält nach der Änderung alle relevanten Daten, möglicherweise auch die Daten, die nicht geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="ade62-109">This block contains all relevant data after the change, possibly including data that has not been modified.</span></span> <span data-ttu-id="ade62-110">Die DiffGram-Verarbeitungslogik ignoriert die Elemente in diesem Block, für die das **diffgr: hasChanges** -Attribut nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="ade62-110">The DiffGram processing logic ignores the elements in this block for which the **diffgr:hasChanges** attribute is not specified.</span></span>  
  
 **\<diffgr:before>**  
 <span data-ttu-id="ade62-111">Dieser optionale Block enthält die ursprünglichen Datensatzinstanzen (Elemente), die aktualisiert oder gelöscht werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ade62-111">This optional block contains the original record instances (elements) that must be updated or deleted.</span></span> <span data-ttu-id="ade62-112">Alle Datenbanktabellen, die vom DiffGram geändert (aktualisiert oder gelöscht) werden, müssen im-Block als Elemente der obersten Ebene angezeigt werden **\<before>** .</span><span class="sxs-lookup"><span data-stu-id="ade62-112">All the database tables being modified (updated or deleted) by the DiffGram must appear as top-level elements in the **\<before>** block.</span></span>  
  
 **\<diffgr:errors>**  
 <span data-ttu-id="ade62-113">Dieser optionale Block wird von der DiffGram-Verarbeitungslogik ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ade62-113">This optional block is ignored by the DiffGram processing logic.</span></span>  
  
## <a name="diffgram-annotations"></a><span data-ttu-id="ade62-114">DiffGram-Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="ade62-114">DiffGram Annotations</span></span>  
 <span data-ttu-id="ade62-115">Diese Anmerkungen werden im DiffGram-Namespace **"urn: Schemas-Microsoft-com: XML-DiffGram-01"** definiert:</span><span class="sxs-lookup"><span data-stu-id="ade62-115">These annotations are defined in the DiffGram namespace **"urn:schemas-microsoft-com:xml-diffgram-01"**:</span></span>  
  
 <span data-ttu-id="ade62-116">**ID**</span><span class="sxs-lookup"><span data-stu-id="ade62-116">**id**</span></span>  
 <span data-ttu-id="ade62-117">Dieses Attribut wird verwendet, um die Elemente in den **\<before>** -und-Blöcken zu koppeln **\<DataInstance>** .</span><span class="sxs-lookup"><span data-stu-id="ade62-117">This attribute is used to pair the elements in the **\<before>** and the **\<DataInstance>** blocks.</span></span>  
  
 <span data-ttu-id="ade62-118">**hasChanges**</span><span class="sxs-lookup"><span data-stu-id="ade62-118">**hasChanges**</span></span>  
 <span data-ttu-id="ade62-119">Bei einem INSERT-oder Update-Vorgang muss das DiffGram-Attribut dieses Attribut mit dem **eingefügten** oder **geänderten**Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="ade62-119">For an insert or an update operation, the DiffGram must specify this attribute with the value **inserted** or **modified**.</span></span> <span data-ttu-id="ade62-120">Wenn dieses Attribut nicht vorhanden ist, wird das entsprechende Element in der **\<DataInstance>** von der Verarbeitungslogik ignoriert, und es werden keine Updates durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="ade62-120">If this attribute is not present, the corresponding element in the **\<DataInstance>** is ignored by the processing logic and no updates are performed.</span></span> <span data-ttu-id="ade62-121">Arbeitsbeispiele finden Sie unter [DiffGram-Beispiele &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="ade62-121">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="ade62-122">**parentID**</span><span class="sxs-lookup"><span data-stu-id="ade62-122">**parentID**</span></span>  
 <span data-ttu-id="ade62-123">Mit diesem Attribut werden Über-/Unterordnungsbeziehungen unter den Elementen des DiffGrams angegeben.</span><span class="sxs-lookup"><span data-stu-id="ade62-123">This attribute is used to specify parent-child relationships among the elements in the DiffGram.</span></span> <span data-ttu-id="ade62-124">Dieses Attribut wird nur im- \<before> Block angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ade62-124">This attribute appears only in the \<before> block.</span></span> <span data-ttu-id="ade62-125">Es wird von SQLXML beim Übernehmen von Updates genutzt.</span><span class="sxs-lookup"><span data-stu-id="ade62-125">It is used by SQLXML when applying updates.</span></span> <span data-ttu-id="ade62-126">Anhand der Über-/Unterordnungsbeziehungen wird die Reihenfolge bestimmt, in der die Elemente des DiffGrams verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="ade62-126">The parent-child relationship is used in determining the order in which the elements in the DiffGram are processed.</span></span>  
  
## <a name="understanding-the-diffgram-processing-logic"></a><span data-ttu-id="ade62-127">Grundlegendes zur DiffGram-Verarbeitungslogik</span><span class="sxs-lookup"><span data-stu-id="ade62-127">Understanding the DiffGram Processing Logic</span></span>  
 <span data-ttu-id="ade62-128">Die DiffGram-Verarbeitungslogik verwendet bestimmte Regeln, um zu bestimmen, ob es sich bei einem Vorgang um einen Einfüge-, Aktualisieren- oder Löschvorgang handelt.</span><span class="sxs-lookup"><span data-stu-id="ade62-128">The DiffGram processing logic uses certain rules to determine whether an operation is an insert, update, or delete operation.</span></span> <span data-ttu-id="ade62-129">Diese Regeln werden in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ade62-129">These rules are described in the following table.</span></span>  
  
|<span data-ttu-id="ade62-130">Vorgang</span><span class="sxs-lookup"><span data-stu-id="ade62-130">Operation</span></span>|<span data-ttu-id="ade62-131">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ade62-131">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ade62-132">Insert</span><span class="sxs-lookup"><span data-stu-id="ade62-132">Insert</span></span>|<span data-ttu-id="ade62-133">Ein DiffGram zeigt einen Einfügevorgang an, wenn ein Element im- **\<DataInstance>** Block, jedoch nicht im entsprechenden **\<before>** -Block angezeigt wird, und das **diffgr: hasChanges** -Attribut (**diffgr: hasChanges = eingefügt**) für das-Element angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ade62-133">A DiffGram indicates an insert operation when an element appears in the **\<DataInstance>** block but not in the corresponding **\<before>** block, and the **diffgr:hasChanges** attribute is specified (**diffgr:hasChanges=inserted**) on the element.</span></span> <span data-ttu-id="ade62-134">In diesem Fall fügt das DiffGram die Daten Satz Instanz, die im-Block angegeben ist, **\<DataInstance>** in die Datenbank ein.</span><span class="sxs-lookup"><span data-stu-id="ade62-134">In this case, the DiffGram inserts the record instance that is specified in the **\<DataInstance>** block into the database.</span></span><br /><br /> <span data-ttu-id="ade62-135">Wenn das **diffgr: hasChanges** -Attribut nicht angegeben wird, wird das-Element von der Verarbeitungslogik ignoriert, und es wird kein INSERT-Vorgang ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ade62-135">If the **diffgr:hasChanges** attribute is not specified, the element is ignored by the processing logic and no insert is performed.</span></span> <span data-ttu-id="ade62-136">Arbeitsbeispiele finden Sie unter [DiffGram-Beispiele &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="ade62-136">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span>|  
|<span data-ttu-id="ade62-137">Aktualisieren</span><span class="sxs-lookup"><span data-stu-id="ade62-137">Update</span></span>|<span data-ttu-id="ade62-138">Das DiffGram zeigt einen Update Vorgang an, wenn ein Element im- \<before> Block vorhanden ist, für das ein entsprechendes-Element im-Block vorhanden ist (d. **\<DataInstance>** h. beide-Elemente verfügen über ein **diffgr: ID** -Attribut mit demselben Wert) und das **diffgr: hasChanges** -Attribut mit dem Wert, der für das-Element im-Block **geändert** wurde **\<DataInstance>** .</span><span class="sxs-lookup"><span data-stu-id="ade62-138">The DiffGram indicates an update operation when there is an element in the \<before> block for which there is a corresponding element in the **\<DataInstance>** block (that is, both elements have a **diffgr:id** attribute with same value) and the **diffgr:hasChanges** attribute is specified with the value **modified** on the element in the **\<DataInstance>** block.</span></span><br /><br /> <span data-ttu-id="ade62-139">Wenn das **diffgr: hasChanges** -Attribut für das-Element im-Block nicht angegeben wird **\<DataInstance>** , wird von der Verarbeitungslogik ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ade62-139">If the **diffgr:hasChanges** attribute is not specified on the element in the **\<DataInstance>** block, an error is returned by the processing logic.</span></span> <span data-ttu-id="ade62-140">Arbeitsbeispiele finden Sie unter [DiffGram-Beispiele &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="ade62-140">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span><br /><br /> <span data-ttu-id="ade62-141">Wenn **diffgr: parameted im-** Block angegeben wird **\<before>** , wird die über-/Unterordnungsbeziehung der Elemente, die von der **parameentid** angegeben werden, verwendet, um die Reihenfolge zu bestimmen, in der die Datensätze aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="ade62-141">If **diffgr:parentID** is specified in the **\<before>** block, the parent-child relationship of elements that are specified by **parentID** are used in determining the order in which records are updated.</span></span>|  
|<span data-ttu-id="ade62-142">Löschen</span><span class="sxs-lookup"><span data-stu-id="ade62-142">Delete</span></span>|<span data-ttu-id="ade62-143">Ein DiffGram gibt einen Löschvorgang an, wenn ein Element im- **\<before>** Block, jedoch nicht im entsprechenden-Block angezeigt wird **\<DataInstance>** .</span><span class="sxs-lookup"><span data-stu-id="ade62-143">A DiffGram indicates a delete operation when an element appears in the **\<before>** block but not in the corresponding **\<DataInstance>** block.</span></span> <span data-ttu-id="ade62-144">In diesem Fall löscht das DiffGram die Daten Satz Instanz, die im- **\<before>** Block aus der Datenbank angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ade62-144">In this case, the DiffGram deletes the record instance that is specified in the **\<before>** block from the database.</span></span> <span data-ttu-id="ade62-145">Arbeitsbeispiele finden Sie unter [DiffGram-Beispiele &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="ade62-145">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span><br /><br /> <span data-ttu-id="ade62-146">Wenn **diffgr: parameted im-** Block angegeben wird **\<before>** , wird die über-/Unterordnungsbeziehung der Elemente, die von der **parameentid** angegeben werden, verwendet, um die Reihenfolge zu bestimmen, in der Datensätze gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="ade62-146">If **diffgr:parentID** is specified in the **\<before>** block, the parent-child relationship of elements that are specified by **parentID** are used in determining the order in which records are deleted.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="ade62-147">DiffGrams können keine Parameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="ade62-147">Parameters cannot be passed to DiffGrams.</span></span>  
  
  
