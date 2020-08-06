---
title: Benutzerdefinierte Eigenschaften der Rohdatendatei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7e81f7e1-fac0-4b57-b145-8f1b9e4720bf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7614c03fbf44f37597e586549e306d01c28b523d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615468"
---
# <a name="raw-file-custom-properties"></a><span data-ttu-id="021e0-102">Benutzerdefinierte Eigenschaften der Rohdatendatei</span><span class="sxs-lookup"><span data-stu-id="021e0-102">Raw File Custom Properties</span></span>
  <span data-ttu-id="021e0-103">**Benutzerdefinierte Eigenschaften von Quellen**</span><span class="sxs-lookup"><span data-stu-id="021e0-103">**Source Custom Properties**</span></span>  
  
 <span data-ttu-id="021e0-104">Die Rohdatendatei-Quelle verfügt sowohl über benutzerdefinierte Eigenschaften als auch über die Eigenschaften, die allen Datenflusskomponenten gemeinsam sind.</span><span class="sxs-lookup"><span data-stu-id="021e0-104">The Raw File source has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="021e0-105">In der folgenden Tabelle werden die benutzerdefinierten Eigenschaften der Rohdatendatei-Quelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="021e0-105">The following table describes the custom properties of the Raw File source.</span></span> <span data-ttu-id="021e0-106">Alle Eigenschaften weisen Lese-/Schreibzugriff auf.</span><span class="sxs-lookup"><span data-stu-id="021e0-106">All properties are read/write.</span></span>  
  
|<span data-ttu-id="021e0-107">Eigenschaftenname</span><span class="sxs-lookup"><span data-stu-id="021e0-107">Property name</span></span>|<span data-ttu-id="021e0-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="021e0-108">Data Type</span></span>|<span data-ttu-id="021e0-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="021e0-109">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="021e0-110">AccessMode</span><span class="sxs-lookup"><span data-stu-id="021e0-110">AccessMode</span></span>|<span data-ttu-id="021e0-111">Ganze Zahl (Enumeration)</span><span class="sxs-lookup"><span data-stu-id="021e0-111">Integer (enumeration)</span></span>|<span data-ttu-id="021e0-112">Der zum Zugreifen auf die Rohdaten verwendete Modus.</span><span class="sxs-lookup"><span data-stu-id="021e0-112">The mode used to access the raw data.</span></span> <span data-ttu-id="021e0-113">Die möglichen Werte sind `File name` (0) und `File name from variable` (1).</span><span class="sxs-lookup"><span data-stu-id="021e0-113">The possible values are `File name` (0) and `File name from variable` (1).</span></span> <span data-ttu-id="021e0-114">Der Standardwert ist `File name` (0).</span><span class="sxs-lookup"><span data-stu-id="021e0-114">The default value is `File name` (0).</span></span>|  
|<span data-ttu-id="021e0-115">FileName</span><span class="sxs-lookup"><span data-stu-id="021e0-115">FileName</span></span>|<span data-ttu-id="021e0-116">String</span><span class="sxs-lookup"><span data-stu-id="021e0-116">String</span></span>|<span data-ttu-id="021e0-117">Der Pfad und der Dateiname der Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="021e0-117">The path and file name of the source file.</span></span>|  
  
 <span data-ttu-id="021e0-118">Die Ausgabe und die Ausgabespalten der Rohdatendatei-Quelle verfügen nicht über benutzerdefinierte Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="021e0-118">The output and the output columns of the Raw File source have no custom properties.</span></span>  
  
 <span data-ttu-id="021e0-119">Weitere Informationen finden Sie unter [Raw File Source](raw-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="021e0-119">For more information, see [Raw File Source](raw-file-source.md).</span></span>  
  
 <span data-ttu-id="021e0-120">**Benutzerdefinierte Eigenschaften von Zielen**</span><span class="sxs-lookup"><span data-stu-id="021e0-120">**Destination Custom Properties**</span></span>  
  
 <span data-ttu-id="021e0-121">Das Rohdatendatei-Ziel verfügt sowohl über benutzerdefinierte Eigenschaften als auch über die Eigenschaften, die allen Datenflusskomponenten gemeinsam sind.</span><span class="sxs-lookup"><span data-stu-id="021e0-121">The Raw File destination has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="021e0-122">Die folgende Tabelle beschreibt die benutzerdefinierten Eigenschaften des Rohdatendatei-Ziels.</span><span class="sxs-lookup"><span data-stu-id="021e0-122">The following table describes the custom properties of the Raw File destination.</span></span> <span data-ttu-id="021e0-123">Alle Eigenschaften weisen Lese-/Schreibzugriff auf.</span><span class="sxs-lookup"><span data-stu-id="021e0-123">All properties are read/write.</span></span>  
  
|<span data-ttu-id="021e0-124">Eigenschaftenname</span><span class="sxs-lookup"><span data-stu-id="021e0-124">Property name</span></span>|<span data-ttu-id="021e0-125">Datentyp</span><span class="sxs-lookup"><span data-stu-id="021e0-125">Data Type</span></span>|<span data-ttu-id="021e0-126">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="021e0-126">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="021e0-127">AccessMode</span><span class="sxs-lookup"><span data-stu-id="021e0-127">AccessMode</span></span>|<span data-ttu-id="021e0-128">Ganze Zahl (Enumeration)</span><span class="sxs-lookup"><span data-stu-id="021e0-128">Integer (enumeration)</span></span>|<span data-ttu-id="021e0-129">Ein Wert, der angibt, ob die FileName-Eigenschaft einen Dateinamen oder den Namen einer Variablen enthält, die einen Dateinamen enthält.</span><span class="sxs-lookup"><span data-stu-id="021e0-129">A value that specifies whether the FileName property contains a file name, or the name of a variable that contains a file name.</span></span> <span data-ttu-id="021e0-130">Die Optionen sind `File name` (0) und `File name from variable` (1).</span><span class="sxs-lookup"><span data-stu-id="021e0-130">The options are `File name` (0) and `File name from variable` (1).</span></span>|  
|<span data-ttu-id="021e0-131">FileName</span><span class="sxs-lookup"><span data-stu-id="021e0-131">FileName</span></span>|<span data-ttu-id="021e0-132">String</span><span class="sxs-lookup"><span data-stu-id="021e0-132">String</span></span>|<span data-ttu-id="021e0-133">Der Name der Datei, in die das Rohdatendatei-Ziel schreibt.</span><span class="sxs-lookup"><span data-stu-id="021e0-133">The name of the file to which the Raw File destination writes.</span></span>|  
|<span data-ttu-id="021e0-134">WriteOption</span><span class="sxs-lookup"><span data-stu-id="021e0-134">WriteOption</span></span>|<span data-ttu-id="021e0-135">Ganze Zahl (Enumeration)</span><span class="sxs-lookup"><span data-stu-id="021e0-135">Integer (enumeration)</span></span>|<span data-ttu-id="021e0-136">Ein Wert, der angibt, ob das Rohdatendatei-Ziel eine vorhandene Datei mit demselben Namen löscht.</span><span class="sxs-lookup"><span data-stu-id="021e0-136">A value that specifies whether the Raw File destination deletes an existing file that has the same name.</span></span> <span data-ttu-id="021e0-137">Die Optionen sind `Create Always` (0), `Create Once` (1), `Truncate and Append` (3) und `Append` (2).</span><span class="sxs-lookup"><span data-stu-id="021e0-137">The options are `Create Always` (0), `Create Once` (1), `Truncate and Append` (3), and `Append` (2).</span></span> <span data-ttu-id="021e0-138">Der Standardwert dieser Eigenschaft ist `Create Always` (0).</span><span class="sxs-lookup"><span data-stu-id="021e0-138">The default value of this property is `Create Always` (0).</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="021e0-139">Zum Anfügen müssen die Metadaten der angefügten Daten mit den Metadaten der in der Datei vorhandenen Daten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="021e0-139">An append operation requires the metadata of the appended data to match the metadata of the data already present in the file.</span></span>  
  
 <span data-ttu-id="021e0-140">Die Eingabe und die Eingabespalten des Rohdatendatei-Ziels verfügen nicht über benutzerdefinierte Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="021e0-140">The input and the input columns of the Raw File destination have no custom properties.</span></span>  
  
 <span data-ttu-id="021e0-141">Weitere Informationen finden Sie unter [Raw File Destination](raw-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="021e0-141">For more information, see [Raw File Destination](raw-file-destination.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="021e0-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="021e0-142">See Also</span></span>  
 [<span data-ttu-id="021e0-143">Common Properties</span><span class="sxs-lookup"><span data-stu-id="021e0-143">Common Properties</span></span>](../common-properties.md)  
  
  
