---
title: Anzeigen von Informationen zu einer Warnung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- viewing alerts
- alerts [SQL Server], viewing
- displaying alerts
- status information [SQL Server], alerts
ms.assetid: a0e3a8c4-e3c2-42a5-b2f8-aa06061d3fa6
author: stevestein
ms.author: sstein
ms.openlocfilehash: ee72512a507299e71f13fee689709a9403bb04e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616320"
---
# <a name="view-information-about-an-alert"></a><span data-ttu-id="c6f64-102">View Information About an Alert</span><span class="sxs-lookup"><span data-stu-id="c6f64-102">View Information About an Alert</span></span>
  <span data-ttu-id="c6f64-103">In diesem Thema wird beschrieben, wie Sie Informationen zu- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Warnungen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von oder anzeigen können [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6f64-103">This topic describes how to view information about [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c6f64-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="c6f64-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c6f64-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="c6f64-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c6f64-106">Security</span><span class="sxs-lookup"><span data-stu-id="c6f64-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c6f64-107">**So zeigen Sie Informationen zu einer Warnung an mit**</span><span class="sxs-lookup"><span data-stu-id="c6f64-107">**To view information about an alert, using:**</span></span>  
  
     [<span data-ttu-id="c6f64-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c6f64-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c6f64-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c6f64-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c6f64-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="c6f64-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c6f64-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c6f64-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c6f64-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c6f64-112">Permissions</span></span>  
 <span data-ttu-id="c6f64-113">Standardmäßig können nur Mitglieder der festen Serverrolle **sysadmin** Information über eine Warnung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c6f64-113">By default, members of the **sysadmin** fixed server role can view information about an alert.</span></span> <span data-ttu-id="c6f64-114">Andere Benutzer müssen Mitglieder der festen Datenbankrolle **SQLAgentOperatorRole** in der **msdb** -Datenbank sein.</span><span class="sxs-lookup"><span data-stu-id="c6f64-114">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c6f64-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c6f64-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-information-about-an-alert"></a><span data-ttu-id="c6f64-116">So zeigen Sie Informationen zu einer Warnung an</span><span class="sxs-lookup"><span data-stu-id="c6f64-116">To view information about an alert</span></span>  
  
1.  <span data-ttu-id="c6f64-117">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, auf dem Sie Informationen über eine Warnung anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="c6f64-117">In **Object Explorer,** click the plus sign to expand the server where you want to view information about an alert.</span></span>  
  
2.  <span data-ttu-id="c6f64-118">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="c6f64-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="c6f64-119">Klicken Sie auf das Pluszeichen, um den Ordner **Warnungen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="c6f64-119">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="c6f64-120">Klicken Sie mit der rechten Maustaste auf die Warnung mit den von Ihnen gewünschten Informationen, die Sie anzeigen möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="c6f64-120">Right-click the alert that has the information you want to view and select **Properties**.</span></span>  
  
     <span data-ttu-id="c6f64-121">Weitere Informationen zu den im Dialogfeld _Eigenschaften von Warnung_**Warnungsname** enthaltenen verfügbaren Optionen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="c6f64-121">For more information on the available options contained in the _alert_name_**alert properties** dialog box, see:</span></span>  
  
    -   [<span data-ttu-id="c6f64-122">Warnungs Eigenschaften-neue Warnung &#40;Seite "Allgemein"&#41;</span><span class="sxs-lookup"><span data-stu-id="c6f64-122">Alert Properties-New Alert &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="c6f64-123">Warnungs Eigenschaften-Seite "neue Warnung &#40;Antwort"&#41;</span><span class="sxs-lookup"><span data-stu-id="c6f64-123">Alert Properties-New Alert &#40;Response Page&#41;</span></span>](alert-properties-new-alert-response-page.md)  
  
    -   [<span data-ttu-id="c6f64-124">Warnungs Eigenschaften: Seite "neue Warnung &#40;Optionen"&#41;</span><span class="sxs-lookup"><span data-stu-id="c6f64-124">Alert Properties: New Alert &#40;Options Page&#41;</span></span>](alert-properties-new-alert-options-page.md)  
  
    -   [<span data-ttu-id="c6f64-125">Warnungseigenschaften &#40;Seite „Verlauf“&#41;</span><span class="sxs-lookup"><span data-stu-id="c6f64-125">Alert Properties &#40;History Page&#41;</span></span>](alert-properties-history-page.md)  
  
5.  <span data-ttu-id="c6f64-126">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6f64-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c6f64-127">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c6f64-127">Using Transact-SQL</span></span>  
  
#### <a name="to-view-information-about-an-alert"></a><span data-ttu-id="c6f64-128">So zeigen Sie Informationen zu einer Warnung an</span><span class="sxs-lookup"><span data-stu-id="c6f64-128">To view information about an alert</span></span>  
  
1.  <span data-ttu-id="c6f64-129">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="c6f64-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c6f64-130">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="c6f64-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c6f64-131">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c6f64-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- reports information about the Demo: Sev. 25 Errors alert  
    -- This example assumes that the 'Demo: Sev. 25 Errors' alert exists.  
    USE msdb ;  
    GO  
  
    EXEC sp_help_alert @alert_name = 'Demo: Sev. 25 Errors'  
    GO  
    ```  
  
 <span data-ttu-id="c6f64-132">Weitere Informationen finden Sie unter [sp_help_alert &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-help-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c6f64-132">For more information, see [sp_help_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-alert-transact-sql).</span></span>  
  
  
