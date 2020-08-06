---
title: Löschen der Analysis Services Caches | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6bf66fdd-6a03-4cea-b7e2-eb676ff276ff
author: minewiskan
ms.author: owend
ms.openlocfilehash: e4890dd322406dcf48bc6b8eca89f292cfe132a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697322"
---
# <a name="clear-the-analysis-services-caches"></a><span data-ttu-id="ffe2e-102">Löschen des Zwischenspeichers von Analysis Services</span><span class="sxs-lookup"><span data-stu-id="ffe2e-102">Clear the Analysis Services Caches</span></span>
  <span data-ttu-id="ffe2e-103">Zur Verbesserung der Abfrageleistung werden Daten von Analysis Services zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-103">Analysis Services caches data to boost query performance.</span></span> <span data-ttu-id="ffe2e-104">In diesem Thema sind Empfehlungen für die Verwendung des XMLA ClearCache-Befehls enthalten. Der Befehl dient dazu, Zwischenspeicher zu leeren, die als Antwort auf eine MDX-Abfrage erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-104">This topic provides recommendations for using the XMLA ClearCache command to clear caches that were created in response to an MDX query.</span></span> <span data-ttu-id="ffe2e-105">Die Auswirkungen der Ausführung von ClearCache sind abhängig davon, ob Sie ein tabellarisches oder ein mehrdimensionales Modell verwenden.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-105">The effects of running ClearCache vary depending on whether you are using a tabular or multidimensional model.</span></span>  
  
 <span data-ttu-id="ffe2e-106">**Löschen des Zwischenspeichers für mehrdimensionale Modelle**</span><span class="sxs-lookup"><span data-stu-id="ffe2e-106">**When to clear the cache for multidimensional models**</span></span>  
  
 <span data-ttu-id="ffe2e-107">Für mehrdimensionale Datenbanken erstellen Analysis Services Zwischenspeicher in der Formular-Engine bei der Auswertung einer Berechnung und in der Speicher-Engine für die Ergebnisse von Dimensionsabfragen und Measuregruppenabfragen.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-107">For multidimensional databases, Analysis Services builds caches in the formula engine when evaluating a calculation, and in the storage engine for the results of dimension queries and measure group queries.</span></span> <span data-ttu-id="ffe2e-108">Measuregruppenabfragen treten auf, wenn die Formel-Engine-Anforderungen Daten für eine Zellenkoordinate oder einen Teilcube abmessen.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-108">Measure group queries occur when the formula engine needs measure data for a cell coordinate or subcube.</span></span> <span data-ttu-id="ffe2e-109">Beim Abfragen von unnatürlichen Hierarchien treten Dimensionsabfragen auf und beim Anwenden von Autoexist-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-109">Dimension queries occur when querying unnatural hierarchies and when applying autoexists.</span></span>  
  
 <span data-ttu-id="ffe2e-110">Beim Durchführen von Leistungstests empfiehlt es sich, den Zwischenspeicher zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-110">Clearing the cache is recommended when conducting performance testing.</span></span> <span data-ttu-id="ffe2e-111">Durch das Löschen des Zwischenspeichers zwischen Testläufen wird sichergestellt, dass das Zwischenspeichern die Testergebnisse nicht verzerrt, die die Auswirkungen auf eine Abfrageentwurfsänderung messen.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-111">By clearing the cache between test runs, you ensure that caching does not skew any test results that measure the impact of a query design change.</span></span>  
  
 <span data-ttu-id="ffe2e-112">**Löschen des Zwischenspeichers für tabellarische Modelle**</span><span class="sxs-lookup"><span data-stu-id="ffe2e-112">**When to clear the cache for tabular models**</span></span>  
  
 <span data-ttu-id="ffe2e-113">Tabellarische Modelle werden im Allgemeinen im Arbeitsspeicher gespeichert, wo Aggregationen und andere Berechnungen beim Ausführen einer Abfrage ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-113">Tabular models are generally stored in memory, where aggregations and other calculations are performed at the time a query is executed.</span></span> <span data-ttu-id="ffe2e-114">Der ClearCache-Befehl hat nur eingeschränkte Auswirkungen auf tabellarische Modelle.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-114">As such, the ClearCache command has a limited effect on tabular models.</span></span> <span data-ttu-id="ffe2e-115">Bei einem tabellarischen Modell werden Daten möglicherweise dem Analysis Services-Zwischenspeicher hinzugefügt, wenn MDX-Abfragen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-115">For a tabular model, data may be added to the Analysis Services caches if MDX queries are run against it.</span></span> <span data-ttu-id="ffe2e-116">DAX-Measures (verwiesen durch MDX) und Autoexists-Vorgänge können im Einzelnen Ergebnisse im Formular- bzw. Dimensionszwischenspeicher zwischenspeichern.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-116">In particular, DAX measures referenced by MDX and autoexists operations can cache results in the formula cache and dimension cache respectively.</span></span> <span data-ttu-id="ffe2e-117">Beachten Sie jedoch, dass unnatürliche Hierarchien und Measuregruppenabfragen in der Speicher-Engine keine Ergebnisse zwischenspeichern.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-117">Note however, that unnatural hierarchies and measure group queries do not cache results in the storage engine.</span></span> <span data-ttu-id="ffe2e-118">Darüber hinaus ist es wichtig zu wissen, dass DAX-Abfragen die Ergebnisse nicht im Formular- bzw. in der Speicher-Engine zwischenspeichern.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-118">Additionally, it is important to recognize that DAX queries do not cache results in the formula and storage engine.</span></span> <span data-ttu-id="ffe2e-119">Falls Caches als Ergebnis von MDX-Abfragen vorhanden sind, werden durch das Ausführen von ClearCache auf ein tabellarisches Modell alle zwischengespeicherten Daten vom System ungültig.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-119">To the extent that caches exist as a result of MDX queries, running ClearCache against a tabular model will invalidate any cached data from the system.</span></span>  
  
 <span data-ttu-id="ffe2e-120">Durch das Ausführen von ClearCache wird auch der speicherinterne Cache in der xVelocity-Engine für Datenanalyse im Arbeitsspeicher (VertiPaq) gelöscht.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-120">Running ClearCache will also clear in-memory caches in the xVelocity in-memory analytics engine (VertiPaq).</span></span> <span data-ttu-id="ffe2e-121">Die xVelocity-Engine behält einen kleinen Satz zwischengespeicherter Ergebnisse bei.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-121">The xVelocity engine maintains a small set of cached results.</span></span> <span data-ttu-id="ffe2e-122">Durch das Ausführen von ClearCache werden diese Zwischenspeicher in der xVelocity-Engine ungültig.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-122">Running ClearCache will invalidate these caches in the xVelocity engine.</span></span>  
  
 <span data-ttu-id="ffe2e-123">Schließlich werden durch das Ausführen von ClearCache auch restliche Daten entfernt, die im Arbeitsspeicher übrig sind, wenn ein tabellarisches Modell für den `DirectQuery`-Modus neu konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-123">Finally, running ClearCache will also remove residual data that is left in memory when a tabular model is reconfigured for `DirectQuery` mode.</span></span> <span data-ttu-id="ffe2e-124">Dies ist besonders wichtig, wenn das Modell sensible Daten enthält, die engen Kontrollen unterliegen.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-124">This is particularly important if the model contains sensitive data that is subject to tight controls.</span></span> <span data-ttu-id="ffe2e-125">In diesem Fall ist das Ausführen von ClearCache eine vorbeugende Aktion, die Sie ergreifen können, um sicherzustellen, dass sensible Daten nur dort vorhanden sind, wo Sie sie erwarten.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-125">In this case, running ClearCache is a precautionary action that you can take to ensure that sensitive data exists only where you expect it to be.</span></span> <span data-ttu-id="ffe2e-126">Das manuelle Löschen des Zwischenspeichers ist notwendig, wenn Sie [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] verwenden, um das Modell bereitzustellen und den Abfragemodus zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-126">Clearing the cache manually is necessary if you are using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to deploy the model and change the query mode.</span></span> <span data-ttu-id="ffe2e-127">Demgegenüber wird durch die Verwendung von [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] zur Bestimmung von `DirectQuery` auf dem Modell der Zwischenspeicher durch die Partitionen automatisch gelöscht, wenn Sie das Modell umschalten, um diesen Abfragemodus zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-127">In contrast, using [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] to specify `DirectQuery` on the model and partitions will automatically clear the cache when you switch the model to use that query mode.</span></span>  
  
 <span data-ttu-id="ffe2e-128">Verglichen mit den Empfehlungen zum Löschen von mehrdimensionalen Modellzwischenspeichern während der Leistungstests gibt es keine umfassende Empfehlung zum Löschen von tabellarische Modellzwischenspeichern.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-128">Compared with recommendations for clearing multidimensional model caches during performance testing, there is no broad recommendation for clearing tabular model caches.</span></span> <span data-ttu-id="ffe2e-129">Wenn Sie die Bereitstellung eines tabellarischen Modells nicht verwalten, das sensible Daten enthält, gibt es keine bestimmte administrative Aufgabe, die erfordert, den Zwischenspeicher zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-129">If you are not managing the deployment of a tabular model that contains sensitive data, there is no specific administrative task that calls for clearing the cache.</span></span>  
  
## <a name="clear-the-cache-for-analysis-services-models"></a><span data-ttu-id="ffe2e-130">Löschen des Zwischenspeichers für Analysis Services-Modelle</span><span class="sxs-lookup"><span data-stu-id="ffe2e-130">Clear the cache for Analysis Services models</span></span>  
 <span data-ttu-id="ffe2e-131">Verwenden Sie XMLA und [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], um den Zwischenspeicher zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-131">To clear the cache, use XMLA and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="ffe2e-132">Sie können den Zwischenspeicher auf Datenbank-, Cube-, Dimensions-, Tabellen- oder Measuregruppenebene löschen.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-132">You can clear the cache at the database, cube, dimension or table, or measure group level.</span></span> <span data-ttu-id="ffe2e-133">Die folgenden Schritte zum Löschen des Zwischenspeichers auf Datenbankebene gelten für mehrdimensionale und tabellarische Modelle.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-133">The following steps for clearing the cache at the database level apply to both multidimensional models and tabular models.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ffe2e-134">Rigorose Leistungstests könnten einen umfassenderen Ansatz zum Löschen des Zwischenspeichers erfordern.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-134">Rigorous performance testing might require a more comprehensive approach to clearing the cache.</span></span> <span data-ttu-id="ffe2e-135">Anweisungen zum Leeren von Analysis Services- und Dateisystemzwischenspeichern finden Sie im Abschnitt zum Löschen von Zwischenspeichern im [SQL Server 2008 R2 Analysis Services-Vorgangshandbuch](https://go.microsoft.com/fwlink/?linkID=https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="ffe2e-135">For instructions on how to flush Analysis Services and file system caches, see the section on clearing caches in the [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?linkID=https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 <span data-ttu-id="ffe2e-136">Sowohl für mehrdimensionale als auch für tabellarische Modelle kann das Löschen dieser Zwischenspeicher ein zweistufiger Vorgang sein. Durch das Ausführen von ClearCache wird der Zwischenspeicher zunächst ungültig, und anschließend wird der Zwischenspeicher geleert, wenn die nächste Abfrage erhalten wird.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-136">For both multidimensional and tabular models, clearing some of these caches can be a two-step process that consists of invalidating the cache when ClearCache executes, followed by emptying the cache when the next query is received.</span></span> <span data-ttu-id="ffe2e-137">Eine Verkleinerung an Arbeitsspeichernutzung ist nur offensichtlich, nachdem der Zwischenspeicher tatsächlich geleert wurde.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-137">A reduction in memory consumption will be evident only after the cache is actually emptied.</span></span>  
  
 <span data-ttu-id="ffe2e-138">Zum Löschen des Zwischenspeichers müssen Sie einen Objektbezeichner für die `ClearCache`-Anweisung in einer XMLA-Abfrage bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-138">Clearing the cache requires that you provide an object identifier to the `ClearCache` statement in an XMLA query.</span></span> <span data-ttu-id="ffe2e-139">Im ersten Schritt in diesem Thema erfahren Sie, wie ein Objektbezeichner abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-139">The first step in this topic explains how to get an object identifier.</span></span>  
  
#### <a name="step-1-get-the-object-identifier"></a><span data-ttu-id="ffe2e-140">Schritt 1: Abrufen des Objektbezeichners</span><span class="sxs-lookup"><span data-stu-id="ffe2e-140">Step 1: Get the object identifier</span></span>  
  
1.  <span data-ttu-id="ffe2e-141">Klicken Sie in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]mit der rechten Maustaste auf ein Objekt, wählen Sie **Eigenschaften**aus, und kopieren Sie den Wert aus der ID-Eigenschaft im Bereich **Eigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="ffe2e-141">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], right-click an object, select **Properties**, and copy the value from the ID property in the **Properties** pane.</span></span> <span data-ttu-id="ffe2e-142">Dieser Ansatz funktioniert für die Datenbank, Cube, Dimension oder Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-142">This approach works for the database, cube, dimension, or table.</span></span>  
  
2.  <span data-ttu-id="ffe2e-143">Klicken Sie mit der rechten Maustaste auf die Measuregruppe, und wählen Sie **Skript für Measuregruppe als**aus, um die Measuregruppen-ID abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-143">To get the measure group ID, right-click the measure group and select **Script Measure Group As**.</span></span> <span data-ttu-id="ffe2e-144">Wählen Sie entweder **Erstellen** oder **Ändern**, und senden Sie die Abfrage an ein Fenster.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-144">Choose either **Create** or **Alter**, and send the query to a window.</span></span> <span data-ttu-id="ffe2e-145">Die ID der Measuregruppe ist in der Objektdefinition sichtbar.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-145">The ID of the measure group will be visible in the object definition.</span></span> <span data-ttu-id="ffe2e-146">Kopieren Sie die ID der Objektdefinition.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-146">Copy the ID of the object definition.</span></span>  
  
#### <a name="step-2-run-the-query"></a><span data-ttu-id="ffe2e-147">Schritt 2: Ausführen der Abfrage</span><span class="sxs-lookup"><span data-stu-id="ffe2e-147">Step 2: Run the query</span></span>  
  
1.  <span data-ttu-id="ffe2e-148">Klicken Sie in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]mit der rechten Maustaste auf eine Datenbank, zeigen Sie auf **Neue Abfrage**, und wählen Sie anschließend **XMLA**aus.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-148">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], right-click a database, point to **New Query**, and select **XMLA**.</span></span>  
  
2.  <span data-ttu-id="ffe2e-149">Kopieren Sie das folgende Codebeispiel in das XMLA-Abfragefenster.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-149">Copy the following code example into the XMLA query window.</span></span> <span data-ttu-id="ffe2e-150">Ändern Sie `DatabaseID` in die ID der Datenbank auf der aktuellen Verbindung.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-150">Change `DatabaseID` to the ID of the database on the current connection.</span></span>  
  
    ```  
    <ClearCache xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
      <Object>  
        <DatabaseID> Adventure Works DW Multidimensional</DatabaseID>  
      </Object>  
    </ClearCache>  
  
    ```  
  
     <span data-ttu-id="ffe2e-151">Alternativ können Sie einen Pfad eines untergeordneten Objekts, z. B. eine Measuregruppe, angeben, um den Zwischenspeicher nur für dieses Objekt zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-151">Alternatively, you can specify a path of a child object, such as a measure group, to clear the cache for just that object.</span></span>  
  
    ```  
    <ClearCache xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
      <Object>  
        <DatabaseID>Adventure Works DW Multidimensional</DatabaseID>  
            <CubeID>Adventure Works</CubeID>  
            <MeasureGroupID>Fact Currency Rate</MeasureGroupID>  
      </Object>  
    </ClearCache>  
    ```  
  
3.  <span data-ttu-id="ffe2e-152">Drücken Sie F5, um die Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ffe2e-152">Press F5 to execute the query.</span></span> <span data-ttu-id="ffe2e-153">Das folgende Ergebnis wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ffe2e-153">You should see the following result:</span></span>  
  
    ```  
    <return xmlns="urn:schemas-microsoft-com:xml-analysis">  
      <root xmlns="urn:schemas-microsoft-com:xml-analysis:empty" />  
    </return>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ffe2e-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ffe2e-154">See Also</span></span>  
 <span data-ttu-id="ffe2e-155">[Skripterstellung für administrative Aufgaben in Analysis Services](../script-administrative-tasks-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="ffe2e-155">[Script Administrative Tasks in Analysis Services](../script-administrative-tasks-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="ffe2e-156">Überwachen einer Instanz von Analysis Services</span><span class="sxs-lookup"><span data-stu-id="ffe2e-156">Monitor an Analysis Services Instance</span></span>](monitor-an-analysis-services-instance.md)  
  
  