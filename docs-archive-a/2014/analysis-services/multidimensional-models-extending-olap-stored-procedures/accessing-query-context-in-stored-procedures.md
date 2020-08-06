---
title: Zugreifen auf den Abfrage Kontext in gespeicherten Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- execution context [Analysis Services]
- stored procedures [Analysis Services], query context
- Context object
- query context [Analysis Services]
ms.assetid: bdc7dad8-2f22-4265-aba4-a3a451527840
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9da8ddb223ed03c0208fe524ea5cd7195a039c97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694797"
---
# <a name="accessing-query-context-in-stored-procedures"></a><span data-ttu-id="df34e-102">Zugreifen auf den Abfragekontext in gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="df34e-102">Accessing Query Context in Stored Procedures</span></span>
  <span data-ttu-id="df34e-103">Der Ausführungskontext einer gespeicherten Prozedur steht innerhalb des Codes der gespeicherten Prozedur als `Context`-Objekt des ADOMD.NET-Serverobjektmodells zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="df34e-103">The execution context of a stored procedure is available within the code of the stored procedure as the `Context` object of the ADOMD.NET server object model.</span></span> <span data-ttu-id="df34e-104">Der Kontext ist schreibgeschützt und kann nicht von der gespeicherten Prozedur geändert werden.</span><span class="sxs-lookup"><span data-stu-id="df34e-104">This is a read-only context and cannot be modified by the stored procedure.</span></span> <span data-ttu-id="df34e-105">Für dieses Objekt stehen die folgenden Eigenschaften zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="df34e-105">The following properties are available on this object.</span></span>  
  
|<span data-ttu-id="df34e-106">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="df34e-106">Property</span></span>|<span data-ttu-id="df34e-107">type</span><span class="sxs-lookup"><span data-stu-id="df34e-107">Type</span></span>|<span data-ttu-id="df34e-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="df34e-108">Description</span></span>|  
|--------------|----------|-----------------|  
|<span data-ttu-id="df34e-109">**CurrentCube**</span><span class="sxs-lookup"><span data-stu-id="df34e-109">**CurrentCube**</span></span>|<span data-ttu-id="df34e-110">Cube</span><span class="sxs-lookup"><span data-stu-id="df34e-110">Cube</span></span>|<span data-ttu-id="df34e-111">Der Cube für den aktuellen Abfragekontext.</span><span class="sxs-lookup"><span data-stu-id="df34e-111">The cube for the current query context.</span></span>|  
|<span data-ttu-id="df34e-112">**CurrentDatabaseName**</span><span class="sxs-lookup"><span data-stu-id="df34e-112">**CurrentDatabaseName**</span></span>|<span data-ttu-id="df34e-113">String</span><span class="sxs-lookup"><span data-stu-id="df34e-113">String</span></span>|<span data-ttu-id="df34e-114">Der Bezeichner der aktuellen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="df34e-114">The identifier of the current database.</span></span>|  
|<span data-ttu-id="df34e-115">**CurrentConnection**</span><span class="sxs-lookup"><span data-stu-id="df34e-115">**CurrentConnection**</span></span>|<span data-ttu-id="df34e-116">Verbindung</span><span class="sxs-lookup"><span data-stu-id="df34e-116">Connection</span></span>|<span data-ttu-id="df34e-117">Ein Verweis auf das Verbindungsobjekt im aktuellen Kontext.</span><span class="sxs-lookup"><span data-stu-id="df34e-117">A reference to the connection object in the current context.</span></span>|  
|<span data-ttu-id="df34e-118">**Erfolgreich**</span><span class="sxs-lookup"><span data-stu-id="df34e-118">**Pass**</span></span>|<span data-ttu-id="df34e-119">Integer</span><span class="sxs-lookup"><span data-stu-id="df34e-119">Integer</span></span>|<span data-ttu-id="df34e-120">Die Durchlaufnummer für den aktuellen Kontext.</span><span class="sxs-lookup"><span data-stu-id="df34e-120">The pass number for the current context.</span></span>|  
  
 <span data-ttu-id="df34e-121">Das `Context`-Objekt ist vorhanden, wenn das MDX-Objektmodell (Multidimensional Expressions) in einer gespeicherten Prozedur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="df34e-121">The `Context` object exists when the Multidimensional Expressions (MDX) object model is used in a stored procedure.</span></span> <span data-ttu-id="df34e-122">Es ist nicht verfügbar, wenn das MDX-Objektmodell auf einem Client verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="df34e-122">It is not available when the MDX object model is used on a client.</span></span> <span data-ttu-id="df34e-123">Das `Context`-Objekt wird nicht explizit an die gespeicherte Prozedur übergeben bzw. von ihr zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="df34e-123">The `Context` object is not explicitly passed to or returned by the stored procedure.</span></span> <span data-ttu-id="df34e-124">Es ist während der Ausführung der gespeicherten Prozedur verfügbar.</span><span class="sxs-lookup"><span data-stu-id="df34e-124">It is available during the execution of the stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df34e-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="df34e-125">See Also</span></span>  
 <span data-ttu-id="df34e-126">[Verwaltung von mehrdimensionalen Modellen](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="df34e-126">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="df34e-127">Definieren von gespeicherten Proze</span><span class="sxs-lookup"><span data-stu-id="df34e-127">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
