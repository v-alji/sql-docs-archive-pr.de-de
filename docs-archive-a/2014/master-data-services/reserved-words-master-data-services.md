---
title: Reservierte Wörter (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- reserved words [Master Data Services]
- Master Data Services, reserved words
ms.assetid: 88afd0d0-4362-4394-8357-4e65388fc0fc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c54bb371cd8f797cfb36f015387e0e21339c0426
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618752"
---
# <a name="reserved-words-master-data-services"></a><span data-ttu-id="d378c-102">Reservierte Wörter (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d378c-102">Reserved Words (Master Data Services)</span></span>
  <span data-ttu-id="d378c-103">Wenn Sie Modellobjekte oder Elemente erstellen, können in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]einige Wörter nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d378c-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], when you create model objects or members, some words cannot be used.</span></span> <span data-ttu-id="d378c-104">Die Verwendung dieser Wörter verursacht möglicherweise Fehler.</span><span class="sxs-lookup"><span data-stu-id="d378c-104">Using these words may cause errors.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d378c-105">Sie sollten auch die Verwendung von Sonderzeichen (Symbole, Silbentrennung usw.) einschränken.</span><span class="sxs-lookup"><span data-stu-id="d378c-105">You should also limit your use of special characters (symbols, hyphenation, etc.).</span></span>  
  
-   [<span data-ttu-id="d378c-106">Modelle</span><span class="sxs-lookup"><span data-stu-id="d378c-106">Models</span></span>](#models)  
  
-   [<span data-ttu-id="d378c-107">Entitäten</span><span class="sxs-lookup"><span data-stu-id="d378c-107">Entities</span></span>](#entities)  
  
-   [<span data-ttu-id="d378c-108">Explizite Hierarchien</span><span class="sxs-lookup"><span data-stu-id="d378c-108">Explicit Hierarchies</span></span>](#exhierarchies)  
  
-   [<span data-ttu-id="d378c-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="d378c-109">Attributes</span></span>](#attributes)  
  
-   [<span data-ttu-id="d378c-110">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="d378c-110">Members</span></span>](#members)  
  
##  <a name="models"></a><a name="models"></a><span data-ttu-id="d378c-111">Bilder</span><span class="sxs-lookup"><span data-stu-id="d378c-111">Models</span></span>  
 <span data-ttu-id="d378c-112">Wenn Sie ein Modell erstellen, dessen Name auf **Name**festgelegt ist, wählen Sie **Entität mit gleichem Namen wie Modell erstellen** nicht aus, da **Name** nicht für den Namen einer Entität verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d378c-112">If you create a model with the name set to **Name**, do not select **Create entity with same name as model** because **Name** cannot be used for the name of an entity.</span></span>  
  
##  <a name="entities"></a><a name="entities"></a><span data-ttu-id="d378c-113">Kleinstunternehmen</span><span class="sxs-lookup"><span data-stu-id="d378c-113">Entities</span></span>  
 <span data-ttu-id="d378c-114">**Name** oder **Code**kann für Entitätsnamen nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d378c-114">For entity names, you cannot use **Name** or **Code**.</span></span>  
  
##  <a name="explicit-hierarchies"></a><a name="exhierarchies"></a><span data-ttu-id="d378c-115">Explizite Hierarchien</span><span class="sxs-lookup"><span data-stu-id="d378c-115">Explicit Hierarchies</span></span>  
 <span data-ttu-id="d378c-116">Für explizite Hierarchienamen können Sie **Name** oder **Code**verwenden.</span><span class="sxs-lookup"><span data-stu-id="d378c-116">For explicit hierarchy names, you cannot use **Name** or **Code**.</span></span>  
  
##  <a name="attributes"></a><a name="attributes"></a><span data-ttu-id="d378c-117">Legt</span><span class="sxs-lookup"><span data-stu-id="d378c-117">Attributes</span></span>  
  
-   <span data-ttu-id="d378c-118">**ID**</span><span class="sxs-lookup"><span data-stu-id="d378c-118">**ID**</span></span>  
  
-   <span data-ttu-id="d378c-119">**Code**</span><span class="sxs-lookup"><span data-stu-id="d378c-119">**Code**</span></span>  
  
-   <span data-ttu-id="d378c-120">**Name**</span><span class="sxs-lookup"><span data-stu-id="d378c-120">**Name**</span></span>  
  
-   <span data-ttu-id="d378c-121">**EnterDTM**</span><span class="sxs-lookup"><span data-stu-id="d378c-121">**EnterDTM**</span></span>  
  
-   <span data-ttu-id="d378c-122">**EnterUserID**</span><span class="sxs-lookup"><span data-stu-id="d378c-122">**EnterUserID**</span></span>  
  
-   <span data-ttu-id="d378c-123">**EnterUserName**</span><span class="sxs-lookup"><span data-stu-id="d378c-123">**EnterUserName**</span></span>  
  
-   <span data-ttu-id="d378c-124">**LastChgDTM**</span><span class="sxs-lookup"><span data-stu-id="d378c-124">**LastChgDTM**</span></span>  
  
-   <span data-ttu-id="d378c-125">**LastChgUserID**</span><span class="sxs-lookup"><span data-stu-id="d378c-125">**LastChgUserID**</span></span>  
  
-   <span data-ttu-id="d378c-126">**Status_ID**</span><span class="sxs-lookup"><span data-stu-id="d378c-126">**Status_ID**</span></span>  
  
-   <span data-ttu-id="d378c-127">**ValidationStatus_ID**</span><span class="sxs-lookup"><span data-stu-id="d378c-127">**ValidationStatus_ID**</span></span>  
  
-   <span data-ttu-id="d378c-128">**Version_ID**</span><span class="sxs-lookup"><span data-stu-id="d378c-128">**Version_ID**</span></span>  
  
##  <a name="members"></a><a name="members"></a><span data-ttu-id="d378c-129">Parlamentariern</span><span class="sxs-lookup"><span data-stu-id="d378c-129">Members</span></span>  
 <span data-ttu-id="d378c-130">Für Member können Sie **mdmmembership Status** oder **root** nicht für den **Code** Attribut Wert verwenden.</span><span class="sxs-lookup"><span data-stu-id="d378c-130">For members, you cannot use **MDMMemberStatus** or **ROOT** for the **Code** attribute value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d378c-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d378c-131">See Also</span></span>  
 [<span data-ttu-id="d378c-132">Übersicht über Master Data Services</span><span class="sxs-lookup"><span data-stu-id="d378c-132">Master Data Services Overview</span></span>](master-data-services-overview-mds.md)  
  
  
