---
title: Editor für Data Mining-Abfrage Tasks (Registerkarte Abfrage) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dmquerytask.query.f1
helpviewer_keywords:
- Data Mining Query Task Editor
ms.assetid: 72b1755d-d226-46c5-b862-0c9333196a10
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6005c92d0d48850461c01353ddf94c61140d0f2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722909"
---
# <a name="data-mining-query-task-editor-query-tab"></a><span data-ttu-id="7e834-102">Editor für Data Mining-Abfragetasks (Registerkarte Abfrage)</span><span class="sxs-lookup"><span data-stu-id="7e834-102">Data Mining Query Task Editor (Query Tab)</span></span>
  <span data-ttu-id="7e834-103">Mithilfe der Registerkarte **Abfrage** des Dialogfelds **Data Mining-Abfragetask** können Sie Vorhersageabfragen auf der Grundlage eines Miningmodells erstellen.</span><span class="sxs-lookup"><span data-stu-id="7e834-103">Use the **Query** tab of the **Data Mining Query Task** dialog box to create prediction queries based on a mining model.</span></span> <span data-ttu-id="7e834-104">In diesem Dialogfeld können Sie auch Parameter und Resultsets an Variablen anbinden.</span><span class="sxs-lookup"><span data-stu-id="7e834-104">In this dialog box you can also bind parameters and result sets to variables.</span></span>  
  
 <span data-ttu-id="7e834-105">Weitere Informationen zur Implementierung von Data Mining in Paketen finden Sie unter [Data Mining-Abfragetask](control-flow/data-mining-query-task.md) und [Data Mining-Projektmappen](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span><span class="sxs-lookup"><span data-stu-id="7e834-105">To learn about implementing data mining in packages, see [Data Mining Query Task](control-flow/data-mining-query-task.md) and [Data Mining Solutions](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="7e834-106">Allgemeine Optionen</span><span class="sxs-lookup"><span data-stu-id="7e834-106">General Options</span></span>  
 <span data-ttu-id="7e834-107">**Name**</span><span class="sxs-lookup"><span data-stu-id="7e834-107">**Name**</span></span>  
 <span data-ttu-id="7e834-108">Geben Sie einen eindeutigen Namen für die Data Mining-Abfragetasks ein.</span><span class="sxs-lookup"><span data-stu-id="7e834-108">Provide a unique name for the Data Mining Query task.</span></span> <span data-ttu-id="7e834-109">Dieser Name wird im Tasksymbol als Bezeichnung verwendet.</span><span class="sxs-lookup"><span data-stu-id="7e834-109">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7e834-110">Tasknamen müssen innerhalb eines Pakets eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="7e834-110">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="7e834-111">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="7e834-111">**Description**</span></span>  
 <span data-ttu-id="7e834-112">Geben Sie eine Beschreibung für den Data Mining-Abfragetask ein.</span><span class="sxs-lookup"><span data-stu-id="7e834-112">Type a description of the Data Mining Query task.</span></span>  
  
## <a name="build-query-tab-options"></a><span data-ttu-id="7e834-113">Optionen der Registerkarte Abfrage erstellen</span><span class="sxs-lookup"><span data-stu-id="7e834-113">Build Query Tab Options</span></span>  
 <span data-ttu-id="7e834-114">**Data Mining-Abfrage**</span><span class="sxs-lookup"><span data-stu-id="7e834-114">**Data mining query**</span></span>  
 <span data-ttu-id="7e834-115">Geben Sie eine Data Mining-Abfrage ein.</span><span class="sxs-lookup"><span data-stu-id="7e834-115">Type a data mining query.</span></span>  
  
 <span data-ttu-id="7e834-116">**Verwandte Themen:**  [Data Mining-Erweiterungen &#40;DMX&#41; – Referenz](/sql/dmx/data-mining-extensions-dmx-reference)</span><span class="sxs-lookup"><span data-stu-id="7e834-116">**Related Topics:**  [Data Mining Extensions &#40;DMX&#41; Reference](/sql/dmx/data-mining-extensions-dmx-reference)</span></span>  
  
 <span data-ttu-id="7e834-117">**Neue Abfrage erstellen**</span><span class="sxs-lookup"><span data-stu-id="7e834-117">**Build New Query**</span></span>  
 <span data-ttu-id="7e834-118">Erstellt die Data Mining-Abfrage mithilfe eines grafischen Tools.</span><span class="sxs-lookup"><span data-stu-id="7e834-118">Create the data mining query using a graphical tool.</span></span>  
  
 <span data-ttu-id="7e834-119">**Verwandte Themen:** [Data Mining Query](control-flow/data-mining-query.md)</span><span class="sxs-lookup"><span data-stu-id="7e834-119">**Related Topics:** [Data Mining Query](control-flow/data-mining-query.md)</span></span>  
  
## <a name="parameter-mapping-tab-options"></a><span data-ttu-id="7e834-120">Optionen der Registerkarte Parameterzuordnung</span><span class="sxs-lookup"><span data-stu-id="7e834-120">Parameter Mapping Tab Options</span></span>  
 <span data-ttu-id="7e834-121">**Parametername**</span><span class="sxs-lookup"><span data-stu-id="7e834-121">**Parameter Name**</span></span>  
 <span data-ttu-id="7e834-122">Sie können optional den Parameternamen aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7e834-122">Optionally, update the parameter name.</span></span> <span data-ttu-id="7e834-123">Ordnen Sie den Parameter einer Variable zu, indem Sie in der Liste **Variablenname** eine Variable auswählen.</span><span class="sxs-lookup"><span data-stu-id="7e834-123">Map the parameter to a variable by selecting a variable in the **Variable Name** list.</span></span>  
  
 <span data-ttu-id="7e834-124">**Variablenname**</span><span class="sxs-lookup"><span data-stu-id="7e834-124">**Variable Name**</span></span>  
 <span data-ttu-id="7e834-125">Wählen Sie in der Liste eine Variable aus, um sie dem Parameter zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="7e834-125">Select a variable in the list to map it to the parameter.</span></span>  
  
 <span data-ttu-id="7e834-126">**Add**</span><span class="sxs-lookup"><span data-stu-id="7e834-126">**Add**</span></span>  
 <span data-ttu-id="7e834-127">Fügt der Liste einen Parameter hinzu.</span><span class="sxs-lookup"><span data-stu-id="7e834-127">Add to a parameter to the list.</span></span>  
  
 <span data-ttu-id="7e834-128">**Entfernen**</span><span class="sxs-lookup"><span data-stu-id="7e834-128">**Remove**</span></span>  
 <span data-ttu-id="7e834-129">Wählen Sie einen Parameter aus, und klicken Sie anschließend auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="7e834-129">Select a parameter, and then click **Remove**.</span></span>  
  
## <a name="result-set-tab-options"></a><span data-ttu-id="7e834-130">Optionen der Registerkarte Resultset</span><span class="sxs-lookup"><span data-stu-id="7e834-130">Result Set Tab Options</span></span>  
 <span data-ttu-id="7e834-131">**Ergebnisname**</span><span class="sxs-lookup"><span data-stu-id="7e834-131">**Result Name**</span></span>  
 <span data-ttu-id="7e834-132">Sie können optional den Resultsetnamen aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7e834-132">Optionally, update the result set name.</span></span> <span data-ttu-id="7e834-133">Ordnen Sie das Resultset einer Variable zu, indem Sie in der Liste **Variablenname** eine Variable auswählen.</span><span class="sxs-lookup"><span data-stu-id="7e834-133">Map the result to a variable by selecting a variable in the **Variable Name** list.</span></span>  
  
 <span data-ttu-id="7e834-134">Nachdem Sie das Ergebnis durch Klicken auf **Hinzufügen**hinzugefügt haben, geben Sie einen eindeutigen Namen für das Ergebnis an.</span><span class="sxs-lookup"><span data-stu-id="7e834-134">After you have added a result by clicking **Add**, provide a unique name for the result.</span></span>  
  
 <span data-ttu-id="7e834-135">**Variablenname**</span><span class="sxs-lookup"><span data-stu-id="7e834-135">**Variable Name**</span></span>  
 <span data-ttu-id="7e834-136">Wählen Sie in der Liste eine Variable aus, um sie dem Resultset zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="7e834-136">Select a variable in the list to map it to the result set.</span></span>  
  
 <span data-ttu-id="7e834-137">**Ergebnistyp**</span><span class="sxs-lookup"><span data-stu-id="7e834-137">**Result Type**</span></span>  
 <span data-ttu-id="7e834-138">Gibt an, ob eine einzelne Zeile oder ein vollständiges Resultset zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="7e834-138">Indicate whether to return a single row or a full result set.</span></span>  
  
 <span data-ttu-id="7e834-139">**Add**</span><span class="sxs-lookup"><span data-stu-id="7e834-139">**Add**</span></span>  
 <span data-ttu-id="7e834-140">Fügt ein Resultset zur Liste hinzu.</span><span class="sxs-lookup"><span data-stu-id="7e834-140">Add a result set to the list.</span></span>  
  
 <span data-ttu-id="7e834-141">**Entfernen**</span><span class="sxs-lookup"><span data-stu-id="7e834-141">**Remove**</span></span>  
 <span data-ttu-id="7e834-142">Wählen Sie ein Ergebnis aus, und klicken Sie anschließen auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="7e834-142">Select a result, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e834-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7e834-143">See Also</span></span>  
 <span data-ttu-id="7e834-144">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="7e834-144">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="7e834-145">[Editor für den Data Mining-Abfrage Task &#40;Registerkarte Mining Modell&#41;](../../2014/integration-services/data-mining-query-task-editor-mining-model-tab.md) </span><span class="sxs-lookup"><span data-stu-id="7e834-145">[Data Mining Query Task Editor &#40;Mining Model Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-mining-model-tab.md) </span></span>  
 <span data-ttu-id="7e834-146">[Editor für Data Mining-Abfrage Tasks &#40;Registerkarte Ausgabe&#41;](../../2014/integration-services/data-mining-query-task-editor-output-tab.md) </span><span class="sxs-lookup"><span data-stu-id="7e834-146">[Data Mining Query Task Editor &#40;Output Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-output-tab.md) </span></span>  
 [<span data-ttu-id="7e834-147">Data Mining Designer</span><span class="sxs-lookup"><span data-stu-id="7e834-147">Data Mining Designer</span></span>](https://docs.microsoft.com/analysis-services/data-mining/data-mining-designer)  
  
  
