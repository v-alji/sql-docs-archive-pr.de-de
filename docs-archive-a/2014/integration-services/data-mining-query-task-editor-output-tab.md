---
title: Editor für Data Mining-Abfrage Tasks (Registerkarte Ausgabe) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dmquerytask.output.f1
helpviewer_keywords:
- Data Mining Query Task Editor
ms.assetid: 62f9e015-6fe0-4396-ad90-3ad51bf00025
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1508972b0487daa90f52af723d58185944a19a58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722913"
---
# <a name="data-mining-query-task-editor-output-tab"></a><span data-ttu-id="9ffa0-102">Editor für Data Mining-Abfragetasks (Registerkarte Ausgabe)</span><span class="sxs-lookup"><span data-stu-id="9ffa0-102">Data Mining Query Task Editor (Output Tab)</span></span>
  <span data-ttu-id="9ffa0-103">Mithilfe der Registerkarte **Ausgabe** des Dialogfelds **Editor für Data Mining-Abfragetasks** können Sie das Ziel der Vorhersageabfrage angeben.</span><span class="sxs-lookup"><span data-stu-id="9ffa0-103">Use the **Output** tab of the **Data Mining Query Task Editor** dialog box to specify the destination of the prediction query.</span></span>  
  
 <span data-ttu-id="9ffa0-104">Weitere Informationen zur Implementierung von Data Mining in Paketen finden Sie unter [Data Mining-Abfragetask](control-flow/data-mining-query-task.md) und [Data Mining-Projektmappen](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span><span class="sxs-lookup"><span data-stu-id="9ffa0-104">To learn about implementing data mining in packages, see [Data Mining Query Task](control-flow/data-mining-query-task.md) and [Data Mining Solutions](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="9ffa0-105">Allgemeine Optionen</span><span class="sxs-lookup"><span data-stu-id="9ffa0-105">General Options</span></span>  
 <span data-ttu-id="9ffa0-106">**Name**</span><span class="sxs-lookup"><span data-stu-id="9ffa0-106">**Name**</span></span>  
 <span data-ttu-id="9ffa0-107">Geben Sie einen eindeutigen Namen für die Data Mining-Abfragetasks ein.</span><span class="sxs-lookup"><span data-stu-id="9ffa0-107">Provide a unique name for the Data Mining Query task.</span></span> <span data-ttu-id="9ffa0-108">Dieser Name wird im Tasksymbol als Bezeichnung verwendet.</span><span class="sxs-lookup"><span data-stu-id="9ffa0-108">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9ffa0-109">Tasknamen müssen innerhalb eines Pakets eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="9ffa0-109">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="9ffa0-110">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="9ffa0-110">**Description**</span></span>  
 <span data-ttu-id="9ffa0-111">Geben Sie eine Beschreibung für den Data Mining-Abfragetask ein.</span><span class="sxs-lookup"><span data-stu-id="9ffa0-111">Type a description of the Data Mining Query task.</span></span>  
  
## <a name="output-tab-options"></a><span data-ttu-id="9ffa0-112">Optionen der Registerkarte Ausgabe</span><span class="sxs-lookup"><span data-stu-id="9ffa0-112">Output Tab Options</span></span>  
 <span data-ttu-id="9ffa0-113">**Connection**</span><span class="sxs-lookup"><span data-stu-id="9ffa0-113">**Connection**</span></span>  
 <span data-ttu-id="9ffa0-114">Wählen Sie einen Verbindungs-Manager aus der Liste aus, oder klicken Sie auf **Neu** , um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9ffa0-114">Select a connection manager in the list or click **New** to create a new connection manager.</span></span>  
  
 <span data-ttu-id="9ffa0-115">**Neu**</span><span class="sxs-lookup"><span data-stu-id="9ffa0-115">**New**</span></span>  
 <span data-ttu-id="9ffa0-116">Erstellt einen neuen Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="9ffa0-116">Create a new connection manager.</span></span> <span data-ttu-id="9ffa0-117">Sie können nur die ADO.NET- und OLE DB-Verbindungsmanagertypen verwenden.</span><span class="sxs-lookup"><span data-stu-id="9ffa0-117">Only the ADO.NET and OLE DB connection manager types can be used.</span></span>  
  
 <span data-ttu-id="9ffa0-118">**Ausgabetabelle**</span><span class="sxs-lookup"><span data-stu-id="9ffa0-118">**Output table**</span></span>  
 <span data-ttu-id="9ffa0-119">Geben Sie die Tabelle an, in die die Vorhersageabfrage ihre Ergebnisse schreiben soll.</span><span class="sxs-lookup"><span data-stu-id="9ffa0-119">Specify the table to which the prediction query writes its results.</span></span>  
  
 <span data-ttu-id="9ffa0-120">**Ausgabetabelle löschen und erneut erstellen**</span><span class="sxs-lookup"><span data-stu-id="9ffa0-120">**Drop and re-create the output table**</span></span>  
 <span data-ttu-id="9ffa0-121">Gibt an, ob die Vorhersageabfrage den Inhalt in der Zieltabelle überschreiben soll, indem die Tabelle gelöscht und anschließend erneut erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="9ffa0-121">Indicate whether the prediction query should overwrite content in the destination table by dropping and then re-creating the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ffa0-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9ffa0-122">See Also</span></span>  
 <span data-ttu-id="9ffa0-123">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="9ffa0-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="9ffa0-124">[Editor für den Data Mining-Abfrage Task &#40;Registerkarte Mining Modell&#41;](../../2014/integration-services/data-mining-query-task-editor-mining-model-tab.md) </span><span class="sxs-lookup"><span data-stu-id="9ffa0-124">[Data Mining Query Task Editor &#40;Mining Model Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-mining-model-tab.md) </span></span>  
 <span data-ttu-id="9ffa0-125">[Editor für Data Mining-Abfrage Tasks &#40;Abfrage Registerkarte&#41;](../../2014/integration-services/data-mining-query-task-editor-query-tab.md) </span><span class="sxs-lookup"><span data-stu-id="9ffa0-125">[Data Mining Query Task Editor &#40;Query Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-query-tab.md) </span></span>  
 [<span data-ttu-id="9ffa0-126">Data Mining Designer</span><span class="sxs-lookup"><span data-stu-id="9ffa0-126">Data Mining Designer</span></span>](https://docs.microsoft.com/analysis-services/data-mining/data-mining-designer)  
  
  
