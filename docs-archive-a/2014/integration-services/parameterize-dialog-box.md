---
title: Dialog Feld ' parametrisieren ' | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.parameter.f1
ms.assetid: fac02b6d-d247-447a-8940-e8700c7ac350
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8db19844132402740aec092d6e88f3c9e3864d58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618082"
---
# <a name="parameterize-dialog-box"></a><span data-ttu-id="a8610-102">Parameterize Dialog Box</span><span class="sxs-lookup"><span data-stu-id="a8610-102">Parameterize Dialog Box</span></span>
  <span data-ttu-id="a8610-103">Im Dialogfeld **Parametrisieren** können Sie einen neuen oder vorhandenen Parameter der Eigenschaft eines Tasks zuordnen.</span><span class="sxs-lookup"><span data-stu-id="a8610-103">The **Parameterize** dialog box enables you to associate a new or an existing parameter with a property of a task.</span></span> <span data-ttu-id="a8610-104">Sie öffnen das Dialogfeld, indem Sie mit der rechten Maustaste auf einen Task oder die Registerkarte „Ablaufsteuerung“ im [!INCLUDE[ssIS](../includes/ssis-md.md)]-Designer klicken und dann auf **Parametrisieren** klicken.</span><span class="sxs-lookup"><span data-stu-id="a8610-104">You open the dialog box by right-clicking a task or the Control Flow tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer and then by clicking **Parameterize**.</span></span> <span data-ttu-id="a8610-105">Die folgende Liste beschreibt Benutzeroberflächenelemente im Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="a8610-105">The following list describes UI elements in the dialog box.</span></span> <span data-ttu-id="a8610-106">Weitere Informationen zu Parametern finden Sie unter [Integration Services-Parameter &#40;SSIS&#41;](integration-services-ssis-package-and-project-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="a8610-106">For more information about parameters, see [Integration Services &#40;SSIS&#41; Parameters](integration-services-ssis-package-and-project-parameters.md).</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="a8610-107">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="a8610-107">UI element list</span></span>  
 <span data-ttu-id="a8610-108">**Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="a8610-108">**Property**</span></span>  
 <span data-ttu-id="a8610-109">Wählen Sie die Eigenschaft der Aufgabe aus, der Sie einem Parameter zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="a8610-109">Select the property of the task that you want to associate with a parameter.</span></span> <span data-ttu-id="a8610-110">Diese Liste wird mit allen Eigenschaften aufgefüllt, die parametrisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="a8610-110">This list is populated with all the properties that can be parameterized.</span></span>  
  
 <span data-ttu-id="a8610-111">**Vorhandenen Parameter verwenden**</span><span class="sxs-lookup"><span data-stu-id="a8610-111">**Use existing parameter**</span></span>  
 <span data-ttu-id="a8610-112">Aktivieren Sie diese Option, um die Eigenschaft der Aufgaben einem vorhandenen Parameter zuzuordnen und dann den Parameter aus Dropdownliste auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="a8610-112">Select this option to associate the property of task with an existing parameter and then select the parameter from drop-down list.</span></span>  
  
 <span data-ttu-id="a8610-113">**Parameter nicht verwenden**</span><span class="sxs-lookup"><span data-stu-id="a8610-113">**Do not use parameter**</span></span>  
 <span data-ttu-id="a8610-114">Wählen Sie diese Option aus, um einen Verweist auf einen Parameter zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="a8610-114">Select this option to remove a reference to a parameter.</span></span> <span data-ttu-id="a8610-115">Der Parameter wurde nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a8610-115">The parameter is not deleted.</span></span>  
  
 <span data-ttu-id="a8610-116">**Neuen Parameter erstellen**</span><span class="sxs-lookup"><span data-stu-id="a8610-116">**Create new parameter**</span></span>  
 <span data-ttu-id="a8610-117">Aktivieren Sie diese Option, um einen neuen Parameter zu erstellen, den Sie der Eigenschaft der Aufgabe zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="a8610-117">Select this option to create a new parameter that you want to associate with the property of the task.</span></span>  
  
 <span data-ttu-id="a8610-118">**Name**</span><span class="sxs-lookup"><span data-stu-id="a8610-118">**Name**</span></span>  
 <span data-ttu-id="a8610-119">Geben Sie den Namen des Parameters an, den Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="a8610-119">Specify the name of the parameter you want to create.</span></span>  
  
 <span data-ttu-id="a8610-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a8610-120">**Description**</span></span>  
 <span data-ttu-id="a8610-121">Geben Sie die Beschreibung für den Parameter an.</span><span class="sxs-lookup"><span data-stu-id="a8610-121">Specify the description for parameter.</span></span>  
  
 <span data-ttu-id="a8610-122">**Wert**</span><span class="sxs-lookup"><span data-stu-id="a8610-122">**Value**</span></span>  
 <span data-ttu-id="a8610-123">Geben Sie den Standardwert für den Parameter an.</span><span class="sxs-lookup"><span data-stu-id="a8610-123">Specify the default value for the parameter.</span></span> <span data-ttu-id="a8610-124">Dies wird auch als der Entwurfsstandard bezeichnet, der später zur Bereitstellungszeit überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="a8610-124">This is also known as the design default, which can be overridden later at the deployment time.</span></span>  
  
 <span data-ttu-id="a8610-125">**Umfang**</span><span class="sxs-lookup"><span data-stu-id="a8610-125">**Scope**</span></span>  
 <span data-ttu-id="a8610-126">Geben Sie den Bereich des Parameters an, indem Sie die Option **Projekt** oder die Option **Paket** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a8610-126">Specify the scope of the parameter by selecting either **Project** or **Package** option.</span></span> <span data-ttu-id="a8610-127">Projektparameter werden verwendet, um jegliche externen Eingaben bereitzustellen, die das Projekt für ein oder mehrere Pakete im Projekt empfängt.</span><span class="sxs-lookup"><span data-stu-id="a8610-127">Project parameters are used to supply any external input the project receives to one or more packages in the project.</span></span> <span data-ttu-id="a8610-128">Mit Paketparametern können Sie die Paketausführung ändern, ohne das Paket bearbeiten und erneut bereitstellen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="a8610-128">Package parameters allow you to modify package execution without having to edit and redeploy the package.</span></span>  
  
 <span data-ttu-id="a8610-129">**Heikles**</span><span class="sxs-lookup"><span data-stu-id="a8610-129">**Sensitive**</span></span>  
 <span data-ttu-id="a8610-130">Geben Sie an, ob der Parameter vertraulich ist, indem Sie das Kontrollkästchen aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a8610-130">Specify whether the parameter is a sensitive by checking or clearing the check box.</span></span> <span data-ttu-id="a8610-131">Vertrauliche Parameterwerte werden im Katalog verschlüsselt und in Transact-SQL oder SQL Server Management Studio als NULL-Wert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a8610-131">Sensitive parameter values are encrypted in the catalog and appear as a NULL value when viewed with Transact-SQL or SQL Server Management Studio.</span></span>  
  
 <span data-ttu-id="a8610-132">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="a8610-132">**Required**</span></span>  
 <span data-ttu-id="a8610-133">Geben Sie an, ob für den Parameter ein anderer als der Entwurfsstandardwert angegeben werden muss, bevor das Paket ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a8610-133">Specify whether the parameter requires that a value, other than the design default, is specified before the package can execute.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="a8610-134">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="a8610-134">UI element list</span></span>  
  
