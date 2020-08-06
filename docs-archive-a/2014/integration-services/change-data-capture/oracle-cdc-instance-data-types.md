---
title: Datentypen von Oracle CDC-Instanzen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: eec13d8d-c15a-4542-bfc4-da66b1a6bfe0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 71d4ce02db89c1bfd11fe9a3a3535fc92fbc49fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695954"
---
# <a name="oracle-cdc-instance-data-types"></a><span data-ttu-id="1800d-102">Datentypen von Oracle CDC-Instanzen</span><span class="sxs-lookup"><span data-stu-id="1800d-102">Oracle CDC Instance Data Types</span></span>
  <span data-ttu-id="1800d-103">Die Oracle CDC-Instanz unterstützt die meisten Oracle-Datentypen.</span><span class="sxs-lookup"><span data-stu-id="1800d-103">The Oracle CDC Instance supports most Oracle data types.</span></span> <span data-ttu-id="1800d-104">In den folgenden Abschnitten werden die unterstützten Datentypen und die nicht unterstützten Datentypen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1800d-104">The following sections describe the supported data types and the non-supported data types.</span></span>  
  
## <a name="supported-data-types"></a><span data-ttu-id="1800d-105">Unterstützte Datentypen</span><span class="sxs-lookup"><span data-stu-id="1800d-105">Supported Data Types</span></span>  
 <span data-ttu-id="1800d-106">In der folgenden Tabelle werden die Oracle-Datentypen, die aufgezeichnet werden können, sowie ihre Standardzuordnung zu SQL Server-Datentypen in den Änderungstabellen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1800d-106">The following table describes the Oracle data types that can be captured and their default mapping to SQL Server data types in the change tables.</span></span> <span data-ttu-id="1800d-107">Beim Hinzufügen einer Aufzeichnungsinstanz für eine Oracle-Quelltabelle können Sie einige dieser Zuordnungen überschreiben.</span><span class="sxs-lookup"><span data-stu-id="1800d-107">When adding a capture instance for a source Oracle table, you can override some of these mappings.</span></span>  
  
|<span data-ttu-id="1800d-108">Datentyp der Oracle-Datenbank</span><span class="sxs-lookup"><span data-stu-id="1800d-108">Oracle Database Data Type</span></span>|<span data-ttu-id="1800d-109">SQL Server-Datentyp</span><span class="sxs-lookup"><span data-stu-id="1800d-109">SQL Server Data Type</span></span>|  
|-------------------------------|--------------------------|  
|<span data-ttu-id="1800d-110">BINARY_FLOAT</span><span class="sxs-lookup"><span data-stu-id="1800d-110">BINARY_FLOAT</span></span>|<span data-ttu-id="1800d-111">real</span><span class="sxs-lookup"><span data-stu-id="1800d-111">REAL</span></span>|  
|<span data-ttu-id="1800d-112">BINARY_DOUBLE</span><span class="sxs-lookup"><span data-stu-id="1800d-112">BINARY_DOUBLE</span></span>|<span data-ttu-id="1800d-113">GLEITKOMMAZAHL</span><span class="sxs-lookup"><span data-stu-id="1800d-113">FLOAT</span></span>|  
|<span data-ttu-id="1800d-114">CHAR</span><span class="sxs-lookup"><span data-stu-id="1800d-114">CHAR</span></span>|<span data-ttu-id="1800d-115">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="1800d-115">NVARCHAR</span></span>|  
|<span data-ttu-id="1800d-116">DATE</span><span class="sxs-lookup"><span data-stu-id="1800d-116">DATE</span></span>|<span data-ttu-id="1800d-117">DATETIME</span><span class="sxs-lookup"><span data-stu-id="1800d-117">DATETIME</span></span>|  
|<span data-ttu-id="1800d-118">GLEITKOMMAZAHL</span><span class="sxs-lookup"><span data-stu-id="1800d-118">FLOAT</span></span>|<span data-ttu-id="1800d-119">GLEITKOMMAZAHL</span><span class="sxs-lookup"><span data-stu-id="1800d-119">FLOAT</span></span>|  
|<span data-ttu-id="1800d-120">INT</span><span class="sxs-lookup"><span data-stu-id="1800d-120">INT</span></span>|<span data-ttu-id="1800d-121">NUMERIC (38)</span><span class="sxs-lookup"><span data-stu-id="1800d-121">NUMERIC (38)</span></span>|  
|<span data-ttu-id="1800d-122">INTERVAL</span><span class="sxs-lookup"><span data-stu-id="1800d-122">INTERVAL</span></span>|<span data-ttu-id="1800d-123">DATETIME</span><span class="sxs-lookup"><span data-stu-id="1800d-123">DATETIME</span></span>|  
|<span data-ttu-id="1800d-124">NCHAR</span><span class="sxs-lookup"><span data-stu-id="1800d-124">NCHAR</span></span>|<span data-ttu-id="1800d-125">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="1800d-125">NVARCHAR</span></span>|  
|<span data-ttu-id="1800d-126">NUMBER</span><span class="sxs-lookup"><span data-stu-id="1800d-126">NUMBER</span></span>|<span data-ttu-id="1800d-127">GLEITKOMMAZAHL</span><span class="sxs-lookup"><span data-stu-id="1800d-127">FLOAT</span></span>|  
|<span data-ttu-id="1800d-128">NAVARCHAR2</span><span class="sxs-lookup"><span data-stu-id="1800d-128">NAVARCHAR2</span></span>|<span data-ttu-id="1800d-129">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="1800d-129">NVARCHAR</span></span>|  
|<span data-ttu-id="1800d-130">RAW</span><span class="sxs-lookup"><span data-stu-id="1800d-130">RAW</span></span>|<span data-ttu-id="1800d-131">VARBINARY</span><span class="sxs-lookup"><span data-stu-id="1800d-131">VARBINARY</span></span>|  
|<span data-ttu-id="1800d-132">real</span><span class="sxs-lookup"><span data-stu-id="1800d-132">REAL</span></span>|<span data-ttu-id="1800d-133">GLEITKOMMAZAHL</span><span class="sxs-lookup"><span data-stu-id="1800d-133">FLOAT</span></span>|  
|<span data-ttu-id="1800d-134">timestamp</span><span class="sxs-lookup"><span data-stu-id="1800d-134">TIMESTAMP</span></span>|<span data-ttu-id="1800d-135">DATETIME2</span><span class="sxs-lookup"><span data-stu-id="1800d-135">DATETIME2</span></span>|  
|<span data-ttu-id="1800d-136">TIMESTAMP WITH TIME ZONE</span><span class="sxs-lookup"><span data-stu-id="1800d-136">TIMESTAMP WITH TIME ZONE</span></span>|<span data-ttu-id="1800d-137">VARCHAR (37)</span><span class="sxs-lookup"><span data-stu-id="1800d-137">VARCHAR (37)</span></span>|  
|<span data-ttu-id="1800d-138">TIMESTAMP WITH LOCAL TIME ZONE</span><span class="sxs-lookup"><span data-stu-id="1800d-138">TIMESTAMP WITH LOCAL TIME ZONE</span></span>|<span data-ttu-id="1800d-139">VARCHAR (37)</span><span class="sxs-lookup"><span data-stu-id="1800d-139">VARCHAR (37)</span></span>|  
|<span data-ttu-id="1800d-140">VARCHAR2</span><span class="sxs-lookup"><span data-stu-id="1800d-140">VARCHAR2</span></span>|<span data-ttu-id="1800d-141">VARCHAR</span><span class="sxs-lookup"><span data-stu-id="1800d-141">VARCHAR</span></span>|  
|<span data-ttu-id="1800d-142">XMLTYPE</span><span class="sxs-lookup"><span data-stu-id="1800d-142">XMLTYPE</span></span>|<span data-ttu-id="1800d-143">NVARCHAR (MAX)</span><span class="sxs-lookup"><span data-stu-id="1800d-143">NVARCHAR (MAX)</span></span>|  
  
## <a name="non-supported-data-types"></a><span data-ttu-id="1800d-144">Nicht unterstützte Datentypen</span><span class="sxs-lookup"><span data-stu-id="1800d-144">Non-Supported Data Types</span></span>  
 <span data-ttu-id="1800d-145">Oracle-Quelltabellen, die Spalten mit den folgenden Oracle-Datentypen enthalten, können nicht aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="1800d-145">Source Oracle tables with columns of the following Oracle data types cannot be captured.</span></span> <span data-ttu-id="1800d-146">Aufgezeichnete Spalten mit diesen Datentypen werden als NULL-Werte angezeigt. Eine Änderung des Werts wird jedoch in der Änderungsmaske der aufgezeichneten Tabellen angegeben.</span><span class="sxs-lookup"><span data-stu-id="1800d-146">Captured columns with these data types will show as null; however, a change in their value is indicated in the change mask of the captured tables.</span></span>  
  
-   <span data-ttu-id="1800d-147">LONG</span><span class="sxs-lookup"><span data-stu-id="1800d-147">LONG</span></span>  
  
-   <span data-ttu-id="1800d-148">XMLTYPE</span><span class="sxs-lookup"><span data-stu-id="1800d-148">XMLTYPE</span></span>  
  
-   <span data-ttu-id="1800d-149">BLOB</span><span class="sxs-lookup"><span data-stu-id="1800d-149">BLOB</span></span>  
  
-   <span data-ttu-id="1800d-150">CLOB</span><span class="sxs-lookup"><span data-stu-id="1800d-150">CLOB</span></span>  
  
 <span data-ttu-id="1800d-151">Oracle-Quelltabellen, die Spalten mit den folgenden Oracle-Datentypen enthalten, können nicht aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="1800d-151">Source Oracle tables with columns of the following Oracle data types cannot be captured.</span></span>  
  
-   <span data-ttu-id="1800d-152">BFILE</span><span class="sxs-lookup"><span data-stu-id="1800d-152">BFILE</span></span>  
  
-   <span data-ttu-id="1800d-153">ROWID</span><span class="sxs-lookup"><span data-stu-id="1800d-153">ROWID</span></span>  
  
-   <span data-ttu-id="1800d-154">REF</span><span class="sxs-lookup"><span data-stu-id="1800d-154">REF</span></span>  
  
-   <span data-ttu-id="1800d-155">UROWID</span><span class="sxs-lookup"><span data-stu-id="1800d-155">UROWID</span></span>  
  
-   <span data-ttu-id="1800d-156">Geschachtelte Tabelle</span><span class="sxs-lookup"><span data-stu-id="1800d-156">Nested Table</span></span>  
  
 <span data-ttu-id="1800d-157">Wenn die folgenden Datentypen in einer Tabelle vorhanden sind, verhindern sie, dass der LogMinder Daten für eine beliebige Spalte der Tabelle abruft:</span><span class="sxs-lookup"><span data-stu-id="1800d-157">If the following data types are present in a table they will prevent the LogMinder from getting any data for any column of the table:</span></span>  
  
-   <span data-ttu-id="1800d-158">Benutzerdefinierte Datentypen</span><span class="sxs-lookup"><span data-stu-id="1800d-158">User-defined data types</span></span>  
  
-   <span data-ttu-id="1800d-159">VARRAY</span><span class="sxs-lookup"><span data-stu-id="1800d-159">VARRAY</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1800d-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1800d-160">See Also</span></span>  
 <span data-ttu-id="1800d-161">[Change Data Capture Designer für Oracle von Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span><span class="sxs-lookup"><span data-stu-id="1800d-161">[Change Data Capture Designer for Oracle by Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span></span>  
 [<span data-ttu-id="1800d-162">Oracle CDC-Instanz</span><span class="sxs-lookup"><span data-stu-id="1800d-162">The Oracle CDC Instance</span></span>](the-oracle-cdc-instance.md)  
  
  
