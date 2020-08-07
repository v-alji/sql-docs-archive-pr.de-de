---
title: Reduzieren der Optimierungsauslastung des Produktionsservers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- overhead [Database Engine Tuning Advisor]
- tuning overhead [SQL Server]
- reducing production server tuning load
- Database Engine Tuning Advisor [SQL Server], test servers
- test servers [Database Engine Tuning Advisor]
- production servers [SQL Server]
- offload tuning overhead [SQL Server]
ms.assetid: bb95ecaf-444a-4771-a625-e0a91c8f0709
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 53a61b17793a50d6b819f7c1684afdc4de4377f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619781"
---
# <a name="reduce-the-production-server-tuning-load"></a><span data-ttu-id="f6736-102">Reduzieren der Optimierungsauslastung des Produktionsservers</span><span class="sxs-lookup"><span data-stu-id="f6736-102">Reduce the Production Server Tuning Load</span></span>
  [!INCLUDE[ssDE](../../../includes/ssde-md.md)] <span data-ttu-id="f6736-103">-Optimierungsratgeber nutzt den Abfrageoptimierer, um die Arbeitsauslastung zu analysieren und Optimierungsempfehlungen zu geben.</span><span class="sxs-lookup"><span data-stu-id="f6736-103">Tuning Advisor relies on the query optimizer to analyze a workload and to make tuning recommendations.</span></span> <span data-ttu-id="f6736-104">Wenn diese Analyse auf dem Produktionsserver ausgeführt wird, erhöht sich die Serverlast. Dies kann zu Einbußen bei der Serverleistung während der Optimierungssitzung führen.</span><span class="sxs-lookup"><span data-stu-id="f6736-104">Performing this analysis on the production server adds to the server load and can hurt server performance during the tuning session.</span></span> <span data-ttu-id="f6736-105">Sie reduzieren die Serverlast während einer Optimierungssitzung, indem Sie zusätzlich zum Produktionsserver einen Testserver verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6736-105">You can reduce the impact to the server load during a tuning session by using a test server in addition to the production server.</span></span>

## <a name="how-database-engine-tuning-advisor-uses-a-test-server"></a><span data-ttu-id="f6736-106">Verwendung eines Testservers durch den Datenbankoptimierungsratgeber</span><span class="sxs-lookup"><span data-stu-id="f6736-106">How Database Engine Tuning Advisor Uses a Test Server</span></span>
 <span data-ttu-id="f6736-107">Die traditionelle Verwendungsweise eines Testservers besteht im Kopieren aller Daten vom Produktionsserver auf den Testserver, Optimieren des Testservers und anschließenden Implementieren der Empfehlung auf dem Produktionsserver.</span><span class="sxs-lookup"><span data-stu-id="f6736-107">The traditional way to use a test server is to copy all of the data from your production server to your test server, tune the test server, and then implement the recommendation on your production server.</span></span> <span data-ttu-id="f6736-108">Dadurch wird zwar die Leistungsbeeinträchtigung auf dem Produktionsserver beseitigt, aber dies entspricht nicht der optimalen Lösung.</span><span class="sxs-lookup"><span data-stu-id="f6736-108">This process eliminates the performance impact on your production server, but nevertheless is not the optimal solution.</span></span> <span data-ttu-id="f6736-109">Beispielsweise kann das Kopieren großer Datenbankmengen vom Produktionsserver auf den Testserver viel Zeit und viele Ressourcen beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="f6736-109">For example, copying large amounts of data from the production to the test server can consume substantial amounts of time and resources.</span></span> <span data-ttu-id="f6736-110">Darüber hinaus ist die Testserverhardware selten so leistungsfähig wie die Hardware, die für Produktionsserver bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f6736-110">In addition, test server hardware is seldom as powerful as the hardware that is deployed for production servers.</span></span> <span data-ttu-id="f6736-111">Der Optimierungsprozess basiert auf dem Abfrageoptimierer, und die von diesem generierten Empfehlungen hängen teilweise von der zugrunde liegenden Hardware ab.</span><span class="sxs-lookup"><span data-stu-id="f6736-111">The tuning process relies on the query optimizer, and the recommendations it generates are based in part on the underlying hardware.</span></span> <span data-ttu-id="f6736-112">Falls die Test- und die Produktionsserverhardware nicht identisch sind, wird dadurch die Qualität der Empfehlungen des [!INCLUDE[ssDE](../../../includes/ssde-md.md)] -Optimierungsratgebers reduziert.</span><span class="sxs-lookup"><span data-stu-id="f6736-112">If the test and production server hardware are not identical, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor recommendation quality is diminished.</span></span>

 <span data-ttu-id="f6736-113">Um diese Probleme zu vermeiden, optimiert der [!INCLUDE[ssDE](../../../includes/ssde-md.md)] -Optimierungsratgeber eine Datenbank auf einem Produktionsserver durch Auslagern des größten Teils der Optimierungslast auf einen Testserver.</span><span class="sxs-lookup"><span data-stu-id="f6736-113">To avoid these problems, [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor tunes a database on a production server by offloading most of the tuning load onto a test server.</span></span> <span data-ttu-id="f6736-114">Dies geschieht durch Verwenden der Hardwarekonfigurationsinformationen des Produktionsservers und ohne die Daten tatsächlich vom Produktionsserver auf den Testserver zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="f6736-114">It does this by using the production server hardware configuration information and without actually copying the data from the production server to the test server.</span></span> [!INCLUDE[ssDE](../../../includes/ssde-md.md)] <span data-ttu-id="f6736-115">-Optimierungsratgeber kopiert keine tatsächlichen Daten vom Produktionsserver auf den Testserver.</span><span class="sxs-lookup"><span data-stu-id="f6736-115">Tuning Advisor does not copy actual data from the production server to the test server.</span></span> <span data-ttu-id="f6736-116">Er kopiert nur die Metadaten und notwendigen Statistiken.</span><span class="sxs-lookup"><span data-stu-id="f6736-116">It only copies the metadata and necessary statistics.</span></span>

 <span data-ttu-id="f6736-117">Die folgenden Schritte beschreiben den Prozess zum Optimieren einer Produktionsdatenbank auf einem Testserver:</span><span class="sxs-lookup"><span data-stu-id="f6736-117">The following steps outline the process for tuning a production database on a test server:</span></span>

1.  <span data-ttu-id="f6736-118">Stellen Sie sicher, dass der Benutzer, der den Testserver verwenden möchte, auf beiden Servern vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f6736-118">Make sure that the user who wants to use the test server exists on both servers.</span></span>

     <span data-ttu-id="f6736-119">Bevor Sie beginnen, sollten Sie sicherstellen, dass der Benutzer, der den Testserver zum Optimieren einer Datenbank auf dem Produktionsserver verwenden möchte, auf beiden Servern vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f6736-119">Before you start, make sure that the user who wants to use the test server to tune a database on the production server exists on both servers.</span></span> <span data-ttu-id="f6736-120">Dazu müssen Sie den Benutzer und den zugehörigen Anmeldenamen auf dem Testserver erstellen.</span><span class="sxs-lookup"><span data-stu-id="f6736-120">This requires that you create the user and his or her login on the test server.</span></span> <span data-ttu-id="f6736-121">Falls Sie ein Mitglied der festen Serverrolle **sysadmin** auf beiden Computern sind, ist dieser Schritt nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f6736-121">If you are a member of the **sysadmin** fixed server role on both computers, this step is not necessary.</span></span>

2.  <span data-ttu-id="f6736-122">Optimieren Sie die Arbeitsauslastung auf dem Testserver.</span><span class="sxs-lookup"><span data-stu-id="f6736-122">Tune the workload on the test server.</span></span>

     <span data-ttu-id="f6736-123">Zum Optimieren einer Arbeitsauslastung auf einem Testserver müssen Sie eine XML-Eingabedatei zusammen mit dem Befehlszeilen-Hilfsprogramm **dta** verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6736-123">To tune a workload on a test server, you must use an XML input file with the **dta** command-line utility.</span></span> <span data-ttu-id="f6736-124">Geben Sie in der XML-Eingabedatei den Namen des Testservers mit dem untergeordneten Element **TestServer** sowie die Werte für die anderen untergeordneten Elemente im übergeordneten Element **TuningOptions** an.</span><span class="sxs-lookup"><span data-stu-id="f6736-124">In the XML input file, specify the name of your test server with the **TestServer** subelement in addition to specifying the values for the other subelements under the **TuningOptions** parent element.</span></span>

     <span data-ttu-id="f6736-125">Während des Optimierungsprozesses erstellt der Datenbankoptimierungsratgeber eine Shelldatenbank auf dem Testserver.</span><span class="sxs-lookup"><span data-stu-id="f6736-125">During the tuning process, Database Engine Tuning Advisor creates a shell database on the test server.</span></span> <span data-ttu-id="f6736-126">Um diese Shelldatenbank zu erstellen und zu optimieren, führt der Datenbankoptimierungsratgeber folgende Aufrufe beim Produktionsserver aus:</span><span class="sxs-lookup"><span data-stu-id="f6736-126">To create this shell database and tune it, Database Engine Tuning Advisor makes calls to the production server for the following:</span></span>

    1.  [!INCLUDE[ssDE](../../../includes/ssde-md.md)] <span data-ttu-id="f6736-127">-Optimierungsratgeber importiert Metadaten aus der Produktionsdatenbank in die Testserver-Shelldatenbank.</span><span class="sxs-lookup"><span data-stu-id="f6736-127">Tuning Advisor imports metadata from the production database to the test server shell database.</span></span> <span data-ttu-id="f6736-128">Zu diesen Metadaten zählen leere Tabellen, Indizes, Sichten, gespeicherte Prozeduren, Trigger usw.</span><span class="sxs-lookup"><span data-stu-id="f6736-128">This metadata includes empty tables, indexes, views, stored procedures, triggers, and so on.</span></span> <span data-ttu-id="f6736-129">Auf diese Weise können die Arbeitsauslastungsabfragen für die Testserver-Shelldatenbank ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f6736-129">This makes it possible for the workload queries to execute against the test server shell database.</span></span>

    2.  [!INCLUDE[ssDE](../../../includes/ssde-md.md)] <span data-ttu-id="f6736-130">-Optimierungsratgeber importiert Statistiken vom Produktionsserver, damit der Abfrageoptimierer Abfragen auf dem Testserver präzise optimieren kann.</span><span class="sxs-lookup"><span data-stu-id="f6736-130">Tuning Advisor imports statistics from the production server so the query optimizer can accurately optimize queries on the test server.</span></span>

    3.  [!INCLUDE[ssDE](../../../includes/ssde-md.md)] <span data-ttu-id="f6736-131">-Optimierungsratgeber importiert Hardwareparameter, die die Anzahl von Prozessoren und den verfügbaren Arbeitsspeicher angeben, vom Produktionsserver, um dem Abfrageoptimierer die erforderlichen Informationen zum Generieren eines Abfrageplans bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f6736-131">Tuning Advisor imports hardware parameters specifying the number of processors and available memory from the production server to provide the query optimizer with the information it needs to generate a query plan.</span></span>

3.  <span data-ttu-id="f6736-132">Nachdem der [!INCLUDE[ssDE](../../../includes/ssde-md.md)] -Optimierungsratgeber die Testserver-Shelldatenbank optimiert hat, wird eine Optimierungsempfehlung generiert.</span><span class="sxs-lookup"><span data-stu-id="f6736-132">After [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor finishes tuning the test server shell database, it generates a tuning recommendation.</span></span>

4.  <span data-ttu-id="f6736-133">Wenden Sie die beim Optimieren des Testservers erhaltene Empfehlung auf den Produktionsserver an.</span><span class="sxs-lookup"><span data-stu-id="f6736-133">Apply the recommendation received from tuning the test server to the production server.</span></span>

 <span data-ttu-id="f6736-134">Die folgende Abbildung veranschaulicht das Szenario mit dem Testserver und dem Produktionsserver:</span><span class="sxs-lookup"><span data-stu-id="f6736-134">The following illustration shows the test server and production server scenario:</span></span>

 <span data-ttu-id="f6736-135">![Datenbankoptimierungsratgeber: Testserververwendung](../../database-engine/media/testsvr.gif "Datenbankoptimierungsratgeber: Testserververwendung")</span><span class="sxs-lookup"><span data-stu-id="f6736-135">![Database Engine Tuning Advisor test server usage](../../database-engine/media/testsvr.gif "Database Engine Tuning Advisor test server usage")</span></span>

> [!NOTE]
>  <span data-ttu-id="f6736-136">Die Funktion der Optimierung mit einem Testserver wird auf der grafischen Benutzeroberfläche (Graphical User Interface, GUI) des [!INCLUDE[ssDE](../../../includes/ssde-md.md)] -Optimierungsratgebers nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f6736-136">The test server tuning feature is not supported in the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor graphical user interface (GUI).</span></span>

## <a name="example"></a><span data-ttu-id="f6736-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f6736-137">Example</span></span>
 <span data-ttu-id="f6736-138">Stellen Sie zunächst sicher, dass der Benutzer, der die Optimierung ausführen möchte, auf dem Testserver und dem Produktionsserver vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f6736-138">First, make sure that the user who wants to perform the tuning exists on both the test and production servers.</span></span>

 <span data-ttu-id="f6736-139">Nachdem die Benutzerinformationen auf den Testserver kopiert wurden, können Sie Ihre Testserver-Optimierungssitzung in der XML-Eingabedatei des [!INCLUDE[ssDE](../../../includes/ssde-md.md)] -Optimierungsratgebers definieren.</span><span class="sxs-lookup"><span data-stu-id="f6736-139">After the user information is copied over to your test server, you can define your test server tuning session in the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor XML input file.</span></span> <span data-ttu-id="f6736-140">Die folgende XML-Beispieleingabedatei veranschaulicht, wie Sie einen Testserver zum Optimieren einer Datenbank mit dem [!INCLUDE[ssDE](../../../includes/ssde-md.md)] -Optimierungsratgeber angeben.</span><span class="sxs-lookup"><span data-stu-id="f6736-140">The following example XML input file illustrates how to specify a test server to tune a database with [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor.</span></span>

 <span data-ttu-id="f6736-141">In diesem Beispiel wird die `MyDatabaseName` -Datenbank auf `MyServerName`optimiert.</span><span class="sxs-lookup"><span data-stu-id="f6736-141">In this example, the `MyDatabaseName` database is being tuned on `MyServerName`.</span></span> <span data-ttu-id="f6736-142">Das [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skript `MyWorkloadScript.sql`wird als Arbeitsauslastung verwendet.</span><span class="sxs-lookup"><span data-stu-id="f6736-142">The [!INCLUDE[tsql](../../includes/tsql-md.md)] script, `MyWorkloadScript.sql`, is used as the workload.</span></span> <span data-ttu-id="f6736-143">Diese Arbeitsauslastung enthält Ereignisse, die für `MyDatabaseName`ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f6736-143">This workload contains events that execute against `MyDatabaseName`.</span></span> <span data-ttu-id="f6736-144">Die meisten Aufrufe des Abfrageoptimierers bei dieser Datenbank im Rahmen des Optimierungsprozesses werden von der Shelldatenbank ausgeführt, die auf `MyTestServerName`gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="f6736-144">Most of the query optimizer calls to this database, which occur as part of the tuning process, are handled by the shell database that resides on `MyTestServerName`.</span></span> <span data-ttu-id="f6736-145">Die Shelldatenbank setzt sich aus Metadaten und Statistiken zusammen.</span><span class="sxs-lookup"><span data-stu-id="f6736-145">The shell database is composed of metadata and statistics.</span></span> <span data-ttu-id="f6736-146">Dieser Prozess führt dazu, dass der Optimierungsaufwand auf den Testserver ausgelagert wird.</span><span class="sxs-lookup"><span data-stu-id="f6736-146">This process results in the tuning overhead being offloaded to the test server.</span></span> <span data-ttu-id="f6736-147">Wenn der [!INCLUDE[ssDE](../../../includes/ssde-md.md)] -Optimierungsratgeber die Optimierungsempfehlung mithilfe dieser XML-Eingabedatei generiert, sollten nur Indizes berücksichtigt werden (`<FeatureSet>IDX</FeatureSet>`), keine Partitionierung. Die vorhandenen physischen Entwurfsstrukturen in `MyDatabaseName`müssen nicht beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="f6736-147">When [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor generates its tuning recommendation using this XML input file, it should consider indexes only (`<FeatureSet>IDX</FeatureSet>`), no partitioning, and need not keep any of the existing physical design structures in `MyDatabaseName`.</span></span>

```
<?xml version="1.0" encoding="utf-16" ?>
<DTAXML xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="https://schemas.microsoft.com/sqlserver/2004/07/dta">
  <DTAInput>
    <Server>
      <Name>MyServerName</Name>
      <Database>
        <Name>MyDatabaseName</Name>
      </Database>
    </Server>
    <Workload>
      <File>MyWorkloadScript.sql</File>
    </Workload>
    <TuningOptions>
      <TestServer>MyTestServerName</TestServer>
      <FeatureSet>IDX</FeatureSet>
      <Partitioning>NONE</Partitioning>
      <KeepExisting>NONE</KeepExisting>
    </TuningOptions>
  </DTAInput>
</DTAXML>
```

## <a name="see-also"></a><span data-ttu-id="f6736-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f6736-148">See Also</span></span>
 <span data-ttu-id="f6736-149">[Überlegungen zur Verwendung von Test Servern](considerations-for-using-test-servers.md) [XML-Eingabedatei Referenz &#40;Datenbankoptimierungsratgeber&#41;](database-engine-tuning-advisor.md)</span><span class="sxs-lookup"><span data-stu-id="f6736-149">[Considerations for Using Test Servers](considerations-for-using-test-servers.md) [XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](database-engine-tuning-advisor.md)</span></span>


