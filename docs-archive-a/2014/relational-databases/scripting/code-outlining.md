---
title: Codegliederung
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Query Editor [SQL Server Management Studio], outlining code
- Query Editor [SQL Server Management Studio], hiding code
ms.assetid: 556c7dfe-7bc8-4cab-a36f-2b753a05d3f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 0a142ca8fbdcdfcfbfd1b71de06c0b0fd4c5339c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616456"
---
# <a name="code-outlining"></a><span data-ttu-id="59988-102">Codegliederung</span><span class="sxs-lookup"><span data-stu-id="59988-102">Code Outlining</span></span>
  <span data-ttu-id="59988-103">Sie können die Gliederungsfunktion in den [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] -Abfrage-Editoren verwenden, um ausgewählten Code auszublenden, wenn Sie Abfragen bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="59988-103">You can use the outlining feature in the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] query editors to selectively hide code when you edit queries.</span></span> <span data-ttu-id="59988-104">Auf diese Weise können Sie insbesondere in großen Abfragedateien den bearbeiteten Code besser anzeigen.</span><span class="sxs-lookup"><span data-stu-id="59988-104">This enables you to more easily view the code you are working on, especially in large query files.</span></span>

## <a name="outlining-overview"></a><span data-ttu-id="59988-105">Übersicht über Gliederungen</span><span class="sxs-lookup"><span data-stu-id="59988-105">Outlining Overview</span></span>
 <span data-ttu-id="59988-106">Standardmäßig wird der gesamte Code angezeigt, wenn Sie ein Abfrage-Editorfenster öffnen.</span><span class="sxs-lookup"><span data-stu-id="59988-106">By default, all code is visible when you open a query editor window.</span></span> <span data-ttu-id="59988-107">Es ist möglich, Codebereiche zu reduzieren, sodass der Code ausgeblendet wird.</span><span class="sxs-lookup"><span data-stu-id="59988-107">Regions of the code can be collapsed to hide it from view.</span></span> <span data-ttu-id="59988-108">Eine vertikale Linie auf der linken Seite des Editorfensters gibt anhand eines Quadrats mit einem Minuszeichen (-) den Beginn eines reduzierbaren Codebereichs an.</span><span class="sxs-lookup"><span data-stu-id="59988-108">A vertical line on the left edge of the editor window uses a square with a minus sign (-) to identify the start of each collapsible code region.</span></span> <span data-ttu-id="59988-109">Wenn Sie auf ein Minuszeichen klicken, wird der Text des Codebereichs durch ein Feld mit drei Punkten (...) ersetzt, und das Minuszeichen wird in ein Pluszeichen (+) geändert.</span><span class="sxs-lookup"><span data-stu-id="59988-109">When you click a minus sign, the text of the code region is replaced with a box that contains three periods (...), and the minus sign changes to a plus sign (+).</span></span> <span data-ttu-id="59988-110">Wenn Sie auf ein Pluszeichen klicken, wird der reduzierte Code angezeigt, und das Pluszeichen wird in ein Minuszeichen (-) geändert.</span><span class="sxs-lookup"><span data-stu-id="59988-110">When you click a plus sign, the collapsed code appears and the plus sign changes to a minus sign.</span></span> <span data-ttu-id="59988-111">Wenn Sie den Mauszeiger über ein Feld mit drei Punkten bewegen, wird eine QuickInfo mit dem Code im reduzierten Abschnitt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="59988-111">When you move the pointer over a box that has three periods, a tooltip appears that shows the code in the collapsed section.</span></span>

## <a name="system-outline-regions"></a><span data-ttu-id="59988-112">Gliederungsbereiche des Systems</span><span class="sxs-lookup"><span data-stu-id="59988-112">System Outline Regions</span></span>
 <span data-ttu-id="59988-113">Jeder [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] -Editor generiert einen Satz vorgegebener systemdefinierter Gliederungsbereiche.</span><span class="sxs-lookup"><span data-stu-id="59988-113">Each [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] editor generates a set of default, system-defined outline regions.</span></span>

 <span data-ttu-id="59988-114">Der MDX- und der DMX-Code-Editor erstellen Gliederungsbereiche für alle mehrzeiligen Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="59988-114">The MDX and DMX code editors create outline regions for each multiline statement.</span></span> <span data-ttu-id="59988-115">Dies ist die einzige von diesen Editoren unterstützte Gliederungsebene.</span><span class="sxs-lookup"><span data-stu-id="59988-115">This is the only level of outlining that these editors support.</span></span>

### <a name="analysis-services-xmla-query-editor-regions"></a><span data-ttu-id="59988-116">Gliederungsbereiche des XMLA-Abfrage-Editors von Analysis Services</span><span class="sxs-lookup"><span data-stu-id="59988-116">Analysis Services XMLA Query Editor Regions</span></span>
 <span data-ttu-id="59988-117">Der XMLA-Abfrage-Editor von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] generiert einen Gliederungsbereich für alle mehrzeiligen XML-Attribute.</span><span class="sxs-lookup"><span data-stu-id="59988-117">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] XMLA Query Editor generates an outline region for each multiline XML attribute.</span></span> <span data-ttu-id="59988-118">Der Editor schachtelt die Gliederungsbereiche für geschachtelte Tags.</span><span class="sxs-lookup"><span data-stu-id="59988-118">The editor nests the outline regions for nested tags.</span></span> <span data-ttu-id="59988-119">So erstellt der XMLA-Editor z. B. drei Gliederungsbereiche für das folgende Dokument.</span><span class="sxs-lookup"><span data-stu-id="59988-119">For example, the XMLA Editor creates three outline regions for the following document.</span></span>

 <span data-ttu-id="59988-120">![XML-Code für Gliederung](../../database-engine/media/editoutlinexmlfull.gif "XML-Code für Gliederung")</span><span class="sxs-lookup"><span data-stu-id="59988-120">![XML code showing outlining](../../database-engine/media/editoutlinexmlfull.gif "XML code showing outlining")</span></span>

 <span data-ttu-id="59988-121">Wenn Sie auf das Minuszeichen in der \<InnerTag> Zeile klicken, wird nur das InnerTag reduziert, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="59988-121">When you click the minus sign on the \<InnerTag> line, just the InnerTag is collapsed, as shown in the following illustration.</span></span>

 <span data-ttu-id="59988-122">![XML-Code mit verborgenem innerem Knoten](../../database-engine/media/editoutlinexmlinnercol.gif "XML-Code mit verborgenem innerem Knoten")</span><span class="sxs-lookup"><span data-stu-id="59988-122">![XML code with inner node hidden](../../database-engine/media/editoutlinexmlinnercol.gif "XML code with inner node hidden")</span></span>

 <span data-ttu-id="59988-123">Wenn Sie den Mauszeiger über das Feld mit den drei Punkten (…) bewegen, wird der Code wie in der folgenden Abbildung gezeigt im reduzierten Bereich in einer QuickInfo angezeigt.</span><span class="sxs-lookup"><span data-stu-id="59988-123">When you move the pointer over the box that has the three periods (...), the code in the collapsed region appears in a tooltip, as shown in the following illustration.</span></span>

 <span data-ttu-id="59988-124">![XML-Code mit QuickInfo mit verborgenem Code](../../database-engine/media/editoutlinexmlmouse.gif "XML-Code mit QuickInfo mit verborgenem Code")</span><span class="sxs-lookup"><span data-stu-id="59988-124">![XML code with tooltip showing hidden code](../../database-engine/media/editoutlinexmlmouse.gif "XML code with tooltip showing hidden code")</span></span>

 <span data-ttu-id="59988-125">Wenn Sie auf das Minuszeichen in der \<MiddleTag> Zeile klicken, werden "MiddleTag" und "InnerTag" reduziert, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="59988-125">When you click the minus sign on the \<MiddleTag> line, both the MiddleTag and InnerTag are collapsed, as shown in the following illustration.</span></span>

 <span data-ttu-id="59988-126">![XML-Code mit verborgenen inneren und mittleren Tags](../../database-engine/media/editoutlinexmlmiddlecol.gif "XML-Code mit verborgenen inneren und mittleren Tags")</span><span class="sxs-lookup"><span data-stu-id="59988-126">![XML code with inner and middle tags hidden](../../database-engine/media/editoutlinexmlmiddlecol.gif "XML code with inner and middle tags hidden")</span></span>

 <span data-ttu-id="59988-127">Wenn Sie auf das Minuszeichen in der \<OuterTag> Zeile klicken, werden alle drei Zeilen reduziert, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="59988-127">When you click the minus sign on the \<OuterTag> line, all three lines are collapsed, as shown in the following illustration.</span></span>

 <span data-ttu-id="59988-128">![XML-Code, bei dem alle drei Tags verborgen sind](../../database-engine/media/editoutlinexmloutercol.gif "XML-Code, bei dem alle drei Tags verborgen sind")</span><span class="sxs-lookup"><span data-stu-id="59988-128">![XML code showing all three tags hidden](../../database-engine/media/editoutlinexmloutercol.gif "XML code showing all three tags hidden")</span></span>

### <a name="database-engine-query-editor-regions"></a><span data-ttu-id="59988-129">Gliederungsbereiche des Datenbank-Engine-Abfrage-Editors</span><span class="sxs-lookup"><span data-stu-id="59988-129">Database Engine Query Editor Regions</span></span>
 <span data-ttu-id="59988-130">Der [!INCLUDE[ssDE](../../../includes/ssde-md.md)] -Abfrage-Editor generiert Gliederungsbereiche für jedes Element in der folgenden Hierarchie:</span><span class="sxs-lookup"><span data-stu-id="59988-130">The [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Query Editor generates outline regions for each element in the following hierarchy:</span></span>

1.  <span data-ttu-id="59988-131">Batches.</span><span class="sxs-lookup"><span data-stu-id="59988-131">Batches.</span></span> <span data-ttu-id="59988-132">Der erste Batch ist der Code vom Anfang der Datei bis zum ersten GO-Befehl oder bis zum Ende der Datei, wenn keine GO-Befehle vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="59988-132">The first batch is the code from the start of the file to either the first GO command or the end of the file when there are no GO commands.</span></span> <span data-ttu-id="59988-133">Nach dem ersten GO-Befehl gibt es einen Batch von jedem GO-Befehl bis zum nächsten GO-Befehl oder bis zum Ende der Datei.</span><span class="sxs-lookup"><span data-stu-id="59988-133">After the first GO, there is one batch from each GO command to either the next GO command or the end of the file.</span></span>

2.  <span data-ttu-id="59988-134">Blöcke, die durch die folgenden Schlüsselwörter begrenzt sind:</span><span class="sxs-lookup"><span data-stu-id="59988-134">Blocks delimited by the following keywords:</span></span>

    -   <span data-ttu-id="59988-135">BEGIN - END</span><span class="sxs-lookup"><span data-stu-id="59988-135">BEGIN - END</span></span>

    -   <span data-ttu-id="59988-136">BEGIN TRY - END TRY</span><span class="sxs-lookup"><span data-stu-id="59988-136">BEGIN TRY - END TRY</span></span>

    -   <span data-ttu-id="59988-137">BEGIN CATCH - END CATCH</span><span class="sxs-lookup"><span data-stu-id="59988-137">BEGIN CATCH - END CATCH</span></span>

3.  <span data-ttu-id="59988-138">Mehrzeilige Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="59988-138">Multiline statements.</span></span>

 <span data-ttu-id="59988-139">Der [!INCLUDE[ssDE](../../../includes/ssde-md.md)] -Abfrage-Editor erstellt z. B. drei Gliederungsbereiche für die folgende Abfrage:</span><span class="sxs-lookup"><span data-stu-id="59988-139">For example, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Query Editor creates three outline regions for the following query:</span></span>

```
CREATE PROCEDURE Sales.SampleProc --Outline region 1
AS
BEGIN --Outline region 2 
  SELECT GETDATE() AS TimeOfQuery;
  SELECT * --Outline region 3
  FROM sys.transmission_queue;
  SELECT @@VERSION;
END;
GO
```

 <span data-ttu-id="59988-140">Sie können auf das Minuszeichen in der `SELECT *` -Zeile klicken, um nur diese `SELECT` -Anweisung zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="59988-140">You can click the minus sign on the `SELECT *` line to collapse just that `SELECT` statement.</span></span> <span data-ttu-id="59988-141">Um den gesamten `BEGIN - END` -Block zu reduzieren, klicken Sie auf das Minuszeichen in der `BEGIN` -Zeile.</span><span class="sxs-lookup"><span data-stu-id="59988-141">To collapse the whole `BEGIN - END` block, click the minus sign on the `BEGIN` line.</span></span> <span data-ttu-id="59988-142">Um den gesamten Batch bis zum `GO` -Befehl zu reduzieren, klicken Sie auf das Minuszeichen in der `CREATE PROCEDURE` -Zeile.</span><span class="sxs-lookup"><span data-stu-id="59988-142">To collapse the whole batch to the `GO` command, click the minus sign on the `CREATE PROCEDURE` line.</span></span> <span data-ttu-id="59988-143">Es ist nicht möglich, die `SELECT GETDATE()` -Zeile oder die `SELECT @@VERSION` -Zeile einzeln zu reduzieren, da es sich um einzeilige Anweisungen handelt, die keine Gliederungsbereiche erhalten.</span><span class="sxs-lookup"><span data-stu-id="59988-143">You cannot collapse the `SELECT GETDATE()` or `SELECT @@VERSION` lines individually because they are single line statements and do not get outlining regions.</span></span>


