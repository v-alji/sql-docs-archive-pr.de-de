---
title: Zugreifen auf den WMI-Anbieter für die Konfigurations Verwaltung mit WQL | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- query language [WMI]
- WMI Query Language [WMI]
- WQL [WMI]
- WMI Provider for Configuration Management, WQL
ms.assetid: 26499530-d93b-452b-bbe4-217ef1d11e68
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b58297c5e292ceb18a6e2e50e2b25b9aa352e2fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607567"
---
# <a name="access-wmi-provider-for-configuration-management-using-wql"></a><span data-ttu-id="01312-102">Zugreifen auf WMI-Anbieter für die Konfigurationsverwaltung mit WQL</span><span class="sxs-lookup"><span data-stu-id="01312-102">Access WMI Provider for Configuration Management using WQL</span></span>
  <span data-ttu-id="01312-103">In diesem Abschnitt wird beschrieben, wie [!INCLUDE[msCoName](../../includes/msconame-md.md)] WQL-Anweisungen (Windows Management Instrumentation Query Language, Abfragesprache der Windows-Verwaltungsinstrumentation) für den WMI-Anbieter für die Computerverwaltung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="01312-103">This section describes how to execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Management Instrumentation Query Language (WQL) statements against the WMI Provider for Computer Management.</span></span>  
  
 <span data-ttu-id="01312-104">Im Beispiel wird ein WQL-Editor, WBEMtest.exe, zum Ausführen von WQL-Abfragen für den WMI-Anbieter verwendet, um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienste, -Netzwerkprotokolle und -Aliasnamen aufzuzählen.</span><span class="sxs-lookup"><span data-stu-id="01312-104">The example uses a WQL editor, WBEMtest.exe, to run WQL queries against the WMI Provider to enumerate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, network protocols, and aliases.</span></span>  
  
### <a name="querying-services-using-wbemtest"></a><span data-ttu-id="01312-105">Abfragen von Diensten mit WBEMtest</span><span class="sxs-lookup"><span data-stu-id="01312-105">Querying services using WBEMtest</span></span>  
  
1.  <span data-ttu-id="01312-106">Klicken Sie im **Startmenü** auf **Ausführen**, und geben Sie dann ein `WBEMtest` .</span><span class="sxs-lookup"><span data-stu-id="01312-106">From the **Start** menu, click **Run**, and then enter `WBEMtest`.</span></span>  
  
2.  <span data-ttu-id="01312-107">Das Dialogfeld WBEMtest.exe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="01312-107">The WBEMtest.exe dialog appears.</span></span> <span data-ttu-id="01312-108">Klicken Sie auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="01312-108">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="01312-109">Geben Sie im ersten Textfeld den Namespace für den WMI-Anbieter für die Computerverwaltung ein: root\Microsoft\SqlServer\ComputerManagement11.</span><span class="sxs-lookup"><span data-stu-id="01312-109">In the first text field, type the WMI Provider for Computer Management namespace: root\Microsoft\SqlServer\ComputerManagement11.</span></span> <span data-ttu-id="01312-110">Klicken Sie auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="01312-110">Click **Connect**.</span></span>  
  
4.  <span data-ttu-id="01312-111">Klicken Sie auf **Abfragen**.</span><span class="sxs-lookup"><span data-stu-id="01312-111">Click **Query**.</span></span> <span data-ttu-id="01312-112">Geben Sie eine Abfrage ein, die die aktuellen Dienste zurückgibt, die auf dem lokalen Computer ausgeführt werden: **Select \* from SqlService.**</span><span class="sxs-lookup"><span data-stu-id="01312-112">Type a query that returns the current services running on the local computer: **SELECT \* FROM SqlService.**</span></span> <span data-ttu-id="01312-113">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="01312-113">Click **Apply**.</span></span>  
  
5.  <span data-ttu-id="01312-114">Verfeinern Sie die Abfrage weiter, indem Sie `WHERE ServiceName = "MSSQLSERVER"` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="01312-114">Further refine the query by adding `WHERE ServiceName = "MSSQLSERVER"`.</span></span>  
  
  
