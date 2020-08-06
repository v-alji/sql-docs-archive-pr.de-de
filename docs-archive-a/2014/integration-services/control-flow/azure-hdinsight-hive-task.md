---
title: Azure HDInsight Hive-Task | Microsoft-Dokumentation
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afphivetask.f1
- sql11.dts.designer.afphivetask.f1
ms.assetid: e1896c73-128a-4128-9814-3e01f7dfe19b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5905dee4a7a195a16d217b28b59cc10bb74dd9a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621131"
---
# <a name="azure-hdinsight-hive-task"></a><span data-ttu-id="8aac2-102">Azure HDInsight Hive-Task</span><span class="sxs-lookup"><span data-stu-id="8aac2-102">Azure HDInsight Hive Task</span></span>
<span data-ttu-id="8aac2-103">Verwenden Sie den **Azure HDInsight Hive-Task** zum Anwenden eines Hive-Skripts auf einen Azure HDInsight-Cluster.</span><span class="sxs-lookup"><span data-stu-id="8aac2-103">Use the **Azure HDInsight Hive Task** to run Hive script on an Azure HDInsight cluster.</span></span>
     
<span data-ttu-id="8aac2-104">Um einen **Azure HDInsight-Hive-Task**hinzuzufügen, legen Sie ihn mittels Drag &amp; Drop auf dem SSIS-Designer ab, und doppelklicken Sie darauf, oder klicken Sie mit der rechten Maustaste, und klicken Sie dann auf **Bearbeiten** , um das folgende Dialogfeld **Azure HDInsight-Hive-Task-Editor** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8aac2-104">To add an **Azure HDInsight Hive Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure HDInsight Hive Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="8aac2-105">Die folgende Liste beschreibt Felder in diesem Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="8aac2-105">The following list describes fields in this dialog box.</span></span>  
  
1.  <span data-ttu-id="8aac2-106">Wählen Sie für das Feld **HDInsightConnection** einen vorhandenen HDInsight-Verbindungs-Manager aus, oder erstellen Sie einen neuen, der auf einen Azure HDInsight-Cluster verweist, in dem das Skript ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8aac2-106">For the **HDInsightConnection** field, select an existing Azure HDInsight Connection Manager or create a new one that refers to the Azure HDInsight cluster used to execute the script.</span></span>
  
2.  <span data-ttu-id="8aac2-107">Wählen Sie für das Feld **AzureStorageConnection** einen vorhandenen Azure Storage-Verbindungs-Manager aus, oder erstellen Sie einen neuen, der auf das Azure Storage-Konto verweist, das mit dem Cluster verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="8aac2-107">For the **AzureStorageConnection** field, select an existing Azure Storage Connection Manager or create a new one that refers to the Azure Storage Account associated with the cluster.</span></span> <span data-ttu-id="8aac2-108">Dies ist nur erforderlich, wenn Sie die Skriptausführungsausgabe- und Fehlerprotokolle herunterladen möchten.</span><span class="sxs-lookup"><span data-stu-id="8aac2-108">This is only necessary if you want to download the script execution output and error logs.</span></span>
 
3.  <span data-ttu-id="8aac2-109">Geben Sie für das Feld **BlobContainer** den Speichercontainernamen an, der mit dem Cluster verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="8aac2-109">For the **BlobContainer** field, specify the storage container name associated with the cluster.</span></span> <span data-ttu-id="8aac2-110">Dies ist nur erforderlich, wenn Sie die Skriptausführungsausgabe- und Fehlerprotokolle herunterladen möchten.</span><span class="sxs-lookup"><span data-stu-id="8aac2-110">This is only necessary if you want to download the script execution output and error logs.</span></span>
  
4.  <span data-ttu-id="8aac2-111">Geben Sie für das Feld **LocalLogFolder** den Ordner an, in den die Skriptausführungsausgabe- und Fehlerprotokolle heruntergeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8aac2-111">For the **LocalLogFolder** field, specify the folder to which the script execution output and error logs will be downloaded to.</span></span> <span data-ttu-id="8aac2-112">Dies ist nur erforderlich, wenn Sie die Skriptausführungsausgabe- und Fehlerprotokolle herunterladen möchten.</span><span class="sxs-lookup"><span data-stu-id="8aac2-112">This is only necessary if you want to download the script execution output and error logs.</span></span>   
  
5.  <span data-ttu-id="8aac2-113">Sie haben zwei Möglichkeiten, das auszuführende Hive-Skript anzugeben:</span><span class="sxs-lookup"><span data-stu-id="8aac2-113">There are two ways to specify the Hive script to execute:</span></span>
  
    1.  <span data-ttu-id="8aac2-114">**Inlineskript**: Legen Sie das Feld **Skript** fest, indem Sie im Dialogfeld **Skript eingeben** inline das auszuführende Skript eingeben.</span><span class="sxs-lookup"><span data-stu-id="8aac2-114">**In-line script**: Specify the **Script** field by typing in-line the script to execute in the **Enter Script** dialog box.</span></span>
  
    2.  <span data-ttu-id="8aac2-115">**Skriptdatei**: Laden Sie die Skriptdatei in Azure Blob Storage hoch, und legen Sie das Feld **BlobName** fest.</span><span class="sxs-lookup"><span data-stu-id="8aac2-115">**Script file**: Upload the script file to Azure Blob Storage and specify the **BlobName** field.</span></span> <span data-ttu-id="8aac2-116">Befindet sich das Blob nicht im Standardspeicherkonto oder -container des HDInsight-Clusters, müssen die Felder **ExternalStorageAccountName** und **ExternalBlobContainer** festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="8aac2-116">If the blob is not in the default storage account or container associated with the HDInsight cluster, the **ExternalStorageAccountName** and **ExternalBlobContainer** fields must be specified.</span></span> <span data-ttu-id="8aac2-117">Stellen Sie bei einem externen Blob sicher, dass es als öffentlich zugänglich konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="8aac2-117">For an external blob, make sure that it is configured as publicly accessible.</span></span>  
  
     <span data-ttu-id="8aac2-118">Wenn Skriptdatei und Inlineskript angegeben sind, wird die Skriptdatei verwendet und das Inlineskript ignoriert.</span><span class="sxs-lookup"><span data-stu-id="8aac2-118">If both are specified, script file will be used and the in-line script will be ignored.</span></span>
