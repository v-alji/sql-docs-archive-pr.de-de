---
title: Automatisches Generieren von Codeattributwerten (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 19b354ee-2906-4cc7-ba2f-32b4543bddcf
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 6c442f37ffe322985ba55b29b2c4cd539b8a3e05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621047"
---
# <a name="automatically-generate-code-attribute-values-master-data-services"></a><span data-ttu-id="d4f03-102">Automatisches Generieren von Codeattributwerten (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d4f03-102">Automatically Generate Code Attribute Values (Master Data Services)</span></span>
  <span data-ttu-id="d4f03-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] können Sie Werte für das Codeattribut einer Entität automatisch generieren lassen, wenn Sie möchten, dass dem Codewert bei jeder Erstellung eines neuen Elements automatisch eine ganze Zahl zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d4f03-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], automatically generate values for an entity's Code attribute when you want an integer to be automatically assigned to the Code value each time a new member is created.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d4f03-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d4f03-104">Prerequisites</span></span>  
 <span data-ttu-id="d4f03-105">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="d4f03-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="d4f03-106">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="d4f03-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="d4f03-107">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="d4f03-107">You must be a model administrator.</span></span> <span data-ttu-id="d4f03-108">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d4f03-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="d4f03-109">Die Entität muss vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="d4f03-109">The entity must exist.</span></span> <span data-ttu-id="d4f03-110">Weitere Informationen finden Sie unter [Erstellen einer Entität &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d4f03-110">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-automatically-generate-code-values"></a><span data-ttu-id="d4f03-111">So generieren Sie automatisch Codewerte</span><span class="sxs-lookup"><span data-stu-id="d4f03-111">To automatically generate Code values</span></span>  
  
1.  <span data-ttu-id="d4f03-112">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="d4f03-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="d4f03-113">Zeigen Sie auf der Seite **Modell-Explorer** auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Entitäten**.</span><span class="sxs-lookup"><span data-stu-id="d4f03-113">On the **Model Explorer** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="d4f03-114">Wählen Sie auf der Seite **Entitätsverwaltung** aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="d4f03-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="d4f03-115">Wählen Sie die Zeile für die Entität aus, für die Sie Codes generieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d4f03-115">Select the row for the entity that you want to generate codes for.</span></span>  
  
5.  <span data-ttu-id="d4f03-116">Klicken Sie auf **Ausgewählte Entität bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="d4f03-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="d4f03-117">Aktivieren Sie das Kontrollkästchen **Codewerte automatisch erstellen** .</span><span class="sxs-lookup"><span data-stu-id="d4f03-117">Select the **Create Code values automatically** check box.</span></span>  
  
7.  <span data-ttu-id="d4f03-118">Geben Sie im Feld **Start bei** eine Zahl ein, die inkrementiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d4f03-118">In the **Start with** box, type a number to begin incrementing.</span></span> <span data-ttu-id="d4f03-119">Wenn Elemente bereits vorhanden sind, wird der Code auf Grundlage des höchsten vorhandenen Werts festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d4f03-119">If members already exist, the Code will be set based on the highest existing value.</span></span> <span data-ttu-id="d4f03-120">Wenn der höchste vorhandene Codewert z.B. 299 ist, wird der Codewert des nächsten Elements auf 300 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d4f03-120">For example, if the highest existing Code value is 299, the next member's Code value will be set to 300.</span></span>  
  
8.  <span data-ttu-id="d4f03-121">Klicken Sie auf **Entität speichern**.</span><span class="sxs-lookup"><span data-stu-id="d4f03-121">Click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4f03-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d4f03-122">See Also</span></span>  
 <span data-ttu-id="d4f03-123">[Automatische Code Erstellung &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d4f03-123">[Automatic Code Creation &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span></span>  
 [<span data-ttu-id="d4f03-124">Automatisches Generieren von anderen Attributwerten als Code &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d4f03-124">Automatically Generate Attribute Values Other Than Code &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/automatically-generate-attribute-values-other-than-code-master-data-services.md)  
  
  
