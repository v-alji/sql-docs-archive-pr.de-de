---
title: Aufgezählte Konstanten in Eigenschaftsausdrücken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- enumerators [Integration Services]
- packages [Integration Services], expressions
- dynamic properties
- updating package properties
- enumerated constants [Integration Services]
- property expressions [Integration Services]
ms.assetid: a4418315-38e2-4ad3-8784-576163b25d6f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9cb4ae32bf564e98d8cfc843e9497b15222fa79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701481"
---
# <a name="enumerated-constants-in-property-expressions"></a><span data-ttu-id="ee524-102">Aufgezählte Konstanten in Eigenschaftsausdrücken</span><span class="sxs-lookup"><span data-stu-id="ee524-102">Enumerated Constants in Property Expressions</span></span>
  <span data-ttu-id="ee524-103">Wenn Eigenschaftsausdrücke Werte aus einer Liste von Enumeratorelementen enthalten, müssen die Ausdrücke den numerischen Wert des Enumeratorelements anstelle des Anzeigenamens des Elements verwenden.</span><span class="sxs-lookup"><span data-stu-id="ee524-103">If property expressions include values from an enumerator member list, the expression must use the numeric value of the enumerator member instead of the friendly name of the member.</span></span> <span data-ttu-id="ee524-104">Wenn z. B. ein Ausdruck die `LoggingMode`-Eigenschaft festlegt, müssen Sie den numerischen Wert 2 anstelle des Anzeigenamens Disabled verwenden.</span><span class="sxs-lookup"><span data-stu-id="ee524-104">For example, if an expression sets the `LoggingMode` property then you must use the numeric value 2 instead of the friendly name Disabled.</span></span>  
  
 <span data-ttu-id="ee524-105">In diesem Thema werden nur die entsprechenden numerischen Werte für Anzeigenamen von Enumeratoren aufgelistet, deren Elemente häufig in Eigenschaftsausdrücken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ee524-105">This topic lists only the numeric values equivalent to friendly names of enumerators whose members are commonly used in property expressions.</span></span> <span data-ttu-id="ee524-106">Das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Objektmodell enthält viele zusätzliche Enumeratoren, die Sie beim Programmieren des Objektmodells verwenden können, um Pakete programmgesteuert zu erstellen oder um benutzerdefinierte Paketelemente, wie z. B. Tasks und Datenflusskomponenten, zu programmieren.</span><span class="sxs-lookup"><span data-stu-id="ee524-106">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model includes many additional enumerators that you use when you program the object model to build packages programmatically or code custom package elements such as tasks and data flow components.</span></span>  
  
 <span data-ttu-id="ee524-107">Neben den benutzerdefinierten Eigenschaften für Pakete und Paketobjekte enthält das Eigenschaftenfenster in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] eine Reihe von Eigenschaften, die für Pakete, Tasks, für die Foreach- und For-Schleife sowie für Sequenzcontainer zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="ee524-107">In addition to the custom properties for packages and package objects, the Properties window in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] includes a set of properties that are available to packages, tasks, and the Foreach Loop, For Loop, and Sequence containers.</span></span> <span data-ttu-id="ee524-108">Die allgemeinen Eigenschaften, die durch Werte von Enumeratoren,, und festgelegt werden, `ForceExecutionResult` `LoggingMode` `IsolationLevel` `Transaction Option` sind im Abschnitt Allgemeine Eigenschaften aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="ee524-108">The common properties that are set by values from enumerators-`ForceExecutionResult`, `LoggingMode`, `IsolationLevel`, and `Transaction Option`-are listed in Common Properties section.</span></span>  
  
 <span data-ttu-id="ee524-109">In den folgenden Abschnitten werden Informationen zu den folgenden aufgelisteten Konstanten bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="ee524-109">The following sections provide information about enumerated constants:</span></span>  
  
 [<span data-ttu-id="ee524-110">Paket</span><span class="sxs-lookup"><span data-stu-id="ee524-110">Package</span></span>](#Package)  
  
 [<span data-ttu-id="ee524-111">Foreach-Schleifenenumeratoren</span><span class="sxs-lookup"><span data-stu-id="ee524-111">Foreach Loop Enumerators</span></span>](#Foreach)  
  
 [<span data-ttu-id="ee524-112">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="ee524-112">Tasks</span></span>](#Tasks)  
  
 [<span data-ttu-id="ee524-113">Wartungsplantasks</span><span class="sxs-lookup"><span data-stu-id="ee524-113">Maintenance Plan Tasks</span></span>](#MaintenancePlanTasks)  
  
 [<span data-ttu-id="ee524-114">Common Properties</span><span class="sxs-lookup"><span data-stu-id="ee524-114">Common Properties</span></span>](#CommonProperties)  
  
##  <a name="package"></a><a name="Package"></a> <span data-ttu-id="ee524-115">Paket</span><span class="sxs-lookup"><span data-stu-id="ee524-115">Package</span></span>  
 <span data-ttu-id="ee524-116">In den folgenden Tabellen finden Sie eine Auflistung der Anzeigenamen und der entsprechenden numerischen Werte für Eigenschaften von Paketen, die Sie mithilfe von Werten eines Enumerators festlegen.</span><span class="sxs-lookup"><span data-stu-id="ee524-116">The following tables lists the friendly names and the numeric value equivalents for properties of packages that you set by using values from an enumerator.</span></span>  
  
 <span data-ttu-id="ee524-117">`PackageType`Eigenschaften Satz mithilfe von Werten aus der- `DTSPackageType` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-117">`PackageType` property-Set by using values from the `DTSPackageType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-118">Anzeigename in DTSPackageType</span><span class="sxs-lookup"><span data-stu-id="ee524-118">Friendly name in DTSPackageType</span></span>|<span data-ttu-id="ee524-119">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-119">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="ee524-120">Standard</span><span class="sxs-lookup"><span data-stu-id="ee524-120">Default</span></span>|<span data-ttu-id="ee524-121">0</span><span class="sxs-lookup"><span data-stu-id="ee524-121">0</span></span>|  
|<span data-ttu-id="ee524-122">DTSWizard</span><span class="sxs-lookup"><span data-stu-id="ee524-122">DTSWizard</span></span>|<span data-ttu-id="ee524-123">1</span><span class="sxs-lookup"><span data-stu-id="ee524-123">1</span></span>|  
|<span data-ttu-id="ee524-124">DTSDesigner</span><span class="sxs-lookup"><span data-stu-id="ee524-124">DTSDesigner</span></span>|<span data-ttu-id="ee524-125">2</span><span class="sxs-lookup"><span data-stu-id="ee524-125">2</span></span>|  
|<span data-ttu-id="ee524-126">SQLReplication</span><span class="sxs-lookup"><span data-stu-id="ee524-126">SQLReplication</span></span>|<span data-ttu-id="ee524-127">3</span><span class="sxs-lookup"><span data-stu-id="ee524-127">3</span></span>|  
|<span data-ttu-id="ee524-128">DTSDesigner100</span><span class="sxs-lookup"><span data-stu-id="ee524-128">DTSDesigner100</span></span>|<span data-ttu-id="ee524-129">5</span><span class="sxs-lookup"><span data-stu-id="ee524-129">5</span></span>|  
|<span data-ttu-id="ee524-130">SQLDBMaint</span><span class="sxs-lookup"><span data-stu-id="ee524-130">SQLDBMaint</span></span>|<span data-ttu-id="ee524-131">6</span><span class="sxs-lookup"><span data-stu-id="ee524-131">6</span></span>|  
  
 <span data-ttu-id="ee524-132">`CheckpointUsage`Eigenschaften Satz mithilfe von Werten aus der- `DTSCheckpointUsage` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-132">`CheckpointUsage` property-Set by using values from the `DTSCheckpointUsage` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-133">Anzeigename in DTSCheckpointUsage</span><span class="sxs-lookup"><span data-stu-id="ee524-133">Friendly name in DTSCheckpointUsage</span></span>|<span data-ttu-id="ee524-134">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-134">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="ee524-135">Nie</span><span class="sxs-lookup"><span data-stu-id="ee524-135">Never</span></span>|<span data-ttu-id="ee524-136">0</span><span class="sxs-lookup"><span data-stu-id="ee524-136">0</span></span>|  
|<span data-ttu-id="ee524-137">IfExists</span><span class="sxs-lookup"><span data-stu-id="ee524-137">IfExists</span></span>|<span data-ttu-id="ee524-138">1</span><span class="sxs-lookup"><span data-stu-id="ee524-138">1</span></span>|  
|<span data-ttu-id="ee524-139">Always</span><span class="sxs-lookup"><span data-stu-id="ee524-139">Always</span></span>|<span data-ttu-id="ee524-140">2</span><span class="sxs-lookup"><span data-stu-id="ee524-140">2</span></span>|  
  
 <span data-ttu-id="ee524-141">`PackagePriorityClass`Eigenschaften Satz mithilfe von Werten aus der- `DTSPriorityClass` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-141">`PackagePriorityClass` property-Set by using values from the `DTSPriorityClass` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-142">Anzeigename in DTSPriorityClass</span><span class="sxs-lookup"><span data-stu-id="ee524-142">Friendly name in DTSPriorityClass</span></span>|<span data-ttu-id="ee524-143">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-143">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="ee524-144">Standard</span><span class="sxs-lookup"><span data-stu-id="ee524-144">Default</span></span>|<span data-ttu-id="ee524-145">0</span><span class="sxs-lookup"><span data-stu-id="ee524-145">0</span></span>|  
|<span data-ttu-id="ee524-146">AboveNormal</span><span class="sxs-lookup"><span data-stu-id="ee524-146">AboveNormal</span></span>|<span data-ttu-id="ee524-147">1</span><span class="sxs-lookup"><span data-stu-id="ee524-147">1</span></span>|  
|<span data-ttu-id="ee524-148">Normal</span><span class="sxs-lookup"><span data-stu-id="ee524-148">Normal</span></span>|<span data-ttu-id="ee524-149">2</span><span class="sxs-lookup"><span data-stu-id="ee524-149">2</span></span>|  
|<span data-ttu-id="ee524-150">BelowNormal</span><span class="sxs-lookup"><span data-stu-id="ee524-150">BelowNormal</span></span>|<span data-ttu-id="ee524-151">3</span><span class="sxs-lookup"><span data-stu-id="ee524-151">3</span></span>|  
|<span data-ttu-id="ee524-152">Idle</span><span class="sxs-lookup"><span data-stu-id="ee524-152">Idle</span></span>|<span data-ttu-id="ee524-153">4</span><span class="sxs-lookup"><span data-stu-id="ee524-153">4</span></span>|  
  
 <span data-ttu-id="ee524-154">`ProtectionLevel`Eigenschaften Satz mithilfe von Werten aus der- `DTSProtectionLevel` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-154">`ProtectionLevel` property-Set by using values from the `DTSProtectionLevel` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-155">Anzeigename in DTSProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="ee524-155">Friendly name in DTSProtectionLevel</span></span>|<span data-ttu-id="ee524-156">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-156">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="ee524-157">DontSaveSensitive</span><span class="sxs-lookup"><span data-stu-id="ee524-157">DontSaveSensitive</span></span>|<span data-ttu-id="ee524-158">0</span><span class="sxs-lookup"><span data-stu-id="ee524-158">0</span></span>|  
|<span data-ttu-id="ee524-159">EncryptSensitiveWithUserKey</span><span class="sxs-lookup"><span data-stu-id="ee524-159">EncryptSensitiveWithUserKey</span></span>|<span data-ttu-id="ee524-160">1</span><span class="sxs-lookup"><span data-stu-id="ee524-160">1</span></span>|  
|<span data-ttu-id="ee524-161">EncryptSensitiveWithPassword</span><span class="sxs-lookup"><span data-stu-id="ee524-161">EncryptSensitiveWithPassword</span></span>|<span data-ttu-id="ee524-162">2</span><span class="sxs-lookup"><span data-stu-id="ee524-162">2</span></span>|  
|<span data-ttu-id="ee524-163">EncryptAllWithPassword</span><span class="sxs-lookup"><span data-stu-id="ee524-163">EncryptAllWithPassword</span></span>|<span data-ttu-id="ee524-164">3</span><span class="sxs-lookup"><span data-stu-id="ee524-164">3</span></span>|  
|<span data-ttu-id="ee524-165">EncryptAllWithUserKey</span><span class="sxs-lookup"><span data-stu-id="ee524-165">EncryptAllWithUserKey</span></span>|<span data-ttu-id="ee524-166">4</span><span class="sxs-lookup"><span data-stu-id="ee524-166">4</span></span>|  
|<span data-ttu-id="ee524-167">ServerStorage</span><span class="sxs-lookup"><span data-stu-id="ee524-167">ServerStorage</span></span>|<span data-ttu-id="ee524-168">5</span><span class="sxs-lookup"><span data-stu-id="ee524-168">5</span></span>|  
  
##  <a name="precedence-constraints"></a><a name="PrecedenceConstraints"></a> <span data-ttu-id="ee524-169">Rangfolgeneinschränkungen</span><span class="sxs-lookup"><span data-stu-id="ee524-169">Precedence Constraints</span></span>  
 <span data-ttu-id="ee524-170">`EvalOp`Eigenschaften Satz mithilfe von Werten aus der- `DTSPrecedenceEvalOp` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-170">`EvalOp` property-Set by using values from the `DTSPrecedenceEvalOp` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-171">Anzeigename in DTSPrecedenceEvalOp</span><span class="sxs-lookup"><span data-stu-id="ee524-171">Friendly name in DTSPrecedenceEvalOp</span></span>|<span data-ttu-id="ee524-172">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-172">Numeric value</span></span>|  
|------------------------------------------|-------------------|  
|<span data-ttu-id="ee524-173">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="ee524-173">Expression</span></span>|<span data-ttu-id="ee524-174">1</span><span class="sxs-lookup"><span data-stu-id="ee524-174">1</span></span>|  
|<span data-ttu-id="ee524-175">Einschränkung</span><span class="sxs-lookup"><span data-stu-id="ee524-175">Constraint</span></span>|<span data-ttu-id="ee524-176">2</span><span class="sxs-lookup"><span data-stu-id="ee524-176">2</span></span>|  
|<span data-ttu-id="ee524-177">ExpressionAndConstraint</span><span class="sxs-lookup"><span data-stu-id="ee524-177">ExpressionAndConstraint</span></span>|<span data-ttu-id="ee524-178">3</span><span class="sxs-lookup"><span data-stu-id="ee524-178">3</span></span>|  
|<span data-ttu-id="ee524-179">ExpressionOrConstraint</span><span class="sxs-lookup"><span data-stu-id="ee524-179">ExpressionOrConstraint</span></span>|<span data-ttu-id="ee524-180">4</span><span class="sxs-lookup"><span data-stu-id="ee524-180">4</span></span>|  
  
 <span data-ttu-id="ee524-181">`Value`Eigenschaften Satz mithilfe von Werten aus der- `DTSExecResult` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-181">`Value` property-Set by using values from the `DTSExecResult` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-182">Anzeigename</span><span class="sxs-lookup"><span data-stu-id="ee524-182">Friendly Name</span></span>|<span data-ttu-id="ee524-183">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-183">Numeric Value</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="ee524-184">Erfolg</span><span class="sxs-lookup"><span data-stu-id="ee524-184">Success</span></span>|<span data-ttu-id="ee524-185">0</span><span class="sxs-lookup"><span data-stu-id="ee524-185">0</span></span>|  
|<span data-ttu-id="ee524-186">Fehler</span><span class="sxs-lookup"><span data-stu-id="ee524-186">Failure</span></span>|<span data-ttu-id="ee524-187">1</span><span class="sxs-lookup"><span data-stu-id="ee524-187">1</span></span>|  
|<span data-ttu-id="ee524-188">Completion</span><span class="sxs-lookup"><span data-stu-id="ee524-188">Completion</span></span>|<span data-ttu-id="ee524-189">2</span><span class="sxs-lookup"><span data-stu-id="ee524-189">2</span></span>|  
|<span data-ttu-id="ee524-190">Canceled</span><span class="sxs-lookup"><span data-stu-id="ee524-190">Canceled</span></span>|<span data-ttu-id="ee524-191">3</span><span class="sxs-lookup"><span data-stu-id="ee524-191">3</span></span>|  
  
##  <a name="foreach-loop-enumerators"></a><a name="Foreach"></a> <span data-ttu-id="ee524-192">Foreach-Schleifenenumeratoren</span><span class="sxs-lookup"><span data-stu-id="ee524-192">Foreach Loop Enumerators</span></span>  
 <span data-ttu-id="ee524-193">Die Foreach-Schleife enthält eine Reihe von Enumeratoren mit Eigenschaften, die mithilfe von Eigenschaftsausdrücken festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="ee524-193">The Foreach Loop includes a set of enumerators with properties that can be set by property expressions.</span></span>  
  
### <a name="foreach-ado-enumerator"></a><span data-ttu-id="ee524-194">Foreach-ADO-Enumerator</span><span class="sxs-lookup"><span data-stu-id="ee524-194">Foreach ADO Enumerator</span></span>  
 <span data-ttu-id="ee524-195">`Type`Eigenschaften Satz mithilfe von Werten aus der- `ADOEnumerationType` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-195">`Type` property-Set by using values from the `ADOEnumerationType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-196">Anzeigename in ADOEnumerationType</span><span class="sxs-lookup"><span data-stu-id="ee524-196">Friendly name in ADOEnumerationType</span></span>|<span data-ttu-id="ee524-197">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-197">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="ee524-198">EnumerateTables</span><span class="sxs-lookup"><span data-stu-id="ee524-198">EnumerateTables</span></span>|<span data-ttu-id="ee524-199">0</span><span class="sxs-lookup"><span data-stu-id="ee524-199">0</span></span>|  
|<span data-ttu-id="ee524-200">EnumerateAllRows</span><span class="sxs-lookup"><span data-stu-id="ee524-200">EnumerateAllRows</span></span>|<span data-ttu-id="ee524-201">1</span><span class="sxs-lookup"><span data-stu-id="ee524-201">1</span></span>|  
|<span data-ttu-id="ee524-202">EnumerateRowsInFirstTable</span><span class="sxs-lookup"><span data-stu-id="ee524-202">EnumerateRowsInFirstTable</span></span>|<span data-ttu-id="ee524-203">2</span><span class="sxs-lookup"><span data-stu-id="ee524-203">2</span></span>|  
  
### <a name="foreach-nodelist-enumerator"></a><span data-ttu-id="ee524-204">Foreach-NodeList-Enumerator</span><span class="sxs-lookup"><span data-stu-id="ee524-204">Foreach Nodelist Enumerator</span></span>  
 <span data-ttu-id="ee524-205">`SourceDocumentType``InnerXPathStringSourceType`die Eigenschaften, und **OuterXPathStringSourceType** werden mithilfe von Werten aus der- `SourceType` Enumeration festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ee524-205">`SourceDocumentType`, `InnerXPathStringSourceType`, and **OuterXPathStringSourceType** properties-Set by using values from the `SourceType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-206">Anzeigename in SourceType</span><span class="sxs-lookup"><span data-stu-id="ee524-206">Friendly name in SourceType</span></span>|<span data-ttu-id="ee524-207">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-207">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="ee524-208">FileConnection</span><span class="sxs-lookup"><span data-stu-id="ee524-208">FileConnection</span></span>|<span data-ttu-id="ee524-209">0</span><span class="sxs-lookup"><span data-stu-id="ee524-209">0</span></span>|  
|<span data-ttu-id="ee524-210">Variable</span><span class="sxs-lookup"><span data-stu-id="ee524-210">Variable</span></span>|<span data-ttu-id="ee524-211">1</span><span class="sxs-lookup"><span data-stu-id="ee524-211">1</span></span>|  
|<span data-ttu-id="ee524-212">DirectInput</span><span class="sxs-lookup"><span data-stu-id="ee524-212">DirectInput</span></span>|<span data-ttu-id="ee524-213">2</span><span class="sxs-lookup"><span data-stu-id="ee524-213">2</span></span>|  
  
 <span data-ttu-id="ee524-214">`EnumerationType`Eigenschaften Satz mithilfe von Werten aus der- `EnumerationType` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-214">`EnumerationType` property-Set by using values from the `EnumerationType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-215">Anzeigename in EnumerationType</span><span class="sxs-lookup"><span data-stu-id="ee524-215">Friendly name in EnumerationType</span></span>|<span data-ttu-id="ee524-216">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-216">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="ee524-217">Navigator</span><span class="sxs-lookup"><span data-stu-id="ee524-217">Navigator</span></span>|<span data-ttu-id="ee524-218">0</span><span class="sxs-lookup"><span data-stu-id="ee524-218">0</span></span>|  
|<span data-ttu-id="ee524-219">Node</span><span class="sxs-lookup"><span data-stu-id="ee524-219">Node</span></span>|<span data-ttu-id="ee524-220">1</span><span class="sxs-lookup"><span data-stu-id="ee524-220">1</span></span>|  
|<span data-ttu-id="ee524-221">NodeText</span><span class="sxs-lookup"><span data-stu-id="ee524-221">NodeText</span></span>|<span data-ttu-id="ee524-222">2</span><span class="sxs-lookup"><span data-stu-id="ee524-222">2</span></span>|  
|<span data-ttu-id="ee524-223">ElementCollection</span><span class="sxs-lookup"><span data-stu-id="ee524-223">ElementCollection</span></span>|<span data-ttu-id="ee524-224">3</span><span class="sxs-lookup"><span data-stu-id="ee524-224">3</span></span>|  
  
 <span data-ttu-id="ee524-225">`InnerElementType`Eigenschaften Satz mithilfe von Werten aus der- `InnerElementType` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-225">`InnerElementType` property-Set by using values from the `InnerElementType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-226">Anzeigename in InnerElementType</span><span class="sxs-lookup"><span data-stu-id="ee524-226">Friendly name in InnerElementType</span></span>|<span data-ttu-id="ee524-227">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-227">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="ee524-228">Navigator</span><span class="sxs-lookup"><span data-stu-id="ee524-228">Navigator</span></span>|<span data-ttu-id="ee524-229">0</span><span class="sxs-lookup"><span data-stu-id="ee524-229">0</span></span>|  
|<span data-ttu-id="ee524-230">Node</span><span class="sxs-lookup"><span data-stu-id="ee524-230">Node</span></span>|<span data-ttu-id="ee524-231">1</span><span class="sxs-lookup"><span data-stu-id="ee524-231">1</span></span>|  
|<span data-ttu-id="ee524-232">NodeText</span><span class="sxs-lookup"><span data-stu-id="ee524-232">NodeText</span></span>|<span data-ttu-id="ee524-233">2</span><span class="sxs-lookup"><span data-stu-id="ee524-233">2</span></span>|  
  
##  <a name="tasks"></a><a name="Tasks"></a> <span data-ttu-id="ee524-234">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="ee524-234">Tasks</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="ee524-235">enthält eine Reihe von Tasks mit Eigenschaften, die mithilfe von Eigenschaftsausdrücken festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="ee524-235">includes numerous tasks with properties that can be set by property expressions.</span></span>  
  
### <a name="analysis-services-execute-ddl-task"></a><span data-ttu-id="ee524-236">DDL ausführen (Analysis Services-Task)</span><span class="sxs-lookup"><span data-stu-id="ee524-236">Analysis Services Execute DDL Task</span></span>  
 <span data-ttu-id="ee524-237">`SourceType`Eigenschaften Satz mithilfe von Werten aus der- `DDLSourceType` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-237">`SourceType` property-Set by using values from the `DDLSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-238">Anzeigename in DDLSourceType</span><span class="sxs-lookup"><span data-stu-id="ee524-238">Friendly name in DDLSourceType</span></span>|<span data-ttu-id="ee524-239">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-239">Numeric value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="ee524-240">DirectInput</span><span class="sxs-lookup"><span data-stu-id="ee524-240">DirectInput</span></span>|<span data-ttu-id="ee524-241">0</span><span class="sxs-lookup"><span data-stu-id="ee524-241">0</span></span>|  
|<span data-ttu-id="ee524-242">FileConnection</span><span class="sxs-lookup"><span data-stu-id="ee524-242">FileConnection</span></span>|<span data-ttu-id="ee524-243">1</span><span class="sxs-lookup"><span data-stu-id="ee524-243">1</span></span>|  
|<span data-ttu-id="ee524-244">Variable</span><span class="sxs-lookup"><span data-stu-id="ee524-244">Variable</span></span>|<span data-ttu-id="ee524-245">2</span><span class="sxs-lookup"><span data-stu-id="ee524-245">2</span></span>|  
  
### <a name="bulk-insert-task"></a><span data-ttu-id="ee524-246">Masseneinfügungstask</span><span class="sxs-lookup"><span data-stu-id="ee524-246">Bulk Insert Task</span></span>  
 <span data-ttu-id="ee524-247">`DataFileType`Eigenschaften Satz mithilfe von Werten aus der- `DTSBulkInsert_DataFileType` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-247">`DataFileType` property-Set by using values from the `DTSBulkInsert_DataFileType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-248">Anzeigename in DTSBulkInsert_DataFileType</span><span class="sxs-lookup"><span data-stu-id="ee524-248">Friendly name in DTSBulkInsert_DataFileType</span></span>|<span data-ttu-id="ee524-249">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-249">Numeric value</span></span>|  
|--------------------------------------------------|-------------------|  
|<span data-ttu-id="ee524-250">DTSBulkInsert_DataFileType_Char</span><span class="sxs-lookup"><span data-stu-id="ee524-250">DTSBulkInsert_DataFileType_Char</span></span>|<span data-ttu-id="ee524-251">0</span><span class="sxs-lookup"><span data-stu-id="ee524-251">0</span></span>|  
|<span data-ttu-id="ee524-252">DTSBulkInsert_DataFileType_Native</span><span class="sxs-lookup"><span data-stu-id="ee524-252">DTSBulkInsert_DataFileType_Native</span></span>|<span data-ttu-id="ee524-253">1</span><span class="sxs-lookup"><span data-stu-id="ee524-253">1</span></span>|  
|<span data-ttu-id="ee524-254">DTSBulkInsert_DataFileType_WideChar</span><span class="sxs-lookup"><span data-stu-id="ee524-254">DTSBulkInsert_DataFileType_WideChar</span></span>|<span data-ttu-id="ee524-255">2</span><span class="sxs-lookup"><span data-stu-id="ee524-255">2</span></span>|  
|<span data-ttu-id="ee524-256">DTSBulkInsert_DataFileType_WideNative</span><span class="sxs-lookup"><span data-stu-id="ee524-256">DTSBulkInsert_DataFileType_WideNative</span></span>|<span data-ttu-id="ee524-257">3</span><span class="sxs-lookup"><span data-stu-id="ee524-257">3</span></span>|  
  
### <a name="execute-sql-task"></a><span data-ttu-id="ee524-258">SQL ausführen (Task)</span><span class="sxs-lookup"><span data-stu-id="ee524-258">Execute SQL Task</span></span>  
 <span data-ttu-id="ee524-259">`ResultSetType`Eigenschaften Satz mithilfe von Werten aus der- `ResultSetType` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-259">`ResultSetType` property-Set by using values from the `ResultSetType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-260">Anzeigename in ResultSetType</span><span class="sxs-lookup"><span data-stu-id="ee524-260">Friendly name in ResultSetType</span></span>|<span data-ttu-id="ee524-261">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-261">Numeric Value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="ee524-262">ResultSetType_None</span><span class="sxs-lookup"><span data-stu-id="ee524-262">ResultSetType_None</span></span>|<span data-ttu-id="ee524-263">1</span><span class="sxs-lookup"><span data-stu-id="ee524-263">1</span></span>|  
|<span data-ttu-id="ee524-264">ResultSetType_SingleRow</span><span class="sxs-lookup"><span data-stu-id="ee524-264">ResultSetType_SingleRow</span></span>|<span data-ttu-id="ee524-265">2</span><span class="sxs-lookup"><span data-stu-id="ee524-265">2</span></span>|  
|<span data-ttu-id="ee524-266">ResultSetType_Rowset</span><span class="sxs-lookup"><span data-stu-id="ee524-266">ResultSetType_Rowset</span></span>|<span data-ttu-id="ee524-267">3</span><span class="sxs-lookup"><span data-stu-id="ee524-267">3</span></span>|  
|<span data-ttu-id="ee524-268">ResultSetType_XML</span><span class="sxs-lookup"><span data-stu-id="ee524-268">ResultSetType_XML</span></span>|<span data-ttu-id="ee524-269">4</span><span class="sxs-lookup"><span data-stu-id="ee524-269">4</span></span>|  
  
 <span data-ttu-id="ee524-270">`SqlStatementSourceType`Eigenschaften Satz mithilfe von Werten aus der- `SqlStatementSourceType` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-270">`SqlStatementSourceType` property-Set by using values from the `SqlStatementSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-271">Anzeigename in SqlStatementSourceType</span><span class="sxs-lookup"><span data-stu-id="ee524-271">Friendly name in SqlStatementSourceType</span></span>|<span data-ttu-id="ee524-272">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-272">Numeric Value</span></span>|  
|---------------------------------------------|-------------------|  
|<span data-ttu-id="ee524-273">DirectInput</span><span class="sxs-lookup"><span data-stu-id="ee524-273">DirectInput</span></span>|<span data-ttu-id="ee524-274">1</span><span class="sxs-lookup"><span data-stu-id="ee524-274">1</span></span>|  
|<span data-ttu-id="ee524-275">FileConnection</span><span class="sxs-lookup"><span data-stu-id="ee524-275">FileConnection</span></span>|<span data-ttu-id="ee524-276">2</span><span class="sxs-lookup"><span data-stu-id="ee524-276">2</span></span>|  
|<span data-ttu-id="ee524-277">Variable</span><span class="sxs-lookup"><span data-stu-id="ee524-277">Variable</span></span>|<span data-ttu-id="ee524-278">3</span><span class="sxs-lookup"><span data-stu-id="ee524-278">3</span></span>|  
  
### <a name="file-system-task"></a><span data-ttu-id="ee524-279">Task Dateisystem</span><span class="sxs-lookup"><span data-stu-id="ee524-279">File System Task</span></span>  
 <span data-ttu-id="ee524-280">`Operation`Eigenschaften Satz mithilfe von Werten aus der- `DTSFileSystemOperation` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-280">`Operation` property-Set by using values from the `DTSFileSystemOperation` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-281">Anzeigename in DTSFileSystemOperation</span><span class="sxs-lookup"><span data-stu-id="ee524-281">Friendly name in DTSFileSystemOperation</span></span>|<span data-ttu-id="ee524-282">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-282">Numeric value</span></span>|  
|---------------------------------------------|-------------------|  
|<span data-ttu-id="ee524-283">CopyFile</span><span class="sxs-lookup"><span data-stu-id="ee524-283">CopyFile</span></span>|<span data-ttu-id="ee524-284">0</span><span class="sxs-lookup"><span data-stu-id="ee524-284">0</span></span>|  
|<span data-ttu-id="ee524-285">MoveFile</span><span class="sxs-lookup"><span data-stu-id="ee524-285">MoveFile</span></span>|<span data-ttu-id="ee524-286">1</span><span class="sxs-lookup"><span data-stu-id="ee524-286">1</span></span>|  
|<span data-ttu-id="ee524-287">DeleteFile</span><span class="sxs-lookup"><span data-stu-id="ee524-287">DeleteFile</span></span>|<span data-ttu-id="ee524-288">2</span><span class="sxs-lookup"><span data-stu-id="ee524-288">2</span></span>|  
|<span data-ttu-id="ee524-289">RenameFile</span><span class="sxs-lookup"><span data-stu-id="ee524-289">RenameFile</span></span>|<span data-ttu-id="ee524-290">3</span><span class="sxs-lookup"><span data-stu-id="ee524-290">3</span></span>|  
|<span data-ttu-id="ee524-291">SetAttributes</span><span class="sxs-lookup"><span data-stu-id="ee524-291">SetAttributes</span></span>|<span data-ttu-id="ee524-292">4</span><span class="sxs-lookup"><span data-stu-id="ee524-292">4</span></span>|  
|<span data-ttu-id="ee524-293">CreateDirectory</span><span class="sxs-lookup"><span data-stu-id="ee524-293">CreateDirectory</span></span>|<span data-ttu-id="ee524-294">5</span><span class="sxs-lookup"><span data-stu-id="ee524-294">5</span></span>|  
|<span data-ttu-id="ee524-295">CopyDirectory</span><span class="sxs-lookup"><span data-stu-id="ee524-295">CopyDirectory</span></span>|<span data-ttu-id="ee524-296">6</span><span class="sxs-lookup"><span data-stu-id="ee524-296">6</span></span>|  
|<span data-ttu-id="ee524-297">MoveDirectory</span><span class="sxs-lookup"><span data-stu-id="ee524-297">MoveDirectory</span></span>|<span data-ttu-id="ee524-298">7</span><span class="sxs-lookup"><span data-stu-id="ee524-298">7</span></span>|  
|<span data-ttu-id="ee524-299">DeleteDirectory</span><span class="sxs-lookup"><span data-stu-id="ee524-299">DeleteDirectory</span></span>|<span data-ttu-id="ee524-300">8</span><span class="sxs-lookup"><span data-stu-id="ee524-300">8</span></span>|  
|<span data-ttu-id="ee524-301">DeleteDirectoryContent</span><span class="sxs-lookup"><span data-stu-id="ee524-301">DeleteDirectoryContent</span></span>|<span data-ttu-id="ee524-302">9</span><span class="sxs-lookup"><span data-stu-id="ee524-302">9</span></span>|  
  
 <span data-ttu-id="ee524-303">`Attributes`Eigenschaften Satz mithilfe von Werten aus der- `DTSFileSystemAttributes` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-303">`Attributes` property-Set by using values from the `DTSFileSystemAttributes` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-304">Anzeigename in DTSFileSystemAttributes</span><span class="sxs-lookup"><span data-stu-id="ee524-304">Friendly name in DTSFileSystemAttributes</span></span>|<span data-ttu-id="ee524-305">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-305">Numeric value</span></span>|  
|----------------------------------------------|-------------------|  
|<span data-ttu-id="ee524-306">Normal</span><span class="sxs-lookup"><span data-stu-id="ee524-306">Normal</span></span>|<span data-ttu-id="ee524-307">0</span><span class="sxs-lookup"><span data-stu-id="ee524-307">0</span></span>|  
|<span data-ttu-id="ee524-308">Archivieren</span><span class="sxs-lookup"><span data-stu-id="ee524-308">Archive</span></span>|<span data-ttu-id="ee524-309">1</span><span class="sxs-lookup"><span data-stu-id="ee524-309">1</span></span>|  
|<span data-ttu-id="ee524-310">Ausgeblendet</span><span class="sxs-lookup"><span data-stu-id="ee524-310">Hidden</span></span>|<span data-ttu-id="ee524-311">2</span><span class="sxs-lookup"><span data-stu-id="ee524-311">2</span></span>|  
|<span data-ttu-id="ee524-312">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="ee524-312">ReadOnly</span></span>|<span data-ttu-id="ee524-313">4</span><span class="sxs-lookup"><span data-stu-id="ee524-313">4</span></span>|  
|<span data-ttu-id="ee524-314">System</span><span class="sxs-lookup"><span data-stu-id="ee524-314">System</span></span>|<span data-ttu-id="ee524-315">8</span><span class="sxs-lookup"><span data-stu-id="ee524-315">8</span></span>|  
  
### <a name="ftp-task"></a><span data-ttu-id="ee524-316">FTP-Task</span><span class="sxs-lookup"><span data-stu-id="ee524-316">FTP Task</span></span>  
 <span data-ttu-id="ee524-317">`Operation`Eigenschaften Satz mithilfe von Werten aus der- `DTSFTPOp` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-317">`Operation` property-Set by using values from the `DTSFTPOp` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-318">Anzeigename in DTSFTPOp</span><span class="sxs-lookup"><span data-stu-id="ee524-318">Friendly name in DTSFTPOp</span></span>|<span data-ttu-id="ee524-319">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-319">Numeric value</span></span>|  
|-------------------------------|-------------------|  
|<span data-ttu-id="ee524-320">Send</span><span class="sxs-lookup"><span data-stu-id="ee524-320">Send</span></span>|<span data-ttu-id="ee524-321">0</span><span class="sxs-lookup"><span data-stu-id="ee524-321">0</span></span>|  
|<span data-ttu-id="ee524-322">Empfangen</span><span class="sxs-lookup"><span data-stu-id="ee524-322">Receive</span></span>|<span data-ttu-id="ee524-323">1</span><span class="sxs-lookup"><span data-stu-id="ee524-323">1</span></span>|  
|<span data-ttu-id="ee524-324">DeleteLocal</span><span class="sxs-lookup"><span data-stu-id="ee524-324">DeleteLocal</span></span>|<span data-ttu-id="ee524-325">2</span><span class="sxs-lookup"><span data-stu-id="ee524-325">2</span></span>|  
|<span data-ttu-id="ee524-326">DeleteRemote</span><span class="sxs-lookup"><span data-stu-id="ee524-326">DeleteRemote</span></span>|<span data-ttu-id="ee524-327">3</span><span class="sxs-lookup"><span data-stu-id="ee524-327">3</span></span>|  
|<span data-ttu-id="ee524-328">MakeDirLocal</span><span class="sxs-lookup"><span data-stu-id="ee524-328">MakeDirLocal</span></span>|<span data-ttu-id="ee524-329">4</span><span class="sxs-lookup"><span data-stu-id="ee524-329">4</span></span>|  
|<span data-ttu-id="ee524-330">MakeDirRemote</span><span class="sxs-lookup"><span data-stu-id="ee524-330">MakeDirRemote</span></span>|<span data-ttu-id="ee524-331">5</span><span class="sxs-lookup"><span data-stu-id="ee524-331">5</span></span>|  
|<span data-ttu-id="ee524-332">RemoveDirLocal</span><span class="sxs-lookup"><span data-stu-id="ee524-332">RemoveDirLocal</span></span>|<span data-ttu-id="ee524-333">6</span><span class="sxs-lookup"><span data-stu-id="ee524-333">6</span></span>|  
|<span data-ttu-id="ee524-334">RemoveDirRemote</span><span class="sxs-lookup"><span data-stu-id="ee524-334">RemoveDirRemote</span></span>|<span data-ttu-id="ee524-335">7</span><span class="sxs-lookup"><span data-stu-id="ee524-335">7</span></span>|  
  
### <a name="message-queue-task"></a><span data-ttu-id="ee524-336">Message Queue Task</span><span class="sxs-lookup"><span data-stu-id="ee524-336">Message Queue Task</span></span>  
 <span data-ttu-id="ee524-337">`MessageType`Eigenschaften Satz mithilfe von Werten aus der- `MQMessageType` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-337">`MessageType` property-Set by using values from the `MQMessageType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-338">Anzeigename in MQMessageType</span><span class="sxs-lookup"><span data-stu-id="ee524-338">Friendly name in MQMessageType</span></span>|<span data-ttu-id="ee524-339">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-339">Numeric value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="ee524-340">DTSMQMessageType_String</span><span class="sxs-lookup"><span data-stu-id="ee524-340">DTSMQMessageType_String</span></span>|<span data-ttu-id="ee524-341">0</span><span class="sxs-lookup"><span data-stu-id="ee524-341">0</span></span>|  
|<span data-ttu-id="ee524-342">DTSMQMessageType_DataFile</span><span class="sxs-lookup"><span data-stu-id="ee524-342">DTSMQMessageType_DataFile</span></span>|<span data-ttu-id="ee524-343">1</span><span class="sxs-lookup"><span data-stu-id="ee524-343">1</span></span>|  
|<span data-ttu-id="ee524-344">DTSMQMessageType_Variables</span><span class="sxs-lookup"><span data-stu-id="ee524-344">DTSMQMessageType_Variables</span></span>|<span data-ttu-id="ee524-345">2</span><span class="sxs-lookup"><span data-stu-id="ee524-345">2</span></span>|  
|<span data-ttu-id="ee524-346">DTSMQMessagType_StringMessageToVariable</span><span class="sxs-lookup"><span data-stu-id="ee524-346">DTSMQMessagType_StringMessageToVariable</span></span>|<span data-ttu-id="ee524-347">3</span><span class="sxs-lookup"><span data-stu-id="ee524-347">3</span></span>|  
  
 <span data-ttu-id="ee524-348">`StringCompareType`Eigenschaften Satz mithilfe von Werten aus der- `MQStringMessageCompare` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-348">`StringCompareType` property-Set by using values from the `MQStringMessageCompare` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-349">Anzeigename in MQStringMessageCompare</span><span class="sxs-lookup"><span data-stu-id="ee524-349">Friendly name in MQStringMessageCompare</span></span>|<span data-ttu-id="ee524-350">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-350">Numeric value</span></span>|  
|---------------------------------------------|-------------------|  
|<span data-ttu-id="ee524-351">DTSMQStringMessageCompare_None</span><span class="sxs-lookup"><span data-stu-id="ee524-351">DTSMQStringMessageCompare_None</span></span>|<span data-ttu-id="ee524-352">0</span><span class="sxs-lookup"><span data-stu-id="ee524-352">0</span></span>|  
|<span data-ttu-id="ee524-353">DTSMQStringMessageCompare_Exact</span><span class="sxs-lookup"><span data-stu-id="ee524-353">DTSMQStringMessageCompare_Exact</span></span>|<span data-ttu-id="ee524-354">1</span><span class="sxs-lookup"><span data-stu-id="ee524-354">1</span></span>|  
|<span data-ttu-id="ee524-355">DTSMQStringMessageCompare_IgnoreCase</span><span class="sxs-lookup"><span data-stu-id="ee524-355">DTSMQStringMessageCompare_IgnoreCase</span></span>|<span data-ttu-id="ee524-356">2</span><span class="sxs-lookup"><span data-stu-id="ee524-356">2</span></span>|  
|<span data-ttu-id="ee524-357">DTSMQStringMessageCompare_Contains</span><span class="sxs-lookup"><span data-stu-id="ee524-357">DTSMQStringMessageCompare_Contains</span></span>|<span data-ttu-id="ee524-358">3</span><span class="sxs-lookup"><span data-stu-id="ee524-358">3</span></span>|  
  
 <span data-ttu-id="ee524-359">`TaskType`Eigenschaften Satz mithilfe von Werten aus der- `MQType` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-359">`TaskType` property-Set by using values from the `MQType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-360">Anzeigename in MQType</span><span class="sxs-lookup"><span data-stu-id="ee524-360">Friendly name in MQType</span></span>|<span data-ttu-id="ee524-361">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-361">Numeric value</span></span>|  
|-----------------------------|-------------------|  
|<span data-ttu-id="ee524-362">DTSMQType_Sender</span><span class="sxs-lookup"><span data-stu-id="ee524-362">DTSMQType_Sender</span></span>|<span data-ttu-id="ee524-363">0</span><span class="sxs-lookup"><span data-stu-id="ee524-363">0</span></span>|  
|<span data-ttu-id="ee524-364">DTSMQType_Receiver</span><span class="sxs-lookup"><span data-stu-id="ee524-364">DTSMQType_Receiver</span></span>|<span data-ttu-id="ee524-365">1</span><span class="sxs-lookup"><span data-stu-id="ee524-365">1</span></span>|  
  
### <a name="send-mail-task"></a><span data-ttu-id="ee524-366">Mail senden (Task)</span><span class="sxs-lookup"><span data-stu-id="ee524-366">Send Mail Task</span></span>  
 <span data-ttu-id="ee524-367">`MessageSourceType`Eigenschaften Satz mithilfe von Werten aus der- `SendMailMessageSourceType` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-367">`MessageSourceType` property-Set by using values from the `SendMailMessageSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-368">Anzeigename in SendMailMessageSourceType</span><span class="sxs-lookup"><span data-stu-id="ee524-368">Friendly Name in SendMailMessageSourceType</span></span>|<span data-ttu-id="ee524-369">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-369">Numeric Value</span></span>|  
|------------------------------------------------|-------------------|  
|<span data-ttu-id="ee524-370">DirectInput</span><span class="sxs-lookup"><span data-stu-id="ee524-370">DirectInput</span></span>|<span data-ttu-id="ee524-371">0</span><span class="sxs-lookup"><span data-stu-id="ee524-371">0</span></span>|  
|<span data-ttu-id="ee524-372">FileConnection</span><span class="sxs-lookup"><span data-stu-id="ee524-372">FileConnection</span></span>|<span data-ttu-id="ee524-373">1</span><span class="sxs-lookup"><span data-stu-id="ee524-373">1</span></span>|  
|<span data-ttu-id="ee524-374">Variable</span><span class="sxs-lookup"><span data-stu-id="ee524-374">Variable</span></span>|<span data-ttu-id="ee524-375">2</span><span class="sxs-lookup"><span data-stu-id="ee524-375">2</span></span>|  
  
 <span data-ttu-id="ee524-376">`Priority`Eigenschaften Satz mithilfe von Werten aus der- `MailPriority` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-376">`Priority` property-Set by using values from the `MailPriority` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-377">Anzeigename in MailPriority</span><span class="sxs-lookup"><span data-stu-id="ee524-377">Friendly Name in MailPriority</span></span>|<span data-ttu-id="ee524-378">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-378">Numeric Value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="ee524-379">High</span><span class="sxs-lookup"><span data-stu-id="ee524-379">High</span></span>|<span data-ttu-id="ee524-380">1</span><span class="sxs-lookup"><span data-stu-id="ee524-380">1</span></span>|  
|<span data-ttu-id="ee524-381">Normal</span><span class="sxs-lookup"><span data-stu-id="ee524-381">Normal</span></span>|<span data-ttu-id="ee524-382">3</span><span class="sxs-lookup"><span data-stu-id="ee524-382">3</span></span>|  
|<span data-ttu-id="ee524-383">Niedrig</span><span class="sxs-lookup"><span data-stu-id="ee524-383">Low</span></span>|<span data-ttu-id="ee524-384">5</span><span class="sxs-lookup"><span data-stu-id="ee524-384">5</span></span>|  
  
### <a name="transfer-database-task"></a><span data-ttu-id="ee524-385">Datenbanken übertragen (Task)</span><span class="sxs-lookup"><span data-stu-id="ee524-385">Transfer Database Task</span></span>  
 <span data-ttu-id="ee524-386">`Action`Eigenschaften Satz mithilfe von Werten aus der- `TransferAction` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-386">`Action` property-Set by using values from the `TransferAction` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-387">Anzeigename in TransferAction</span><span class="sxs-lookup"><span data-stu-id="ee524-387">Friendly name in TransferAction</span></span>|<span data-ttu-id="ee524-388">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-388">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="ee524-389">Kopieren</span><span class="sxs-lookup"><span data-stu-id="ee524-389">Copy</span></span>|<span data-ttu-id="ee524-390">0</span><span class="sxs-lookup"><span data-stu-id="ee524-390">0</span></span>|  
|<span data-ttu-id="ee524-391">Move</span><span class="sxs-lookup"><span data-stu-id="ee524-391">Move</span></span>|<span data-ttu-id="ee524-392">1</span><span class="sxs-lookup"><span data-stu-id="ee524-392">1</span></span>|  
  
 <span data-ttu-id="ee524-393">`Method`Eigenschaften Satz mithilfe von Werten aus der- `TransferMethod` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-393">`Method` property-Set by using values from the `TransferMethod` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-394">Anzeigename in TransferMethod</span><span class="sxs-lookup"><span data-stu-id="ee524-394">Friendly name in TransferMethod</span></span>|<span data-ttu-id="ee524-395">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-395">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="ee524-396">DatabaseOffline</span><span class="sxs-lookup"><span data-stu-id="ee524-396">DatabaseOffline</span></span>|<span data-ttu-id="ee524-397">0</span><span class="sxs-lookup"><span data-stu-id="ee524-397">0</span></span>|  
|<span data-ttu-id="ee524-398">DatabaseOnline</span><span class="sxs-lookup"><span data-stu-id="ee524-398">DatabaseOnline</span></span>|<span data-ttu-id="ee524-399">1</span><span class="sxs-lookup"><span data-stu-id="ee524-399">1</span></span>|  
  
### <a name="transfer-error-messages-task"></a><span data-ttu-id="ee524-400">Fehlermeldungen übertragen (Task)</span><span class="sxs-lookup"><span data-stu-id="ee524-400">Transfer Error Messages Task</span></span>  
 <span data-ttu-id="ee524-401">`IfObjectExists`Eigenschaften Satz mithilfe von Werten aus der- `IfObjectExists` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-401">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-402">Anzeigename in IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="ee524-402">Friendly Name in IfObjectExists</span></span>|<span data-ttu-id="ee524-403">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-403">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="ee524-404">FailTask</span><span class="sxs-lookup"><span data-stu-id="ee524-404">FailTask</span></span>|<span data-ttu-id="ee524-405">0</span><span class="sxs-lookup"><span data-stu-id="ee524-405">0</span></span>|  
|<span data-ttu-id="ee524-406">Overwrite</span><span class="sxs-lookup"><span data-stu-id="ee524-406">Overwrite</span></span>|<span data-ttu-id="ee524-407">1</span><span class="sxs-lookup"><span data-stu-id="ee524-407">1</span></span>|  
|<span data-ttu-id="ee524-408">Skip</span><span class="sxs-lookup"><span data-stu-id="ee524-408">Skip</span></span>|<span data-ttu-id="ee524-409">2</span><span class="sxs-lookup"><span data-stu-id="ee524-409">2</span></span>|  
  
### <a name="transfer-jobs-task"></a><span data-ttu-id="ee524-410">Aufträge übertragen (Task)</span><span class="sxs-lookup"><span data-stu-id="ee524-410">Transfer Jobs Task</span></span>  
 <span data-ttu-id="ee524-411">`IfObjectExists`Eigenschaften Satz mithilfe von Werten aus der- `IfObjectExists` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-411">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-412">Anzeigename in IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="ee524-412">Friendly Name in IfObjectExists</span></span>|<span data-ttu-id="ee524-413">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-413">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="ee524-414">FailTask</span><span class="sxs-lookup"><span data-stu-id="ee524-414">FailTask</span></span>|<span data-ttu-id="ee524-415">0</span><span class="sxs-lookup"><span data-stu-id="ee524-415">0</span></span>|  
|<span data-ttu-id="ee524-416">Overwrite</span><span class="sxs-lookup"><span data-stu-id="ee524-416">Overwrite</span></span>|<span data-ttu-id="ee524-417">1</span><span class="sxs-lookup"><span data-stu-id="ee524-417">1</span></span>|  
|<span data-ttu-id="ee524-418">Skip</span><span class="sxs-lookup"><span data-stu-id="ee524-418">Skip</span></span>|<span data-ttu-id="ee524-419">2</span><span class="sxs-lookup"><span data-stu-id="ee524-419">2</span></span>|  
  
### <a name="transfer-logins-task"></a><span data-ttu-id="ee524-420">Task "Anmeldungen übertragen"</span><span class="sxs-lookup"><span data-stu-id="ee524-420">Transfer Logins Task</span></span>  
 <span data-ttu-id="ee524-421">`IfObjectExists`Eigenschaften Satz mithilfe von Werten aus der- `IfObjectExists` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-421">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-422">Anzeigename in IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="ee524-422">Friendly name in IfObjectExists</span></span>|<span data-ttu-id="ee524-423">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-423">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="ee524-424">FailTask</span><span class="sxs-lookup"><span data-stu-id="ee524-424">FailTask</span></span>|<span data-ttu-id="ee524-425">0</span><span class="sxs-lookup"><span data-stu-id="ee524-425">0</span></span>|  
|<span data-ttu-id="ee524-426">Overwrite</span><span class="sxs-lookup"><span data-stu-id="ee524-426">Overwrite</span></span>|<span data-ttu-id="ee524-427">1</span><span class="sxs-lookup"><span data-stu-id="ee524-427">1</span></span>|  
|<span data-ttu-id="ee524-428">Skip</span><span class="sxs-lookup"><span data-stu-id="ee524-428">Skip</span></span>|<span data-ttu-id="ee524-429">2</span><span class="sxs-lookup"><span data-stu-id="ee524-429">2</span></span>|  
  
 <span data-ttu-id="ee524-430">`LoginsToTransfer`Eigenschaften Satz mithilfe von Werten aus der- `LoginsToTransfer` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-430">`LoginsToTransfer` property-Set by using values from the `LoginsToTransfer` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-431">Anzeigename in LoginsToTransfer</span><span class="sxs-lookup"><span data-stu-id="ee524-431">Friendly name in LoginsToTransfer</span></span>|<span data-ttu-id="ee524-432">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-432">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="ee524-433">AllLogins</span><span class="sxs-lookup"><span data-stu-id="ee524-433">AllLogins</span></span>|<span data-ttu-id="ee524-434">0</span><span class="sxs-lookup"><span data-stu-id="ee524-434">0</span></span>|  
|<span data-ttu-id="ee524-435">SelectedLogins</span><span class="sxs-lookup"><span data-stu-id="ee524-435">SelectedLogins</span></span>|<span data-ttu-id="ee524-436">1</span><span class="sxs-lookup"><span data-stu-id="ee524-436">1</span></span>|  
|<span data-ttu-id="ee524-437">AllLoginsFromSelectedDatabases</span><span class="sxs-lookup"><span data-stu-id="ee524-437">AllLoginsFromSelectedDatabases</span></span>|<span data-ttu-id="ee524-438">2</span><span class="sxs-lookup"><span data-stu-id="ee524-438">2</span></span>|  
  
### <a name="transfer-master-stored-procedures-task"></a><span data-ttu-id="ee524-439">In master gespeicherte Prozeduren übertragen (Task)</span><span class="sxs-lookup"><span data-stu-id="ee524-439">Transfer Master Stored Procedures Task</span></span>  
 <span data-ttu-id="ee524-440">`IfObjectExists`Eigenschaften Satz mithilfe von Werten aus der- `IfObjectExists` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-440">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-441">Anzeigename in IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="ee524-441">Friendly name in IfObjectExists</span></span>|<span data-ttu-id="ee524-442">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-442">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="ee524-443">FailTask</span><span class="sxs-lookup"><span data-stu-id="ee524-443">FailTask</span></span>|<span data-ttu-id="ee524-444">0</span><span class="sxs-lookup"><span data-stu-id="ee524-444">0</span></span>|  
|<span data-ttu-id="ee524-445">Overwrite</span><span class="sxs-lookup"><span data-stu-id="ee524-445">Overwrite</span></span>|<span data-ttu-id="ee524-446">1</span><span class="sxs-lookup"><span data-stu-id="ee524-446">1</span></span>|  
|<span data-ttu-id="ee524-447">Skip</span><span class="sxs-lookup"><span data-stu-id="ee524-447">Skip</span></span>|<span data-ttu-id="ee524-448">2</span><span class="sxs-lookup"><span data-stu-id="ee524-448">2</span></span>|  
  
### <a name="transfer-sql-server-objects-task"></a><span data-ttu-id="ee524-449">SQL Server-Objekte kopieren (Task)</span><span class="sxs-lookup"><span data-stu-id="ee524-449">Transfer SQL Server Objects Task</span></span>  
 <span data-ttu-id="ee524-450">`ExistingData`Eigenschaften Satz mithilfe von Werten aus der- `ExistingData` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-450">`ExistingData` property-Set by using values from the `ExistingData` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-451">Anzeigename in ExistingData</span><span class="sxs-lookup"><span data-stu-id="ee524-451">Friendly name in ExistingData</span></span>|<span data-ttu-id="ee524-452">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-452">Numeric Value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="ee524-453">Replace</span><span class="sxs-lookup"><span data-stu-id="ee524-453">Replace</span></span>|<span data-ttu-id="ee524-454">0</span><span class="sxs-lookup"><span data-stu-id="ee524-454">0</span></span>|  
|<span data-ttu-id="ee524-455">Anfügen</span><span class="sxs-lookup"><span data-stu-id="ee524-455">Append</span></span>|<span data-ttu-id="ee524-456">1</span><span class="sxs-lookup"><span data-stu-id="ee524-456">1</span></span>|  
  
### <a name="web-service-task"></a><span data-ttu-id="ee524-457">Webdienst (Task)</span><span class="sxs-lookup"><span data-stu-id="ee524-457">Web Service Task</span></span>  
 <span data-ttu-id="ee524-458">`OutputType`Eigenschaften Satz mithilfe von Werten aus der- `DTSOutputType` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-458">`OutputType` property-Set by using values from the `DTSOutputType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-459">Anzeigename in DTSOutputType</span><span class="sxs-lookup"><span data-stu-id="ee524-459">Friendly name in DTSOutputType</span></span>|<span data-ttu-id="ee524-460">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-460">Numeric value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="ee524-461">Datei</span><span class="sxs-lookup"><span data-stu-id="ee524-461">File</span></span>|<span data-ttu-id="ee524-462">0</span><span class="sxs-lookup"><span data-stu-id="ee524-462">0</span></span>|  
|<span data-ttu-id="ee524-463">Variable</span><span class="sxs-lookup"><span data-stu-id="ee524-463">Variable</span></span>|<span data-ttu-id="ee524-464">1</span><span class="sxs-lookup"><span data-stu-id="ee524-464">1</span></span>|  
  
### <a name="wmi-data-reader-task"></a><span data-ttu-id="ee524-465">WMI-Datenleser (Task)</span><span class="sxs-lookup"><span data-stu-id="ee524-465">WMI Data Reader Task</span></span>  
 <span data-ttu-id="ee524-466">`OverwriteDestination`Eigenschaften Satz mithilfe von Werten aus der- `OverwriteDestination` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-466">`OverwriteDestination` property-Set by using values from the `OverwriteDestination` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-467">Anzeigename in OverwriteDestination</span><span class="sxs-lookup"><span data-stu-id="ee524-467">Friendly name in OverwriteDestination</span></span>|<span data-ttu-id="ee524-468">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-468">Numeric value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="ee524-469">OverwriteDestination</span><span class="sxs-lookup"><span data-stu-id="ee524-469">OverwriteDestination</span></span>|<span data-ttu-id="ee524-470">0</span><span class="sxs-lookup"><span data-stu-id="ee524-470">0</span></span>|  
|<span data-ttu-id="ee524-471">AppendToDestination</span><span class="sxs-lookup"><span data-stu-id="ee524-471">AppendToDestination</span></span>|<span data-ttu-id="ee524-472">1</span><span class="sxs-lookup"><span data-stu-id="ee524-472">1</span></span>|  
|<span data-ttu-id="ee524-473">KeepOriginal</span><span class="sxs-lookup"><span data-stu-id="ee524-473">KeepOriginal</span></span>|<span data-ttu-id="ee524-474">2</span><span class="sxs-lookup"><span data-stu-id="ee524-474">2</span></span>|  
  
 <span data-ttu-id="ee524-475">`OutputType`Eigenschaften Satz mithilfe von Werten aus der- `OutputType` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-475">`OutputType` property-Set by using values from the `OutputType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-476">Anzeigename in OutputType</span><span class="sxs-lookup"><span data-stu-id="ee524-476">Friendly name in OutputType</span></span>|<span data-ttu-id="ee524-477">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-477">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="ee524-478">DataTable</span><span class="sxs-lookup"><span data-stu-id="ee524-478">DataTable</span></span>|<span data-ttu-id="ee524-479">0</span><span class="sxs-lookup"><span data-stu-id="ee524-479">0</span></span>|  
|<span data-ttu-id="ee524-480">PropertyValue</span><span class="sxs-lookup"><span data-stu-id="ee524-480">PropertyValue</span></span>|<span data-ttu-id="ee524-481">1</span><span class="sxs-lookup"><span data-stu-id="ee524-481">1</span></span>|  
|<span data-ttu-id="ee524-482">PropertyNameAndValue</span><span class="sxs-lookup"><span data-stu-id="ee524-482">PropertyNameAndValue</span></span>|<span data-ttu-id="ee524-483">2</span><span class="sxs-lookup"><span data-stu-id="ee524-483">2</span></span>|  
  
 <span data-ttu-id="ee524-484">`DestinationType`Eigenschaften Satz mithilfe von Werten aus der- `DestinationType` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-484">`DestinationType` property-Set by using values from the `DestinationType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-485">Anzeigename in DestinationType</span><span class="sxs-lookup"><span data-stu-id="ee524-485">Friendly name in DestinationType</span></span>|<span data-ttu-id="ee524-486">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-486">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="ee524-487">FileConnection</span><span class="sxs-lookup"><span data-stu-id="ee524-487">FileConnection</span></span>|<span data-ttu-id="ee524-488">0</span><span class="sxs-lookup"><span data-stu-id="ee524-488">0</span></span>|  
|<span data-ttu-id="ee524-489">Variable</span><span class="sxs-lookup"><span data-stu-id="ee524-489">Variable</span></span>|<span data-ttu-id="ee524-490">1</span><span class="sxs-lookup"><span data-stu-id="ee524-490">1</span></span>|  
  
 <span data-ttu-id="ee524-491">`WqlQuerySourceType`Eigenschaften Satz mithilfe von Werten aus der- `QuerySourceType` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-491">`WqlQuerySourceType` property-Set by using values from the `QuerySourceType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-492">Anzeigename in QuerySourceType</span><span class="sxs-lookup"><span data-stu-id="ee524-492">Friendly Name in QuerySourceType</span></span>|<span data-ttu-id="ee524-493">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-493">Numeric Value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="ee524-494">FileConnection</span><span class="sxs-lookup"><span data-stu-id="ee524-494">FileConnection</span></span>|<span data-ttu-id="ee524-495">0</span><span class="sxs-lookup"><span data-stu-id="ee524-495">0</span></span>|  
|<span data-ttu-id="ee524-496">DirectInput</span><span class="sxs-lookup"><span data-stu-id="ee524-496">DirectInput</span></span>|<span data-ttu-id="ee524-497">1</span><span class="sxs-lookup"><span data-stu-id="ee524-497">1</span></span>|  
|<span data-ttu-id="ee524-498">Variable</span><span class="sxs-lookup"><span data-stu-id="ee524-498">Variable</span></span>|<span data-ttu-id="ee524-499">2</span><span class="sxs-lookup"><span data-stu-id="ee524-499">2</span></span>|  
  
 <span data-ttu-id="ee524-500">Eigenschaft "WMI-Ereignisüberwachung", `ActionAtEvent` die mithilfe von Werten aus der-Enumeration festgelegt wird `ActionAtEvent` .</span><span class="sxs-lookup"><span data-stu-id="ee524-500">WMI Event Watcher `ActionAtEvent` property-Set by using values from the `ActionAtEvent` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-501">Anzeigename in ActionAtEvent</span><span class="sxs-lookup"><span data-stu-id="ee524-501">Friendly Name in ActionAtEvent</span></span>|<span data-ttu-id="ee524-502">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-502">Numeric Value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="ee524-503">LogTheEventAndFireDTSEvent</span><span class="sxs-lookup"><span data-stu-id="ee524-503">LogTheEventAndFireDTSEvent</span></span>|<span data-ttu-id="ee524-504">0</span><span class="sxs-lookup"><span data-stu-id="ee524-504">0</span></span>|  
|<span data-ttu-id="ee524-505">LogTheEvent</span><span class="sxs-lookup"><span data-stu-id="ee524-505">LogTheEvent</span></span>|<span data-ttu-id="ee524-506">1</span><span class="sxs-lookup"><span data-stu-id="ee524-506">1</span></span>|  
  
 <span data-ttu-id="ee524-507">`ActionAtTimeout`Eigenschaften Satz mithilfe von Werten aus der- `ActionAtTimeout` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-507">`ActionAtTimeout` property-Set by using values from the `ActionAtTimeout` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-508">Anzeigename in ActionAtTimeout</span><span class="sxs-lookup"><span data-stu-id="ee524-508">Friendly name in ActionAtTimeout</span></span>|<span data-ttu-id="ee524-509">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-509">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="ee524-510">LogTimeoutAndFireDTSEvent</span><span class="sxs-lookup"><span data-stu-id="ee524-510">LogTimeoutAndFireDTSEvent</span></span>|<span data-ttu-id="ee524-511">0</span><span class="sxs-lookup"><span data-stu-id="ee524-511">0</span></span>|  
|<span data-ttu-id="ee524-512">LogTimeout</span><span class="sxs-lookup"><span data-stu-id="ee524-512">LogTimeout</span></span>|<span data-ttu-id="ee524-513">1</span><span class="sxs-lookup"><span data-stu-id="ee524-513">1</span></span>|  
  
 <span data-ttu-id="ee524-514">`AfterEvent`Eigenschaften Satz mithilfe von Werten aus der- `AfterEvent` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-514">`AfterEvent` property-Set by using values from the `AfterEvent` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-515">Anzeigename in AfterEvent</span><span class="sxs-lookup"><span data-stu-id="ee524-515">Friendly name in AfterEvent</span></span>|<span data-ttu-id="ee524-516">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-516">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="ee524-517">ReturnWithSuccess</span><span class="sxs-lookup"><span data-stu-id="ee524-517">ReturnWithSuccess</span></span>|<span data-ttu-id="ee524-518">0</span><span class="sxs-lookup"><span data-stu-id="ee524-518">0</span></span>|  
|<span data-ttu-id="ee524-519">ReturnWithFailure</span><span class="sxs-lookup"><span data-stu-id="ee524-519">ReturnWithFailure</span></span>|<span data-ttu-id="ee524-520">1</span><span class="sxs-lookup"><span data-stu-id="ee524-520">1</span></span>|  
|<span data-ttu-id="ee524-521">WatchfortheEventAgain</span><span class="sxs-lookup"><span data-stu-id="ee524-521">WatchfortheEventAgain</span></span>|<span data-ttu-id="ee524-522">2</span><span class="sxs-lookup"><span data-stu-id="ee524-522">2</span></span>|  
  
 <span data-ttu-id="ee524-523">`AfterTimeout`Eigenschaften Satz mithilfe von Werten aus der- `AfterTimeout` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-523">`AfterTimeout` property-Set by using values from the `AfterTimeout` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-524">Anzeigename in AfterTimeout</span><span class="sxs-lookup"><span data-stu-id="ee524-524">Friendly name in AfterTimeout</span></span>|<span data-ttu-id="ee524-525">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-525">Numeric value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="ee524-526">ReturnWithSuccess</span><span class="sxs-lookup"><span data-stu-id="ee524-526">ReturnWithSuccess</span></span>|<span data-ttu-id="ee524-527">0</span><span class="sxs-lookup"><span data-stu-id="ee524-527">0</span></span>|  
|<span data-ttu-id="ee524-528">ReturnWithFailure</span><span class="sxs-lookup"><span data-stu-id="ee524-528">ReturnWithFailure</span></span>|<span data-ttu-id="ee524-529">1</span><span class="sxs-lookup"><span data-stu-id="ee524-529">1</span></span>|  
|<span data-ttu-id="ee524-530">WatchfortheEventAgain</span><span class="sxs-lookup"><span data-stu-id="ee524-530">WatchfortheEventAgain</span></span>|<span data-ttu-id="ee524-531">2</span><span class="sxs-lookup"><span data-stu-id="ee524-531">2</span></span>|  
  
 <span data-ttu-id="ee524-532">`WqlQuerySourceType`Eigenschaften Satz mithilfe von Werten aus der- `QuerySourceType` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-532">`WqlQuerySourceType` property-Set by using values from the `QuerySourceType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-533">Anzeigename in QuerySourceType</span><span class="sxs-lookup"><span data-stu-id="ee524-533">Friendly name in QuerySourceType</span></span>|<span data-ttu-id="ee524-534">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-534">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="ee524-535">FileConnection</span><span class="sxs-lookup"><span data-stu-id="ee524-535">FileConnection</span></span>|<span data-ttu-id="ee524-536">0</span><span class="sxs-lookup"><span data-stu-id="ee524-536">0</span></span>|  
|<span data-ttu-id="ee524-537">DirectInput</span><span class="sxs-lookup"><span data-stu-id="ee524-537">DirectInput</span></span>|<span data-ttu-id="ee524-538">1</span><span class="sxs-lookup"><span data-stu-id="ee524-538">1</span></span>|  
|<span data-ttu-id="ee524-539">Variable</span><span class="sxs-lookup"><span data-stu-id="ee524-539">Variable</span></span>|<span data-ttu-id="ee524-540">2</span><span class="sxs-lookup"><span data-stu-id="ee524-540">2</span></span>|  
  
### <a name="xml-task"></a><span data-ttu-id="ee524-541">XML-Task</span><span class="sxs-lookup"><span data-stu-id="ee524-541">XML Task</span></span>  
 <span data-ttu-id="ee524-542">`OperationType`Eigenschaften Satz mithilfe von Werten aus der- `DTSXMLOperation` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-542">`OperationType` property-Set by using values from the `DTSXMLOperation` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-543">Anzeigename in DTSXMLOperation</span><span class="sxs-lookup"><span data-stu-id="ee524-543">Friendly name in DTSXMLOperation</span></span>|<span data-ttu-id="ee524-544">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-544">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="ee524-545">Überprüfen</span><span class="sxs-lookup"><span data-stu-id="ee524-545">Validate</span></span>|<span data-ttu-id="ee524-546">0</span><span class="sxs-lookup"><span data-stu-id="ee524-546">0</span></span>|  
|<span data-ttu-id="ee524-547">XSLT</span><span class="sxs-lookup"><span data-stu-id="ee524-547">XSLT</span></span>|<span data-ttu-id="ee524-548">1</span><span class="sxs-lookup"><span data-stu-id="ee524-548">1</span></span>|  
|<span data-ttu-id="ee524-549">XPATH</span><span class="sxs-lookup"><span data-stu-id="ee524-549">XPATH</span></span>|<span data-ttu-id="ee524-550">2</span><span class="sxs-lookup"><span data-stu-id="ee524-550">2</span></span>|  
|<span data-ttu-id="ee524-551">Merge</span><span class="sxs-lookup"><span data-stu-id="ee524-551">Merge</span></span>|<span data-ttu-id="ee524-552">3</span><span class="sxs-lookup"><span data-stu-id="ee524-552">3</span></span>|  
|<span data-ttu-id="ee524-553">Diff</span><span class="sxs-lookup"><span data-stu-id="ee524-553">Diff</span></span>|<span data-ttu-id="ee524-554">4</span><span class="sxs-lookup"><span data-stu-id="ee524-554">4</span></span>|  
|<span data-ttu-id="ee524-555">Patch</span><span class="sxs-lookup"><span data-stu-id="ee524-555">Patch</span></span>|<span data-ttu-id="ee524-556">5</span><span class="sxs-lookup"><span data-stu-id="ee524-556">5</span></span>|  
  
 <span data-ttu-id="ee524-557">`SourceType``SecondOperandType` `XPathSourceType` -,-und-Eigenschaften, die mithilfe von Werten aus der-Enumeration festgelegt werden `DTSXMLSourceType` .</span><span class="sxs-lookup"><span data-stu-id="ee524-557">`SourceType`, `SecondOperandType`, and `XPathSourceType` properties-Set by using values from the `DTSXMLSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-558">Anzeigename in DTSXMLSourceType</span><span class="sxs-lookup"><span data-stu-id="ee524-558">Friendly name in DTSXMLSourceType</span></span>|<span data-ttu-id="ee524-559">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-559">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="ee524-560">FileConnection</span><span class="sxs-lookup"><span data-stu-id="ee524-560">FileConnection</span></span>|<span data-ttu-id="ee524-561">0</span><span class="sxs-lookup"><span data-stu-id="ee524-561">0</span></span>|  
|<span data-ttu-id="ee524-562">Variable</span><span class="sxs-lookup"><span data-stu-id="ee524-562">Variable</span></span>|<span data-ttu-id="ee524-563">1</span><span class="sxs-lookup"><span data-stu-id="ee524-563">1</span></span>|  
|<span data-ttu-id="ee524-564">DirectInput</span><span class="sxs-lookup"><span data-stu-id="ee524-564">DirectInput</span></span>|<span data-ttu-id="ee524-565">2</span><span class="sxs-lookup"><span data-stu-id="ee524-565">2</span></span>|  
  
 <span data-ttu-id="ee524-566">`DestinationType`und **diffgrammdestinationtype** -Eigenschaften, die mithilfe von Werten aus der-Enumeration festgelegt werden `DTSXMLSaveResultTo` .</span><span class="sxs-lookup"><span data-stu-id="ee524-566">`DestinationType` and **DiffGramDestinationType** properties-Set by using values from the `DTSXMLSaveResultTo` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-567">Anzeigename in DTSXMLSaveResultTo</span><span class="sxs-lookup"><span data-stu-id="ee524-567">Friendly name in DTSXMLSaveResultTo</span></span>|<span data-ttu-id="ee524-568">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-568">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="ee524-569">FileConnection</span><span class="sxs-lookup"><span data-stu-id="ee524-569">FileConnection</span></span>|<span data-ttu-id="ee524-570">0</span><span class="sxs-lookup"><span data-stu-id="ee524-570">0</span></span>|  
|<span data-ttu-id="ee524-571">Variable</span><span class="sxs-lookup"><span data-stu-id="ee524-571">Variable</span></span>|<span data-ttu-id="ee524-572">1</span><span class="sxs-lookup"><span data-stu-id="ee524-572">1</span></span>|  
  
 <span data-ttu-id="ee524-573">`ValidationType`Eigenschaften Satz mithilfe von Werten aus der- `DTSXMLValidationType` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-573">`ValidationType` property-Set by using values from the `DTSXMLValidationType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-574">Anzeigename in DTSXMLValidationType</span><span class="sxs-lookup"><span data-stu-id="ee524-574">Friendly name in DTSXMLValidationType</span></span>|<span data-ttu-id="ee524-575">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-575">Numeric value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="ee524-576">DTD</span><span class="sxs-lookup"><span data-stu-id="ee524-576">DTD</span></span>|<span data-ttu-id="ee524-577">0</span><span class="sxs-lookup"><span data-stu-id="ee524-577">0</span></span>|  
|<span data-ttu-id="ee524-578">XSD</span><span class="sxs-lookup"><span data-stu-id="ee524-578">XSD</span></span>|<span data-ttu-id="ee524-579">1</span><span class="sxs-lookup"><span data-stu-id="ee524-579">1</span></span>|  
  
 <span data-ttu-id="ee524-580">`XPathOperation`Eigenschaften Satz mithilfe von Werten aus der- `DTSXMLXPathOperation` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-580">`XPathOperation` property-Set by using values from the `DTSXMLXPathOperation` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-581">Anzeigename in DTSXMLXPathOperation</span><span class="sxs-lookup"><span data-stu-id="ee524-581">Friendly name in DTSXMLXPathOperation</span></span>|<span data-ttu-id="ee524-582">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-582">Numeric Value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="ee524-583">Auswertung</span><span class="sxs-lookup"><span data-stu-id="ee524-583">Evaluation</span></span>|<span data-ttu-id="ee524-584">0</span><span class="sxs-lookup"><span data-stu-id="ee524-584">0</span></span>|  
|<span data-ttu-id="ee524-585">Werte</span><span class="sxs-lookup"><span data-stu-id="ee524-585">Values</span></span>|<span data-ttu-id="ee524-586">1</span><span class="sxs-lookup"><span data-stu-id="ee524-586">1</span></span>|  
|<span data-ttu-id="ee524-587">NodeList</span><span class="sxs-lookup"><span data-stu-id="ee524-587">NodeList</span></span>|<span data-ttu-id="ee524-588">2</span><span class="sxs-lookup"><span data-stu-id="ee524-588">2</span></span>|  
  
 <span data-ttu-id="ee524-589">`DiffOptions`Eigenschaften Satz mithilfe von Werten aus der- `DTSXMLDiffOptions` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-589">`DiffOptions` property-Set by using values from the `DTSXMLDiffOptions` enumeration.</span></span> <span data-ttu-id="ee524-590">Die Optionen in diesem Enumerator schließen sich nicht gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="ee524-590">The options in this enumerator are not mutually exclusive.</span></span> <span data-ttu-id="ee524-591">Stellen Sie eine durch Trennzeichen getrennte Liste der anzuwendenden Optionen bereit, um mehrere Optionen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ee524-591">To use multiple options, provide a comma-separated list of the options to apply.</span></span>  
  
|<span data-ttu-id="ee524-592">Anzeigename in DTSXMLDiffOptions</span><span class="sxs-lookup"><span data-stu-id="ee524-592">Friendly name in DTSXMLDiffOptions</span></span>|<span data-ttu-id="ee524-593">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-593">Numeric Value</span></span>|  
|----------------------------------------|-------------------|  
|<span data-ttu-id="ee524-594">Keine</span><span class="sxs-lookup"><span data-stu-id="ee524-594">None</span></span>|<span data-ttu-id="ee524-595">0</span><span class="sxs-lookup"><span data-stu-id="ee524-595">0</span></span>|  
|<span data-ttu-id="ee524-596">IgnoreChildOrder</span><span class="sxs-lookup"><span data-stu-id="ee524-596">IgnoreChildOrder</span></span>|<span data-ttu-id="ee524-597">1</span><span class="sxs-lookup"><span data-stu-id="ee524-597">1</span></span>|  
|<span data-ttu-id="ee524-598">IgnoreComments</span><span class="sxs-lookup"><span data-stu-id="ee524-598">IgnoreComments</span></span>|<span data-ttu-id="ee524-599">2</span><span class="sxs-lookup"><span data-stu-id="ee524-599">2</span></span>|  
|<span data-ttu-id="ee524-600">IgnorePI</span><span class="sxs-lookup"><span data-stu-id="ee524-600">IgnorePI</span></span>|<span data-ttu-id="ee524-601">4</span><span class="sxs-lookup"><span data-stu-id="ee524-601">4</span></span>|  
|<span data-ttu-id="ee524-602">IgnoreWhitespace</span><span class="sxs-lookup"><span data-stu-id="ee524-602">IgnoreWhitespace</span></span>|<span data-ttu-id="ee524-603">8</span><span class="sxs-lookup"><span data-stu-id="ee524-603">8</span></span>|  
|<span data-ttu-id="ee524-604">IgnoreNamespaces</span><span class="sxs-lookup"><span data-stu-id="ee524-604">IgnoreNamespaces</span></span>|<span data-ttu-id="ee524-605">16</span><span class="sxs-lookup"><span data-stu-id="ee524-605">16</span></span>|  
|<span data-ttu-id="ee524-606">IgnorePrefixes</span><span class="sxs-lookup"><span data-stu-id="ee524-606">IgnorePrefixes</span></span>|<span data-ttu-id="ee524-607">32</span><span class="sxs-lookup"><span data-stu-id="ee524-607">32</span></span>|  
|<span data-ttu-id="ee524-608">IgnoreXmlDecl</span><span class="sxs-lookup"><span data-stu-id="ee524-608">IgnoreXmlDecl</span></span>|<span data-ttu-id="ee524-609">64</span><span class="sxs-lookup"><span data-stu-id="ee524-609">64</span></span>|  
|<span data-ttu-id="ee524-610">IgnoreDtd</span><span class="sxs-lookup"><span data-stu-id="ee524-610">IgnoreDtd</span></span>|<span data-ttu-id="ee524-611">128</span><span class="sxs-lookup"><span data-stu-id="ee524-611">128</span></span>|  
  
 <span data-ttu-id="ee524-612">`DiffAlgorithm`Eigenschaften Satz mithilfe von Werten aus der- `DTSXMLDiffAlgorithm` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-612">`DiffAlgorithm` property-Set by using values from the `DTSXMLDiffAlgorithm` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-613">Anzeigename in DTSXMLDiffAlgorithm</span><span class="sxs-lookup"><span data-stu-id="ee524-613">Friendly name in DTSXMLDiffAlgorithm</span></span>|<span data-ttu-id="ee524-614">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-614">Numeric value</span></span>|  
|------------------------------------------|-------------------|  
|<span data-ttu-id="ee524-615">Auto</span><span class="sxs-lookup"><span data-stu-id="ee524-615">Auto</span></span>|<span data-ttu-id="ee524-616">0</span><span class="sxs-lookup"><span data-stu-id="ee524-616">0</span></span>|  
|<span data-ttu-id="ee524-617">Schnell</span><span class="sxs-lookup"><span data-stu-id="ee524-617">Fast</span></span>|<span data-ttu-id="ee524-618">1</span><span class="sxs-lookup"><span data-stu-id="ee524-618">1</span></span>|  
|<span data-ttu-id="ee524-619">Precise</span><span class="sxs-lookup"><span data-stu-id="ee524-619">Precise</span></span>|<span data-ttu-id="ee524-620">2</span><span class="sxs-lookup"><span data-stu-id="ee524-620">2</span></span>|  
  
##  <a name="maintenance-plan-tasks"></a><a name="MaintenancePlanTasks"></a> <span data-ttu-id="ee524-621">Wartungsplantasks</span><span class="sxs-lookup"><span data-stu-id="ee524-621">Maintenance Plan Tasks</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="ee524-622">enthält eine Reihe von Tasks, mit denen SQL Server-Tasks für die Verwendung in Wartungsplänen und [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paketen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ee524-622">includes a set of tasks that perform SQL Server tasks for use in maintenance plans and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ee524-623">unterstützt nicht die programmgesteuerte Verwendung dieser Tasks, und die Programmierungsreferenzdokumentation enthält keine API-Dokumentation dieser Tasks und ihrer zugehörigen Enumeratoren.</span><span class="sxs-lookup"><span data-stu-id="ee524-623">does not support working with these tasks programmatically and programming reference documentation does not include API documentation of these tasks and their enumerators.</span></span>  
  
### <a name="all-maintenance-tasks"></a><span data-ttu-id="ee524-624">Alle Wartungstasks</span><span class="sxs-lookup"><span data-stu-id="ee524-624">All Maintenance Tasks</span></span>  
 <span data-ttu-id="ee524-625">Die folgenden Enumerationen werden in allen Wartungstasks verwendet, um die angegebenen Eigenschaften festzulegen.</span><span class="sxs-lookup"><span data-stu-id="ee524-625">All maintenance tasks use the following enumerations to set the specified properties.</span></span>  
  
 <span data-ttu-id="ee524-626">`DatabaseSelectionType`Eigenschaften Satz mithilfe von Werten aus der- `DatabaseSelection` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-626">`DatabaseSelectionType` property-Set by using values from the `DatabaseSelection` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-627">Anzeigename in DatabaseSelection</span><span class="sxs-lookup"><span data-stu-id="ee524-627">Friendly name in DatabaseSelection</span></span>|<span data-ttu-id="ee524-628">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-628">Numeric value</span></span>|  
|----------------------------------------|-------------------|  
|<span data-ttu-id="ee524-629">Keine</span><span class="sxs-lookup"><span data-stu-id="ee524-629">None</span></span>|<span data-ttu-id="ee524-630">0</span><span class="sxs-lookup"><span data-stu-id="ee524-630">0</span></span>|  
|<span data-ttu-id="ee524-631">All</span><span class="sxs-lookup"><span data-stu-id="ee524-631">All</span></span>|<span data-ttu-id="ee524-632">1</span><span class="sxs-lookup"><span data-stu-id="ee524-632">1</span></span>|  
|<span data-ttu-id="ee524-633">System</span><span class="sxs-lookup"><span data-stu-id="ee524-633">System</span></span>|<span data-ttu-id="ee524-634">2</span><span class="sxs-lookup"><span data-stu-id="ee524-634">2</span></span>|  
|<span data-ttu-id="ee524-635">Benutzer</span><span class="sxs-lookup"><span data-stu-id="ee524-635">User</span></span>|<span data-ttu-id="ee524-636">3</span><span class="sxs-lookup"><span data-stu-id="ee524-636">3</span></span>|  
|<span data-ttu-id="ee524-637">Spezifisch</span><span class="sxs-lookup"><span data-stu-id="ee524-637">Specific</span></span>|<span data-ttu-id="ee524-638">4</span><span class="sxs-lookup"><span data-stu-id="ee524-638">4</span></span>|  
  
 <span data-ttu-id="ee524-639">`TableSelectionType`Eigenschaften Satz mithilfe von Werten aus der- `TableSelection` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-639">`TableSelectionType` property-Set by using values from the `TableSelection` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-640">Anzeigename in TableSelection</span><span class="sxs-lookup"><span data-stu-id="ee524-640">Friendly name in TableSelection</span></span>|<span data-ttu-id="ee524-641">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-641">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="ee524-642">Keine</span><span class="sxs-lookup"><span data-stu-id="ee524-642">None</span></span>|<span data-ttu-id="ee524-643">0</span><span class="sxs-lookup"><span data-stu-id="ee524-643">0</span></span>|  
|<span data-ttu-id="ee524-644">All</span><span class="sxs-lookup"><span data-stu-id="ee524-644">All</span></span>|<span data-ttu-id="ee524-645">1</span><span class="sxs-lookup"><span data-stu-id="ee524-645">1</span></span>|  
|<span data-ttu-id="ee524-646">Spezifisch</span><span class="sxs-lookup"><span data-stu-id="ee524-646">Specific</span></span>|<span data-ttu-id="ee524-647">2</span><span class="sxs-lookup"><span data-stu-id="ee524-647">2</span></span>|  
  
 <span data-ttu-id="ee524-648">`ObjectTypeSelection`Eigenschaften Satz mithilfe von Werten aus der- `ObjectType` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-648">`ObjectTypeSelection` property-Set by using values from the `ObjectType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-649">Anzeigename in ObjectType</span><span class="sxs-lookup"><span data-stu-id="ee524-649">Friendly name in ObjectType</span></span>|<span data-ttu-id="ee524-650">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-650">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="ee524-651">Tabelle</span><span class="sxs-lookup"><span data-stu-id="ee524-651">Table</span></span>|<span data-ttu-id="ee524-652">0</span><span class="sxs-lookup"><span data-stu-id="ee524-652">0</span></span>|  
|<span data-ttu-id="ee524-653">Sicht</span><span class="sxs-lookup"><span data-stu-id="ee524-653">View</span></span>|<span data-ttu-id="ee524-654">1</span><span class="sxs-lookup"><span data-stu-id="ee524-654">1</span></span>|  
|<span data-ttu-id="ee524-655">TableView</span><span class="sxs-lookup"><span data-stu-id="ee524-655">TableView</span></span>|<span data-ttu-id="ee524-656">2</span><span class="sxs-lookup"><span data-stu-id="ee524-656">2</span></span>|  
  
### <a name="back-up-database-task"></a><span data-ttu-id="ee524-657">Datenbank sichern (Task)</span><span class="sxs-lookup"><span data-stu-id="ee524-657">Back Up Database Task</span></span>  
 <span data-ttu-id="ee524-658">`DestinationCreationType`Eigenschaften Satz mithilfe von Werten aus der- `DestinationType` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-658">`DestinationCreationType` property-Set by using values from the `DestinationType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-659">Anzeigename in DestinationType</span><span class="sxs-lookup"><span data-stu-id="ee524-659">Friendly name in DestinationType</span></span>|<span data-ttu-id="ee524-660">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-660">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="ee524-661">Auto</span><span class="sxs-lookup"><span data-stu-id="ee524-661">Auto</span></span>|<span data-ttu-id="ee524-662">0</span><span class="sxs-lookup"><span data-stu-id="ee524-662">0</span></span>|  
|<span data-ttu-id="ee524-663">Manuell</span><span class="sxs-lookup"><span data-stu-id="ee524-663">Manual</span></span>|<span data-ttu-id="ee524-664">1</span><span class="sxs-lookup"><span data-stu-id="ee524-664">1</span></span>|  
  
 <span data-ttu-id="ee524-665">`ExistingBackupsAction`Eigenschaften Satz mithilfe von Werten aus der- `ActionForExistingBackups` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-665">`ExistingBackupsAction` property-Set by using values from the `ActionForExistingBackups` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-666">Anzeigename in ActionForExistingBackups</span><span class="sxs-lookup"><span data-stu-id="ee524-666">Friendly name in ActionForExistingBackups</span></span>|<span data-ttu-id="ee524-667">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-667">Numeric value</span></span>|  
|-----------------------------------------------|-------------------|  
|<span data-ttu-id="ee524-668">Anfügen</span><span class="sxs-lookup"><span data-stu-id="ee524-668">Append</span></span>|<span data-ttu-id="ee524-669">0</span><span class="sxs-lookup"><span data-stu-id="ee524-669">0</span></span>|  
|<span data-ttu-id="ee524-670">Overwrite</span><span class="sxs-lookup"><span data-stu-id="ee524-670">Overwrite</span></span>|<span data-ttu-id="ee524-671">1</span><span class="sxs-lookup"><span data-stu-id="ee524-671">1</span></span>|  
  
 <span data-ttu-id="ee524-672">`BackupAction`Eigenschaften Satz mithilfe von Werten aus der- `BackupTaskType` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-672">`BackupAction` property-Set by using values from the `BackupTaskType` enumeration.</span></span> <span data-ttu-id="ee524-673">Diese Eigenschaft arbeitet mit der `BackupIsIncremental`-Eigenschaft zusammen, um den Typ der vom Task durchgeführten Sicherung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="ee524-673">This property works with the `BackupIsIncremental` property to define the type of backup that the task performs.</span></span>  
  
|<span data-ttu-id="ee524-674">Anzeigename in BackupTaskType</span><span class="sxs-lookup"><span data-stu-id="ee524-674">Friendly name in BackupTaskType</span></span>|<span data-ttu-id="ee524-675">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-675">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="ee524-676">Datenbank</span><span class="sxs-lookup"><span data-stu-id="ee524-676">Database</span></span>|<span data-ttu-id="ee524-677">0</span><span class="sxs-lookup"><span data-stu-id="ee524-677">0</span></span>|  
|<span data-ttu-id="ee524-678">Dateien</span><span class="sxs-lookup"><span data-stu-id="ee524-678">Files</span></span>|<span data-ttu-id="ee524-679">1</span><span class="sxs-lookup"><span data-stu-id="ee524-679">1</span></span>|  
|<span data-ttu-id="ee524-680">Log</span><span class="sxs-lookup"><span data-stu-id="ee524-680">Log</span></span>|<span data-ttu-id="ee524-681">2</span><span class="sxs-lookup"><span data-stu-id="ee524-681">2</span></span>|  
  
 <span data-ttu-id="ee524-682">`BackupDevice`Eigenschaften Satz, der mithilfe von Werten der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO)-Enumeration festgelegt wird `DeviceType` .</span><span class="sxs-lookup"><span data-stu-id="ee524-682">`BackupDevice` property-Set by using values from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO) `DeviceType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-683">Anzeigename in DeviceType</span><span class="sxs-lookup"><span data-stu-id="ee524-683">Friendly name in DeviceType</span></span>|<span data-ttu-id="ee524-684">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-684">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="ee524-685">LogicalDevice</span><span class="sxs-lookup"><span data-stu-id="ee524-685">LogicalDevice</span></span>|<span data-ttu-id="ee524-686">0</span><span class="sxs-lookup"><span data-stu-id="ee524-686">0</span></span>|  
|<span data-ttu-id="ee524-687">Band</span><span class="sxs-lookup"><span data-stu-id="ee524-687">Tape</span></span>|<span data-ttu-id="ee524-688">1</span><span class="sxs-lookup"><span data-stu-id="ee524-688">1</span></span>|  
|<span data-ttu-id="ee524-689">Datei</span><span class="sxs-lookup"><span data-stu-id="ee524-689">File</span></span>|<span data-ttu-id="ee524-690">2</span><span class="sxs-lookup"><span data-stu-id="ee524-690">2</span></span>|  
|<span data-ttu-id="ee524-691">Pipe</span><span class="sxs-lookup"><span data-stu-id="ee524-691">Pipe</span></span>|<span data-ttu-id="ee524-692">3</span><span class="sxs-lookup"><span data-stu-id="ee524-692">3</span></span>|  
|<span data-ttu-id="ee524-693">VirtualDevice</span><span class="sxs-lookup"><span data-stu-id="ee524-693">VirtualDevice</span></span>|<span data-ttu-id="ee524-694">4</span><span class="sxs-lookup"><span data-stu-id="ee524-694">4</span></span>|  
  
### <a name="maintenance-cleanup-task"></a><span data-ttu-id="ee524-695">Wartungscleanup (Task)</span><span class="sxs-lookup"><span data-stu-id="ee524-695">Maintenance Cleanup Task</span></span>  
 <span data-ttu-id="ee524-696">`FileTypeSelected`Eigenschaften Satz mithilfe von Werten aus der- `FileType` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-696">`FileTypeSelected` property-Set by using values from the `FileType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-697">Anzeigename in FileType</span><span class="sxs-lookup"><span data-stu-id="ee524-697">Friendly name in FileType</span></span>|<span data-ttu-id="ee524-698">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-698">Numeric value</span></span>|  
|-------------------------------|-------------------|  
|<span data-ttu-id="ee524-699">FileBackup</span><span class="sxs-lookup"><span data-stu-id="ee524-699">FileBackup</span></span>|<span data-ttu-id="ee524-700">0</span><span class="sxs-lookup"><span data-stu-id="ee524-700">0</span></span>|  
|<span data-ttu-id="ee524-701">FileReport</span><span class="sxs-lookup"><span data-stu-id="ee524-701">FileReport</span></span>|<span data-ttu-id="ee524-702">1</span><span class="sxs-lookup"><span data-stu-id="ee524-702">1</span></span>|  
  
 <span data-ttu-id="ee524-703">`OlderThanTimeUnitType`Eigenschaften Satz mithilfe von Werten aus der- `TimeUnitType` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-703">`OlderThanTimeUnitType` property-Set by using values from the `TimeUnitType` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-704">Anzeigename in TimeUnitType</span><span class="sxs-lookup"><span data-stu-id="ee524-704">Friendly Name in TimeUnitType</span></span>|<span data-ttu-id="ee524-705">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-705">Numeric Value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="ee524-706">Day (Tag)</span><span class="sxs-lookup"><span data-stu-id="ee524-706">Day</span></span>|<span data-ttu-id="ee524-707">0</span><span class="sxs-lookup"><span data-stu-id="ee524-707">0</span></span>|  
|<span data-ttu-id="ee524-708">Week</span><span class="sxs-lookup"><span data-stu-id="ee524-708">Week</span></span>|<span data-ttu-id="ee524-709">1</span><span class="sxs-lookup"><span data-stu-id="ee524-709">1</span></span>|  
|<span data-ttu-id="ee524-710">Month (Monat)</span><span class="sxs-lookup"><span data-stu-id="ee524-710">Month</span></span>|<span data-ttu-id="ee524-711">2</span><span class="sxs-lookup"><span data-stu-id="ee524-711">2</span></span>|  
|<span data-ttu-id="ee524-712">Jahr</span><span class="sxs-lookup"><span data-stu-id="ee524-712">Year</span></span>|<span data-ttu-id="ee524-713">3</span><span class="sxs-lookup"><span data-stu-id="ee524-713">3</span></span>|  
  
### <a name="update-statistics-task"></a><span data-ttu-id="ee524-714">Statistiken aktualisieren (Task)</span><span class="sxs-lookup"><span data-stu-id="ee524-714">Update Statistics Task</span></span>  
 <span data-ttu-id="ee524-715">`UpdateType`Eigenschaften Satz, der mithilfe von Werten der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO)-Enumeration festgelegt wird `StatisticsTarget` .</span><span class="sxs-lookup"><span data-stu-id="ee524-715">`UpdateType` property-Set by using values from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO) `StatisticsTarget` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-716">Anzeigename in StatisticsTarget</span><span class="sxs-lookup"><span data-stu-id="ee524-716">Friendly name in StatisticsTarget</span></span>|<span data-ttu-id="ee524-717">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-717">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="ee524-718">Column</span><span class="sxs-lookup"><span data-stu-id="ee524-718">Column</span></span>|<span data-ttu-id="ee524-719">1</span><span class="sxs-lookup"><span data-stu-id="ee524-719">1</span></span>|  
|<span data-ttu-id="ee524-720">Index</span><span class="sxs-lookup"><span data-stu-id="ee524-720">Index</span></span>|<span data-ttu-id="ee524-721">2</span><span class="sxs-lookup"><span data-stu-id="ee524-721">2</span></span>|  
|<span data-ttu-id="ee524-722">All</span><span class="sxs-lookup"><span data-stu-id="ee524-722">All</span></span>|<span data-ttu-id="ee524-723">3</span><span class="sxs-lookup"><span data-stu-id="ee524-723">3</span></span>|  
  
##  <a name="common-properties"></a><a name="CommonProperties"></a> <span data-ttu-id="ee524-724">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ee524-724">Common Properties</span></span>  
 <span data-ttu-id="ee524-725">Pakete, Tasks, die Foreach-Schleife, die For-Schleife und Sequenzcontainer können die folgenden Enumerationen verwenden, um die angegebenen Eigenschaften festzulegen.</span><span class="sxs-lookup"><span data-stu-id="ee524-725">Packages, tasks, and the Foreach Loop, For Loop, and Sequence containers can use the following enumerations to set the specified properties.</span></span>  
  
 <span data-ttu-id="ee524-726">`ForceExecutionResult`Eigenschaften Satz mithilfe von Werten aus der- `DTSForcedExecResult` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-726">`ForceExecutionResult` property-Set by using values from the `DTSForcedExecResult` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-727">Anzeigename in DTSForcedExecResult</span><span class="sxs-lookup"><span data-stu-id="ee524-727">Friendly name in DTSForcedExecResult</span></span>|<span data-ttu-id="ee524-728">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-728">Numeric value</span></span>|  
|------------------------------------------|-------------------|  
|<span data-ttu-id="ee524-729">Keine</span><span class="sxs-lookup"><span data-stu-id="ee524-729">None</span></span>|<span data-ttu-id="ee524-730">-1</span><span class="sxs-lookup"><span data-stu-id="ee524-730">-1</span></span>|  
|<span data-ttu-id="ee524-731">Erfolg</span><span class="sxs-lookup"><span data-stu-id="ee524-731">Success</span></span>|<span data-ttu-id="ee524-732">0</span><span class="sxs-lookup"><span data-stu-id="ee524-732">0</span></span>|  
|<span data-ttu-id="ee524-733">Fehler</span><span class="sxs-lookup"><span data-stu-id="ee524-733">Failure</span></span>|<span data-ttu-id="ee524-734">1</span><span class="sxs-lookup"><span data-stu-id="ee524-734">1</span></span>|  
|<span data-ttu-id="ee524-735">Completion</span><span class="sxs-lookup"><span data-stu-id="ee524-735">Completion</span></span>|<span data-ttu-id="ee524-736">2</span><span class="sxs-lookup"><span data-stu-id="ee524-736">2</span></span>|  
  
 <span data-ttu-id="ee524-737">`IsolationLevel`Eigenschaft: Festlegung durch die .NET Framework- `IsolationLevel` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-737">`IsolationLevel` property-Set by the .NET Framework `IsolationLevel` enumeration.</span></span> <span data-ttu-id="ee524-738">Weitere Informationen finden Sie in der .NET Framework-Klassenbibliothek unter der [MSDN Library](https://go.microsoft.com/fwlink?LinkId=17313).</span><span class="sxs-lookup"><span data-stu-id="ee524-738">For more information, see the .NET Framework Class Library in the [MSDN Library](https://go.microsoft.com/fwlink?LinkId=17313).</span></span>  
  
 <span data-ttu-id="ee524-739">`LoggingMode`Eigenschaften Satz mithilfe von Werten aus der- `DTSLoggingMode` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-739">`LoggingMode` property-Set by using values from the `DTSLoggingMode` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-740">Anzeigename in DTSLoggingMode</span><span class="sxs-lookup"><span data-stu-id="ee524-740">Friendly name in DTSLoggingMode</span></span>|<span data-ttu-id="ee524-741">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-741">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="ee524-742">UseParentSetting</span><span class="sxs-lookup"><span data-stu-id="ee524-742">UseParentSetting</span></span>|<span data-ttu-id="ee524-743">0</span><span class="sxs-lookup"><span data-stu-id="ee524-743">0</span></span>|  
|<span data-ttu-id="ee524-744">Enabled</span><span class="sxs-lookup"><span data-stu-id="ee524-744">Enabled</span></span>|<span data-ttu-id="ee524-745">1</span><span class="sxs-lookup"><span data-stu-id="ee524-745">1</span></span>|  
|<span data-ttu-id="ee524-746">Disabled</span><span class="sxs-lookup"><span data-stu-id="ee524-746">Disabled</span></span>|<span data-ttu-id="ee524-747">2</span><span class="sxs-lookup"><span data-stu-id="ee524-747">2</span></span>|  
  
 <span data-ttu-id="ee524-748">`TransactionOption`Eigenschaften Satz mithilfe von Werten aus der- `DTSTransactionOption` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ee524-748">`TransactionOption` property-Set by using values from the `DTSTransactionOption` enumeration.</span></span>  
  
|<span data-ttu-id="ee524-749">Anzeigename in DTSTransactionOption</span><span class="sxs-lookup"><span data-stu-id="ee524-749">Friendly name in DTSTransactionOption</span></span>|<span data-ttu-id="ee524-750">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="ee524-750">Numeric value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="ee524-751">NotSupported</span><span class="sxs-lookup"><span data-stu-id="ee524-751">NotSupported</span></span>|<span data-ttu-id="ee524-752">0</span><span class="sxs-lookup"><span data-stu-id="ee524-752">0</span></span>|  
|<span data-ttu-id="ee524-753">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="ee524-753">Supported</span></span>|<span data-ttu-id="ee524-754">1</span><span class="sxs-lookup"><span data-stu-id="ee524-754">1</span></span>|  
|<span data-ttu-id="ee524-755">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="ee524-755">Required</span></span>|<span data-ttu-id="ee524-756">2</span><span class="sxs-lookup"><span data-stu-id="ee524-756">2</span></span>|  
  
## <a name="related-tasks"></a><span data-ttu-id="ee524-757">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="ee524-757">Related Tasks</span></span>  
 [<span data-ttu-id="ee524-758">Hinzufügen oder Ändern eines Eigenschaftsausdrucks</span><span class="sxs-lookup"><span data-stu-id="ee524-758">Add or Change a Property Expression</span></span>](add-or-change-a-property-expression.md)  
  
## <a name="see-also"></a><span data-ttu-id="ee524-759">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ee524-759">See Also</span></span>  
 <span data-ttu-id="ee524-760">[Verwenden von Eigenschaftsausdrücken in Paketen](use-property-expressions-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="ee524-760">[Use Property Expressions in Packages](use-property-expressions-in-packages.md) </span></span>  
 <span data-ttu-id="ee524-761">[Integration Services-Pakete &#40;SSIS&#41;](../integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="ee524-761">[Integration Services &#40;SSIS&#41; Packages](../integration-services-ssis-packages.md) </span></span>  
 <span data-ttu-id="ee524-762">[Integration Services-Container](../control-flow/integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="ee524-762">[Integration Services Containers](../control-flow/integration-services-containers.md) </span></span>  
 <span data-ttu-id="ee524-763">[Integration Services-Tasks](../control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="ee524-763">[Integration Services Tasks](../control-flow/integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="ee524-764">Rangfolgeneinschränkungen</span><span class="sxs-lookup"><span data-stu-id="ee524-764">Precedence Constraints</span></span>](../control-flow/precedence-constraints.md)  
  
  
