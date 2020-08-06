---
title: Ändern einer Partitions Quelle für die Verwendung einer anderen Fakten Tabelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- fact tables [Analysis Services]
- partitions [Analysis Services], fact tables
ms.assetid: 5508312f-8e46-4802-9362-6688ca03d098
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0063a6023d769dc6dccd616655d10e0bd3c65a98
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721998"
---
# <a name="change-a-partition-source-to-use-a-different-fact-table"></a><span data-ttu-id="d7b12-102">Ändern einer Partitionsquelle für die Verwendung einer anderen Faktentabelle</span><span class="sxs-lookup"><span data-stu-id="d7b12-102">Change a partition source to use a different fact table</span></span>
  <span data-ttu-id="d7b12-103">Bei der Erstellung von Partitionen können Sie für Cubes unterschiedliche Faktentabellen verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7b12-103">When you create a partition for a cube, you can choose to use a different fact table.</span></span> <span data-ttu-id="d7b12-104">Die unterschiedlichen Tabellen können dabei aus einer einzelnen Datenquellensicht, aus verschiedenen Datenquellensichten oder aus verschiedenen Datenquellen stammen.</span><span class="sxs-lookup"><span data-stu-id="d7b12-104">Different tables may be from a single data source view, from different data source views, or from different data sources.</span></span> <span data-ttu-id="d7b12-105">Eine Datenquellensicht kann auch unterschiedliche Tabellen aus mehreren Datenquellen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d7b12-105">A data source view may also contain different tables from more than one data source.</span></span>  
  
 <span data-ttu-id="d7b12-106">Alle Faktentabellen und Dimensionen für die Partitionen eines Cubes müssen dieselbe Struktur wie die Faktentabelle und die Dimensionen des Cubes besitzen.</span><span class="sxs-lookup"><span data-stu-id="d7b12-106">All fact tables and dimensions for a cube's partitions must have the same structure as the fact table and dimensions of the cube.</span></span> <span data-ttu-id="d7b12-107">Unterschiedliche Faktentabellen können z. B. dieselbe Struktur besitzen, aber Daten für verschiedene Jahre oder verschiedene Produktlinien enthalten.</span><span class="sxs-lookup"><span data-stu-id="d7b12-107">For example, different fact tables can have the same structure but contain data for different years or different product lines.</span></span>  
  
 <span data-ttu-id="d7b12-108">Eine Faktentabelle geben Sie auf der Seite **Quellinformationen angeben** des Partitions-Assistenten an.</span><span class="sxs-lookup"><span data-stu-id="d7b12-108">You specify a fact table on the **Specify Source Information** page of the Partition Wizard.</span></span> <span data-ttu-id="d7b12-109">Geben Sie auf dieser Seite im Gruppenfeld Partitionsquelle neben **Suchen in**an, in welcher Datenquelle bzw. Datenquellensicht gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="d7b12-109">On this page, in the Partition Source group next to **Look in**, specify a data source or data source view in which to look.</span></span> <span data-ttu-id="d7b12-110">Klicken Sie als Nächstes auf **Tabellen suchen**, und wählen Sie dann unter **Verfügbare Tabellen**die zu verwendende Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="d7b12-110">Next, click **Find Tables**, and then, under **Available Tables**, select the table you want to use.</span></span>  
  
 <span data-ttu-id="d7b12-111">Wenn Sie unterschiedliche Faktentabellen verwenden, sollten Sie sicherstellen, dass in den Partitionen keine Daten doppelt auftreten.</span><span class="sxs-lookup"><span data-stu-id="d7b12-111">When you use different fact tables, ensure that no data is duplicated among the partitions.</span></span> <span data-ttu-id="d7b12-112">Wenn eine Faktentabelle z. B. Transaktionen nur für das Jahr 2012 und eine andere Faktentabelle Transaktionen nur für das Jahr 2013 enthält, weisen diese Tabellen unabhängige Daten auf.</span><span class="sxs-lookup"><span data-stu-id="d7b12-112">For example, if one fact table contains transactions for 2012 only, and another fact table contains transactions for 2013 only, these tables contain independent data.</span></span> <span data-ttu-id="d7b12-113">Ebenso sind Faktentabellen für verschiedene Produktlinien oder verschiedene geografische Gebiete unabhängig voneinander.</span><span class="sxs-lookup"><span data-stu-id="d7b12-113">Similarly, fact tables for distinct product lines or distinct geographical areas are independent.</span></span>  
  
 <span data-ttu-id="d7b12-114">Es ist möglich, aber nicht empfehlenswert, dass Sie unterschiedliche Faktentabellen verwenden, die doppelte Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="d7b12-114">It is possible, but not recommended, to use different fact tables that contain duplicated data.</span></span> <span data-ttu-id="d7b12-115">In diesem Fall müssen Sie Filter in den Partitionen verwenden, um sicherzustellen, dass die von einer Partition verwendeten Daten nicht von einer anderen Partition verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d7b12-115">In this case, you must use filters in the partitions to ensure that data used by one partition is not used by any other partition.</span></span> <span data-ttu-id="d7b12-116">Weitere Informationen finden Sie unter [Erstellen und Verwalten einer lokalen Partition &#40;Analysis Services&#41;](create-and-manage-a-local-partition-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="d7b12-116">For more information, see [Create and Manage a Local Partition &#40;Analysis Services&#41;](create-and-manage-a-local-partition-analysis-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7b12-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d7b12-117">See Also</span></span>  
 [<span data-ttu-id="d7b12-118">Erstellen und Verwalten einer lokalen Partition &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d7b12-118">Create and Manage a Local Partition &#40;Analysis Services&#41;</span></span>](create-and-manage-a-local-partition-analysis-services.md)  
  
  
