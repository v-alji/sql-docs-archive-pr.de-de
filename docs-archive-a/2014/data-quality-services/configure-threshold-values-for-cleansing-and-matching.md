---
title: Konfigurieren der Schwellenwerte für Bereinigung und Abgleich | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.admin.config.general.f1
helpviewer_keywords:
- cleansing,threshold value
- cleansing threshold values
- matching,threshold value
ms.assetid: d2305409-7115-45a4-8f60-1213c0a47368
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0faf64e96468a3a9aac0de12d3ec3acbb1e1ed85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696082"
---
# <a name="configure-threshold-values-for-cleansing-and-matching"></a><span data-ttu-id="56c53-102">Konfigurieren der Schwellenwerte für Bereinigung und Abgleich</span><span class="sxs-lookup"><span data-stu-id="56c53-102">Configure Threshold Values for Cleansing and Matching</span></span>
  <span data-ttu-id="56c53-103">In diesem Thema wird beschrieben, wie Schwellenwerte, die während den computerunterstützten Bereinigungs- und Abgleichsaktivitäten in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) verwendet werden, konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="56c53-103">This topic describes how to configure threshold values that will be used during the computer-assisted cleansing and matching activities in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="56c53-104">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="56c53-104">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="56c53-105">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="56c53-105">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="56c53-106">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="56c53-106">Permissions</span></span>  
 <span data-ttu-id="56c53-107">Sie müssen die Rolle „dqs_administrator“ in der DQS_MAIN-Datenbank haben, um diese Schwellenwerte zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="56c53-107">You must have the dqs_administrator role on the DQS_MAIN database to configure these threshold values.</span></span>  
  
##  <a name="configuring-the-threshold-values"></a><a name="Configure"></a> <span data-ttu-id="56c53-108">Konfigurieren der Schwellenwerte</span><span class="sxs-lookup"><span data-stu-id="56c53-108">Configuring the Threshold Values</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="56c53-109">[Führen Sie die Data Quality-Client Anwendung](../../2014/data-quality-services/run-the-data-quality-client-application.md)aus.</span><span class="sxs-lookup"><span data-stu-id="56c53-109">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="56c53-110">Klicken Sie im [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Startbildschirm auf **Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="56c53-110">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="56c53-111">Klicken Sie anschließend auf die Registerkarte **Allgemeine Einstellungen** . Auf dieser Registerkarte können Sie Schwellenwerte für die Bereinigung und abgleichsaktivitäten angeben.</span><span class="sxs-lookup"><span data-stu-id="56c53-111">Next, click the **General Settings** tab. This tab enables you to specify threshold values for cleansing as well as matching activities.</span></span>  
  
4.  <span data-ttu-id="56c53-112">Um Schwellenwerte für die Bereinigungsaktivität anzugeben, geben Sie entsprechende Werte in den folgenden Feldern im Bereich **Interaktive Bereinigung** an:</span><span class="sxs-lookup"><span data-stu-id="56c53-112">To specify threshold values for the cleansing activity, specify appropriate values in the following boxes under the **Interactive Cleansing** area:</span></span>  
  
    -   <span data-ttu-id="56c53-113">**Mindestergebnis für Vorschläge**: Das minimale Ergebnis oder der Vertrauensgrad, der von DQS zum Vorschlagen von Ersetzungen für einen Wert während des computerunterstützten Bereinigungsprozesses verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="56c53-113">**Min score for suggestions**: The minimum score or the confidence level that will be used by DQS for suggesting replacements for a value during the computer-assisted cleansing process.</span></span> <span data-ttu-id="56c53-114">Geben Sie einen Wert in der Dezimalnotation des entsprechenden Prozentwerts ein.</span><span class="sxs-lookup"><span data-stu-id="56c53-114">Enter a value in the decimal notation of the corresponding percentage value.</span></span> <span data-ttu-id="56c53-115">Geben Sie beispielsweise 0,75 für 75 % ein.</span><span class="sxs-lookup"><span data-stu-id="56c53-115">For example, type 0.75 for 75%.</span></span> <span data-ttu-id="56c53-116">Dieser Wert sollte kleiner oder gleich dem Wert sein, der im Feld **Mindestergebnis für automatische Korrekturen** angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="56c53-116">This value should be less than or equal to the value specified in the **Min score for auto corrections** box.</span></span> <span data-ttu-id="56c53-117">Der Standardwert ist 0,7.</span><span class="sxs-lookup"><span data-stu-id="56c53-117">The default value is 0.7.</span></span>  
  
    -   <span data-ttu-id="56c53-118">**Mindestergebnis für automatische Korrekturen**: Das minimale Ergebnis oder der Vertrauensgrad, der von DQS zum automatischen Korrigieren eines Werts während des computerunterstützten Bereinigungsprozesses verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="56c53-118">**Min score for auto corrections**: The minimum score or the confidence level that will be used by DQS for automatically correcting a value during the computer-assisted cleansing process.</span></span> <span data-ttu-id="56c53-119">Geben Sie einen Wert in der Dezimalnotation des entsprechenden Prozentwerts ein.</span><span class="sxs-lookup"><span data-stu-id="56c53-119">Enter a value in the decimal notation of the corresponding percentage value.</span></span> <span data-ttu-id="56c53-120">Geben Sie beispielsweise 0,9 für 90 % ein.</span><span class="sxs-lookup"><span data-stu-id="56c53-120">For example, enter 0.9 for 90%.</span></span> <span data-ttu-id="56c53-121">Der Standardwert ist 0,8.</span><span class="sxs-lookup"><span data-stu-id="56c53-121">The default value is 0.8.</span></span>  
  
5.  <span data-ttu-id="56c53-122">Um einen Schwellenwert für die Abgleichsaktivität anzugeben, geben Sie einen Wert im Feld **Mindestergebnis für Datensätze** unter dem Bereich **Abgleich** an.</span><span class="sxs-lookup"><span data-stu-id="56c53-122">To specify threshold value for the matching activity, specify a value in the **Min record score** box under the **Matching** area.</span></span> <span data-ttu-id="56c53-123">Dieser Wert gibt das minimale Ergebnis für einen Datensatz an, das als Übereinstimmung mit einem anderen Datensatz betrachtet werden soll.</span><span class="sxs-lookup"><span data-stu-id="56c53-123">This value signifies the minimum score for a record to be considered as a match for another record.</span></span> <span data-ttu-id="56c53-124">Der Standardwert ist 80 %.</span><span class="sxs-lookup"><span data-stu-id="56c53-124">The default value is 80%.</span></span>  
  
6.  <span data-ttu-id="56c53-125">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="56c53-125">Click **Close**.</span></span>  
  
  
