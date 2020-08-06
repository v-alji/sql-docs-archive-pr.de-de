---
title: MSSQLSERVER_1793 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: 808db1d0-acc1-41d0-9287-8a5455001a02
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 54172adb957c3cbc1dbc221d1cae2a583830a1cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699692"
---
# <a name="mssqlserver_1793"></a><span data-ttu-id="c850a-102">MSSQLSERVER_1793</span><span class="sxs-lookup"><span data-stu-id="c850a-102">MSSQLSERVER_1793</span></span>
    
## <a name="details"></a><span data-ttu-id="c850a-103">Details</span><span class="sxs-lookup"><span data-stu-id="c850a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c850a-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="c850a-104">Product Name</span></span>|<span data-ttu-id="c850a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c850a-105">SQL Server</span></span>|  
|<span data-ttu-id="c850a-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c850a-106">Event ID</span></span>|<span data-ttu-id="c850a-107">1793</span><span class="sxs-lookup"><span data-stu-id="c850a-107">1793</span></span>|  
|<span data-ttu-id="c850a-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="c850a-108">Event Source</span></span>|<span data-ttu-id="c850a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c850a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c850a-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="c850a-110">Component</span></span>|<span data-ttu-id="c850a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c850a-111">SQLEngine</span></span>|  
|<span data-ttu-id="c850a-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="c850a-112">Symbolic Name</span></span>|<span data-ttu-id="c850a-113">FILESTREAM_BASEDATA_NEED_SAME_PARTITION</span><span class="sxs-lookup"><span data-stu-id="c850a-113">FILESTREAM_BASEDATA_NEED_SAME_PARTITION</span></span>|  
|<span data-ttu-id="c850a-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="c850a-114">Message Text</span></span>|<span data-ttu-id="c850a-115">Das Löschen des Indexes '%.\*ls' ist nicht möglich, da kein Partitionsschema für FILESTREAM-Daten angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="c850a-115">Cannot drop index '%.\*ls' since a partition scheme is not specified for FILESTREAM data.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c850a-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="c850a-116">Explanation</span></span>  
 <span data-ttu-id="c850a-117">Diese Meldung wird angezeigt, wenn Sie versuchen, einen gruppierten Index für eine Tabelle zu löschen, die FILESTREAM-Daten enthält, und eine **MOVE TO**-Klausel für die Basisdaten angeben, dabei aber keine **FILESTREAM_ON**-Klausel für die FILESTREAM-Daten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c850a-117">This message occurs when you try to drop a clustered index on a table that contains FILESTREAM data, and you specify a **MOVE TO** clause for the base data, but you do not specify a **FILESTREAM_ON** clause for the FILESTREAM data.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c850a-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="c850a-118">User Action</span></span>  
 <span data-ttu-id="c850a-119">Verwenden Sie beim Löschen eines gruppierten Indexes in einer Tabelle, die FILESTREAM-Daten enthält, eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="c850a-119">When dropping a clustered index on a table that contains FILESTREAM data, use one of the following options:</span></span>  
  
-   <span data-ttu-id="c850a-120">Geben Sie sowohl eine **MOVE TO**-Klausel für die Basisdaten als auch eine **FILESTREAM_ON**-Klausel für die FILESTREAM-Daten an.</span><span class="sxs-lookup"><span data-stu-id="c850a-120">Specify both a **MOVE TO** clause for the base data and a **FILESTREAM_ON** clause for the FILESTREAM data.</span></span>  
  
-   <span data-ttu-id="c850a-121">Geben Sie nicht entweder eine **MOVE TO**-Klausel für die Basisdaten oder eine **FILESTREAM_ON**-Klausel für die FILESTREAM-Daten an.</span><span class="sxs-lookup"><span data-stu-id="c850a-121">Do not specify either a **MOVE TO** clause for the base data or a **FILESTREAM_ON** clause for the FILESTREAM data.</span></span>  
  
 <span data-ttu-id="c850a-122">Im folgenden Beispiel tritt ein Fehler auf, da ein Partitionsschema für die Basisdaten angegeben ist, jedoch nicht für die FILESTREAM-Daten.</span><span class="sxs-lookup"><span data-stu-id="c850a-122">The following example fails because a partition scheme is specified for the base data, but is not specified for the FILESTREAM data.</span></span>  
  
```sql  
DROP INDEX [<clustered_index_name>] ON [<table_name>]   
WITH ( ONLINE = OFF, MOVE TO [PRIMARY] )  
GO  
```  
  
 <span data-ttu-id="c850a-123">Das folgende Beispiel ist erfolgreich, da sowohl eine **MOVE TO**-Klausel für die Basisdaten als auch eine **FILESTREAM_ON**-Klausel für die FILESTREAM-Daten angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c850a-123">The following example succeeds because both a **MOVE TO** clause for the base data and a **FILESTREAM_ON** clause for the FILESTREAM data are specified.</span></span>  
  
```sql  
DROP INDEX [<clustered_index_name>] ON [<table_name>]   
WITH ( ONLINE = OFF, MOVE TO [PRIMARY], filestream_on 'default' )  
GO  
```  
  
 <span data-ttu-id="c850a-124">Das folgende Beispiel ist auch erfolgreich, da weder eine **MOVE TO**-Klausel für die Basisdaten noch eine **FILESTREAM_ON**-Klausel für die FILESTREAM-Daten angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c850a-124">The following example also succeeds because neither a **MOVE TO** clause for the base data nor a **FILESTREAM_ON** clause for the FILESTREAM data is specified.</span></span>  
  
```sql  
DROP INDEX [<clustered_index_name>] ON [<table_name>]   
WITH ( ONLINE = OFF )  
GO  
```  
  
  
