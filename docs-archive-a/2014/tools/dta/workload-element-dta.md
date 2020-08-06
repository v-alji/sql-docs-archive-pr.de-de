---
title: Workloadelement (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Workload element
ms.assetid: 68ffd473-6546-4015-98d0-3763165de65c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 20184760c3fcb5eed6c02b8f8fd9b63f5586c9af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616884"
---
# <a name="workload-element-dta"></a><span data-ttu-id="60e54-102">Workload-Element (DTA)</span><span class="sxs-lookup"><span data-stu-id="60e54-102">Workload Element (DTA)</span></span>
  <span data-ttu-id="60e54-103">Gibt die für eine Optimierungssitzung zu verwendende Arbeitsauslastung an.</span><span class="sxs-lookup"><span data-stu-id="60e54-103">Specifies the workload to be used for a tuning session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60e54-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="60e54-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>  
...code removed...  
    <Workload>...</Workload>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="60e54-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="60e54-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="60e54-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="60e54-106">Characteristic</span></span>|<span data-ttu-id="60e54-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="60e54-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="60e54-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="60e54-108">**Data type and length**</span></span>|<span data-ttu-id="60e54-109">Keine.</span><span class="sxs-lookup"><span data-stu-id="60e54-109">None.</span></span>|  
|<span data-ttu-id="60e54-110">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="60e54-110">**Default value**</span></span>|<span data-ttu-id="60e54-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="60e54-111">None.</span></span>|  
|<span data-ttu-id="60e54-112">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="60e54-112">**Occurrence**</span></span>|<span data-ttu-id="60e54-113">Für jedes `DTAInput`-Element erforderlich.</span><span class="sxs-lookup"><span data-stu-id="60e54-113">Required once for each `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="60e54-114">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="60e54-114">Element Relationships</span></span>  
  
|<span data-ttu-id="60e54-115">Beziehung</span><span class="sxs-lookup"><span data-stu-id="60e54-115">Relationship</span></span>|<span data-ttu-id="60e54-116">Elemente</span><span class="sxs-lookup"><span data-stu-id="60e54-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="60e54-117">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="60e54-117">**Parent element**</span></span>|[<span data-ttu-id="60e54-118">Starten und Verwenden des Datenbankoptimierungsratgebers</span><span class="sxs-lookup"><span data-stu-id="60e54-118">Start and Use the Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md)|  
|<span data-ttu-id="60e54-119">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="60e54-119">**Child elements**</span></span>|[<span data-ttu-id="60e54-120">File-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="60e54-120">File Element &#40;DTA&#41;</span></span>](file-element-dta.md)<br /><br /> [<span data-ttu-id="60e54-121">Database-Element zur Arbeitsauslastung &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="60e54-121">Database Element for Workload &#40;DTA&#41;</span></span>](database-element-for-workload-dta.md)<br /><br /> [<span data-ttu-id="60e54-122">EventString-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="60e54-122">EventString Element &#40;DTA&#41;</span></span>](eventstring-element-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="60e54-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="60e54-123">Remarks</span></span>  
 <span data-ttu-id="60e54-124">Die Arbeitsauslastung besteht aus einer Reihe von [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen, die für eine oder mehrere Datenbanken ausgeführt werden, die Sie optimieren möchten.</span><span class="sxs-lookup"><span data-stu-id="60e54-124">A workload is a set of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that execute against a database or databases that you want to tune.</span></span> <span data-ttu-id="60e54-125">Der Datenbankoptimierungsratgeber kann [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skripts, Ablaufverfolgungsdateien und Ablaufverfolgungstabellen als Arbeitsauslastung verwenden.</span><span class="sxs-lookup"><span data-stu-id="60e54-125">The Database Engine Tuning Advisor can use [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, trace files, and trace tables as workloads.</span></span>  
  
 <span data-ttu-id="60e54-126">Wenn Sie sowohl in einer XML-Eingabedatei als auch mit dem Tool **dta** in der Befehlszeile eine Arbeitsauslastung angeben, wird die in der Befehlszeile angegebene Arbeitsauslastung für die Optimierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="60e54-126">If you specify a workload in an XML input file and a workload on the command line with the **dta** tool, the workload specified on the command line will be used for tuning.</span></span> <span data-ttu-id="60e54-127">Alle Optimierungsoptionen, die in der Befehlszeile angegeben sind, überschreiben die in XML-Eingabedateien angegebenen Optionen.</span><span class="sxs-lookup"><span data-stu-id="60e54-127">All tuning options specified on the command line override those that are specified in an XML input file.</span></span> <span data-ttu-id="60e54-128">Die einzige Ausnahme hiervon sind benutzerdefinierte Konfigurationen, die im Auswertungsmodus in der XML-Eingabedatei eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="60e54-128">The only exception is if a user-specified configuration is entered in the evaluate mode in the XML input file.</span></span> <span data-ttu-id="60e54-129">Wenn z. B. eine Konfiguration in das `Configuration`-Element der XML-Eingabedatei eingegeben wird und auch das `EvaluateConfiguration`-Element als eine der Optimierungsoptionen angegeben ist, überschreiben die in der XML-Eingabedatei angegebenen Optimierungsoptionen die in der Befehlszeile eingegebenen Optimierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="60e54-129">For example, if a configuration is entered in the `Configuration` element of the XML input file and the `EvaluateConfiguration` element is also specified as one of the tuning options, the tuning options specified in the XML input file will override any tuning options entered at the command line.</span></span>  
  
 <span data-ttu-id="60e54-130">Die Angabe einer Arbeitsauslastung ist für jede Optimierungssitzung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="60e54-130">One workload must be specified for each tuning session.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60e54-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="60e54-131">Example</span></span>  
 <span data-ttu-id="60e54-132">Das folgende Codebeispiel gibt die **MyDatabase. MyDBOwner. TuningTable001** -Ablauf Verfolgungs Tabelle für das- `Workload` Element an.</span><span class="sxs-lookup"><span data-stu-id="60e54-132">The following code example specifies the **MyDatabase.MyDBOwner.TuningTable001** trace table for the `Workload` element.</span></span> <span data-ttu-id="60e54-133">Die **TuningTable001** -Tabelle wurde mithilfe der Optimierungsvorlage von SQL Server Profiler und Speichern der Ablaufverfolgungsausgabe als Tabelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="60e54-133">The **TuningTable001** was created by using the Tuning template with SQL Server Profiler and saving the trace output as a table.</span></span>  
  
```  
<DTAXML ...>  
  <DTAInput>  
    <Server>  
...code removed here...  
    </Server>  
    <Workload>  
      <Database>  
        <Name>MyDatabase</Name>  
        <Schema>  
          <Name>MyDBOwner</Name>  
            <Table>  
              <Name>TuningTable001</Name>  
            </Table>  
        </Schema>  
      </Database>  
    </Workload>  
...code removed here...  
  </DTAInput>  
</DTAXML>  
```  
  
## <a name="see-also"></a><span data-ttu-id="60e54-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60e54-134">See Also</span></span>  
 [<span data-ttu-id="60e54-135">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="60e54-135">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
