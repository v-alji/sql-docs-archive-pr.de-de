---
title: Gespeicherte Überprüfungsprozedur (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 332d3c86-4440-4f12-a6cb-ffbfbccde52c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8fa6b01d950c87768d10b0252c1ccbab2b932fe1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618065"
---
# <a name="validation-stored-procedure-master-data-services"></a><span data-ttu-id="ca30a-102">Gespeicherte Überprüfungsprozedur (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ca30a-102">Validation Stored Procedure (Master Data Services)</span></span>
  <span data-ttu-id="ca30a-103">Überprüfen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]eine Version, um Geschäftsregeln auf alle Elemente in der Modellversion anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="ca30a-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], validate a version to apply business rules to all members in the model version.</span></span>  
  
 <span data-ttu-id="ca30a-104">Dieses Thema erklärt, wie die gespeicherte Prozedur **mdm.udpValidateModel** verwendet wird, um Daten zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ca30a-104">This topic explains how to use the **mdm.udpValidateModel** stored procedure to validate data.</span></span> <span data-ttu-id="ca30a-105">Wenn Sie Administrator in der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Webanwendung sind, können Sie stattdessen eine Überprüfung in der Benutzeroberfläche ausführen.</span><span class="sxs-lookup"><span data-stu-id="ca30a-105">If you are an administrator in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application, you can do validation in the UI instead.</span></span> <span data-ttu-id="ca30a-106">Weitere Informationen finden Sie unter [Überprüfen einer Version anhand von Geschäftsregeln &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ca30a-106">For more information, see [Validate a Version against Business Rules &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ca30a-107">Wenn Sie Überprüfung vor dem Abschluss des Stagingprozesses aufrufen, werden Elemente nicht überprüft, für die das Staging noch nicht beendet ist.</span><span class="sxs-lookup"><span data-stu-id="ca30a-107">If you invoke validation before the staging process is complete, members that have not finished staging will not be validated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca30a-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ca30a-108">Example</span></span>  
  
```  
DECLARE @ModelName nVarchar(50) = 'Customer'   
DECLARE @Model_id int   
DECLARE @UserName nvarchar(50)= 'DOMAIN\user_name'   
DECLARE @User_ID int   
DECLARE @Version_ID int   
  
SET @User_ID = (SELECT ID    
                 FROM mdm.tblUser u   
                 WHERE u.UserName = @UserName)   
SET @Model_ID = (SELECT Top 1 Model_ID   
                 FROM mdm.viw_SYSTEM_SCHEMA_VERSION   
                 WHERE Model_Name = @ModelName)   
SET @Version_ID = (SELECT MAX(ID)   
                 FROM mdm.viw_SYSTEM_SCHEMA_VERSION   
                 WHERE Model_ID = @Model_ID)  
  
EXECUTE mdm.udpValidateModel @User_ID, @Model_ID, @Version_ID, 1  
  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca30a-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="ca30a-109">Parameters</span></span>  
 <span data-ttu-id="ca30a-110">Zu dieser Prozedur gehören die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="ca30a-110">The parameters of this procedure are as follows:</span></span>  
  
|<span data-ttu-id="ca30a-111">Parameter</span><span class="sxs-lookup"><span data-stu-id="ca30a-111">Parameter</span></span>|<span data-ttu-id="ca30a-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ca30a-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ca30a-113">UserID</span><span class="sxs-lookup"><span data-stu-id="ca30a-113">UserID</span></span>|<span data-ttu-id="ca30a-114">Die Benutzer-ID.</span><span class="sxs-lookup"><span data-stu-id="ca30a-114">The user ID.</span></span>|  
|<span data-ttu-id="ca30a-115">Model_ID</span><span class="sxs-lookup"><span data-stu-id="ca30a-115">Model_ID</span></span>|<span data-ttu-id="ca30a-116">Die Modell-ID.</span><span class="sxs-lookup"><span data-stu-id="ca30a-116">The model ID.</span></span>|  
|<span data-ttu-id="ca30a-117">Version_ID</span><span class="sxs-lookup"><span data-stu-id="ca30a-117">Version_ID</span></span>|<span data-ttu-id="ca30a-118">Die Versions-ID.</span><span class="sxs-lookup"><span data-stu-id="ca30a-118">The version ID.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca30a-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ca30a-119">See Also</span></span>  
 <span data-ttu-id="ca30a-120">[Daten Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ca30a-120">[Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md) </span></span>  
 [<span data-ttu-id="ca30a-121">Überprüfen einer Version anhand von Geschäftsregeln &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ca30a-121">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](validate-a-version-against-business-rules-master-data-services.md)  
  
  
