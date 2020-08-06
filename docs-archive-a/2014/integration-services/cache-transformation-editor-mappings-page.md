---
title: Cache Transformations-Editor (Seite ' Zuordnungen ') | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.cachetransmap.f1
ms.assetid: ffd53f18-9646-458a-a84a-f2467d601ea5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6bb31e479ea98133da34dcbf257d59e70f4ffe8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621151"
---
# <a name="cache-transformation-editor-mappings-page"></a><span data-ttu-id="ff4e1-102">Cachetransformations-Editor (Seite 'Zuordnungen')</span><span class="sxs-lookup"><span data-stu-id="ff4e1-102">Cache Transformation Editor (Mappings Page)</span></span>
  <span data-ttu-id="ff4e1-103">Auf der Seite **Zuordnungen** des **Cachetransformations-Editors** können Sie den Zielspalten im Cacheverbindungs-Manager die Eingabespalten in der Transformation für Cachetransformation zuordnen.</span><span class="sxs-lookup"><span data-stu-id="ff4e1-103">Use the **Mappings** page of the **Cache Transformation Editor** to map the input columns in the Cache Transform transformation to destination columns in the Cache connection manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff4e1-104">Jede Eingabespalte muss einer Zielspalte zugeordnet werden, und die Spaltendatentypen müssen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="ff4e1-104">Each input column must be mapped to a destination column, and the column data types must match.</span></span> <span data-ttu-id="ff4e1-105">Andernfalls zeigt der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Designer eine Fehlermeldung an.</span><span class="sxs-lookup"><span data-stu-id="ff4e1-105">Otherwise, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Designer displays an error message.</span></span>  
  
 <span data-ttu-id="ff4e1-106">Weitere Informationen zur Cachetransformation finden Sie unter [Cache Transform](data-flow/transformations/cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="ff4e1-106">To learn more about the Cache Transform, see [Cache Transform](data-flow/transformations/cache-transform.md).</span></span>  
  
 <span data-ttu-id="ff4e1-107">Weitere Informationen zum Cacheverbindungs-Manager finden Sie unter [Cache Connection Manager](connection-manager/cache-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="ff4e1-107">To learn more about the Cache connection manager, see [Cache Connection Manager](connection-manager/cache-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ff4e1-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ff4e1-108">Options</span></span>  
 <span data-ttu-id="ff4e1-109">**Verfügbare Eingabespalten**</span><span class="sxs-lookup"><span data-stu-id="ff4e1-109">**Available Input Columns**</span></span>  
 <span data-ttu-id="ff4e1-110">Zeigt die Liste der verfügbaren Eingabespalten an.</span><span class="sxs-lookup"><span data-stu-id="ff4e1-110">View the list of available input columns.</span></span> <span data-ttu-id="ff4e1-111">Mithilfe eines Drag-und-Drop-Vorgangs können Sie verfügbare Eingabespalten den Zielspalten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="ff4e1-111">Use a drag-and-drop operation to map available input columns to destination columns.</span></span>  
  
 <span data-ttu-id="ff4e1-112">Sie können auch mithilfe der Tastatur Eingabespalten bestimmten Zielspalten zuordnen. Dazu heben Sie eine Spalte in der Tabelle **Verfügbare Eingabespalten** hervor, drücken die Menütaste und wählen dann **Elemente nach übereinstimmenden Namen zuordnen**aus.</span><span class="sxs-lookup"><span data-stu-id="ff4e1-112">You can also map input columns to destination columns using the keyboard, by highlighting a column in the **Available Input Columns** table, pressing the menu key, and then selecting **Map Items By Matching Names**.</span></span>  
  
 <span data-ttu-id="ff4e1-113">**Verfügbare Zielspalten**</span><span class="sxs-lookup"><span data-stu-id="ff4e1-113">**Available Destination Columns**</span></span>  
 <span data-ttu-id="ff4e1-114">Zeigt die Liste der verfügbaren Zielspalten an.</span><span class="sxs-lookup"><span data-stu-id="ff4e1-114">View the list of available destination columns.</span></span> <span data-ttu-id="ff4e1-115">Mithilfe eines Drag-und-Drop-Vorgangs können Sie verfügbare Zielspalten den Eingabespalten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="ff4e1-115">Use a drag-and-drop operation to map available destination columns to input columns.</span></span>  
  
 <span data-ttu-id="ff4e1-116">Sie können auch mithilfe der Tastatur Eingabespalten bestimmten Zielspalten zuordnen. Dazu heben Sie eine Spalte in der Tabelle **Verfügbare Zielspalten** hervor, drücken die Menütaste und wählen dann **Elemente nach übereinstimmenden Namen zuordnen**aus.</span><span class="sxs-lookup"><span data-stu-id="ff4e1-116">You can also map input columns to destination columns using the keyboard, by highlighting a column in the **Available Destination Columns** table, pressing the menu key, and then selecting **Map Items By Matching Names**.</span></span>  
  
 <span data-ttu-id="ff4e1-117">**Eingabespalte**</span><span class="sxs-lookup"><span data-stu-id="ff4e1-117">**Input Column**</span></span>  
 <span data-ttu-id="ff4e1-118">Zeigt die zu einem früheren Zeitpunkt in diesem Thema ausgewählten Eingabespalten an.</span><span class="sxs-lookup"><span data-stu-id="ff4e1-118">View input columns selected earlier in this topic.</span></span> <span data-ttu-id="ff4e1-119">Die Zuordnungen können Sie mithilfe der Liste **Verfügbare Eingabespalten**ändern.</span><span class="sxs-lookup"><span data-stu-id="ff4e1-119">You can change the mappings by using the list of **Available Input Columns**.</span></span>  
  
 <span data-ttu-id="ff4e1-120">**Zielspalte**</span><span class="sxs-lookup"><span data-stu-id="ff4e1-120">**Destination Column**</span></span>  
 <span data-ttu-id="ff4e1-121">Zeigt jede verfügbare Zielspalte an.</span><span class="sxs-lookup"><span data-stu-id="ff4e1-121">View each available destination column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff4e1-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ff4e1-122">See Also</span></span>  
 [<span data-ttu-id="ff4e1-123">Cachetransformations-Editor &#40;Seite „Verbindungs-Manager“&#41;</span><span class="sxs-lookup"><span data-stu-id="ff4e1-123">Cache Transformation Editor &#40;Connection Manager Page&#41;</span></span>](../../2014/integration-services/cache-transformation-editor-connection-manager-page.md)  
  
  
