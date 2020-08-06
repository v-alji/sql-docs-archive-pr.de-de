---
title: Ziel-Editor für SQL (Seite erweitert) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlserverdestadapter.advanced.f1
helpviewer_keywords:
- SQL Server Destination Editor
ms.assetid: 9b46bcf8-ddaf-4d7d-90a6-80bc19517e9b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ccf25ad888c93f694678a152417affe5c0e16091
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609953"
---
# <a name="sql-destination-editor-advanced-page"></a><span data-ttu-id="a5d77-102">Ziel-Editor für SQL (Seite Erweitert)</span><span class="sxs-lookup"><span data-stu-id="a5d77-102">SQL Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="a5d77-103">Auf der Seite **Erweitert** des Dialogfelds **Ziel-Editor für SQL** können Sie Optionen für die erweiterte Masseneinfügung angeben.</span><span class="sxs-lookup"><span data-stu-id="a5d77-103">Use the **Advanced** page of the **SQL Destination Editor** dialog box to specify advanced bulk insert options.</span></span>  
  
 <span data-ttu-id="a5d77-104">Weitere Informationen zum SQL Server-Ziel finden Sie unter [SQL Server Destination](data-flow/sql-server-destination.md).</span><span class="sxs-lookup"><span data-stu-id="a5d77-104">To learn more about the SQL Server destination, see [SQL Server Destination](data-flow/sql-server-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a5d77-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="a5d77-105">Options</span></span>  
 <span data-ttu-id="a5d77-106">**Identität beibehalten**</span><span class="sxs-lookup"><span data-stu-id="a5d77-106">**Keep identity**</span></span>  
 <span data-ttu-id="a5d77-107">Gibt an, ob der Task Werte in Identitätsspalten einfügen soll.</span><span class="sxs-lookup"><span data-stu-id="a5d77-107">Specify whether the task should insert values into identity columns.</span></span> <span data-ttu-id="a5d77-108">Der Standardwert dieser Eigenschaft ist `False`.</span><span class="sxs-lookup"><span data-stu-id="a5d77-108">The default value of this property is `False`.</span></span>  
  
 <span data-ttu-id="a5d77-109">**NULL-Werte beibehalten**</span><span class="sxs-lookup"><span data-stu-id="a5d77-109">**Keep nulls**</span></span>  
 <span data-ttu-id="a5d77-110">Gibt an, ob der Task NULL-Werte beibehalten soll.</span><span class="sxs-lookup"><span data-stu-id="a5d77-110">Specify whether the task should keep null values.</span></span> <span data-ttu-id="a5d77-111">Der Standardwert dieser Eigenschaft ist `False`.</span><span class="sxs-lookup"><span data-stu-id="a5d77-111">The default value of this property is `False`.</span></span>  
  
 <span data-ttu-id="a5d77-112">**Tabellensperre**</span><span class="sxs-lookup"><span data-stu-id="a5d77-112">**Table lock**</span></span>  
 <span data-ttu-id="a5d77-113">Gibt an, ob die Tabelle beim Laden der Daten gesperrt wird.</span><span class="sxs-lookup"><span data-stu-id="a5d77-113">Specify whether the table is locked when the data is loaded.</span></span> <span data-ttu-id="a5d77-114">Der Standardwert dieser Eigenschaft ist `True`.</span><span class="sxs-lookup"><span data-stu-id="a5d77-114">The default value of this property is `True`.</span></span>  
  
 <span data-ttu-id="a5d77-115">**Check-Einschränkungen**</span><span class="sxs-lookup"><span data-stu-id="a5d77-115">**Check constraints**</span></span>  
 <span data-ttu-id="a5d77-116">Gibt an, ob Einschränkungen vom Task überprüft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a5d77-116">Specify whether the task should check constraints.</span></span> <span data-ttu-id="a5d77-117">Der Standardwert dieser Eigenschaft ist `True`.</span><span class="sxs-lookup"><span data-stu-id="a5d77-117">The default value of this property is `True`.</span></span>  
  
 <span data-ttu-id="a5d77-118">**Trigger auslösen**</span><span class="sxs-lookup"><span data-stu-id="a5d77-118">**Fire triggers**</span></span>  
 <span data-ttu-id="a5d77-119">Gibt an, ob die Masseneinfügung Trigger in Tabellen auslösen soll.</span><span class="sxs-lookup"><span data-stu-id="a5d77-119">Specify whether the bulk insert should fire triggers on tables.</span></span> <span data-ttu-id="a5d77-120">Der Standardwert dieser Eigenschaft ist `False`.</span><span class="sxs-lookup"><span data-stu-id="a5d77-120">The default value of this property is `False`.</span></span>  
  
 <span data-ttu-id="a5d77-121">**Erste Zeile**</span><span class="sxs-lookup"><span data-stu-id="a5d77-121">**First Row**</span></span>  
 <span data-ttu-id="a5d77-122">Gibt die erste einzufügende Zeile an.</span><span class="sxs-lookup"><span data-stu-id="a5d77-122">Specify the first row to insert.</span></span> <span data-ttu-id="a5d77-123">Der Standardwert dieser Eigenschaft ist **-1**und gibt an, dass kein Wert zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="a5d77-123">The default value of this property is **-1**, indicating that no value has been assigned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5d77-124">Löschen Sie den Inhalt des Textfelds im Dialogfeld **Ziel-Editor für SQL** , um anzugeben, dass Sie keinen Wert für diese Eigenschaft zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="a5d77-124">Clear the text box in the **SQL Destination Editor** to indicate that you do not want to assign a value for this property.</span></span> <span data-ttu-id="a5d77-125">Verwenden Sie im Fenster **Eigenschaften** , im Dialogfeld **Erweiterter Editor**und im Objektmodell den Wert -1.</span><span class="sxs-lookup"><span data-stu-id="a5d77-125">Use -1 in the **Properties** window, the **Advanced Editor**, and the object model.</span></span>  
  
 <span data-ttu-id="a5d77-126">**Letzte Zeile**</span><span class="sxs-lookup"><span data-stu-id="a5d77-126">**Last Row**</span></span>  
 <span data-ttu-id="a5d77-127">Gibt die letzte einzufügende Zeile an.</span><span class="sxs-lookup"><span data-stu-id="a5d77-127">Specify the last row to insert.</span></span> <span data-ttu-id="a5d77-128">Der Standardwert dieser Eigenschaft ist **-1**und gibt an, dass kein Wert zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="a5d77-128">The default value of this property is **-1**, indicating that no value has been assigned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5d77-129">Löschen Sie den Inhalt des Textfelds im Dialogfeld **Ziel-Editor für SQL** , um anzugeben, dass Sie keinen Wert für diese Eigenschaft zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="a5d77-129">Clear the text box in the **SQL Destination Editor** to indicate that you do not want to assign a value for this property.</span></span> <span data-ttu-id="a5d77-130">Verwenden Sie im Fenster **Eigenschaften** , im Dialogfeld **Erweiterter Editor**und im Objektmodell den Wert -1.</span><span class="sxs-lookup"><span data-stu-id="a5d77-130">Use -1 in the **Properties** window, the **Advanced Editor**, and the object model.</span></span>  
  
 <span data-ttu-id="a5d77-131">**Maximale Anzahl von Fehlern**</span><span class="sxs-lookup"><span data-stu-id="a5d77-131">**Maximum number of errors**</span></span>  
 <span data-ttu-id="a5d77-132">Gibt die Anzahl der Fehler an, die auftreten können, bevor die Masseneinfügung abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="a5d77-132">Specify the number of errors that can occur before the bulk insert stops.</span></span> <span data-ttu-id="a5d77-133">Der Standardwert dieser Eigenschaft ist **-1**und gibt an, dass kein Wert zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="a5d77-133">The default value of this property is **-1**, indicating that no value has been assigned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5d77-134">Löschen Sie den Inhalt des Textfelds im Dialogfeld **Ziel-Editor für SQL** , um anzugeben, dass Sie keinen Wert für diese Eigenschaft zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="a5d77-134">Clear the text box in the **SQL Destination Editor** to indicate that you do not want to assign a value for this property.</span></span> <span data-ttu-id="a5d77-135">Verwenden Sie im Fenster **Eigenschaften** , im Dialogfeld **Erweiterter Editor**und im Objektmodell den Wert -1.</span><span class="sxs-lookup"><span data-stu-id="a5d77-135">Use -1 in the **Properties** window, the **Advanced Editor**, and the object model.</span></span>  
  
 <span data-ttu-id="a5d77-136">**Timeout**</span><span class="sxs-lookup"><span data-stu-id="a5d77-136">**Timeout**</span></span>  
 <span data-ttu-id="a5d77-137">Gibt die Anzahl der Sekunden an, die abgewartet werden, bevor die Masseneinfügung aufgrund eines Timeouts abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="a5d77-137">Specify the number of seconds to wait before the bulk insert stops because of a time-out.</span></span>  
  
 <span data-ttu-id="a5d77-138">**Spalten sortieren**</span><span class="sxs-lookup"><span data-stu-id="a5d77-138">**Order columns**</span></span>  
 <span data-ttu-id="a5d77-139">Geben Sie die Namen der zu sortierenden Spalten an.</span><span class="sxs-lookup"><span data-stu-id="a5d77-139">Type the names of the sort columns.</span></span> <span data-ttu-id="a5d77-140">Jede Spalte kann in auf- oder absteigender Reihenfolge sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="a5d77-140">Each column can be sorted in ascending or descending order.</span></span> <span data-ttu-id="a5d77-141">Wenn Sie mehrere Spalten verwenden, nach denen sortiert werden soll, trennen Sie die Namen in der Liste mit Kommas.</span><span class="sxs-lookup"><span data-stu-id="a5d77-141">If you use multiple sort columns, delimit the list with commas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5d77-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a5d77-142">See Also</span></span>  
 <span data-ttu-id="a5d77-143">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a5d77-143">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a5d77-144">[Der Ziel-Editor für SQL &#40;Seite Verbindungs-Manager&#41;](../../2014/integration-services/sql-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="a5d77-144">[SQL Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/sql-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="a5d77-145">[Ziel-Editor für SQL &#40;Seite "Zuordnungen"&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="a5d77-145">[SQL Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="a5d77-146">Massenladen von Daten mithilfe des SQL Server-Ziels</span><span class="sxs-lookup"><span data-stu-id="a5d77-146">Bulk Load Data by Using the SQL Server Destination</span></span>](data-flow/bulk-load-data-by-using-the-sql-server-destination.md)  
  
  
