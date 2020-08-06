---
title: Aktivieren oder Deaktivieren von Profilerstellungsbenachrichtigungen in DQS | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
helpviewer_keywords:
- enable notifications
- notifications,enable
- notifications,disable
ms.assetid: e439bb29-60cc-4afd-a79a-f629b8d843c1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b3b5e8cec1cac3eb1ce4357480c0f994a33d4c40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700263"
---
# <a name="enable-or-disable-profiling-notifications-in-dqs"></a><span data-ttu-id="ca28c-102">Aktivieren oder Deaktivieren von Profilerstellungsbenachrichtigungen in DQS</span><span class="sxs-lookup"><span data-stu-id="ca28c-102">Enable or Disable Profiling Notifications in DQS</span></span>
  <span data-ttu-id="ca28c-103">In diesem Thema wird beschrieben, wie Profilerstellungsbenachrichtigungen in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) aktiviert und deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="ca28c-103">This topic describes how to enable or disable profiling notifications in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="ca28c-104">Standardmäßig sind Profilerstellungsbenachrichtigungen in DQS aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ca28c-104">By default, profiling notifications are enabled in DQS.</span></span> <span data-ttu-id="ca28c-105">Profilerstellungsbenachrichtigungen liefern Ihnen wichtige Fakten zur Datenquelle und der Effektivität der aktuellen Aktivität, die für die Daten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ca28c-105">Profiling notifications tell you important facts about the data source and the effectiveness of the current activity performed on the data.</span></span> <span data-ttu-id="ca28c-106">Weitere Informationen finden Sie unter [Data Profiling and Notifications in DQS](../../2014/data-quality-services/data-profiling-and-notifications-in-dqs.md).</span><span class="sxs-lookup"><span data-stu-id="ca28c-106">For more information, see [Data Profiling and Notifications in DQS](../../2014/data-quality-services/data-profiling-and-notifications-in-dqs.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ca28c-107">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="ca28c-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ca28c-108">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ca28c-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ca28c-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ca28c-109">Permissions</span></span>  
 <span data-ttu-id="ca28c-110">Sie müssen die Rolle „dqs_administrator“ der DQS_MAIN-Datenbank haben, um Benachrichtigungen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ca28c-110">You must have the dqs_administrator role on the DQS_MAIN database to enable notifications.</span></span>  
  
##  <a name="enable-or-disable-profiling-notifications"></a><a name="Enable"></a><span data-ttu-id="ca28c-111">Aktivieren oder Deaktivieren von Profil Erstellungs Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="ca28c-111">Enable or Disable Profiling Notifications</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="ca28c-112">[Führen Sie die Data Quality-Client Anwendung](../../2014/data-quality-services/run-the-data-quality-client-application.md)aus.</span><span class="sxs-lookup"><span data-stu-id="ca28c-112">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="ca28c-113">Klicken Sie im [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Startbildschirm auf **Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="ca28c-113">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="ca28c-114">Klicken dann auf die Registerkarte **Allgemeine Einstellungen** .</span><span class="sxs-lookup"><span data-stu-id="ca28c-114">Next, click the **General Settings** tab.</span></span>  
  
4.  <span data-ttu-id="ca28c-115">Deaktivieren oder aktivieren Sie das Kontrollkästchen **Benachrichtigungen aktivieren** , um Profilerstellungsbenachrichtigungen für verschiedene Aktivitäten in DQS zu deaktivieren oder zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ca28c-115">Clear or select the **Enable Notifications** check box to disable or enable profiling notifications for various activities in DQS.</span></span>  
  
5.  <span data-ttu-id="ca28c-116">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="ca28c-116">Click **Close**.</span></span>  
  
  
