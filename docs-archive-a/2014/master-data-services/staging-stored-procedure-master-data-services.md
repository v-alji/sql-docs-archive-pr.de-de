---
title: Gespeicherte Stagingprozedur (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 6a613106-9f87-4caf-a23a-a726fc6561c5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9259352350a099db5d9b18411ad4da06dfb19819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622745"
---
# <a name="staging-stored-procedure-master-data-services"></a><span data-ttu-id="f1827-102">Gespeicherte Stagingprozedur (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f1827-102">Staging Stored Procedure (Master Data Services)</span></span>
  <span data-ttu-id="f1827-103">Wenn Sie den Stagingprozess von [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]initiieren, verwenden Sie eine von drei gespeicherten Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="f1827-103">When initiating the staging process from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], you use one of three stored procedures.</span></span>  
  
-   <span data-ttu-id="f1827-104">stg.udp_name_Leaf</span><span class="sxs-lookup"><span data-stu-id="f1827-104">stg.udp_name_Leaf</span></span>  
  
-   <span data-ttu-id="f1827-105">stg.udp_name_Consolidated</span><span class="sxs-lookup"><span data-stu-id="f1827-105">stg.udp_name_Consolidated</span></span>  
  
-   <span data-ttu-id="f1827-106">stg.udp_name_Relationship</span><span class="sxs-lookup"><span data-stu-id="f1827-106">stg.udp_name_Relationship</span></span>  
  
 <span data-ttu-id="f1827-107">"name" steht für den Namen der Stagingtabelle, die beim Erstellen der Entität angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="f1827-107">Where name is the name of the staging table that was specified when the entity was created.</span></span>  
  
## <a name="staging-process-stored-procedure-parameters"></a><span data-ttu-id="f1827-108">Parameter der gespeicherten Prozeduren für den Stagingprozess</span><span class="sxs-lookup"><span data-stu-id="f1827-108">Staging Process Stored Procedure Parameters</span></span>  
 <span data-ttu-id="f1827-109">In der folgenden Tabelle sind die Parameter dieser gespeicherten Prozeduren aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f1827-109">The following table lists the parameters of these stored procedures.</span></span>  
  
|<span data-ttu-id="f1827-110">Parameter</span><span class="sxs-lookup"><span data-stu-id="f1827-110">Parameter</span></span>|<span data-ttu-id="f1827-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f1827-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f1827-112">**VersionName**</span><span class="sxs-lookup"><span data-stu-id="f1827-112">**VersionName**</span></span><br /><br /> <span data-ttu-id="f1827-113">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="f1827-113">Required</span></span>|<span data-ttu-id="f1827-114">Der Name der Version.</span><span class="sxs-lookup"><span data-stu-id="f1827-114">The name of the version.</span></span> <span data-ttu-id="f1827-115">Dabei wird ggf. abhängig von der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Sortiereinstellung die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="f1827-115">This may or may not be case-sensitive, depending on your [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] collation setting.</span></span>|  
|<span data-ttu-id="f1827-116">**LogFlag**</span><span class="sxs-lookup"><span data-stu-id="f1827-116">**LogFlag**</span></span><br /><br /> <span data-ttu-id="f1827-117">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="f1827-117">Required</span></span>|<span data-ttu-id="f1827-118">Bestimmt, ob Transaktionen während des Stagingprozesses protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="f1827-118">Determines whether transactions are logged during the staging process.</span></span> <span data-ttu-id="f1827-119">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="f1827-119">Possible values are:</span></span><br /><br /> <span data-ttu-id="f1827-120">**0**: Transaktionen nicht protokollieren.</span><span class="sxs-lookup"><span data-stu-id="f1827-120">**0**: Do not log transactions.</span></span><br /><span data-ttu-id="f1827-121">**1**: Transaktionen protokollieren.</span><span class="sxs-lookup"><span data-stu-id="f1827-121">**1**: Log transactions.</span></span><br /><br /> <br /><br /> <span data-ttu-id="f1827-122">Weitere Informationen über Transaktionen finden Sie unter [Transaktionen &#40;Master Data Services&#41;](transactions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f1827-122">For more information about transactions, see [Transactions &#40;Master Data Services&#41;](transactions-master-data-services.md).</span></span>|  
|<span data-ttu-id="f1827-123">**BatchTag**</span><span class="sxs-lookup"><span data-stu-id="f1827-123">**BatchTag**</span></span><br /><br /> <span data-ttu-id="f1827-124">Erforderlich, außer vom Webdienst</span><span class="sxs-lookup"><span data-stu-id="f1827-124">Required, except by web service</span></span>|<span data-ttu-id="f1827-125">Der **BatchTag** -Wert wie in der Stagingtabelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="f1827-125">The **BatchTag** value as specified in the staging table.</span></span>|  
|<span data-ttu-id="f1827-126">**Batch_ID**</span><span class="sxs-lookup"><span data-stu-id="f1827-126">**Batch_ID**</span></span><br /><br /> <span data-ttu-id="f1827-127">Wird nur vom Webdienst benötigt</span><span class="sxs-lookup"><span data-stu-id="f1827-127">Required by web service only</span></span>|<span data-ttu-id="f1827-128">Der Wert der **Batch_ID** wie in der Stagingtabelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="f1827-128">The **Batch_ID** value as specified in the staging table.</span></span>|  
  
### <a name="staging-process-stored-procedure-example"></a><span data-ttu-id="f1827-129">Beispiel einer gespeicherten Prozedur für den Stagingprozess</span><span class="sxs-lookup"><span data-stu-id="f1827-129">Staging Process Stored Procedure Example</span></span>  
 <span data-ttu-id="f1827-130">Im folgenden Beispiel wird gezeigt, wie der Stagingprozess mit der entsprechenden gespeicherten Prozedur gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="f1827-130">The following example shows how to start the staging process by using the staging stored procedure.</span></span>  
  
```  
USE [DATABASE_NAME]  
GO  
  
EXEC[stg].[udp_name_Leaf]  
      @VersionName = N'VERSION_1',  
@LogFlag = 1,  
@BatchTag = N'batch1'  
  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="f1827-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1827-131">See Also</span></span>  
 <span data-ttu-id="f1827-132">[Die gespeicherte Überprüfungs Prozedur &#40;Master Data Services&#41;](../../2014/master-data-services/validation-stored-procedure-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="f1827-132">[Validation Stored Procedure &#40;Master Data Services&#41;](../../2014/master-data-services/validation-stored-procedure-master-data-services.md) </span></span>  
 <span data-ttu-id="f1827-133">[Laden oder Aktualisieren von Elementen in Master Data Services mithilfe des Stagingprozesses](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="f1827-133">[Load or Update Members in Master Data Services by Using the Staging Process](add-update-and-delete-data-master-data-services.md) </span></span>  
 [<span data-ttu-id="f1827-134">Anzeigen von Fehlern, die während des Stagingprozesses auftreten &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f1827-134">View Errors that Occur During the Staging Process &#40;Master Data Services&#41;</span></span>](view-errors-that-occur-during-staging-master-data-services.md)  
  
  
