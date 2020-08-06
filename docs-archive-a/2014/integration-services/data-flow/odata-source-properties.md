---
title: OData-Quelleneigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4fde5bb0-6d78-4ec4-8f0b-67f91c53fe99
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8139f79ed595ca3e6204f96823f6bc95e6fb40df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724821"
---
# <a name="odata-source-properties"></a><span data-ttu-id="998b4-102">OData-Quelleneigenschaften</span><span class="sxs-lookup"><span data-stu-id="998b4-102">OData Source Properties</span></span>
  <span data-ttu-id="998b4-103">Wenn Sie im Datenfluss mit der rechten Maustaste auf **OData-Quelle** und anschließend auf **Eigenschaften**klicken, werden die Eigenschaften der Komponente **OData-Quelle** im Fenster **Eigenschaften** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="998b4-103">When you right-click **OData Source** in the data flow and click **Properties**, you will see properties for the **OData Source** component in the **Properties** window.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="998b4-104">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="998b4-104">Property</span></span>|<span data-ttu-id="998b4-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="998b4-105">Description</span></span>|  
|<span data-ttu-id="998b4-106">CollectionName</span><span class="sxs-lookup"><span data-stu-id="998b4-106">CollectionName</span></span>|<span data-ttu-id="998b4-107">Der Name der Auflistung, die Sie vom OData-Dienst abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="998b4-107">Name of the collection you wish to retrieve from the OData service.</span></span> <span data-ttu-id="998b4-108">Die Eigenschaft **CollectionName** wird verwendet, wenn **UseResourcePath** FALSE ist.</span><span class="sxs-lookup"><span data-stu-id="998b4-108">The **CollectionName** property is used when **UseResourcePath** is False.</span></span><br /><br /> <span data-ttu-id="998b4-109">Diese Eigenschaft ist ausdrucksfähig, d. h., der Wert kann zur Laufzeit festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="998b4-109">This property is expression-able, allowing the value to be set at runtime.</span></span> <span data-ttu-id="998b4-110">Wenn die Metadaten der Auflistung jedoch nicht mit den Metadaten übereinstimmen, die zur Entwurfszeit verwendet wurden, tritt ein Überprüfungsfehler auf, der zum Abbruch der Datenflussausführung führt.</span><span class="sxs-lookup"><span data-stu-id="998b4-110">However, if the metadata of the collection does not match the metadata that was used at design time, a validation error will occur, causing the data flow execution to fail.</span></span>|  
|<span data-ttu-id="998b4-111">DefaultStringLength</span><span class="sxs-lookup"><span data-stu-id="998b4-111">DefaultStringLength</span></span>|<span data-ttu-id="998b4-112">Dieser Wert gibt die Standardlänge für Zeichenfolgenspalten an, die keine maximale Länge aufweisen.</span><span class="sxs-lookup"><span data-stu-id="998b4-112">This value specifies default length for string columns that have no max length.</span></span><br /><br /> <span data-ttu-id="998b4-113">**Standardwert:** 4000</span><span class="sxs-lookup"><span data-stu-id="998b4-113">**Default:** 4000</span></span>|  
|<span data-ttu-id="998b4-114">Abfrage</span><span class="sxs-lookup"><span data-stu-id="998b4-114">Query</span></span>|<span data-ttu-id="998b4-115">Die OData-Abfrageparameter.</span><span class="sxs-lookup"><span data-stu-id="998b4-115">The OData query parameters.</span></span> <span data-ttu-id="998b4-116">Diese Eigenschaft ist ausdrucksfähig und kann zur Laufzeit festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="998b4-116">This property is expression-able and can be set at runtime.</span></span>|  
|<span data-ttu-id="998b4-117">ResourcePath</span><span class="sxs-lookup"><span data-stu-id="998b4-117">ResourcePath</span></span>|<span data-ttu-id="998b4-118">Verwenden Sie diese Eigenschaft, wenn Sie einen vollständigen Ressourcenpfad angeben müssen, anstatt nur einen Auflistungsnamen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="998b4-118">Use this property when you need to specify a full resource path, rather than just selecting a collection name.</span></span> <span data-ttu-id="998b4-119">Diese Eigenschaft wird verwendet, wenn **UseResourcePath** TRUE ist.</span><span class="sxs-lookup"><span data-stu-id="998b4-119">This property is used when **UseResourcePath** is True.</span></span>|  
|<span data-ttu-id="998b4-120">UseResourcePath</span><span class="sxs-lookup"><span data-stu-id="998b4-120">UseResourcePath</span></span>|<span data-ttu-id="998b4-121">Beim Wert TRUE wird der **ResourcePath** -Wert an die Basis-URL angefügt, um den Speicherort des OData-Feeds zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="998b4-121">When set to True, the **ResourcePath** value is appended to the base URL to determine the OData feed location.</span></span> <span data-ttu-id="998b4-122">Bei FALSE wird der **CollectionName** -Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="998b4-122">When set to False, the **CollectionName** value is used.</span></span><br /><br /> <span data-ttu-id="998b4-123">**Standardwert:** Alarm</span><span class="sxs-lookup"><span data-stu-id="998b4-123">**Default:** False</span></span>|  
  
  
