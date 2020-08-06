---
title: Quellen-Editor für odata (Seite ' Verbindung ') | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- Sql12.dts.designer.odatasource.connection.f1
ms.assetid: 20bcd347-4547-4fad-b182-9571030101df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6ecd0d060ea2197ae7174325b654645fefa23505
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619201"
---
# <a name="odata-source-editor-connection-page"></a><span data-ttu-id="4b778-102">Quellen-Editor für OData (Seite 'Verbindung')</span><span class="sxs-lookup"><span data-stu-id="4b778-102">OData Source Editor (Connection Page)</span></span>
  <span data-ttu-id="4b778-103">Auf der Seite **Verbindung** des Dialogfelds **Quellen-Editor für OData** wählen Sie den OData-Verbindungs-Manager für die OData-Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="4b778-103">Use the **Connection** page of the **OData Source Editor** dialog box to select the OData connection manager for the OData source.</span></span> <span data-ttu-id="4b778-104">Auf dieser Seite können Sie außerdem eine Auflistung oder einen Ressourcenpfad sowie beliebige Abfrageoptionen angeben, mit denen die aus der OData-Quelle abzurufenden Daten bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="4b778-104">This page also lets you specify a collection or a resource path and any query options to indicate what data needs to be retrieved from the OData source.</span></span> <span data-ttu-id="4b778-105">Weitere Informationen zur OData-Quelle finden Sie unter [OData Source](data-flow/odata-source.md).</span><span class="sxs-lookup"><span data-stu-id="4b778-105">To learn more about the OData source, see [OData Source](data-flow/odata-source.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="4b778-106">Statische Optionen</span><span class="sxs-lookup"><span data-stu-id="4b778-106">Static Options</span></span>  
 <span data-ttu-id="4b778-107">**Odata-Verbindungs-Manager**</span><span class="sxs-lookup"><span data-stu-id="4b778-107">**OData connection manager**</span></span>  
 <span data-ttu-id="4b778-108">Wählen Sie in der Liste einen vorhandenen Verbindungs-Manager aus, oder erstellen Sie eine neue Verbindung, indem Sie auf **Neu**klicken.</span><span class="sxs-lookup"><span data-stu-id="4b778-108">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="4b778-109">**Neu**</span><span class="sxs-lookup"><span data-stu-id="4b778-109">**New**</span></span>  
 <span data-ttu-id="4b778-110">Erstellen Sie mithilfe des Dialogfelds **OData-Verbindungs-Manager-Editor** einen neuen Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="4b778-110">Create a new connection manager by using the **OData Connection Manager Editor** dialog box.</span></span>  
  
 <span data-ttu-id="4b778-111">**Auflistung oder Ressourcenpfad verwenden**</span><span class="sxs-lookup"><span data-stu-id="4b778-111">**Use collection or resource path**</span></span>  
 <span data-ttu-id="4b778-112">Geben Sie die Methode für die Auswahl von Daten aus der Quelle an.</span><span class="sxs-lookup"><span data-stu-id="4b778-112">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="4b778-113">Option</span><span class="sxs-lookup"><span data-stu-id="4b778-113">Option</span></span>|<span data-ttu-id="4b778-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4b778-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="4b778-115">Sammlung</span><span class="sxs-lookup"><span data-stu-id="4b778-115">Collection</span></span>|<span data-ttu-id="4b778-116">Rufen Sie mithilfe eines Auflistungsnamens Daten aus der OData-Quelle ab.</span><span class="sxs-lookup"><span data-stu-id="4b778-116">Retrieve data from the OData source by using a collection name.</span></span>|  
|<span data-ttu-id="4b778-117">Ressourcenpfad</span><span class="sxs-lookup"><span data-stu-id="4b778-117">Resource Path</span></span>|<span data-ttu-id="4b778-118">Rufen Sie mithilfe eines Ressourcenpfads Daten aus der OData-Quelle ab.</span><span class="sxs-lookup"><span data-stu-id="4b778-118">Retrieve data from the OData source by using a resource path.</span></span>|  
  
 <span data-ttu-id="4b778-119">**Abfrage Optionen**</span><span class="sxs-lookup"><span data-stu-id="4b778-119">**Query options**</span></span>  
 <span data-ttu-id="4b778-120">Geben Sie Optionen für die Abfrage an.</span><span class="sxs-lookup"><span data-stu-id="4b778-120">Specify options for the query.</span></span>  <span data-ttu-id="4b778-121">Beispiel: $top=5</span><span class="sxs-lookup"><span data-stu-id="4b778-121">For example: $top=5</span></span>  
  
 <span data-ttu-id="4b778-122">**Feed-URL**</span><span class="sxs-lookup"><span data-stu-id="4b778-122">**Feed url**</span></span>  
 <span data-ttu-id="4b778-123">Zeigt die schreibgeschützte Feed-URL auf Grundlage der Optionen an, die Sie in diesem Dialogfeld ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="4b778-123">Displays the read-only Feed URL based on options you selected on this dialog box.</span></span>  
  
 <span data-ttu-id="4b778-124">**Vorschau**</span><span class="sxs-lookup"><span data-stu-id="4b778-124">**Preview**</span></span>  
 <span data-ttu-id="4b778-125">Zeigt mithilfe des Dialogfelds **Vorschau** eine Vorschau der Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="4b778-125">Preview results by using the **Preview** dialog box.</span></span> <span data-ttu-id="4b778-126">In der**Vorschau** können bis zu 20 Zeilen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4b778-126">**Preview** can display up to 20 rows.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="4b778-127">Dynamische Optionen</span><span class="sxs-lookup"><span data-stu-id="4b778-127">Dynamic Options</span></span>  
  
### <a name="use-collection-or-resource-path--collection"></a><span data-ttu-id="4b778-128">Auflistung oder Ressourcenpfad verwenden = Auflistung</span><span class="sxs-lookup"><span data-stu-id="4b778-128">Use collection or resource path = Collection</span></span>  
 <span data-ttu-id="4b778-129">**Sammlung**</span><span class="sxs-lookup"><span data-stu-id="4b778-129">**Collection**</span></span>  
 <span data-ttu-id="4b778-130">Wählen Sie eine Auflistung aus dem Dropdownlistenfeld aus.</span><span class="sxs-lookup"><span data-stu-id="4b778-130">Select a collection from the drop-down list.</span></span>  
  
### <a name="use-collection-or-resource-path--resource-path"></a><span data-ttu-id="4b778-131">Auflistung oder Ressourcenpfad verwenden = Ressourcenpfad</span><span class="sxs-lookup"><span data-stu-id="4b778-131">Use collection or resource path = Resource Path</span></span>  
 <span data-ttu-id="4b778-132">**Ressourcen Pfad**</span><span class="sxs-lookup"><span data-stu-id="4b778-132">**Resource path**</span></span>  
 <span data-ttu-id="4b778-133">Geben Sie einen Ressourcenpfad ein.</span><span class="sxs-lookup"><span data-stu-id="4b778-133">Type a resource path.</span></span> <span data-ttu-id="4b778-134">Beispiel: Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="4b778-134">For example: Employees</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b778-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4b778-135">See Also</span></span>  
 <span data-ttu-id="4b778-136">[Der Quellen-Editor für odata &#40;Spalten Seite&#41;](../../2014/integration-services/odata-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="4b778-136">[OData Source Editor &#40;Columns Page&#41;](../../2014/integration-services/odata-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="4b778-137">[Quellen-Editor für odata &#40;Seite "Fehlerausgabe"&#41;](../../2014/integration-services/odata-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="4b778-137">[OData Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/odata-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="4b778-138">OData-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="4b778-138">OData Connection Manager</span></span>](connection-manager/odata-connection-manager.md)  
  
  
