---
title: Konfigurieren allgemeiner Eigenschaften der richtlinienbasierten Verwaltung | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.PolicyManagement.f1
helpviewer_keywords:
- Policy-Based Management, configure properties
ms.assetid: 6d1e0e37-29ea-408a-a055-384984d884be
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a2efb37fafa29bcb043dedbcfa8719d0092b1c77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699471"
---
# <a name="configure-the-general-properties-of-policy-based-management"></a><span data-ttu-id="dba34-102">Konfigurieren allgemeiner Eigenschaften der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="dba34-102">Configure the General Properties of Policy-Based Management</span></span>
  <span data-ttu-id="dba34-103">In diesem Thema wird beschrieben, wie die Eigenschaften für die richtlinienbasierte Verwaltung in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="dba34-103">This topic describes how to configure the properties for Policy-Based Management in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="dba34-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="dba34-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="dba34-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="dba34-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="dba34-106">Security</span><span class="sxs-lookup"><span data-stu-id="dba34-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="dba34-107">**Konfigurieren der richtlinienbasierten Verwaltung mit:**</span><span class="sxs-lookup"><span data-stu-id="dba34-107">**To configure Policy-Based Management, using:**</span></span>  
  
     [<span data-ttu-id="dba34-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dba34-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="dba34-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dba34-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dba34-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="dba34-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dba34-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="dba34-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="dba34-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="dba34-112">Permissions</span></span>  
 <span data-ttu-id="dba34-113">Erfordert die Mitgliedschaft in der festen Datenbankrolle PolicyAdministratorRole.</span><span class="sxs-lookup"><span data-stu-id="dba34-113">Requires membership in the PolicyAdministratorRole fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="dba34-114">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dba34-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-policy-based-management"></a><span data-ttu-id="dba34-115">So konfigurieren Sie die richtlinienbasierte Verwaltung</span><span class="sxs-lookup"><span data-stu-id="dba34-115">To configure Policy-Based Management</span></span>  
  
1.  <span data-ttu-id="dba34-116">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, auf dem Sie die Eigenschaften der richtlinienbasierten Verwaltung konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="dba34-116">In **Object Explorer**, click the plus sign to expand the server where you want to configure Policy-Based Management properties.</span></span>  
  
2.  <span data-ttu-id="dba34-117">Klicken Sie auf das Pluszeichen, um den Ordner **Verwaltung** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="dba34-117">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="dba34-118">Klicken Sie mit der rechten Maustaste auf **Richtlinienverwaltung** , und wählen Sie dann **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="dba34-118">Right-click **Policy Management** and select **Properties**.</span></span>  
  
     <span data-ttu-id="dba34-119">Die folgenden Optionen sind im Dialogfeld **Richtlinienverwaltungseigenschaften** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dba34-119">The following options are available in **Policy Management Properties** dialog box.</span></span>  
  
     <span data-ttu-id="dba34-120">**Aktiviert**</span><span class="sxs-lookup"><span data-stu-id="dba34-120">**Enabled**</span></span>  
     <span data-ttu-id="dba34-121">Gibt an, ob die richtlinienbasierte Verwaltung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="dba34-121">Specifies whether Policy-Based Management is enabled.</span></span>  
  
     <span data-ttu-id="dba34-122">**HistoryRetentionInDays**</span><span class="sxs-lookup"><span data-stu-id="dba34-122">**HistoryRetentionInDays**</span></span>  
     <span data-ttu-id="dba34-123">Gibt die Anzahl der Tage an, wie lange der Richtlinienauswertungsverlauf beibehalten werden soll.</span><span class="sxs-lookup"><span data-stu-id="dba34-123">Specifies the number of days that policy evaluation history should be retained.</span></span> <span data-ttu-id="dba34-124">Wenn dieser Wert 0 ist (Standardeinstellung), wird der Verlauf nicht automatisch entfernt.</span><span class="sxs-lookup"><span data-stu-id="dba34-124">If this value is 0 (the default), the history will not be automatically removed.</span></span>  
  
     <span data-ttu-id="dba34-125">**LogOnSuccess**</span><span class="sxs-lookup"><span data-stu-id="dba34-125">**LogOnSuccess**</span></span>  
     <span data-ttu-id="dba34-126">Gibt an, ob die richtlinienbasierte Verwaltung erfolgreiche Richtlinienauswertungen protokolliert.</span><span class="sxs-lookup"><span data-stu-id="dba34-126">Specifies whether Policy-Based Management logs successful policy evaluations.</span></span>  
  
    -   <span data-ttu-id="dba34-127">Wenn dieser Wert false ist (Standardeinstellung), werden nur fehlerhafte Richtlinienauswertungen protokolliert.</span><span class="sxs-lookup"><span data-stu-id="dba34-127">When this value is false (the default), only failed policy evaluations are logged.</span></span>  
  
    -   <span data-ttu-id="dba34-128">Wenn dieser Wert true ist, werden sowohl erfolgreiche als auch fehlerhafte Richtlinienauswertungen protokolliert.</span><span class="sxs-lookup"><span data-stu-id="dba34-128">When this value is true, both successful and failed policy evaluations are logged.</span></span>  
  
4.  <span data-ttu-id="dba34-129">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dba34-129">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="dba34-130">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dba34-130">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-policy-based-management"></a><span data-ttu-id="dba34-131">So konfigurieren Sie die richtlinienbasierte Verwaltung</span><span class="sxs-lookup"><span data-stu-id="dba34-131">To configure Policy-Based Management</span></span>  
  
1.  <span data-ttu-id="dba34-132">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="dba34-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="dba34-133">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="dba34-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="dba34-134">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="dba34-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- enables Policy-Based Management   
    USE msdb;  
    GO  
    EXEC dbo.sp_syspolicy_configure   
         @name = N'Enabled',   
         @value = 1;  
    GO  
    ```  
  
 <span data-ttu-id="dba34-135">Weitere Informationen finden Sie unter [sp_syspolicy_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-configure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dba34-135">For more information, see [sp_syspolicy_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-configure-transact-sql).</span></span>  
  
  
