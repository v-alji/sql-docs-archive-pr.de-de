---
title: MSSQLSERVER_107 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 107 (Database Engine error)
ms.assetid: f33f514c-56aa-42e2-841b-e91244da90e2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b9388bbda6f00b1aafd02caee1b6a7b8387564f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620444"
---
# <a name="mssqlserver_107"></a><span data-ttu-id="f6bb0-102">MSSQLSERVER_107</span><span class="sxs-lookup"><span data-stu-id="f6bb0-102">MSSQLSERVER_107</span></span>
    
## <a name="details"></a><span data-ttu-id="f6bb0-103">Details</span><span class="sxs-lookup"><span data-stu-id="f6bb0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f6bb0-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="f6bb0-104">Product Name</span></span>|<span data-ttu-id="f6bb0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f6bb0-105">SQL Server</span></span>|  
|<span data-ttu-id="f6bb0-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="f6bb0-106">Event ID</span></span>|<span data-ttu-id="f6bb0-107">107</span><span class="sxs-lookup"><span data-stu-id="f6bb0-107">107</span></span>|  
|<span data-ttu-id="f6bb0-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="f6bb0-108">Event Source</span></span>|<span data-ttu-id="f6bb0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f6bb0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f6bb0-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="f6bb0-110">Component</span></span>|<span data-ttu-id="f6bb0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f6bb0-111">SQLEngine</span></span>|  
|<span data-ttu-id="f6bb0-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="f6bb0-112">Symbolic Name</span></span>|<span data-ttu-id="f6bb0-113">P_NOCORRMATCH</span><span class="sxs-lookup"><span data-stu-id="f6bb0-113">P_NOCORRMATCH</span></span>|  
|<span data-ttu-id="f6bb0-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="f6bb0-114">Message Text</span></span>|<span data-ttu-id="f6bb0-115">Das Spaltenpräfix '%.\*ls' stimmt mit keinem in der Abfrage verwendeten Tabellen- oder Aliasnamen überein.</span><span class="sxs-lookup"><span data-stu-id="f6bb0-115">The column prefix '%.\*ls' does not match with a table name or alias name used in the query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f6bb0-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="f6bb0-116">Explanation</span></span>  
 <span data-ttu-id="f6bb0-117">Die Auswahlliste der Abfrage enthält ein Sternchen (\*), das falsch mit einem Spaltenpräfix gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="f6bb0-117">The select list of the query contains an asterisk (\*) that is incorrectly qualified with a column prefix.</span></span> <span data-ttu-id="f6bb0-118">Dieser Fehler kann unter folgenden Bedingungen zurückgegeben werden:</span><span class="sxs-lookup"><span data-stu-id="f6bb0-118">This error can be returned under the following conditions:</span></span>  
  
-   <span data-ttu-id="f6bb0-119">Das Spaltenpräfix stimmt mit keinem in der Abfrage verwendeten Tabellen- oder Aliasnamen überein.</span><span class="sxs-lookup"><span data-stu-id="f6bb0-119">The column prefix does not correspond to any table or alias name used in the query.</span></span> <span data-ttu-id="f6bb0-120">In der folgenden Anweisung wird beispielsweise ein Aliasname (`T1`) als Spaltenpräfix verwendet, der Alias ist jedoch nicht in der FROM-Klausel definiert.</span><span class="sxs-lookup"><span data-stu-id="f6bb0-120">For example, the following statement uses an alias name (`T1`) as a column prefix, but the alias is not defined in the FROM clause.</span></span>  
  
    ```  
    SELECT T1.* FROM dbo.ErrorLog;  
    ```  
  
-   <span data-ttu-id="f6bb0-121">Wenn in der FROM-Klausel ein Aliasname für die Tabelle festgelegt ist, wird ein Tabellenname als Spaltenpräfix angegeben.</span><span class="sxs-lookup"><span data-stu-id="f6bb0-121">A table name is specified as a column prefix when an alias name for the table is supplied in the FROM clause.</span></span> <span data-ttu-id="f6bb0-122">In der folgenden Anweisung wird beispielsweise der Tabellenname `ErrorLog` als Spaltenpräfix verwendet, für die Tabelle ist jedoch ein Alias (`T1`) in der FROM-Klausel definiert.</span><span class="sxs-lookup"><span data-stu-id="f6bb0-122">For example, the following statement uses the table name `ErrorLog` as the column prefix; however, the table has an alias (`T1`) defined in the FROM clause.</span></span>  
  
    ```  
    SELECT ErrorLog.* FROM dbo.ErrorLog AS T1;  
    ```  
  
     <span data-ttu-id="f6bb0-123">Wenn in der FROM-Klausel ein Alias für einen Tabellennamen angegeben wurde, kann nur der Alias verwendet werden, der den Spalten in der Tabelle als Präfix vorangestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f6bb0-123">If an alias has been provided for a table name in the FROM clause, you can only use the alias to prefix columns from the table.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f6bb0-124">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="f6bb0-124">User Action</span></span>  
 <span data-ttu-id="f6bb0-125">Gleichen Sie die Spaltenpräfixe mit den in der FROM-Klausel der Abfrage angegeben Tabellen- oder Aliasnamen ab.</span><span class="sxs-lookup"><span data-stu-id="f6bb0-125">Match the column prefixes against the table names or alias names specified in the FROM clause of the query.</span></span> <span data-ttu-id="f6bb0-126">Die oben genannten Anweisungen können beispielsweise folgendermaßen korrigiert werden:</span><span class="sxs-lookup"><span data-stu-id="f6bb0-126">For example, the statements above can be corrected as follows:</span></span>  
  
```  
SELECT T1.* FROM dbo.ErrorLog AS T1;  
```  
  
 <span data-ttu-id="f6bb0-127">oder</span><span class="sxs-lookup"><span data-stu-id="f6bb0-127">or</span></span>  
  
```  
SELECT ErrorLog.* FROM dbo.ErrorLog;  
```  
  
## <a name="see-also"></a><span data-ttu-id="f6bb0-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f6bb0-128">See Also</span></span>  
 [<span data-ttu-id="f6bb0-129">MSSQLSERVER_4104</span><span class="sxs-lookup"><span data-stu-id="f6bb0-129">MSSQLSERVER_4104</span></span>](mssqlserver-4104-database-engine-error.md)  
  
  
