---
title: Transformations-Editor für Ausdrucksextrahierung (Registerkarte Ausschluss Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termextraction.inclusionexclusion.f1
helpviewer_keywords:
- Term Extraction Transformation Editor
ms.assetid: 90110d95-fd97-4542-9cda-832c86606130
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9bc4b0401a1dd27111d0498e9e0d848c80da1742
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622213"
---
# <a name="term-extraction-transformation-editor-exclusion-tab"></a><span data-ttu-id="60f84-102">Transformations-Editor für Ausdrucksextrahierung (Registerkarte Ausschluss)</span><span class="sxs-lookup"><span data-stu-id="60f84-102">Term Extraction Transformation Editor (Exclusion Tab)</span></span>
  <span data-ttu-id="60f84-103">Auf der Registerkarte **Ausschluss** des Dialogfelds **Transformations-Editor für Ausdrucksextrahierung** können Sie eine Verbindung mit einer Ausschlusstabelle einrichten und die Spalten mit den Ausschlussausdrücken angeben.</span><span class="sxs-lookup"><span data-stu-id="60f84-103">Use the **Exclusion** tab of the **Term Extraction Transformation Editor** dialog box to set up a connection to an exclusion table and specify the columns that contain exclusion terms.</span></span>  
  
 <span data-ttu-id="60f84-104">Weitere Informationen zur Transformation für Ausdrucksextrahierung finden Sie unter [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="60f84-104">To learn more about the Term Extraction transformation, see [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="60f84-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="60f84-105">Options</span></span>  
 <span data-ttu-id="60f84-106">**Ausschlussausdrücke verwenden**</span><span class="sxs-lookup"><span data-stu-id="60f84-106">**Use exclusion terms**</span></span>  
 <span data-ttu-id="60f84-107">Geben Sie an, ob bei der Ausdrucksextrahierung bestimmte Ausdrücke ausgeschlossen werden sollen, indem eine Spalte mit Ausschlussausdrücken angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="60f84-107">Indicate whether to exclude specific terms during term extraction by specifying a column that contains exclusion terms.</span></span> <span data-ttu-id="60f84-108">Wenn Sie bestimmte Ausdrücke ausschließen möchten, müssen Sie folgende Quelleigenschaften angeben.</span><span class="sxs-lookup"><span data-stu-id="60f84-108">You must specify the following source properties if you choose to exclude terms.</span></span>  
  
 <span data-ttu-id="60f84-109">**Teilcache**</span><span class="sxs-lookup"><span data-stu-id="60f84-109">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="60f84-110">Wählen Sie einen vorhandenen OLE DB-Verbindungs-Manager aus, oder erstellen Sie eine neue Verbindung, indem Sie auf **Neu**klicken.</span><span class="sxs-lookup"><span data-stu-id="60f84-110">Select an existing OLE DB connection manager, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="60f84-111">**Neu**</span><span class="sxs-lookup"><span data-stu-id="60f84-111">**New**</span></span>  
 <span data-ttu-id="60f84-112">Stellen Sie mithilfe des Dialogfelds **OLE DB-Verbindungs-Manager konfigurieren** eine neue Verbindung mit einer Datenbank her.</span><span class="sxs-lookup"><span data-stu-id="60f84-112">Create a new connection to a database by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="60f84-113">**Tabelle oder Sicht**</span><span class="sxs-lookup"><span data-stu-id="60f84-113">**Table or view**</span></span>  
 <span data-ttu-id="60f84-114">Wählen Sie die Tabelle oder Sicht aus, die die Ausschlussausdrücke enthält.</span><span class="sxs-lookup"><span data-stu-id="60f84-114">Select the table or view that contains the exclusion terms.</span></span>  
  
 <span data-ttu-id="60f84-115">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="60f84-115">**Column**</span></span>  
 <span data-ttu-id="60f84-116">Wählen Sie in der Tabelle oder Sicht die Spalte aus, die die Ausschlussausdrücke enthält.</span><span class="sxs-lookup"><span data-stu-id="60f84-116">Select the column in the table or view that contains the exclusion terms.</span></span>  
  
 <span data-ttu-id="60f84-117">**Konfigurieren der Fehlerausgabe**</span><span class="sxs-lookup"><span data-stu-id="60f84-117">**Configure Error Output**</span></span>  
 <span data-ttu-id="60f84-118">Geben Sie mit dem Dialogfeld [Fehlerausgabe konfigurieren](../../2014/integration-services/configure-error-output.md) die Fehlerbehandlung für Zeilen an, die Fehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="60f84-118">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling for rows that cause errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60f84-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60f84-119">See Also</span></span>  
 <span data-ttu-id="60f84-120">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="60f84-120">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="60f84-121">[Transformations-Editor für Ausdrucksextrahierung &#40;Registerkarten&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span><span class="sxs-lookup"><span data-stu-id="60f84-121">[Term Extraction Transformation Editor &#40;Term Extraction Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span></span>  
 <span data-ttu-id="60f84-122">[Transformations-Editor für Ausdrucksextrahierung &#40;&#41;Register](../../2014/integration-services/term-extraction-transformation-editor-advanced-tab.md) </span><span class="sxs-lookup"><span data-stu-id="60f84-122">[Term Extraction Transformation Editor &#40;Advanced Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-advanced-tab.md) </span></span>  
 [<span data-ttu-id="60f84-123">Transformation für Ausdruckssuche</span><span class="sxs-lookup"><span data-stu-id="60f84-123">Term Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
