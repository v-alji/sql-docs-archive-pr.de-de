---
title: Transformations-Editor für Überwachung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.audittransformation.f1
helpviewer_keywords:
- Audit Transformation Editor
ms.assetid: 32786a34-5870-4fde-83c7-ec74d62404b8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: af6490643a0bef60cca961dc9a0564c5f6b46484
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724057"
---
# <a name="audit-transformation-editor"></a><span data-ttu-id="f61ac-102">Transformations-Editor für Überwachung</span><span class="sxs-lookup"><span data-stu-id="f61ac-102">Audit Transformation Editor</span></span>
  <span data-ttu-id="f61ac-103">Mithilfe der Überwachungstransformation werden in den Datenfluss eines Pakets Daten zur Umgebung, in der das Paket ausgeführt wird, eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f61ac-103">The Audit transformation enables the data flow in a package to include data about the environment in which the package runs.</span></span> <span data-ttu-id="f61ac-104">Dem Datenfluss kann z. B. der Name des Pakets, Computers und Operators hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f61ac-104">For example, the name of the package, computer, and operator can be added to the data flow.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="f61ac-105">enthält Systemvariablen, die diese Informationen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f61ac-105">includes system variables that provide this information.</span></span>  
  
 <span data-ttu-id="f61ac-106">Weitere Informationen zur Überwachungstransformation finden Sie unter [Audit Transformation](data-flow/transformations/audit-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="f61ac-106">To learn more about the Audit transformation, see [Audit Transformation](data-flow/transformations/audit-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f61ac-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="f61ac-107">Options</span></span>  
 <span data-ttu-id="f61ac-108">**Name der Ausgabe Spalte**</span><span class="sxs-lookup"><span data-stu-id="f61ac-108">**Output column name**</span></span>  
 <span data-ttu-id="f61ac-109">Geben Sie den Namen der neuen Ausgabespalte an, die die Überwachungsinformationen enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="f61ac-109">Provide the name for a new output column that will contain the audit information.</span></span>  
  
 <span data-ttu-id="f61ac-110">**Überwachungstyp**</span><span class="sxs-lookup"><span data-stu-id="f61ac-110">**Audit type**</span></span>  
 <span data-ttu-id="f61ac-111">Wählen Sie eine verfügbare Systemvariable zum Bereitstellen der Überwachungsinformationen aus.</span><span class="sxs-lookup"><span data-stu-id="f61ac-111">Select an available system variable to supply the audit information.</span></span>  
  
|<span data-ttu-id="f61ac-112">Wert</span><span class="sxs-lookup"><span data-stu-id="f61ac-112">Value</span></span>|<span data-ttu-id="f61ac-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f61ac-113">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f61ac-114">**GUID der Ausführungsinstanz**</span><span class="sxs-lookup"><span data-stu-id="f61ac-114">**Execution instance GUID**</span></span>|<span data-ttu-id="f61ac-115">Fügen Sie die GUID ein, die die Ausführungsinstanz des Pakets eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f61ac-115">Insert the GUID that uniquely identifies the execution instance of the package.</span></span>|  
|<span data-ttu-id="f61ac-116">**Paket-ID**</span><span class="sxs-lookup"><span data-stu-id="f61ac-116">**Package ID**</span></span>|<span data-ttu-id="f61ac-117">Fügen Sie die GUID ein, die das Paket eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f61ac-117">Insert the GUID that uniquely identifies the package.</span></span>|  
|<span data-ttu-id="f61ac-118">**Paketname**</span><span class="sxs-lookup"><span data-stu-id="f61ac-118">**Package name**</span></span>|<span data-ttu-id="f61ac-119">Fügen Sie den Paketnamen ein.</span><span class="sxs-lookup"><span data-stu-id="f61ac-119">Insert the package name.</span></span>|  
|<span data-ttu-id="f61ac-120">**Versions-ID**</span><span class="sxs-lookup"><span data-stu-id="f61ac-120">**Version ID**</span></span>|<span data-ttu-id="f61ac-121">Fügen Sie die GUID ein, die die Paketversion eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f61ac-121">Insert the GUID that uniquely identifies the version of the package.</span></span>|  
|<span data-ttu-id="f61ac-122">**Startzeit der Ausführung**</span><span class="sxs-lookup"><span data-stu-id="f61ac-122">**Execution start time**</span></span>|<span data-ttu-id="f61ac-123">Fügen Sie den Zeitpunkt ein, zu dem mit der Ausführung des Pakets begonnen wird.</span><span class="sxs-lookup"><span data-stu-id="f61ac-123">Insert the time at which package execution started.</span></span>|  
|<span data-ttu-id="f61ac-124">**Computername**</span><span class="sxs-lookup"><span data-stu-id="f61ac-124">**Machine name**</span></span>|<span data-ttu-id="f61ac-125">Fügen Sie den Namen des Computers ein, auf dem das Paket gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f61ac-125">Insert the name of the computer on which the package was launched.</span></span>|  
|<span data-ttu-id="f61ac-126">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="f61ac-126">**User name**</span></span>|<span data-ttu-id="f61ac-127">Fügen Sie den Anmeldenamen des Benutzers ein, der das Paket gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="f61ac-127">Insert the login name of the user who launched the package.</span></span>|  
|<span data-ttu-id="f61ac-128">**Taskname**</span><span class="sxs-lookup"><span data-stu-id="f61ac-128">**Task name**</span></span>|<span data-ttu-id="f61ac-129">Fügen Sie den Namen von dem Datenflusstask ein, mit dem die Überwachungstransformation verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="f61ac-129">Insert the name of the Data Flow task with which the Audit transformation is associated.</span></span>|  
|<span data-ttu-id="f61ac-130">**Aufgaben-ID**</span><span class="sxs-lookup"><span data-stu-id="f61ac-130">**Task ID**</span></span>|<span data-ttu-id="f61ac-131">Fügen Sie die GUID ein, die den mit der Überwachungstransformation verknüpften Datenflusstask eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f61ac-131">Insert the GUID that uniquely identifies the Data Flow task with which the Audit transformation is associated.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f61ac-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f61ac-132">See Also</span></span>  
 [<span data-ttu-id="f61ac-133">Fehler- und Meldungsreferenz von Integration Services</span><span class="sxs-lookup"><span data-stu-id="f61ac-133">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
