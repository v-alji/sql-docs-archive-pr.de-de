---
title: Schema Optionen für die Themenbereichs Datenbank (Schemagenerierungs-Assistent) (Analysis Services-Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.schemagenwizard.subjectareaschemaopts.f1
ms.assetid: 4c109bb8-e19d-412b-908f-bfdd7f872439
author: minewiskan
ms.author: owend
ms.openlocfilehash: 98460332478d02de823addcd113fb9c1e87d6958
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616716"
---
# <a name="subject-area-database-schema-options-schema-generation-wizard-analysis-services---multidimensional-data"></a><span data-ttu-id="813f6-102">Schemaoptionen für die Themenbereichsdatenbank (Schemagenerierungs-Assistent) (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="813f6-102">Subject Area Database Schema Options (Schema Generation Wizard) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="813f6-103">Mithilfe der Seite **Schemaoptionen für die Themenbereichsdatenbank** können Sie die Generierung des Schemas steuern und definieren, wie Daten erhalten bleiben.</span><span class="sxs-lookup"><span data-stu-id="813f6-103">Use the **Subject Area Database Schema Options** page to control how the schema is generated, as well as to define how data is preserved.</span></span>  
  
## <a name="options"></a><span data-ttu-id="813f6-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="813f6-104">Options</span></span>  
 <span data-ttu-id="813f6-105">**Besitzendes Schema**</span><span class="sxs-lookup"><span data-stu-id="813f6-105">**Owning schema**</span></span>  
 <span data-ttu-id="813f6-106">Gibt den Namen des Schemas innerhalb der neuen Themenbereichsdatenbank an.</span><span class="sxs-lookup"><span data-stu-id="813f6-106">Specifies the name of the schema within the new subject area database.</span></span>  
  
 <span data-ttu-id="813f6-107">**Primärschlüssel für Dimensionstabellen erstellen**</span><span class="sxs-lookup"><span data-stu-id="813f6-107">**Create primary keys on dimension tables**</span></span>  
 <span data-ttu-id="813f6-108">Erstellt Primärschlüssel für die Dimensionstabellen im generierten Schema.</span><span class="sxs-lookup"><span data-stu-id="813f6-108">Creates primary keys on the dimension tables in the generated schema.</span></span> <span data-ttu-id="813f6-109">Wenn Sie diese Option nicht auswählen, wird kein Index erstellt.</span><span class="sxs-lookup"><span data-stu-id="813f6-109">No index is generated if you do not select this option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="813f6-110">Wenn Sie diese Option nicht auswählen, wird die referenzielle Integrität erzwungen.</span><span class="sxs-lookup"><span data-stu-id="813f6-110">If you do not select this option, referential integrity is enforced.</span></span>  
  
 <span data-ttu-id="813f6-111">**Erstellen von Indizes**</span><span class="sxs-lookup"><span data-stu-id="813f6-111">**Create indexes**</span></span>  
 <span data-ttu-id="813f6-112">Erstellt Indizes für Fremdschlüsselspalten im generierten Schema.</span><span class="sxs-lookup"><span data-stu-id="813f6-112">Creates indexes on foreign key columns in the generated schema.</span></span>  
  
 <span data-ttu-id="813f6-113">**Referenzielle Integrität erzwingen**</span><span class="sxs-lookup"><span data-stu-id="813f6-113">**Enforce referential integrity**</span></span>  
 <span data-ttu-id="813f6-114">Erzwingt die referenzielle Integrität innerhalb des generierten Schemas.</span><span class="sxs-lookup"><span data-stu-id="813f6-114">Enforces referential integrity within the generated schema.</span></span> <span data-ttu-id="813f6-115">Wenn Sie diese Option nicht auswählen, werden Beziehungen erstellt, aber nicht erzwungen.</span><span class="sxs-lookup"><span data-stu-id="813f6-115">If you do not select this option, relationships are created but not enforced.</span></span>  
  
 <span data-ttu-id="813f6-116">**Daten bei erneuter Generierung beibehalten**</span><span class="sxs-lookup"><span data-stu-id="813f6-116">**Preserve data on regeneration**</span></span>  
 <span data-ttu-id="813f6-117">Behält die Daten in der Themenbereichsdatenbank bei Abschluss des Assistenten bei.</span><span class="sxs-lookup"><span data-stu-id="813f6-117">Retains data in the subject area database when the wizard finishes.</span></span> <span data-ttu-id="813f6-118">Wenn Sie diese Option nicht auswählen, werden möglicherweise alle Daten in der Themenbereichsdatenbank ohne Warnung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="813f6-118">If you do not select this option, all the data in the subject area database may be erased without warning.</span></span>  
  
 <span data-ttu-id="813f6-119">**Zeittabelle(n) auffüllen**</span><span class="sxs-lookup"><span data-stu-id="813f6-119">**Populate time table(s)**</span></span>  
 <span data-ttu-id="813f6-120">Gibt an, wie der Assistent die Zeittabellen auffüllt.</span><span class="sxs-lookup"><span data-stu-id="813f6-120">Specifies how the wizard populates the time tables.</span></span> <span data-ttu-id="813f6-121">Die folgende Tabelle beschreibt die möglichen Werte für diese Option.</span><span class="sxs-lookup"><span data-stu-id="813f6-121">The following table describes the possible values for this option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="813f6-122">Diese Option ist nur aktiviert, wenn der Schemagenerierungs-Assistent von einem [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Projekt aus mithilfe von [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] im Projektmodus aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="813f6-122">This option is enabled only if Schema Generation Wizard is called from an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, using [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] in project mode.</span></span>  
  
|<span data-ttu-id="813f6-123">Wert</span><span class="sxs-lookup"><span data-stu-id="813f6-123">Value</span></span>|<span data-ttu-id="813f6-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="813f6-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="813f6-125">Auffüllen</span><span class="sxs-lookup"><span data-stu-id="813f6-125">Populate</span></span>|<span data-ttu-id="813f6-126">Die Themenbereichs-Zeittabellen werden aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="813f6-126">The subject area time tables are populated.</span></span>|  
|<span data-ttu-id="813f6-127">Nicht auffüllen</span><span class="sxs-lookup"><span data-stu-id="813f6-127">Do not populate</span></span>|<span data-ttu-id="813f6-128">Die Themenbereichs-Zeittabellen werden nicht aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="813f6-128">The subject area time tables are not populated.</span></span>|  
|<span data-ttu-id="813f6-129">Nur auffüllen, wenn leer</span><span class="sxs-lookup"><span data-stu-id="813f6-129">Populate only if empty</span></span>|<span data-ttu-id="813f6-130">Die Themenbereichs-Zeittabellen werden nur aufgefüllt, wenn sie leer sind.</span><span class="sxs-lookup"><span data-stu-id="813f6-130">The subject area time tables are populated only if they are empty.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="813f6-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="813f6-131">See Also</span></span>  
 [<span data-ttu-id="813f6-132">Schemagenerierungs-Assistent F1-Hilfe &#40;Analysis Services-mehrdimensionalen Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="813f6-132">Schema Generation Wizard F1 Help &#40;Analysis Services - Multidimensional Data&#41;</span></span>](schema-generation-wizard-f1-help-analysis-services-multidimensional-data.md)  
  
  
