---
title: Änderungsnachverfolgung (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- change tracking [SQL Server]
ms.assetid: 5e879c65-0d38-454f-9a20-62a6e72c89f7
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 2d3b69057b02884f41a43aa9a009ab3db937ed25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701282"
---
# <a name="change-tracking-master-data-services"></a><span data-ttu-id="bd27c-102">Änderungsnachverfolgung (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="bd27c-102">Change Tracking (Master Data Services)</span></span>
  <span data-ttu-id="bd27c-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]können Sie Änderungsnachverfolgungsgruppen verwenden, um Aktionen durchzuführen, wenn sich ein Attributwert ändert.</span><span class="sxs-lookup"><span data-stu-id="bd27c-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can use change tracking groups to take action when an attribute value changes.</span></span> <span data-ttu-id="bd27c-104">Verwenden Sie die Änderungsnachverfolgung, wenn Sie nicht wissen, was der neue Wert ist, aber wissen möchten, ob eine Änderung aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="bd27c-104">Use change tracking when you don't know what the new value will be, but instead want to know if any change occurred.</span></span>  
  
## <a name="configuring-change-tracking"></a><span data-ttu-id="bd27c-105">Konfigurieren der Änderungsnachverfolgung</span><span class="sxs-lookup"><span data-stu-id="bd27c-105">Configuring Change Tracking</span></span>  
 <span data-ttu-id="bd27c-106">Um die Änderungsnachverfolgung zu konfigurieren, fügen Sie einer Änderungsnachverfolgungsgruppe ein Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="bd27c-106">To configure change tracking, you add an attribute to a change tracking group.</span></span> <span data-ttu-id="bd27c-107">Die Gruppe kann ein oder viele Attribute enthalten.</span><span class="sxs-lookup"><span data-stu-id="bd27c-107">The group can contain one or many attributes.</span></span> <span data-ttu-id="bd27c-108">Erstellen Sie dann eine Geschäftsregel, um die Aktion zu definieren, die ausgeführt wird, wenn sich eines der Attribute in der Gruppe ändert.</span><span class="sxs-lookup"><span data-stu-id="bd27c-108">Then, you create a business rule to define the action that is taken when any of the attributes in the group change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd27c-109">Änderungsnachverfolgungs-Geschäftsregeln stufen bereitgestellte (importierte) Daten als geändert ein.</span><span class="sxs-lookup"><span data-stu-id="bd27c-109">Change tracking business rules consider staged (imported) data to be changed.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="bd27c-110">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="bd27c-110">Related Tasks</span></span>  
  
|<span data-ttu-id="bd27c-111">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="bd27c-111">Task Description</span></span>|<span data-ttu-id="bd27c-112">Thema</span><span class="sxs-lookup"><span data-stu-id="bd27c-112">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="bd27c-113">Hinzufügen von Attributen zu einer Änderungsnachverfolgungsgruppe.</span><span class="sxs-lookup"><span data-stu-id="bd27c-113">Add attributes to a change tracking group.</span></span>|[<span data-ttu-id="bd27c-114">Hinzufügen von Attributen zu einer Änderungsnachverfolgungsgruppe &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bd27c-114">Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;</span></span>](add-attributes-to-a-change-tracking-group-master-data-services.md)|  
|<span data-ttu-id="bd27c-115">Erstellen einer Geschäftsregel, die Aktionen auf der Grundlage von Änderungen an Attributwerten initiiert.</span><span class="sxs-lookup"><span data-stu-id="bd27c-115">Create a business rule that initiates actions based on attribute changes.</span></span>|[<span data-ttu-id="bd27c-116">Initiieren von Aktionen auf der Grundlage von Attributwertänderungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bd27c-116">Initiate Actions Based on Attribute Value Changes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/initiate-actions-based-on-attribute-value-changes-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="bd27c-117">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="bd27c-117">Related Content</span></span>  
  
-   [<span data-ttu-id="bd27c-118">Überprüfung &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bd27c-118">Validation &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validation-master-data-services.md)  
  
-   [<span data-ttu-id="bd27c-119">Geschäftsregeln &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bd27c-119">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="bd27c-120">Attribute &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bd27c-120">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
