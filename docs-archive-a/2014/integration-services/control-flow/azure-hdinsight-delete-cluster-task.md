---
title: Azure HDInsight-Delete Cluster-Task | Microsoft-Dokumentation
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpdelcltask.f1
- sql11.dts.designer.afpdelcltask.f1
ms.assetid: e298776e-d18a-4393-a8e6-65ee3d555749
author: chugugrace
ms.author: chugu
ms.openlocfilehash: db0a15aaea37c6d18c1d3c2136e0fd0c94eb7506
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621133"
---
# <a name="azure-hdinsight-delete-cluster-task"></a><span data-ttu-id="ae0c7-102">Azure HDInsight-Delete Cluster-Task</span><span class="sxs-lookup"><span data-stu-id="ae0c7-102">Azure HDInsight Delete Cluster Task</span></span>
<span data-ttu-id="ae0c7-103">Der **Azure HDInsight-Delete Cluster-Task** ermöglicht einem SSIS-Paket das Löschen eines Azure HDInsight-Clusters im angegebenen Azure-Abonnement und der Ressourcengruppe.</span><span class="sxs-lookup"><span data-stu-id="ae0c7-103">The **Azure HDInsight Delete Cluster Task** enables an SSIS package to delete an Azure HDInsight cluster in the specified Azure subscription and resource group.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ae0c7-104">Das Löschen eines HDInsight-Clusters kann 10-20 Minuten in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="ae0c7-104">Deleting an HDInsight cluster may take 10~20 minutes.</span></span>  
  
<span data-ttu-id="ae0c7-105">Um einen **Azure HDInsight-Delete Cluster-Task**hinzuzufügen, legen Sie ihn mittels Drag &amp; Drop auf dem SSIS-Designer ab, und doppelklicken Sie darauf, oder klicken Sie mit der rechten Maustaste, und klicken Sie dann auf **Bearbeiten** , um das folgende Dialogfeld A **zure HDInsight-Delete Cluster-Task-Editor** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ae0c7-105">To add an **Azure HDInsight Delete Cluster Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure HDInsight Delete Cluster Task Editor** dialog box.</span></span>  
  
<span data-ttu-id="ae0c7-106">Die folgende Tabelle enthält Beschreibungen für die Felder in diesem Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="ae0c7-106">The following table provides a description for the fields in the dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ae0c7-107">**Feld**</span><span class="sxs-lookup"><span data-stu-id="ae0c7-107">**Field**</span></span>|<span data-ttu-id="ae0c7-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ae0c7-108">**Description**</span></span>|  
|<span data-ttu-id="ae0c7-109">AzureResourceManagerConnection</span><span class="sxs-lookup"><span data-stu-id="ae0c7-109">AzureResourceManagerConnection</span></span>|<span data-ttu-id="ae0c7-110">Wählen Sie einen vorhandenen Azure Resource Manager-Verbindungs-Manager aus, oder erstellen Sie einen neuen, mit dem der HDInsight-Cluster gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="ae0c7-110">Select an existing Azure Resource Manager Connection Manager or create a new one that will be used to delete the HDInsight cluster.</span></span>|
|<span data-ttu-id="ae0c7-111">SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="ae0c7-111">SubscriptionId</span></span>|<span data-ttu-id="ae0c7-112">Geben Sie die ID des Abonnements an, in dem sich der HDInsight-Cluster befindet.</span><span class="sxs-lookup"><span data-stu-id="ae0c7-112">Specify the ID of the subscription the HDInsight cluster is in.</span></span>|
|<span data-ttu-id="ae0c7-113">ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="ae0c7-113">ResourceGroup</span></span>|<span data-ttu-id="ae0c7-114">Geben Sie die Azure-Ressourcengruppe an, in der sich der HDInsight-Cluster befindet.</span><span class="sxs-lookup"><span data-stu-id="ae0c7-114">Specify the Azure resource group the HDInsight cluster is in.</span></span>|
|<span data-ttu-id="ae0c7-115">ClusterName</span><span class="sxs-lookup"><span data-stu-id="ae0c7-115">ClusterName</span></span>|<span data-ttu-id="ae0c7-116">Geben Sie den Namen des zu löschenden Clusters an.</span><span class="sxs-lookup"><span data-stu-id="ae0c7-116">Specify the name of the cluster to be deleted.</span></span>|  
|<span data-ttu-id="ae0c7-117">FailIfNotExists</span><span class="sxs-lookup"><span data-stu-id="ae0c7-117">FailIfNotExists</span></span>|<span data-ttu-id="ae0c7-118">Geben Sie an, ob der Task einen Fehler ausgeben soll, wenn der Cluster nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ae0c7-118">Specify whether the task should fail if the cluster does not exist.</span></span>|
