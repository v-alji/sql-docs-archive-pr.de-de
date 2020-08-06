---
title: Überwachungstransformation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.audittrans.f1
helpviewer_keywords:
- environment data in packages [Integration Services]
- Audit transformation
ms.assetid: 8c143682-9c81-4150-83d6-1d9678151d37
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e8e302f6dd1dc5666ae65af2eb9705a4922915c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695873"
---
# <a name="audit-transformation"></a><span data-ttu-id="ec231-102">Überwachungstransformation</span><span class="sxs-lookup"><span data-stu-id="ec231-102">Audit Transformation</span></span>
  <span data-ttu-id="ec231-103">Mithilfe der Überwachungstransformation werden in den Datenfluss eines Pakets Daten zur Umgebung, in der das Paket ausgeführt wird, eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ec231-103">The Audit transformation enables the data flow in a package to include data about the environment in which the package runs.</span></span> <span data-ttu-id="ec231-104">Dem Datenfluss kann z. B. der Name des Pakets, Computers und Operators hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ec231-104">For example, the name of the package, computer, and operator can be added to the data flow.</span></span> [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="ec231-105">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] enthält Systemvariablen, die diese Informationen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ec231-105">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] includes system variables that provide this information.</span></span>  
  
## <a name="system-variables"></a><span data-ttu-id="ec231-106">Systemvariablen</span><span class="sxs-lookup"><span data-stu-id="ec231-106">System Variables</span></span>  
 <span data-ttu-id="ec231-107">In der folgenden Tabelle sind die Systemvariablen beschrieben, die von der Überwachungstransformation verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ec231-107">The following table describes the system variables that the Audit transformation can use.</span></span>  
  
|<span data-ttu-id="ec231-108">Systemvariable</span><span class="sxs-lookup"><span data-stu-id="ec231-108">System variable</span></span>|<span data-ttu-id="ec231-109">Index</span><span class="sxs-lookup"><span data-stu-id="ec231-109">Index</span></span>|<span data-ttu-id="ec231-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ec231-110">Description</span></span>|  
|---------------------|-----------|-----------------|  
|`ExecutionInstanceGUID`|<span data-ttu-id="ec231-111">0</span><span class="sxs-lookup"><span data-stu-id="ec231-111">0</span></span>|<span data-ttu-id="ec231-112">Der GUID, der die Ausführungsinstanz des Pakets identifiziert.</span><span class="sxs-lookup"><span data-stu-id="ec231-112">The GUID that identifies the execution instance of the package.</span></span>|  
|`PackageID`|<span data-ttu-id="ec231-113">1</span><span class="sxs-lookup"><span data-stu-id="ec231-113">1</span></span>|<span data-ttu-id="ec231-114">Der eindeutige Bezeichner des Pakets.</span><span class="sxs-lookup"><span data-stu-id="ec231-114">The unique identifier of the package.</span></span>|  
|`PackageName`|<span data-ttu-id="ec231-115">2</span><span class="sxs-lookup"><span data-stu-id="ec231-115">2</span></span>|<span data-ttu-id="ec231-116">Der Paketname.</span><span class="sxs-lookup"><span data-stu-id="ec231-116">The package name.</span></span>|  
|`VersionID`|<span data-ttu-id="ec231-117">3</span><span class="sxs-lookup"><span data-stu-id="ec231-117">3</span></span>|<span data-ttu-id="ec231-118">Die Paketversion.</span><span class="sxs-lookup"><span data-stu-id="ec231-118">The version of the package.</span></span>|  
|`ExecutionStartTime`|<span data-ttu-id="ec231-119">4</span><span class="sxs-lookup"><span data-stu-id="ec231-119">4</span></span>|<span data-ttu-id="ec231-120">Der Zeitpunkt, zu dem das Paket gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="ec231-120">The time the package started to run.</span></span>|  
|`MachineName`|<span data-ttu-id="ec231-121">5</span><span class="sxs-lookup"><span data-stu-id="ec231-121">5</span></span>|<span data-ttu-id="ec231-122">Der Computername.</span><span class="sxs-lookup"><span data-stu-id="ec231-122">The computer name.</span></span>|  
|`UserName`|<span data-ttu-id="ec231-123">6</span><span class="sxs-lookup"><span data-stu-id="ec231-123">6</span></span>|<span data-ttu-id="ec231-124">Der Anmeldename der Person, die das Paket gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="ec231-124">The login name of the person who started the package.</span></span>|  
|`TaskName`|<span data-ttu-id="ec231-125">7</span><span class="sxs-lookup"><span data-stu-id="ec231-125">7</span></span>|<span data-ttu-id="ec231-126">Der Name des Datenflusstasks, dem die Überwachungstransformation zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="ec231-126">The name of the Data Flow task with which the Audit transformation is associated.</span></span>|  
|<span data-ttu-id="ec231-127">**TaskId**</span><span class="sxs-lookup"><span data-stu-id="ec231-127">**TaskId**</span></span>|<span data-ttu-id="ec231-128">8</span><span class="sxs-lookup"><span data-stu-id="ec231-128">8</span></span>|<span data-ttu-id="ec231-129">Der eindeutige Bezeichner des Datenflusstasks.</span><span class="sxs-lookup"><span data-stu-id="ec231-129">The unique identifier of the Data Flow task.</span></span>|  
  
## <a name="configuration-of-the-audit-transformation"></a><span data-ttu-id="ec231-130">Konfiguration der Überwachungstransformation</span><span class="sxs-lookup"><span data-stu-id="ec231-130">Configuration of the Audit Transformation</span></span>  
 <span data-ttu-id="ec231-131">Zum Konfigurieren der Überwachungstransformation stellen Sie den Namen einer neuen Ausgabespalte bereit, die der Transformationsausgabe hinzugefügt werden soll, und ordnen dann der Ausgabespalte die Systemvariable zu.</span><span class="sxs-lookup"><span data-stu-id="ec231-131">You configure the Audit transformation by providing the name of a new output column to add to the transformation output, and then mapping the system variable to the output column.</span></span> <span data-ttu-id="ec231-132">Eine einzelne Systemvariable kann mehreren Spalten zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="ec231-132">You can map a single system variable to multiple columns.</span></span>  
  
 <span data-ttu-id="ec231-133">Diese Transformation weist je eine Eingabe und eine Ausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="ec231-133">This transformation has one input and one output.</span></span> <span data-ttu-id="ec231-134">Eine Fehlerausgabe wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ec231-134">It does not support an error output.</span></span>  
  
 <span data-ttu-id="ec231-135">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="ec231-135">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="ec231-136">Weitere Informationen zu den Eigenschaften, die Sie im Dialogfeld **Transformations-Editor für Überwachung** festlegen können, finden Sie unter [Audit Transformation Editor](../../audit-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="ec231-136">For more information about the properties that you can set in the **Audit Transformation Editor** dialog box, see [Audit Transformation Editor](../../audit-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="ec231-137">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="ec231-137">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="ec231-138">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="ec231-138">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="ec231-139">Common Properties</span><span class="sxs-lookup"><span data-stu-id="ec231-139">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="ec231-140">Benutzerdefinierte Eigenschaften von Transformationen</span><span class="sxs-lookup"><span data-stu-id="ec231-140">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="ec231-141">Weitere Informationen zum Festlegen der Eigenschaften finden Sie unter [Festlegen der Eigenschaften einer Datenflusskomponente](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="ec231-141">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
