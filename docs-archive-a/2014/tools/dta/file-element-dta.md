---
title: File-Element (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- File element
ms.assetid: 73dce835-9a80-4aef-8e0f-9dcf07dd5b80
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0eeb2bdcc9513ca6283447daca63c8bbc4fa1726
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720662"
---
# <a name="file-element-dta"></a><span data-ttu-id="159ab-102">File-Element (DTA)</span><span class="sxs-lookup"><span data-stu-id="159ab-102">File Element (DTA)</span></span>
  <span data-ttu-id="159ab-103">Gibt die Arbeitsauslastungsdatei an.</span><span class="sxs-lookup"><span data-stu-id="159ab-103">Specifies the workload file.</span></span> <span data-ttu-id="159ab-104">Die Arbeitsauslastung besteht aus einer Reihe von [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen, die für eine oder mehrere Datenbanken ausgeführt werden, die Sie optimieren möchten.</span><span class="sxs-lookup"><span data-stu-id="159ab-104">A workload is a set of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that execute against a database or databases that you want to tune.</span></span> <span data-ttu-id="159ab-105">Arbeitsauslastungsdateien können [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skripts (SQL) oder Ablaufverfolgungsdateien (TRC) sein.</span><span class="sxs-lookup"><span data-stu-id="159ab-105">Workload files can be [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts (.sql) or trace files (.trc).</span></span> <span data-ttu-id="159ab-106">Weitere Informationen finden Sie unter [Starten und Verwenden des Datenbankoptimierungsratgebers](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="159ab-106">For more information, see [Start and Use the Database Engine Tuning Advisor](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="159ab-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="159ab-107">Syntax</span></span>  
  
```  
  
<DTAInput>  
  <Server>...</Server>  
  <Workload>  
    <File>...</File>  
  </Workload>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="159ab-108">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="159ab-108">Element Characteristics</span></span>  
  
|<span data-ttu-id="159ab-109">Merkmal</span><span class="sxs-lookup"><span data-stu-id="159ab-109">Characteristic</span></span>|<span data-ttu-id="159ab-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="159ab-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="159ab-111">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="159ab-111">**Data type and length**</span></span>|<span data-ttu-id="159ab-112">Mit dem `string`-Datentyp geben Sie den Verzeichnispfad zu der Arbeitsauslastungsdatei an.</span><span class="sxs-lookup"><span data-stu-id="159ab-112">Use the `string` data type to specify the directory path to your workload file.</span></span> <span data-ttu-id="159ab-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="159ab-113">For example:</span></span><br /><br /> `<File>C:\Tuning\tun.sql</File>`<br /><br /> <span data-ttu-id="159ab-114">Der Grenzwert für die Länge wird vom Server erzwungen.</span><span class="sxs-lookup"><span data-stu-id="159ab-114">Length limit is enforced by the server.</span></span>|  
|<span data-ttu-id="159ab-115">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="159ab-115">**Default value**</span></span>|<span data-ttu-id="159ab-116">Keine.</span><span class="sxs-lookup"><span data-stu-id="159ab-116">None.</span></span>|  
|<span data-ttu-id="159ab-117">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="159ab-117">**Occurrence**</span></span>|<span data-ttu-id="159ab-118">Einmalig erforderlich, wenn kein anderer Arbeitsauslastungstyp angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="159ab-118">Required once if no other type of workload is specified.</span></span> <span data-ttu-id="159ab-119">Sie müssen ein untergeordnetes **EventString**-, **File**- oder **Database** -Element für das übergeordnete **Workload** -Element angeben. Es kann jedoch nur ein Typ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="159ab-119">You must specify an **EventString**, a **File**, or a **Database** child element for the **Workload** parent, but only one type can be used.</span></span> <span data-ttu-id="159ab-120">Wenn Sie beispielsweise eine Arbeitsauslastung mit dem **File** -Element angeben, können Sie in dieser XML-Eingabedatei keine Arbeitsauslastung mit dem **Database** -Element festlegen.</span><span class="sxs-lookup"><span data-stu-id="159ab-120">For example, if you specify a workload with the **File** element, then you cannot also specify a workload with the **Database** element in the same XML input file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="159ab-121">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="159ab-121">Element Relationships</span></span>  
  
|<span data-ttu-id="159ab-122">Beziehung</span><span class="sxs-lookup"><span data-stu-id="159ab-122">Relationship</span></span>|<span data-ttu-id="159ab-123">Elemente</span><span class="sxs-lookup"><span data-stu-id="159ab-123">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="159ab-124">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="159ab-124">**Parent element**</span></span>|[<span data-ttu-id="159ab-125">Workload-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="159ab-125">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)|  
|<span data-ttu-id="159ab-126">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="159ab-126">**Child elements**</span></span>|<span data-ttu-id="159ab-127">Keine.</span><span class="sxs-lookup"><span data-stu-id="159ab-127">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="159ab-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="159ab-128">Example</span></span>  
 <span data-ttu-id="159ab-129">Ein Beispiel für die Verwendung dieses Elements finden Sie unter [Beispiel für eine einfache XML-Eingabedatei &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="159ab-129">For a usage example of this element, see [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="159ab-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="159ab-130">See Also</span></span>  
 [<span data-ttu-id="159ab-131">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="159ab-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
