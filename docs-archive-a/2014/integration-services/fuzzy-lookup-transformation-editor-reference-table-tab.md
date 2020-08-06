---
title: Transformations-Editor für Fuzzysuche (Registerkarte Verweis Tabelle) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzylookuptransformation.referencetable.f1
helpviewer_keywords:
- Fuzzy Lookup Transformation Editor
ms.assetid: 451f4e7d-1c8e-4784-b540-df0806509bf1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9ce51dd64c9c5807ab23ac645694cfec29a36d52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609332"
---
# <a name="fuzzy-lookup-transformation-editor-reference-table-tab"></a><span data-ttu-id="63ed1-102">Transformations-Editor für Fuzzysuche (Registerkarte Verweistabelle)</span><span class="sxs-lookup"><span data-stu-id="63ed1-102">Fuzzy Lookup Transformation Editor (Reference Table Tab)</span></span>
  <span data-ttu-id="63ed1-103">Auf der Registerkarte **Verweistabelle** des Dialogfelds **Transformations-Editor für Fuzzysuche** können Sie die Quelltabelle und den Index für die Suche angeben.</span><span class="sxs-lookup"><span data-stu-id="63ed1-103">Use the **Reference Table** tab of the **Fuzzy Lookup Transformation Editor** dialog box to specify the source table and the index to use for the lookup.</span></span> <span data-ttu-id="63ed1-104">Bei der Verweisdatenquelle muss es sich um eine Tabelle in einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Datenbank handeln.</span><span class="sxs-lookup"><span data-stu-id="63ed1-104">The reference data source must be a table in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63ed1-105">Durch die Transformation für die Fuzzysuche wird eine Arbeitskopie der Verweistabelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="63ed1-105">The Fuzzy Lookup transformation creates a working copy of the reference table.</span></span> <span data-ttu-id="63ed1-106">Die nachfolgend beschriebenen Indizes werden für diese Arbeitstabelle mithilfe einer Spezialtabelle erstellt, und nicht mit einem normalen [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Index.</span><span class="sxs-lookup"><span data-stu-id="63ed1-106">The indexes described below are created on this working table by using a special table, not an ordinary [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] index.</span></span> <span data-ttu-id="63ed1-107">Durch die Transformation werden die vorhandenen Quelltabellen nicht verändert, sofern Sie nicht **Gespeicherten Index beibehalten**auswählen.</span><span class="sxs-lookup"><span data-stu-id="63ed1-107">The transformation does not modify the existing source tables unless you select **Maintain stored index**.</span></span> <span data-ttu-id="63ed1-108">In diesem Fall wird ein Trigger für die Verweistabelle erstellt, der die Arbeitstabelle und die Suchindextabelle auf der Grundlage von Änderungen an der Verweistabelle aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="63ed1-108">In this case, it creates a trigger on the reference table that updates the working table and the lookup index table based on changes to the reference table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63ed1-109">Die `Exhaustive` -Eigenschaft und die-Eigenschaft der `MaxMemoryUsage` Transformation für Fuzzysuche sind im **Transformations-Editor für Fuzzysuche**nicht verfügbar, können jedoch mit dem- **Erweiterter Editor**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="63ed1-109">The `Exhaustive` and the `MaxMemoryUsage` properties of the Fuzzy Lookup transformation are not available in the **Fuzzy Lookup Transformation Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="63ed1-110">Außerdem kann ein Wert, der größer als 100 für ist, `MaxOutputMatchesPerInput` nur in der **Erweiterter Editor**angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="63ed1-110">In addition, a value greater than 100 for `MaxOutputMatchesPerInput` can be specified only in the **Advanced Editor**.</span></span> <span data-ttu-id="63ed1-111">Weitere Informationen zu diesen Eigenschaften finden Sie im Abschnitt Transformation für Fuzzysuche von [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="63ed1-111">For more information on these properties, see the Fuzzy Lookup Transformation section of [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="63ed1-112">Weitere Informationen zur Transformation für Fuzzysuche finden Sie unter [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="63ed1-112">To learn more about the Fuzzy Lookup transformation, see [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="63ed1-113">Tastatur</span><span class="sxs-lookup"><span data-stu-id="63ed1-113">Options</span></span>  
 <span data-ttu-id="63ed1-114">**Teilcache**</span><span class="sxs-lookup"><span data-stu-id="63ed1-114">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="63ed1-115">Wählen Sie einen vorhandenen OLE DB-Verbindungs-Manager aus der Liste aus, oder erstellen Sie eine neue Verbindung, indem Sie auf **Neu**klicken.</span><span class="sxs-lookup"><span data-stu-id="63ed1-115">Select an existing OLE DB connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="63ed1-116">**Neu**</span><span class="sxs-lookup"><span data-stu-id="63ed1-116">**New**</span></span>  
 <span data-ttu-id="63ed1-117">Erstellen Sie mithilfe des Dialogfelds **OLE DB-Verbindungs-Manager konfigurieren** eine neue Verbindung.</span><span class="sxs-lookup"><span data-stu-id="63ed1-117">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="63ed1-118">**Neuen Index generieren**</span><span class="sxs-lookup"><span data-stu-id="63ed1-118">**Generate new index**</span></span>  
 <span data-ttu-id="63ed1-119">Geben Sie an, dass die Transformation einen neuen Index erstellen soll, der für die Suche verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="63ed1-119">Specify that the transformation should create a new index to use for the lookup.</span></span>  
  
 <span data-ttu-id="63ed1-120">**Name der Verweistabelle**</span><span class="sxs-lookup"><span data-stu-id="63ed1-120">**Reference table name**</span></span>  
 <span data-ttu-id="63ed1-121">Wählen Sie die vorhandene Tabelle aus, die als Verweis-(Such-)Tabelle verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="63ed1-121">Select the existing table to use as the reference (lookup) table.</span></span>  
  
 <span data-ttu-id="63ed1-122">**Neuen Index speichern**</span><span class="sxs-lookup"><span data-stu-id="63ed1-122">**Store new index**</span></span>  
 <span data-ttu-id="63ed1-123">Wählen Sie diese Option aus, wenn Sie den neuen Suchindex speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="63ed1-123">Select this option if you want to save the new lookup index.</span></span>  
  
 <span data-ttu-id="63ed1-124">**Name des neuen Indexes**</span><span class="sxs-lookup"><span data-stu-id="63ed1-124">**New index name**</span></span>  
 <span data-ttu-id="63ed1-125">Wenn Sie den neuen Suchindex speichern möchten, geben Sie einen beschreibenden Namen für den Index ein.</span><span class="sxs-lookup"><span data-stu-id="63ed1-125">If you have chosen to save the new lookup index, type a descriptive name for the index.</span></span>  
  
 <span data-ttu-id="63ed1-126">**Gespeicherten Index beibehalten**</span><span class="sxs-lookup"><span data-stu-id="63ed1-126">**Maintain stored index**</span></span>  
 <span data-ttu-id="63ed1-127">Wenn Sie den neuen Suchindex speichern möchten, geben Sie an, ob der Index auch in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] beibehalten werden soll.</span><span class="sxs-lookup"><span data-stu-id="63ed1-127">If you have chosen to save the new lookup index, specify whether you also want [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to maintain the index.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63ed1-128">Wenn Sie **Gespeicherten Index beibehalten** auf der Registerkarte **Verweistabelle** des Dialogfelds **Transformations-Editor für Fuzzysuche**wählen, verwendet die Transformation verwaltete gespeicherte Prozeduren zum Verwalten des Index.</span><span class="sxs-lookup"><span data-stu-id="63ed1-128">When you select **Maintain stored index** on the **Reference Table** tab of the **Fuzzy Lookup Transformation Editor**, the transformation uses managed stored procedures to maintain the index.</span></span> <span data-ttu-id="63ed1-129">Diese verwalteten gespeicherten Prozeduren verwenden die Common Language Runtime-Integrationsfunktion (CLR) in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63ed1-129">These managed stored procedures use the common language runtime (CLR) integration feature in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="63ed1-130">Standardmäßig ist die CLR-Integration in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="63ed1-130">By default, CLR integration in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is not enabled.</span></span> <span data-ttu-id="63ed1-131">Um die Funktion **Gespeicherten Index beibehalten** zu verwenden, müssen Sie die CLR-Integration aktivieren.</span><span class="sxs-lookup"><span data-stu-id="63ed1-131">To use the **Maintain stored index** functionality, you must enable CLR integration.</span></span> <span data-ttu-id="63ed1-132">Weitere Informationen finden Sie unter [Enabling CLR Integration](../relational-databases/clr-integration/clr-integration-enabling.md).</span><span class="sxs-lookup"><span data-stu-id="63ed1-132">For more information, see [Enabling CLR Integration](../relational-databases/clr-integration/clr-integration-enabling.md).</span></span>  
>   
>  <span data-ttu-id="63ed1-133">Da die Option **Gespeicherten Index beibehalten** die CLR-Integration erfordert, kann diese Funktion nur verwendet werden, wenn Sie in einer Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] eine Verweistabelle auswählen, für die die CLR-Integration aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="63ed1-133">Because the **Maintain stored index** option requires CLR integration, this feature works only when you select a reference table on an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] where CLR integration is enabled.</span></span>  
  
 <span data-ttu-id="63ed1-134">**Vorhandenen Index verwenden**</span><span class="sxs-lookup"><span data-stu-id="63ed1-134">**Use existing index**</span></span>  
 <span data-ttu-id="63ed1-135">Gibt an, dass bei der Transformation ein vorhandener Index für die Suche verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="63ed1-135">Specify that the transformation should use an existing index for the lookup.</span></span>  
  
 <span data-ttu-id="63ed1-136">**Name eines vorhandenen Indexes**</span><span class="sxs-lookup"><span data-stu-id="63ed1-136">**Name of an existing index**</span></span>  
 <span data-ttu-id="63ed1-137">Wählen Sie einen zu einem früheren Zeitpunkt erstellten Index aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="63ed1-137">Select a previously created lookup index from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63ed1-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="63ed1-138">See Also</span></span>  
 <span data-ttu-id="63ed1-139">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="63ed1-139">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="63ed1-140">[Transformations-Editor für Fuzzysuche &#40;Registerkarte Spalten&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-columns-tab.md) </span><span class="sxs-lookup"><span data-stu-id="63ed1-140">[Fuzzy Lookup Transformation Editor &#40;Columns Tab&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-columns-tab.md) </span></span>  
 [<span data-ttu-id="63ed1-141">Transformations-Editor für Fuzzysuche &#40;Registerkarte „Erweitert“&#41;</span><span class="sxs-lookup"><span data-stu-id="63ed1-141">Fuzzy Lookup Transformation Editor &#40;Advanced Tab&#41;</span></span>](../../2014/integration-services/fuzzy-lookup-transformation-editor-advanced-tab.md)  
  
  
