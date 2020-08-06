---
title: DTAXML-Element (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DTAXML element
ms.assetid: 3d9942ed-8a27-40db-a7c9-808984d914a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9f428cf996bb819ece74c13226fcd5116a19142b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719240"
---
# <a name="dtaxml-element-dta"></a><span data-ttu-id="45888-102">DTAXML-Element (DTA)</span><span class="sxs-lookup"><span data-stu-id="45888-102">DTAXML Element (DTA)</span></span>
  <span data-ttu-id="45888-103">Das Stammelement einer XML-Eingabe- oder -Ausgabedatei des Datenbankoptimierungsratgebers. **DTAXML** enthält alle Elemente, die die vom Datenbankoptimierungsratgeber generierte Optimierungseingabe und -ausgabe beschreiben.</span><span class="sxs-lookup"><span data-stu-id="45888-103">The root element of a Database Engine Tuning Advisor XML input or output file, **DTAXML** contains all elements that describe tuning input and the tuning output that Database Engine Tuning Advisor generates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45888-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="45888-104">Syntax</span></span>  
  
```  
  
<DTAXML   
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"   
    xmlns="https://schemas.microsoft.com/sqlserver/2004/07/dta">  
    ...code removed here...  
</DTAXML>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="45888-105">Elementattribute</span><span class="sxs-lookup"><span data-stu-id="45888-105">Element Attributes</span></span>  
  
|<span data-ttu-id="45888-106">attribute</span><span class="sxs-lookup"><span data-stu-id="45888-106">Attribute</span></span>|<span data-ttu-id="45888-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="45888-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns:xsi`|<span data-ttu-id="45888-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="45888-108">Required.</span></span> <span data-ttu-id="45888-109">Identifiziert den XML-Schemainstanzennamespace.</span><span class="sxs-lookup"><span data-stu-id="45888-109">Identifies the XML Schema Instance namespace.</span></span> <span data-ttu-id="45888-110">Attribute aus diesem Namespace dienen zum Verweisen auf das Schema, das zum Überprüfen der XML-Datei des Datenbankoptimierungsratgebers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="45888-110">Attributes from this namespace are used to reference the schema that is used to validate the Database Engine Tuning Advisor XML file.</span></span><br /><br /> <span data-ttu-id="45888-111">Erforderlicher Wert: [http://www.w3.org/2001/XMLSchema-instance](http://www.w3.org/2001/XMLSchema-instance)</span><span class="sxs-lookup"><span data-stu-id="45888-111">Required value: [http://www.w3.org/2001/XMLSchema-instance](http://www.w3.org/2001/XMLSchema-instance)</span></span>|  
|`xmlns`|<span data-ttu-id="45888-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="45888-112">Required.</span></span> <span data-ttu-id="45888-113">Identifiziert den Namespace des Datenbankoptimierungsratgebers.</span><span class="sxs-lookup"><span data-stu-id="45888-113">Identifies the Database Engine Tuning Advisor namespace.</span></span><br /><br /> <span data-ttu-id="45888-114">Wenn Sie die XML-Datei des Datenbankoptimierungsratgebers mit dem XML-Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]bearbeiten, wird dieser Wert von der F1-Hilfe und der dynamischen Hilfe verwendet, um mögliche Referenzthemen in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="45888-114">If you edit the Database Engine Tuning Advisor XML file using the XML editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], this value is used by F1 Help and Dynamic Help to locate possible reference topics in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span><br /><br /> <span data-ttu-id="45888-115">Erforderlicher Wert:</span><span class="sxs-lookup"><span data-stu-id="45888-115">Required value:</span></span><br /><br /> <span data-ttu-id="45888-116">für das[XML-Schema des Datenbankoptimierungsratgebers](https://go.microsoft.com/fwlink/?LinkId=43100)</span><span class="sxs-lookup"><span data-stu-id="45888-116">[Database Engine Tuning Advisor XML Schema](https://go.microsoft.com/fwlink/?LinkId=43100) Namespace</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="45888-117">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="45888-117">Element Characteristics</span></span>  
  
|<span data-ttu-id="45888-118">Merkmal</span><span class="sxs-lookup"><span data-stu-id="45888-118">Characteristic</span></span>|<span data-ttu-id="45888-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="45888-119">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="45888-120">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="45888-120">**Data type and length**</span></span>|<span data-ttu-id="45888-121">Keine.</span><span class="sxs-lookup"><span data-stu-id="45888-121">None.</span></span>|  
|<span data-ttu-id="45888-122">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="45888-122">**Default value**</span></span>|<span data-ttu-id="45888-123">Keine.</span><span class="sxs-lookup"><span data-stu-id="45888-123">None.</span></span>|  
|<span data-ttu-id="45888-124">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="45888-124">**Occurrence**</span></span>|<span data-ttu-id="45888-125">Einmal pro DTA XML-Datei erforderlich.</span><span class="sxs-lookup"><span data-stu-id="45888-125">Required once per DTA XML file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="45888-126">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="45888-126">Element Relationships</span></span>  
  
|<span data-ttu-id="45888-127">Beziehung</span><span class="sxs-lookup"><span data-stu-id="45888-127">Relationship</span></span>|<span data-ttu-id="45888-128">Elemente</span><span class="sxs-lookup"><span data-stu-id="45888-128">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="45888-129">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="45888-129">**Parent element**</span></span>|<span data-ttu-id="45888-130">Keine</span><span class="sxs-lookup"><span data-stu-id="45888-130">None</span></span>|  
|<span data-ttu-id="45888-131">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="45888-131">**Child elements**</span></span>|[<span data-ttu-id="45888-132">DTAInput-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="45888-132">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)<br /><br /> <span data-ttu-id="45888-133">`DTAOutput`-Element (Weitere Informationen finden Sie unter [Datenbankoptimierungsratgeber XML-Schema](https://schemas.microsoft.com/sqlserver/) )</span><span class="sxs-lookup"><span data-stu-id="45888-133">`DTAOutput` Element (see [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45888-134">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="45888-134">Remarks</span></span>  
 <span data-ttu-id="45888-135">Weitere Informationen zu XML-Namespaces finden Sie unter [Namespaces in an XML Document](https://go.microsoft.com/fwlink/?LinkId=7341) (in Englisch) in der [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="45888-135">For more information about XML namespaces, see [Namespaces in an XML Document](https://go.microsoft.com/fwlink/?LinkId=7341) in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN Library.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45888-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="45888-136">Example</span></span>  
 <span data-ttu-id="45888-137">Beispiele für typische **DTAXML**-Elemente finden Sie unter [Beispiele für XML-Eingabedateien &#40;DTA&#41;](xml-input-file-samples-dta.md).</span><span class="sxs-lookup"><span data-stu-id="45888-137">For examples of typical **DTAXML** elements, see [XML Input File Samples &#40;DTA&#41;](xml-input-file-samples-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45888-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="45888-138">See Also</span></span>  
 <span data-ttu-id="45888-139">[XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;](xml-input-file-reference-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="45888-139">[XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](xml-input-file-reference-database-engine-tuning-advisor.md) </span></span>  
 [<span data-ttu-id="45888-140">Starten und Verwenden des Datenbankoptimierungsratgebers</span><span class="sxs-lookup"><span data-stu-id="45888-140">Start and Use the Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md)  
  
  
