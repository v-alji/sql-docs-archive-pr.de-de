---
title: Azure HDInsight Create Cluster-Task | Microsoft-Dokumentation
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpcreatecltask.f1
- sql11.dts.designer.afpcreatecltask.f1
ms.assetid: a8ec413a-38d3-45df-887e-6f5f4d9f8465
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e4029e3a01cbcfe04be5f2879a9b60866bfc867a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697070"
---
# <a name="azure-hdinsight-create-cluster-task"></a><span data-ttu-id="47d31-102">Azure HDInsight Create Cluster-Task</span><span class="sxs-lookup"><span data-stu-id="47d31-102">Azure HDInsight Create Cluster Task</span></span>
<span data-ttu-id="47d31-103">Der **Azure HDInsight Create Cluster-Task** ermöglicht einem SSIS-Paket das Erstellen eines Azure HDInsight-Clusters im angegebenen Azure-Abonnement und in der Ressourcengruppe.</span><span class="sxs-lookup"><span data-stu-id="47d31-103">The **Azure HDInsight Create Cluster Task** enables an SSIS package to create an Azure HDInsight cluster in the specified Azure subscription and resource group.</span></span>
  
> [!NOTE]  
> - <span data-ttu-id="47d31-104">Das Erstellen eines neuen HDInsight-Clusters kann 10-20 Minuten in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="47d31-104">Creating a new HDInsight cluster may take 10~20 minutes.</span></span>  
> - <span data-ttu-id="47d31-105">Beim Erstellen und Ausführen eines Azure HDInsight-Clusters fallen Kosten an.</span><span class="sxs-lookup"><span data-stu-id="47d31-105">There is a cost associated with creating and running an Azure HDInsight cluster.</span></span> <span data-ttu-id="47d31-106">Details finden Sie auf der Webseite mit den [Preisinformationen für HDInsight](https://azure.microsoft.com/pricing/details/hdinsight/).</span><span class="sxs-lookup"><span data-stu-id="47d31-106">See [HDInsight Pricing](https://azure.microsoft.com/pricing/details/hdinsight/) for details.</span></span>  
  
<span data-ttu-id="47d31-107">Um einen **Azure HDInsight Create Cluster-Task**hinzuzufügen, legen Sie ihn mittels Drag &amp; Drop auf dem SSIS-Designer ab, und doppelklicken Sie darauf, oder klicken Sie mit der rechten Maustaste darauf. Klicken Sie dann auf **Bearbeiten** , um das folgende Dialogfeld **Azure HDInsight Create Cluster-Task-Editor** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="47d31-107">To add an **Azure HDInsight Create Cluster Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure HDInsight Create Cluster Task Editor** dialog box.</span></span>  
  
<span data-ttu-id="47d31-108">Die folgende Tabelle enthält eine Beschreibung für die Felder in diesem Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="47d31-108">The following table provides a description of the fields in this dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="47d31-109">**Feld**</span><span class="sxs-lookup"><span data-stu-id="47d31-109">**Field**</span></span>|<span data-ttu-id="47d31-110">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="47d31-110">**Description**</span></span>|  
|<span data-ttu-id="47d31-111">AzureResourceManagerConnection</span><span class="sxs-lookup"><span data-stu-id="47d31-111">AzureResourceManagerConnection</span></span>|<span data-ttu-id="47d31-112">Wählen Sie einen vorhandenen Azure Resource Manager-Verbindungs-Manager aus, oder erstellen Sie einen neuen, mit dem der HDInsight-Cluster erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="47d31-112">Select an existing Azure Resource Manager Connection Manager or create a new one that will be used to create the HDInsight cluster.</span></span>|  
|<span data-ttu-id="47d31-113">AzureStorageConnection</span><span class="sxs-lookup"><span data-stu-id="47d31-113">AzureStorageConnection</span></span>|<span data-ttu-id="47d31-114">Wählen Sie einen vorhandenen Azure Storage-Verbindungs-Manager aus, oder erstellen Sie einen neuen, der auf ein Azure Storage-Konto verweist, um ihn mit dem HDInsight-Cluster zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="47d31-114">Select an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account that will be associated with the HDInsight cluster.</span></span>|
|<span data-ttu-id="47d31-115">SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="47d31-115">SubscriptionId</span></span>|<span data-ttu-id="47d31-116">Geben Sie die ID des Abonnements an, in dem der HDInsight-Cluster erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="47d31-116">Specify the ID of the subscription the HDInsight cluster will be created in.</span></span>|
|<span data-ttu-id="47d31-117">ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="47d31-117">ResourceGroup</span></span>|<span data-ttu-id="47d31-118">Geben Sie die Azure-Ressourcengruppe an, wo der HDInsight-Cluster erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="47d31-118">Specify the Azure resource group the HDInsight cluster will be created in.</span></span>|
|<span data-ttu-id="47d31-119">Standort</span><span class="sxs-lookup"><span data-stu-id="47d31-119">Location</span></span>|<span data-ttu-id="47d31-120">Geben Sie den Speicherort des HDInsight-Clusters an.</span><span class="sxs-lookup"><span data-stu-id="47d31-120">Specify the location of the HDInsight cluster.</span></span> <span data-ttu-id="47d31-121">Der Cluster muss am selben Speicherort erstellt werden, wo sich das Azure-Speicherkonto befindet.</span><span class="sxs-lookup"><span data-stu-id="47d31-121">The cluster must be created in the same location as the Azure Storage Account specified.</span></span>|  
|<span data-ttu-id="47d31-122">ClusterName</span><span class="sxs-lookup"><span data-stu-id="47d31-122">ClusterName</span></span>|<span data-ttu-id="47d31-123">Geben Sie einen Namen für den zu erstellenden HDInsight-Cluster an.</span><span class="sxs-lookup"><span data-stu-id="47d31-123">Specify a name for the HDInsight cluster to be created.</span></span>|  
|<span data-ttu-id="47d31-124">clusterSize</span><span class="sxs-lookup"><span data-stu-id="47d31-124">ClusterSize</span></span>|<span data-ttu-id="47d31-125">Geben Sie die Anzahl der Knoten an, die im Cluster erstellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="47d31-125">Specify the number of nodes to create in the cluster.</span></span>|  
|<span data-ttu-id="47d31-126">BlobContainer</span><span class="sxs-lookup"><span data-stu-id="47d31-126">BlobContainer</span></span>|<span data-ttu-id="47d31-127">Geben Sie den Namen des standardmäßigen Speichercontainers an, der mit dem HDInsight-Cluster verbunden sein soll.</span><span class="sxs-lookup"><span data-stu-id="47d31-127">Specify the name of the default storage container to be associated with the HDInsight cluster.</span></span>|  
|<span data-ttu-id="47d31-128">UserName</span><span class="sxs-lookup"><span data-stu-id="47d31-128">UserName</span></span>|<span data-ttu-id="47d31-129">Geben Sie den Benutzernamen zum Herstellen einer Verbindung mit dem HDInsight-Cluster an.</span><span class="sxs-lookup"><span data-stu-id="47d31-129">Specify the user name to be used for connecting to the HDInsight cluster.</span></span>|  
|<span data-ttu-id="47d31-130">Kennwort</span><span class="sxs-lookup"><span data-stu-id="47d31-130">Password</span></span>|<span data-ttu-id="47d31-131">Geben Sie das Kennwort zum Herstellen einer Verbindung mit dem HDInsight-Cluster an.</span><span class="sxs-lookup"><span data-stu-id="47d31-131">Specify the password to be used for connecting to the HDInsight cluster.</span></span>|
|<span data-ttu-id="47d31-132">SshUserName</span><span class="sxs-lookup"><span data-stu-id="47d31-132">SshUserName</span></span>|<span data-ttu-id="47d31-133">Geben Sie den Benutzernamen für den Remotezugriff auf den HDInsight-Cluster mithilfe von SSH an.</span><span class="sxs-lookup"><span data-stu-id="47d31-133">Specify the user name used to remotely access the HDInsight cluster using SSH.</span></span>|
|<span data-ttu-id="47d31-134">SshPassword</span><span class="sxs-lookup"><span data-stu-id="47d31-134">SshPassword</span></span>|<span data-ttu-id="47d31-135">Geben Sie das Kennwort für den Remotezugriff auf den HDInsight-Cluster mithilfe von SSH an.</span><span class="sxs-lookup"><span data-stu-id="47d31-135">Specify the password used to remotely access the HDInsight cluster using SSH.</span></span>|
|<span data-ttu-id="47d31-136">FailIfExists</span><span class="sxs-lookup"><span data-stu-id="47d31-136">FailIfExists</span></span>|<span data-ttu-id="47d31-137">Geben Sie an, ob der Task einen Fehler ausgeben soll, wenn der Cluster bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="47d31-137">Specify whether the task should fail if the cluster already exists.</span></span>|  
  
> [!NOTE]  
> <span data-ttu-id="47d31-138">Die Speicherorte von HDInsight-Cluster und Azure-Speicherkonto müssen identisch sein.</span><span class="sxs-lookup"><span data-stu-id="47d31-138">The locations of the HDInsight cluster and the Azure Storage Account must be the same.</span></span>
