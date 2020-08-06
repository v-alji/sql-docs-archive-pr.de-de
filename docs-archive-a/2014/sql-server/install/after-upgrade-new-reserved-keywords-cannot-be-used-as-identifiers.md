---
title: Nach dem Upgrade können neue reservierte Schlüsselwörter nicht als Bezeichner verwendet werden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- keywords [SQL Server], after upgrade
- keywords [SQL Server], reserved
- keywords [SQL Server]
ms.assetid: cb242081-54f8-4273-a8ef-52f3751c25ef
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 36f7f8cadcba5e114feee4a3c42de6f40070ce72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617537"
---
# <a name="after-upgrade-new-reserved-keywords-cannot-be-used-as-identifiers"></a><span data-ttu-id="1fc38-102">Nach dem Upgrade können neue reservierte Schlüsselwörter nicht als Bezeichner verwendet werden</span><span class="sxs-lookup"><span data-stu-id="1fc38-102">After upgrade, new reserved keywords cannot be used as identifiers</span></span>
  <span data-ttu-id="1fc38-103">Der Upgrade Advisor hat die Verwendung von Wörtern erkannt, die als Schlüsselwörter reserviert sind.</span><span class="sxs-lookup"><span data-stu-id="1fc38-103">Upgrade Advisor detected the use of words that are reserved keywords.</span></span> <span data-ttu-id="1fc38-104">Ein reserviertes Schlüsselwort kann nicht als Bezeichner oder Objektname verwendet werden, es sei denn, der Name ist mit Trennzeichen versehen.</span><span class="sxs-lookup"><span data-stu-id="1fc38-104">A reserved keyword cannot be used as an identifier or object name unless the name is delimited.</span></span>  
  
## <a name="component"></a><span data-ttu-id="1fc38-105">Komponente</span><span class="sxs-lookup"><span data-stu-id="1fc38-105">Component</span></span>  
 <span data-ttu-id="1fc38-106">Datenbank-Engine</span><span class="sxs-lookup"><span data-stu-id="1fc38-106">Database Engine</span></span>  
  
## <a name="description"></a><span data-ttu-id="1fc38-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1fc38-107">Description</span></span>  
 <span data-ttu-id="1fc38-108">Bei Kompatibilitätsgrad 90 oder niedriger sind die folgenden Wörter keine reservierten Schlüsselwörter und können in [!INCLUDE[tsql](../../includes/tsql-md.md)]-Skripts als Bezeichner oder Objektnamen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1fc38-108">At compatibility level 90 or lower, the following words are not reserved keywords and can be used as identifiers or object names in [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="1fc38-109">Bei Kompatibilitätsgrad 100 sind diese Wörter vollständig reservierte Schlüsselwörter und sollten nicht als Bezeichner oder Objektnamen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1fc38-109">At compatibility level 100, these words are fully reserved keywords and should not be used as identifiers or object names.</span></span>  
  
-   <span data-ttu-id="1fc38-110">EXTERNAL</span><span class="sxs-lookup"><span data-stu-id="1fc38-110">EXTERNAL</span></span>  
  
-   <span data-ttu-id="1fc38-111">MERGE</span><span class="sxs-lookup"><span data-stu-id="1fc38-111">MERGE</span></span>  
  
-   <span data-ttu-id="1fc38-112">PIVOT</span><span class="sxs-lookup"><span data-stu-id="1fc38-112">PIVOT</span></span>  
  
-   <span data-ttu-id="1fc38-113">REVERT</span><span class="sxs-lookup"><span data-stu-id="1fc38-113">REVERT</span></span>  
  
-   <span data-ttu-id="1fc38-114">STOPLIST</span><span class="sxs-lookup"><span data-stu-id="1fc38-114">STOPLIST</span></span>  
  
-   <span data-ttu-id="1fc38-115">TABLESAMPLE</span><span class="sxs-lookup"><span data-stu-id="1fc38-115">TABLESAMPLE</span></span>  
  
-   <span data-ttu-id="1fc38-116">UNPIVOT</span><span class="sxs-lookup"><span data-stu-id="1fc38-116">UNPIVOT</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="1fc38-117">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="1fc38-117">Corrective Action</span></span>  
 <span data-ttu-id="1fc38-118">Es wird empfohlen, das Objekt umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="1fc38-118">We recommend that you rename the object.</span></span> <span data-ttu-id="1fc38-119">Falls dies vor dem Upgrade nicht möglich ist, können Sie eine der folgenden Methoden verwenden, bis der Name geändert werden kann:</span><span class="sxs-lookup"><span data-stu-id="1fc38-119">If that cannot be done before upgrading, use one of the following methods until the name can be changed:</span></span>  
  
-   <span data-ttu-id="1fc38-120">Behalten Sie die Einstellung von 90 oder niedriger für den Datenbankkompatibilitätsgrad bei.</span><span class="sxs-lookup"><span data-stu-id="1fc38-120">Retain the database compatibility level setting of 90 or lower.</span></span>  
  
-   <span data-ttu-id="1fc38-121">Verweisen Sie mit Begrenzungsbezeichnern auf das Objekt.</span><span class="sxs-lookup"><span data-stu-id="1fc38-121">Refer to the object by using delimited identifiers.</span></span> <span data-ttu-id="1fc38-122">Beispielsweise verwendet die-Anweisung eckige `CREATE TABLE [MERGE] ([MERGE] int);` Klammern, um den Objektnamen Merge zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="1fc38-122">For example, the statement `CREATE TABLE [MERGE] ([MERGE] int);` uses brackets to delimit the object name MERGE.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="1fc38-123">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="1fc38-123">External Resources</span></span>  
 [<span data-ttu-id="1fc38-124">Reserved Keywords &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1fc38-124">Reserved Keywords &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reserved-keywords-transact-sql)  
  
 [<span data-ttu-id="1fc38-125">MERGE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1fc38-125">MERGE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/merge-transact-sql)  
  
 [<span data-ttu-id="1fc38-126">Begrenzungsbezeichner (Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="1fc38-126">Delimited Identifiers (Database Engine)</span></span>](https://go.microsoft.com/fwlink/?LinkId=112509)  
  
 [<span data-ttu-id="1fc38-127">ALTER DATABASE-Kompatibilitätsgrad &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1fc38-127">ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level)  
  
  
