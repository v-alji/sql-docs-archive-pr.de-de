---
title: Issue-Element (ssbdiagnose) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- issue element
- XML output file format [ssbdiagnose], issue element
- ssbdiagnose
ms.assetid: 2246a886-686b-44ca-9771-b155cedad8be
author: stevestein
ms.author: sstein
ms.openlocfilehash: a178c1323c1c20f84e67d4d7699fc313090a4c71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694890"
---
# <a name="issue-element-ssbdiagnose"></a><span data-ttu-id="6e563-102">Issue-Element (ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="6e563-102">Issue Element (ssbdiagnose)</span></span>
  <span data-ttu-id="6e563-103">Meldet ein vom Hilfsprogramm **ssbdiagnose** gefundenes Problem.</span><span class="sxs-lookup"><span data-stu-id="6e563-103">Reports an issue that was found by the **ssbdiagnose** utility.</span></span> <span data-ttu-id="6e563-104">Die XML-Ausgabedatei von **ssbdiagnose** enthält für jedes gemeldete Problem ein Issue-Element.</span><span class="sxs-lookup"><span data-stu-id="6e563-104">The **ssbdiagnose** XML output file has one Issue element per issue reported.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e563-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e563-105">Syntax</span></span>  
  
```  
  
<Issue  
    type="..."   
    code="..."   
    server="..."   
    database="..."   
    object="...">   
    ...   
</Issue>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="6e563-106">Elementattribute</span><span class="sxs-lookup"><span data-stu-id="6e563-106">Element Attributes</span></span>  
  
|<span data-ttu-id="6e563-107">attribute</span><span class="sxs-lookup"><span data-stu-id="6e563-107">Attribute</span></span>|<span data-ttu-id="6e563-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6e563-108">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="6e563-109">Identifiziert die Kategorie des vom Issue-Element gemeldeten Problems:</span><span class="sxs-lookup"><span data-stu-id="6e563-109">Identifies which category of problem the Issue element is reporting:</span></span><br /><br /> <span data-ttu-id="6e563-110">**„Diagnose“** meldet ein bei der Analyse einer [!INCLUDE[ssSB](../../includes/sssb-md.md)] -Konfiguration „gefundenes Konfigurationsproblem.</span><span class="sxs-lookup"><span data-stu-id="6e563-110">**"Diagnosis"** Reports a configuration issue found when you analyze a [!INCLUDE[ssSB](../../includes/sssb-md.md)] configuration.</span></span><br /><br /> <span data-ttu-id="6e563-111">**„Problem“** meldet ein Problem, aufgrund dessen **ssbdiagnose** die Analyse nicht abschließen konnte.</span><span class="sxs-lookup"><span data-stu-id="6e563-111">**"Problem"** Reports an issue that has prevented **ssbdiagnose** from completing its analysis.</span></span> <span data-ttu-id="6e563-112">Beheben Sie das Problem, und führen Sie **ssbdiagnose**erneut aus.</span><span class="sxs-lookup"><span data-stu-id="6e563-112">Correct the problem and rerun **ssbdiagnose**.</span></span><br /><br /> <span data-ttu-id="6e563-113">**„Event“** meldet ein [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] -Ereignis, das bei der Ausführung einer **-RUNTIME** -Überprüfung gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="6e563-113">**"Event"** Reports a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] event found when you run a **-RUNTIME** check.</span></span> <span data-ttu-id="6e563-114">Ereignisse werden nur gemeldet, wenn **-SHOWEVENTS** angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="6e563-114">Events are only reported if **-SHOWEVENTS** is specified.</span></span>|  
|`code`|<span data-ttu-id="6e563-115">Gibt die Fehlernummer für die Meldung an.</span><span class="sxs-lookup"><span data-stu-id="6e563-115">Identifies the error number for the message.</span></span>|  
|`server`|<span data-ttu-id="6e563-116">Identifiziert die Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] , in der das Problem gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="6e563-116">Identifies the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] in which the problem was found.</span></span> <span data-ttu-id="6e563-117">Wenn das Problem in einer Standardinstanz gefunden wurde, enthält das Serverattribut nur den Computernamen.</span><span class="sxs-lookup"><span data-stu-id="6e563-117">If the problem was in a default instance, the server attribute only has the computer name.</span></span> <span data-ttu-id="6e563-118">Wenn das Problem in einer benannten Instanz gefunden wurde, weist das Serverattribut das Format Computername\Instanzname auf.</span><span class="sxs-lookup"><span data-stu-id="6e563-118">If the problem was in a named instance, the server attribute is in the form ComputerName\InstanceName.</span></span>|  
|`database`|<span data-ttu-id="6e563-119">Identifiziert den Namen der Datenbank, in der das Problem gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="6e563-119">Identifies the name of the database in which the problem was found.</span></span>|  
|`object`|<span data-ttu-id="6e563-120">Identifiziert den Namen des Objekts, in dem das Problem gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="6e563-120">Identifies the name of the object in which the problem was found.</span></span> <span data-ttu-id="6e563-121">Wenn das Problem auf der Ebene einer Instanz oder Datenbank aufgetreten ist, wird im Objektattribut der Name der Instanz bzw. Datenbank wiederholt.</span><span class="sxs-lookup"><span data-stu-id="6e563-121">If the problem was an instance or database level issue, the object attribute repeats the instance or database name.</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="6e563-122">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="6e563-122">Element Characteristics</span></span>  
  
|<span data-ttu-id="6e563-123">Merkmal</span><span class="sxs-lookup"><span data-stu-id="6e563-123">Characteristic</span></span>|<span data-ttu-id="6e563-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6e563-124">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="6e563-125">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="6e563-125">**Data type and length**</span></span>|<span data-ttu-id="6e563-126">`string`, die Länge ist unbegrenzt.</span><span class="sxs-lookup"><span data-stu-id="6e563-126">`string`, length is unlimited.</span></span>|  
|<span data-ttu-id="6e563-127">**Wert**</span><span class="sxs-lookup"><span data-stu-id="6e563-127">**Value**</span></span>|<span data-ttu-id="6e563-128">Gibt den Text der Fehlermeldung zurück.</span><span class="sxs-lookup"><span data-stu-id="6e563-128">Returns the text of the error message.</span></span>|  
|<span data-ttu-id="6e563-129">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="6e563-129">**Occurrence**</span></span>|<span data-ttu-id="6e563-130">Einmal pro gemeldeten Fehler.</span><span class="sxs-lookup"><span data-stu-id="6e563-130">Once per reported error.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="6e563-131">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="6e563-131">Element Relationships</span></span>  
  
|<span data-ttu-id="6e563-132">Beziehung</span><span class="sxs-lookup"><span data-stu-id="6e563-132">Relationship</span></span>|<span data-ttu-id="6e563-133">Elemente</span><span class="sxs-lookup"><span data-stu-id="6e563-133">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="6e563-134">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="6e563-134">**Parent element**</span></span>|[<span data-ttu-id="6e563-135">DiagnosticInformation-Element &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="6e563-135">DiagnosticInformation Element &#40;ssbdiagnose&#41;</span></span>](diagnosticinformation-element-ssbdiagnose.md)|  
|<span data-ttu-id="6e563-136">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="6e563-136">**Child elements**</span></span>|<span data-ttu-id="6e563-137">Keine</span><span class="sxs-lookup"><span data-stu-id="6e563-137">None</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6e563-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e563-138">Example</span></span>  
 <span data-ttu-id="6e563-139">Dieses Element meldet einen 1102-Fehler für eine Datenbank ohne Hauptschlüssel, wobei der Fehler bei der Analyse einer [!INCLUDE[ssSB](../../includes/sssb-md.md)] -Konfiguration gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="6e563-139">This element reports an 1102 error for a database that does not have a master key, where the error was found when you analyzed a [!INCLUDE[ssSB](../../includes/sssb-md.md)] configuration.</span></span>  
  
```  
<Issue type="Diagnosis" code="1102" server="TestComputer" database="TargetDB" object="TargetDB">The master key was not found</diagnostic>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6e563-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6e563-140">See Also</span></span>  
 [<span data-ttu-id="6e563-141">ssbdiagnose-Hilfsprogramm &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="6e563-141">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
