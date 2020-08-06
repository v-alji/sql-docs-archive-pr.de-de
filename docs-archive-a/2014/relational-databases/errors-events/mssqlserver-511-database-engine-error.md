---
title: MSSQLSERVER_511 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/19/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 511 (Database Engine error)
ms.assetid: 0c85686a-53c1-4180-ba8c-2000e68a0d63
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5b69d2c043997e2947563de119bc4ee89fdf4e32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698240"
---
# <a name="mssqlserver_511"></a><span data-ttu-id="2a26e-102">MSSQLSERVER_511</span><span class="sxs-lookup"><span data-stu-id="2a26e-102">MSSQLSERVER_511</span></span>
    
## <a name="details"></a><span data-ttu-id="2a26e-103">Details</span><span class="sxs-lookup"><span data-stu-id="2a26e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2a26e-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="2a26e-104">Product Name</span></span>|<span data-ttu-id="2a26e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2a26e-105">SQL Server</span></span>|  
|<span data-ttu-id="2a26e-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2a26e-106">Event ID</span></span>|<span data-ttu-id="2a26e-107">511</span><span class="sxs-lookup"><span data-stu-id="2a26e-107">511</span></span>|  
|<span data-ttu-id="2a26e-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="2a26e-108">Event Source</span></span>|<span data-ttu-id="2a26e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2a26e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2a26e-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="2a26e-110">Component</span></span>|<span data-ttu-id="2a26e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2a26e-111">SQLEngine</span></span>|  
|<span data-ttu-id="2a26e-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="2a26e-112">Symbolic Name</span></span>|<span data-ttu-id="2a26e-113">ROW_TOOBIG</span><span class="sxs-lookup"><span data-stu-id="2a26e-113">ROW_TOOBIG</span></span>|  
|<span data-ttu-id="2a26e-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="2a26e-114">Message Text</span></span>|<span data-ttu-id="2a26e-115">Eine Zeile der Größe %d kann nicht erstellt werden, da sie länger als das zulässige Maximum von %d wäre.</span><span class="sxs-lookup"><span data-stu-id="2a26e-115">Cannot create a row of size %d which is greater than the allowable maximum of %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2a26e-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="2a26e-116">Explanation</span></span>  
 <span data-ttu-id="2a26e-117">Der Vorgang hat die maximale Größe für eine Zeile überschritten.</span><span class="sxs-lookup"><span data-stu-id="2a26e-117">The operation you have tried has exceeded the maximum size of a row.</span></span> <span data-ttu-id="2a26e-118">Die maximale Größe einer Zeile beträgt normalerweise 8060 Bytes.</span><span class="sxs-lookup"><span data-stu-id="2a26e-118">Usually, the maximum size of a row is 8,060 bytes.</span></span> <span data-ttu-id="2a26e-119">Einige Speicherformate verfügen über Overhead, mit dem die für Daten verfügbare Zeilengröße reduziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="2a26e-119">Some storage formats contain overhead that can reduce the row size that is available for data.</span></span> <span data-ttu-id="2a26e-120">Wenn Sie z. B. Sparsespalten verwenden, ist die maximale Größe einer Zeile 8018 Bytes.</span><span class="sxs-lookup"><span data-stu-id="2a26e-120">For example, when you use sparse columns, the maximum size of a row is 8,018 bytes.</span></span> <span data-ttu-id="2a26e-121">Bei einigen Vorgängen zum Hinzufügen und Entfernen von Zeilen sowie bei einigen Vorgängen, mit denen der Datentyp einer Spalte geändert wird, muss die Zeile erneut auf die Datenseite geschrieben werden. Danach wird die ursprüngliche Zeile entfernt.</span><span class="sxs-lookup"><span data-stu-id="2a26e-121">Some operations that add or remove rows and some operations that change the data type of a column require the row to be rewritten on the data page, and then the original row is removed.</span></span> <span data-ttu-id="2a26e-122">Bei diesen Vorgängen liegt die wirksame Grenze für die Größe der Zeile bei der Hälfte der maximalen Grenze.</span><span class="sxs-lookup"><span data-stu-id="2a26e-122">In these operations, the effective limit to the size of the row is half the maximum limit.</span></span> <span data-ttu-id="2a26e-123">Die Ursache hierfür liegt darin, dass sich sowohl die ursprüngliche Zeile als auch die geänderte Zeile kurzfristig gemeinsam auf der Datenseite befinden müssen.</span><span class="sxs-lookup"><span data-stu-id="2a26e-123">This is because the original row and the modified row must both be contained on the data page for a short period.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="2a26e-124">Jede **varchar (max)** -oder **nvarchar (max)** -Spalte, die ungleich NULL ist, erfordert 24 Byte an zusätzlicher fester Zuordnung, die während eines Sortier Vorgangs mit dem Zeilen Limit von 8.060 Byte gezählt wird.</span><span class="sxs-lookup"><span data-stu-id="2a26e-124">Each non-null  **varchar(max)** or **nvarchar(max)** column requires 24 bytes of additional fixed allocation which counts against the 8,060 byte row limit during a sort operation.</span></span> <span data-ttu-id="2a26e-125">Dadurch kann ein implizites Limit für die Anzahl der **varchar (max)** -oder **nvarchar (max)** -Spalten ungleich NULL erstellt werden, die in einer Tabelle erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="2a26e-125">This can create an implicit limit to the number of non-null **varchar(max)** or **nvarchar(max)** columns that can be created in a table.</span></span> <span data-ttu-id="2a26e-126">Beim Erstellen der Tabelle (außerhalb der üblichen Warnung darüber, dass die maximale Zeilengröße das zulässige Maximum von 8.060 Bytes überschreitet) oder zum Zeitpunkt der Dateneinfügung wird kein spezieller Fehler ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="2a26e-126">No special error is provided when the table is created (beyond the usual warning that the maximum row size exceeds the allowed maximum of 8060 bytes) or at the time of data insertion.</span></span> <span data-ttu-id="2a26e-127">Diese große Zeilengröße kann während einiger normaler Vorgänge Fehler (z. B. Fehler 512) verursachen. Dazu gehören z. B. die Aktualisierung des gruppierten Indexschlüssels oder Teile des vollständigen Spaltensatzes. Bis zum Ausführen eines Vorgangs können Benutzer diese Fehler nicht vorhersehen.</span><span class="sxs-lookup"><span data-stu-id="2a26e-127">This large row size can cause errors (such as error 512) during some normal operations, such as a clustered index key update, or sorts of the full column set, which users cannot anticipate until performing an operation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2a26e-128">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="2a26e-128">User Action</span></span>  
 <span data-ttu-id="2a26e-129">Reduzieren Sie, sofern möglich, die Größe der Zeile.</span><span class="sxs-lookup"><span data-stu-id="2a26e-129">If it is possible, reduce the size of the row.</span></span>  
  
 <span data-ttu-id="2a26e-130">Wenn Sie vermuten, dass das Problem aufgrund eines Updates der Zeile entstanden ist, müssen Sie die Tabelle in mehreren Schritten ändern.</span><span class="sxs-lookup"><span data-stu-id="2a26e-130">If you think the problem is caused by an in-place update of the row, you must change the table in multiple steps.</span></span> <span data-ttu-id="2a26e-131">Erstellen Sie eine neue Tabelle, und übertragen Sie die Daten in die neue Tabelle.</span><span class="sxs-lookup"><span data-stu-id="2a26e-131">Create a new table, and transfer the data into the new table.</span></span> <span data-ttu-id="2a26e-132">Löschen Sie dann die ursprüngliche Tabelle, und benennen Sie die neue Tabelle um, oder schneiden Sie die ursprüngliche Tabelle ab, ändern Sie die Zeilen in der ursprünglichen Tabelle, und fügen Sie die Daten dann wieder ein.</span><span class="sxs-lookup"><span data-stu-id="2a26e-132">Then, either delete the original table and rename the new table, or truncate the original table, modify the rows in the original table, and then move the data back into it.</span></span>  
  
  
