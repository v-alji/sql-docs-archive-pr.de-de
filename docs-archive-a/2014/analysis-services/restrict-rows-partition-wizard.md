---
title: Zeilen einschränken (Partitions-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.typefilterexpression.f1
ms.assetid: eec8da8f-eab4-4ac4-a81d-995c814f88ca
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9b0acc9ab24cfe92877d9abcd86353c85b4f8905
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610142"
---
# <a name="restrict-rows-partition-wizard"></a><span data-ttu-id="99aef-102">Zeilen einschränken (Partitions-Assistent)</span><span class="sxs-lookup"><span data-stu-id="99aef-102">Restrict Rows (Partition Wizard)</span></span>
  <span data-ttu-id="99aef-103">Mithilfe der Seite **Zeilen einschränken** können Sie die Zeilen einschränken, die aus der angegebenen Tabelle abgerufen, aggregiert und in die Partition eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="99aef-103">Use the **Restrict Rows** page to restrict the rows that will be retrieved from the specified table and will be aggregated and included in the partition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="99aef-104">Diese Seite wird nur angezeigt, wenn Sie auf der Seite **Quellinformationen angeben** eine einzelne Tabelle ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="99aef-104">This page is appears only if you selected a single table in the **Specify Source Information** page.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="99aef-105">Wenn Sie auf der Seite **Quellinformationen angeben** unter **Verfügbare Tabellen** eine Tabelle angeben, die auch von einer anderen Partition verwendet wird, müssen Sie auf der Seite **Zeilen einschränken** eine Abfrage bereitstellen, da andernfalls die Gefahr besteht, dass die Daten im Cube dupliziert werden.</span><span class="sxs-lookup"><span data-stu-id="99aef-105">If you specified a table in **Available Tables** on the **Specify Source Information** page that is used by another partition, you must provide a query in the **Restrict Rows** page or risk duplicating data in the cube.</span></span>  
  
## <a name="options"></a><span data-ttu-id="99aef-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="99aef-106">Options</span></span>  
 <span data-ttu-id="99aef-107">**Abfrage zum Einschränken der Zeilen angeben**</span><span class="sxs-lookup"><span data-stu-id="99aef-107">**Specify a query to restrict rows**</span></span>  
 <span data-ttu-id="99aef-108">Wählen Sie diese Option aus, um eine Abfrage in das Feld **Abfrage** einzugeben, die die Zeilen einschränkt.</span><span class="sxs-lookup"><span data-stu-id="99aef-108">Select to enter a query that restricts rows into the **Query** box.</span></span>  
  
 <span data-ttu-id="99aef-109">Wenn beim Auswählen dieser Option das Feld **WHERE-Klausel hinzufügen** leer ist, wird dort eine SQL-Anweisung eingetragen, die alle Spalten und Zeilen aus der zuvor ausgewählten Tabelle abruft.</span><span class="sxs-lookup"><span data-stu-id="99aef-109">If **Supply a WHERE clause** is empty when this option is selected, that option is populated with an SQL statement that retrieves all columns and all rows from the previously selected table.</span></span>  
  
 <span data-ttu-id="99aef-110">**Abfrage**</span><span class="sxs-lookup"><span data-stu-id="99aef-110">**Query**</span></span>  
 <span data-ttu-id="99aef-111">Geben Sie die SQL-Anweisung ein, die während der Verarbeitung der Partition zum Abrufen von Zeilen aus der Tabelle verwendet wird, oder ändern Sie diese.</span><span class="sxs-lookup"><span data-stu-id="99aef-111">Type or modify the SQL statement used when retrieving rows from the table when the partition is processed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="99aef-112">Wenn Sie eine WHERE-Klausel angeben, kann für diese Partition eine Teilmenge von Datensätzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="99aef-112">By specifying a WHERE clause, a subset of records can be used for this partition.</span></span> <span data-ttu-id="99aef-113">Dies ist von wesentlicher Bedeutung, um das Duplizieren von Daten zu verhindern, wenn mehrere Partitionen auf einer einzigen Faktentabelle basieren.</span><span class="sxs-lookup"><span data-stu-id="99aef-113">This is essential to prevent duplication of data when multiple partitions are based on a single fact table.</span></span>  
  
 <span data-ttu-id="99aef-114">**Überprüfung**</span><span class="sxs-lookup"><span data-stu-id="99aef-114">**Check**</span></span>  
 <span data-ttu-id="99aef-115">Überprüft, ob es sich bei der Anweisung in **Abfrage** um eine gültige SQL-Anweisung handelt.</span><span class="sxs-lookup"><span data-stu-id="99aef-115">Verifies that the statement in **Query** is a valid SQL statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99aef-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="99aef-116">See Also</span></span>  
 [<span data-ttu-id="99aef-117">Partitionen &#40;Analysis Services – mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="99aef-117">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
