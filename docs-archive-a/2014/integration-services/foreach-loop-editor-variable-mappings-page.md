---
title: Foreach-Schleifen-Editor (Seite Variablen Zuordnungen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.foreachloopcontainer.mapping.f1
ms.assetid: aa847b87-f391-48a5-9849-eeda2d6b00b9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd37c8c6c00f18d8b5493a058239cc880ecc1f5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727058"
---
# <a name="foreach-loop-editor-variable-mappings-page"></a><span data-ttu-id="163b6-102">Foreach-Schleifen-Editor (Seite Variablenzuordnungen)</span><span class="sxs-lookup"><span data-stu-id="163b6-102">Foreach Loop Editor (Variable Mappings Page)</span></span>
  <span data-ttu-id="163b6-103">Auf der Seite **Variablenzuordnungen** des Dialogfelds **Foreach-Schleifen-Editor** können Sie dem Sammlungswert Variablen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="163b6-103">Use the **Variables Mappings** page of the **Foreach Loop Editor** dialog box to map variables to the collection value.</span></span> <span data-ttu-id="163b6-104">Der Wert der Variablen wird bei jeder Iteration der Schleife mit den Sammlungswerten aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="163b6-104">The value of the variable is updated with the collection values on each iteration of the loop.</span></span>  
  
 <span data-ttu-id="163b6-105">Informationen zum Verwenden des Foreach-Schleifencontainers in einem Integration Services-Paket finden Sie unter [Foreach Loop Container](control-flow/foreach-loop-container.md) .</span><span class="sxs-lookup"><span data-stu-id="163b6-105">To learn about how to use the Foreach Loop container in an Integration Services package,  see [Foreach Loop Container](control-flow/foreach-loop-container.md) .</span></span> <span data-ttu-id="163b6-106">Informationen zum Konfigurieren dieses Containers finden Sie unter [Konfigurieren eines Foreach-Schleifencontainers](../../2014/integration-services/configure-a-foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="163b6-106">To learn about how to configure it, see [Configure a Foreach Loop Container](../../2014/integration-services/configure-a-foreach-loop-container.md).</span></span>  
  
 <span data-ttu-id="163b6-107">Das Tutorial für [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] zum Erstellen eines einfachen ETL-Pakets enthält eine Lektion, die Ihnen zeigt, wie Sie eine Foreach-Schleife hinzufügen und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="163b6-107">The [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] tutorial, Creating a Simple ETL Package Tutorial, includes a lesson that teaches you to add and configure a Foreach Loop.</span></span>  
  
## <a name="options"></a><span data-ttu-id="163b6-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="163b6-108">Options</span></span>  
 <span data-ttu-id="163b6-109">**Variable**</span><span class="sxs-lookup"><span data-stu-id="163b6-109">**Variable**</span></span>  
 <span data-ttu-id="163b6-110">Wählen Sie eine vorhandene Variable aus der Liste aus, oder klicken Sie auf \<**New variable...**>, um eine neue Variable zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="163b6-110">Select an existing variable, or click \<**New variable...**> to create a new variable.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="163b6-111">Nachdem Sie eine Variable zugeordnet haben, wird der Liste **Variable** automatisch eine neue Zeile hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="163b6-111">After you map a variable, a new row is automatically added to the **Variable** list.</span></span>  
  
 <span data-ttu-id="163b6-112">**Verwandte Themen:** [Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md), [Hinzufügen von Variablen](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="163b6-112">**Related Topics**: [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
 <span data-ttu-id="163b6-113">**Index**</span><span class="sxs-lookup"><span data-stu-id="163b6-113">**Index**</span></span>  
 <span data-ttu-id="163b6-114">Geben Sie bei Verwendung des Foreach-Element-Enumerators den Index der Spalte im Sammlungswert an, der der Variable zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="163b6-114">If using the Foreach Item enumerator, specify the index of the column in the collection value to map to the variable.</span></span> <span data-ttu-id="163b6-115">Bei anderen Enumeratortypen ist der Index schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="163b6-115">For other enumerator types, the index is read-only.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="163b6-116">Der Index basiert auf 0.</span><span class="sxs-lookup"><span data-stu-id="163b6-116">The index is 0-based.</span></span>  
  
 <span data-ttu-id="163b6-117">**Verwandte Themen**: [Schleife durch Excel-Dateien und Tabellen mit einem Foreach-Schleifencontainer](control-flow/loop-through-excel-files-and-tables-by-using-a-foreach-loop-container.md)</span><span class="sxs-lookup"><span data-stu-id="163b6-117">**Related Topics**: [Loop through Excel Files and Tables by Using a Foreach Loop Container](control-flow/loop-through-excel-files-and-tables-by-using-a-foreach-loop-container.md)</span></span>  
  
 <span data-ttu-id="163b6-118">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="163b6-118">**Delete**</span></span>  
 <span data-ttu-id="163b6-119">Wählen Sie eine Variable aus, und klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="163b6-119">Select a variable, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="163b6-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="163b6-120">See Also</span></span>  
 <span data-ttu-id="163b6-121">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="163b6-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="163b6-122">[Foreach-Schleifen-Editor &#40;Seite "Allgemein"&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="163b6-122">[Foreach Loop Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="163b6-123">[Foreach-Schleifen-Editor &#40;Sammlungs Seite&#41;](../../2014/integration-services/foreach-loop-editor-collection-page.md) </span><span class="sxs-lookup"><span data-stu-id="163b6-123">[Foreach Loop Editor &#40;Collection Page&#41;](../../2014/integration-services/foreach-loop-editor-collection-page.md) </span></span>  
 <span data-ttu-id="163b6-124">[Seite Ausdrücke](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="163b6-124">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="163b6-125">For-Schleifencontainer</span><span class="sxs-lookup"><span data-stu-id="163b6-125">For Loop Container</span></span>](control-flow/for-loop-container.md)  
  
  
