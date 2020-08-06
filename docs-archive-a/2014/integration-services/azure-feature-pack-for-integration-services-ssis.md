---
title: Azure Feature Pack | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL11.SSIS.AZURE.F1
- SQL12.SSIS.AZURE.F1
ms.assetid: 31de555f-ae62-4f2f-a6a6-77fea1fa8189
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8bca2b4d3ce91f6010fbe01da836efd8a67ca6bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696014"
---
# <a name="azure-feature-pack"></a><span data-ttu-id="55e94-102">Azure Feature Pack</span><span class="sxs-lookup"><span data-stu-id="55e94-102">Azure Feature Pack</span></span>
<span data-ttu-id="55e94-103">Das SQL Server Integration Services-Feature Pack (SSIS) für Azure ist eine Erweiterung, die die auf dieser Seite für SSIS aufgelisteten Komponenten für Verbindungen mit Azure-Diensten, für die Übertragung von Daten zwischen Azure und lokalen Datenquellen und für die Verarbeitung der in Azure gespeicherten Daten bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="55e94-103">SQL Server Integration Services (SSIS) Feature Pack for Azure is an extension that provides the components listed on this page for SSIS to connect to Azure services, transfer data between Azure and on-premises data sources, and process data stored in Azure.</span></span>

## <a name="components-in-the-feature-pack"></a><span data-ttu-id="55e94-104">Komponenten im Feature Pack</span><span class="sxs-lookup"><span data-stu-id="55e94-104">Components in the Feature Pack</span></span>
  
-   <span data-ttu-id="55e94-105">Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="55e94-105">Connection Managers</span></span>  
  
    -   [<span data-ttu-id="55e94-106">Azure Storage-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="55e94-106">Azure Storage Connection Manager</span></span>](connection-manager/azure-storage-connection-manager.md)  
  
    -   [<span data-ttu-id="55e94-107">Verbindungs-Manager für Azure-Abonnements</span><span class="sxs-lookup"><span data-stu-id="55e94-107">Azure Subscription Connection Manager</span></span>](connection-manager/azure-subscription-connection-manager.md)  
    
    -   [<span data-ttu-id="55e94-108">Azure Data Lake Store Connection Manager (Azure Data Lake Store-Verbindungs-Manager)</span><span class="sxs-lookup"><span data-stu-id="55e94-108">Azure Data Lake Store Connection Manager</span></span>](../../2014/integration-services/azure-data-lake-store-connection-manager.md)
    
    -   [<span data-ttu-id="55e94-109">Azure Resource Manager-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="55e94-109">Azure Resource Manager Connection Manager</span></span>](../../2014/integration-services/azure-resource-manager-connection-manager.md)
    
    -   [<span data-ttu-id="55e94-110">Azure HDInsight-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="55e94-110">Azure HDInsight Connection Manager</span></span>](../../2014/integration-services/azure-hdinsight-connection-manager.md)
  
-   <span data-ttu-id="55e94-111">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="55e94-111">Tasks</span></span>  
  
    -   [<span data-ttu-id="55e94-112">Azure-Blob-Uploadtask</span><span class="sxs-lookup"><span data-stu-id="55e94-112">Azure Blob Upload Task</span></span>](control-flow/azure-blob-upload-task.md)  
  
    -   [<span data-ttu-id="55e94-113">Azure Blob-Download-Task</span><span class="sxs-lookup"><span data-stu-id="55e94-113">Azure Blob Download Task</span></span>](control-flow/azure-blob-download-task.md)  
  
    -   [<span data-ttu-id="55e94-114">Hive-Aufgabe in Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="55e94-114">Azure HDInsight Hive Task</span></span>](control-flow/azure-hdinsight-hive-task.md)  
  
    -   <span data-ttu-id="55e94-115">[Azure HDInsight Pig-Task](https://msdn.microsoft.com/library/mt146781(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="55e94-115">[Azure HDInsight Pig Task](https://msdn.microsoft.com/library/mt146781(v=sql.120).aspx)</span></span>
  
    -   [<span data-ttu-id="55e94-116">Azure HDInsight Create Cluster-Task</span><span class="sxs-lookup"><span data-stu-id="55e94-116">Azure HDInsight Create Cluster Task</span></span>](control-flow/azure-hdinsight-create-cluster-task.md)  
  
    -   [<span data-ttu-id="55e94-117">Azure HDInsight-Delete Cluster-Task</span><span class="sxs-lookup"><span data-stu-id="55e94-117">Azure HDInsight Delete Cluster Task</span></span>](control-flow/azure-hdinsight-delete-cluster-task.md)
    
    -   [<span data-ttu-id="55e94-118">Azure SQL DW-Uploadtask</span><span class="sxs-lookup"><span data-stu-id="55e94-118">Azure SQL DW Upload Task</span></span>](../../2014/integration-services/azure-sql-dw-upload-task.md)    
    
    -   [<span data-ttu-id="55e94-119">Azure Data Lake Store-Dateisystemtask</span><span class="sxs-lookup"><span data-stu-id="55e94-119">Azure Data Lake Store File System Task</span></span>](control-flow/file-system-task.md)    
  
-   <span data-ttu-id="55e94-120">Datenflusskomponenten</span><span class="sxs-lookup"><span data-stu-id="55e94-120">Data Flow Components</span></span>  
  
    -   <span data-ttu-id="55e94-121">[Azure-Blob-Quelle](https://msdn.microsoft.com/library/mt146775(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="55e94-121">[Azure Blob Source](https://msdn.microsoft.com/library/mt146775(v=sql.120).aspx)</span></span>  
  
    -   [<span data-ttu-id="55e94-122">Azure-BLOB-Ziel</span><span class="sxs-lookup"><span data-stu-id="55e94-122">Azure Blob Destination</span></span>](data-flow/azure-blob-destination.md)  
    
    -   [<span data-ttu-id="55e94-123">Azure Data Lake Store Source</span><span class="sxs-lookup"><span data-stu-id="55e94-123">Azure Data Lake Store Source</span></span>](../../2014/integration-services/azure-data-lake-store-source.md)
    
    -   [<span data-ttu-id="55e94-124">Azure Data Lake Store Destination</span><span class="sxs-lookup"><span data-stu-id="55e94-124">Azure Data Lake Store Destination</span></span>](../../2014/integration-services/azure-data-lake-store-destination.md)
  
-   <span data-ttu-id="55e94-125">Azure-BLOB-Enumerator & ADLS-Datei-Enumerator.</span><span class="sxs-lookup"><span data-stu-id="55e94-125">Azure Blob Enumerator & ADLS File Enumerator.</span></span> <span data-ttu-id="55e94-126">Siehe [foreach-Schleifen Container](control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="55e94-126">See [Foreach Loop Container](control-flow/foreach-loop-container.md).</span></span>  
  
 
## <a name="download-the-feature-pack"></a><span data-ttu-id="55e94-127">Download des Feature Packs</span><span class="sxs-lookup"><span data-stu-id="55e94-127">Download the Feature Pack</span></span>  
<span data-ttu-id="55e94-128">Sie können das SQL Server Integration Services-Feature Pack (SSIS) für Azure hier herunterladen.</span><span class="sxs-lookup"><span data-stu-id="55e94-128">Download the SQL Server Integration Services (SSIS) Feature Pack for Azure.</span></span>  
  
-   [<span data-ttu-id="55e94-129">Microsoft SQL Server 2014 Integration Services-Feature Pack für Azure</span><span class="sxs-lookup"><span data-stu-id="55e94-129">Microsoft SQL Server 2014 Integration Services Feature Pack for Azure</span></span>](https://www.microsoft.com/download/details.aspx?id=47366)  

## <a name="prerequisites"></a><span data-ttu-id="55e94-130">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="55e94-130">Prerequisites</span></span>  
<span data-ttu-id="55e94-131">Sie müssen die folgenden erforderlichen Komponenten installieren, bevor Sie dieses Feature Pack installieren.</span><span class="sxs-lookup"><span data-stu-id="55e94-131">You must install the following prerequisites before installing this feature pack.</span></span>  
  
-   <span data-ttu-id="55e94-132">SQL Server Integration Services</span><span class="sxs-lookup"><span data-stu-id="55e94-132">SQL Server Integration Services</span></span>  
-   <span data-ttu-id="55e94-133">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="55e94-133">.Net Framework 4.5</span></span>  
  
## <a name="scenarios"></a><span data-ttu-id="55e94-134">Szenarien</span><span class="sxs-lookup"><span data-stu-id="55e94-134">Scenarios</span></span>  
  
### <a name="big-data-processing"></a><span data-ttu-id="55e94-135">Big Data-Verarbeitung</span><span class="sxs-lookup"><span data-stu-id="55e94-135">Big Data Processing</span></span>  
 <span data-ttu-id="55e94-136">Verwenden Sie den Azure Connector zum Ausführen der folgenden Big Data-Verarbeitungsaufgaben:</span><span class="sxs-lookup"><span data-stu-id="55e94-136">Use Azure Connector to complete following big data processing work:</span></span>  
  
1.  <span data-ttu-id="55e94-137">Verwenden Sie den Azure Blob Upload-Task zum Hochladen von Eingabedaten in den Azure BLOB-Speicher.</span><span class="sxs-lookup"><span data-stu-id="55e94-137">Use the Azure Blob Upload Task to upload input data to Azure Blob Storage.</span></span>  
  
2.  <span data-ttu-id="55e94-138">Verwenden Sie den Azure HDInsight Create Cluster-Task zum Erstellen eines Azure HDInsight-Clusters.</span><span class="sxs-lookup"><span data-stu-id="55e94-138">Use the Azure HDInsight Create Cluster Task to create an Azure HDInsight cluster.</span></span> <span data-ttu-id="55e94-139">Dieser Schritt ist optional, wenn Sie einen eigenen Cluster verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="55e94-139">This step is optional if you want to use your own cluster.</span></span>  
  
3.  <span data-ttu-id="55e94-140">Verwenden Sie den Azure HDInsight Hive-Task oder Azure HDInsight Pig-Task zum Aufrufen eines Pig- oder Hive-Auftrags auf dem Azure HDInsight-Cluster.</span><span class="sxs-lookup"><span data-stu-id="55e94-140">Use the Azure HDInsight Hive Task or Azure HDInsight Pig Task to invoke a Pig or Hive job on the Azure HDInsight cluster.</span></span>  
  
4.  <span data-ttu-id="55e94-141">Verwenden Sie den Azure HDInsight Delete Cluster-Task zum Löschen des HDInsight-Clusters nach der Verwendung, wenn Sie in Schritt 2 einen HDInsight-Bedarfscluster erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="55e94-141">Use the Azure HDInsight Delete Cluster Task to delete the HDInsight Cluster after use if you have created an on-demand HDInsight cluster in step #2.</span></span>  
  
5.  <span data-ttu-id="55e94-142">Verwenden Sie den Azure HDInsight Blob Download-Task zum Herunterladen der Pig/Hive-Ausgabedaten vom Azure BLOB-Speicher.</span><span class="sxs-lookup"><span data-stu-id="55e94-142">Use the Azure HDInsight Blob Download Task to download the Pig/Hive output data from the Azure Blob Storage.</span></span>  
  
 <span data-ttu-id="55e94-143">![SSIS-AzureConnector-BigDataScenario](media/ssis-azureconnector-bigdatascenario.png "SSIS-AzureConnector-BigDataScenario")</span><span class="sxs-lookup"><span data-stu-id="55e94-143">![SSIS-AzureConnector-BigDataScenario](media/ssis-azureconnector-bigdatascenario.png "SSIS-AzureConnector-BigDataScenario")</span></span>  
  
### <a name="cloud-data-archiving"></a><span data-ttu-id="55e94-144">Archivieren von Clouddaten</span><span class="sxs-lookup"><span data-stu-id="55e94-144">Cloud Data Archiving</span></span>  
 <span data-ttu-id="55e94-145">Verwenden Sie das Azure BLOB-Ziel in einem SSIS-Paket, um Ausgabedaten in einen Azure BLOB-Speicher zu schreiben, oder verwenden Sie die Azure Blob-Quelle zum Lesen von Daten aus einem Azure BLOB-Speicher.</span><span class="sxs-lookup"><span data-stu-id="55e94-145">Use the Azure Blob Destination in an SSIS package to write output data to an Azure Blob Storage, or use the Azure Blob Source to read data from an Azure Blob Storage.</span></span>  
  
 <span data-ttu-id="55e94-146">![SSIS-AzureConnector-CloudArchive-1](media/ssis-azureconnector-cloudarchive-1.png "SSIS-AzureConnector-CloudArchive-1")</span><span class="sxs-lookup"><span data-stu-id="55e94-146">![SSIS-AzureConnector-CloudArchive-1](media/ssis-azureconnector-cloudarchive-1.png "SSIS-AzureConnector-CloudArchive-1")</span></span>  
  
 <span data-ttu-id="55e94-147">![SSIS-AzureConnector-CloudArchive-2](media/ssis-azureconnector-cloudarchive-2.png "SSIS-AzureConnector-CloudArchive-2")</span><span class="sxs-lookup"><span data-stu-id="55e94-147">![SSIS-AzureConnector-CloudArchive-2](media/ssis-azureconnector-cloudarchive-2.png "SSIS-AzureConnector-CloudArchive-2")</span></span>  
  
 <span data-ttu-id="55e94-148">Und verwenden Sie den Foreach-Schleifencontainer mit dem Azure Blob-Enumerator, um Daten in mehreren BLOB-Dateien zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="55e94-148">And use the Foreach Loop Container with Azure Blob Enumerator to process data in multiple bob files.</span></span>  
  
 <span data-ttu-id="55e94-149">![SSIS-AzureConnector-CloudArchive-3](media/ssis-azureconnector-cloudarchive-3.png "SSIS-AzureConnector-CloudArchive-3")</span><span class="sxs-lookup"><span data-stu-id="55e94-149">![SSIS-AzureConnector-CloudArchive-3](media/ssis-azureconnector-cloudarchive-3.png "SSIS-AzureConnector-CloudArchive-3")</span></span>  
  
  
