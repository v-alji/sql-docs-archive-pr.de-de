---
title: Erstellen eines Data Quality-Projekts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.dqproject.newdqproject.f1
helpviewer_keywords:
- create,data quality project
- data quality project,create
ms.assetid: 19c52d2b-d28e-4449-ab59-5fe0dc326cd9
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3bab14b34123464450bcf0de7540364fc642343e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696066"
---
# <a name="create-a-data-quality-project"></a><span data-ttu-id="817f5-102">Erstellen eines Data Quality-Projekts</span><span class="sxs-lookup"><span data-stu-id="817f5-102">Create a Data Quality Project</span></span>
  <span data-ttu-id="817f5-103">In diesem Thema wird beschrieben, wie mit [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]ein Data Quality-Projekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="817f5-103">This topic describes how to create a data quality project by using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span> <span data-ttu-id="817f5-104">Ein Data Quality-Projekt wird verwendet, um die Bereinigungs- oder Abgleichsaktivität in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) auszuführen.</span><span class="sxs-lookup"><span data-stu-id="817f5-104">A data quality project is used to run the cleansing or matching activity in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="817f5-105">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="817f5-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="817f5-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="817f5-106">Prerequisites</span></span>  
 <span data-ttu-id="817f5-107">Sie müssen über eine relevante Wissensdatenbank verfügen, die im Data Quality-Projekt für die Bereinigungs- oder Abgleichsaktivität verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="817f5-107">You must have a relevant knowledge base to use in the data quality project for the cleansing or matching activity.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="817f5-108">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="817f5-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="817f5-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="817f5-109">Permissions</span></span>  
 <span data-ttu-id="817f5-110">Sie müssen über die dqs_kb_editor- oder dqs_kb_operator-Rolle in der DQS_MAIN-Datenbank verfügen, um ein Data Quality-Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="817f5-110">You must have the dqs_kb_editor or dqs_kb_operator role on the DQS_MAIN database to create a data quality project.</span></span>  
  
##  <a name="create-a-data-quality-project"></a><a name="Create"></a><span data-ttu-id="817f5-111">Erstellen eines Data Quality-Projekts</span><span class="sxs-lookup"><span data-stu-id="817f5-111">Create a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="817f5-112">[Führen Sie die Data Quality-Client Anwendung](../../2014/data-quality-services/run-the-data-quality-client-application.md)aus.</span><span class="sxs-lookup"><span data-stu-id="817f5-112">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="817f5-113">Klicken Sie im [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Startbildschirm auf **Neues Data Quality-Projekt**.</span><span class="sxs-lookup"><span data-stu-id="817f5-113">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **New data quality project**.</span></span>  
  
3.  <span data-ttu-id="817f5-114">Im Bildschirm **Neues Data Quality-Projekt** :</span><span class="sxs-lookup"><span data-stu-id="817f5-114">In the **New Data Quality Project** screen:</span></span>  
  
    1.  <span data-ttu-id="817f5-115">Geben Sie im Feld **Name** einen Namen für das neue Data Quality-Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="817f5-115">In the **Name** box, type a name for the new data quality project.</span></span>  
  
    2.  <span data-ttu-id="817f5-116">(Optional) Geben Sie im Textfeld **Beschreibung** eine Beschreibung für das neue Data Quality-Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="817f5-116">(Optional) In the **Description** box, type a description for the new data quality project.</span></span>  
  
    3.  <span data-ttu-id="817f5-117">Wählen Sie in der Liste **Wissensdatenbank verwenden** eine Wissensdatenbank aus, die für das Data Quality-Projekt verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="817f5-117">In the **Use Knowledge base** list, click to select a knowledge base to be used for the data quality project.</span></span> <span data-ttu-id="817f5-118">Der Bereich **Details zur Wissensdatenbank: <Name der Wissensdatenbank>** auf der rechten Seite zeigt die in der ausgewählten Wissenschaftsdatenbank verfügbaren Domänennamen an.</span><span class="sxs-lookup"><span data-stu-id="817f5-118">The **Knowledge base details: <Knowledge_Base_Name>** area on the right side displays the domain names available in the selected knowledge base.</span></span>  
  
    4.  <span data-ttu-id="817f5-119">Klicken Sie im Bereich **Aktivität auswählen** auf eine Aktivität, die Sie mit diesem Data Quality-Projekt ausführen möchten:</span><span class="sxs-lookup"><span data-stu-id="817f5-119">In the **Select Activity** area, click on an activity that you want to perform using this data quality project:</span></span>  
  
        -   <span data-ttu-id="817f5-120">**Bereinigung**: Wählen Sie diese Aktivität, um die Quelldaten zu bereinigen.</span><span class="sxs-lookup"><span data-stu-id="817f5-120">**Cleansing**: Select this activity to cleanse the source data.</span></span>  
  
        -   <span data-ttu-id="817f5-121">**Abgleich**: Wählen Sie diese Aktivität, um einen Abgleich durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="817f5-121">**Matching**: Select this activity to perform matching.</span></span> <span data-ttu-id="817f5-122">Diese Aktivität ist nur verfügbar, wenn die für das Data Quality-Projekt ausgewählte Wissensdatenbank eine Abgleichsrichtlinie umfasst.</span><span class="sxs-lookup"><span data-stu-id="817f5-122">This activity is available only if the knowledge base selected for the data quality project contains a matching policy.</span></span>  
  
4.  <span data-ttu-id="817f5-123">Klicken Sie auf **Erstellen** , um ein Data Quality-Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="817f5-123">Click **Create** to create a data quality project.</span></span>  
  
##  <a name="follow-up-after-creating-a-data-quality-project"></a><a name="FollowUp"></a><span data-ttu-id="817f5-124">Nachverfolgung: nach dem Erstellen eines Data Quality-Projekts</span><span class="sxs-lookup"><span data-stu-id="817f5-124">Follow Up: After Creating a Data Quality Project</span></span>  
 <span data-ttu-id="817f5-125">Nachdem Sie ein Data Quality-Projekt erstellt haben, wird ein Assistent angezeigt, mit dem Sie die ausgewählte Aktivität – Bereinigung oder Abgleich – ausführen können.</span><span class="sxs-lookup"><span data-stu-id="817f5-125">After you create a data quality project, you are presented with a wizard that you use to perform the selected activity: cleansing or matching.</span></span> <span data-ttu-id="817f5-126">Weitere Informationen zu den Bereinigungs- und Abgleichsaktivitäten finden Sie unter [Datenbereinigung](../../2014/data-quality-services/data-cleansing.md) und [Datenabgleich](../../2014/data-quality-services/data-matching.md).</span><span class="sxs-lookup"><span data-stu-id="817f5-126">For more information about the cleansing and matching activities, see [Data Cleansing](../../2014/data-quality-services/data-cleansing.md) and [Data Matching](../../2014/data-quality-services/data-matching.md).</span></span>  
  
  
