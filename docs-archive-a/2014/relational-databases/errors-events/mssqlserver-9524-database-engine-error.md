---
title: MSSQLSERVER_9524 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9524 (Database Engine error)
ms.assetid: 12da7931-e124-4466-889c-046f1b7b7bfd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e6c46ee0ef0bd1be299614e2cb04a3d6cd99d92e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617037"
---
# <a name="mssqlserver_9524"></a><span data-ttu-id="79277-102">MSSQLSERVER_9524</span><span class="sxs-lookup"><span data-stu-id="79277-102">MSSQLSERVER_9524</span></span>
    
## <a name="details"></a><span data-ttu-id="79277-103">Details</span><span class="sxs-lookup"><span data-stu-id="79277-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="79277-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="79277-104">Product Name</span></span>|<span data-ttu-id="79277-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="79277-105">SQL Server</span></span>|  
|<span data-ttu-id="79277-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="79277-106">Event ID</span></span>|<span data-ttu-id="79277-107">9254</span><span class="sxs-lookup"><span data-stu-id="79277-107">9254</span></span>|  
|<span data-ttu-id="79277-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="79277-108">Event Source</span></span>|<span data-ttu-id="79277-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="79277-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="79277-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="79277-110">Component</span></span>|<span data-ttu-id="79277-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="79277-111">SQLEngine</span></span>|  
|<span data-ttu-id="79277-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="79277-112">Symbolic Name</span></span>|<span data-ttu-id="79277-113">XMLERR_INVALID_COLUMNSET_XML</span><span class="sxs-lookup"><span data-stu-id="79277-113">XMLERR_INVALID_COLUMNSET_XML</span></span>|  
|<span data-ttu-id="79277-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="79277-114">Message Text</span></span>|<span data-ttu-id="79277-115">Der angegebene XML-Inhalt entspricht nicht dem erforderlichen XML-Format für Sparsespaltensätze.</span><span class="sxs-lookup"><span data-stu-id="79277-115">The XML content provided does not conform to the required XML format for sparse column sets.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="79277-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="79277-116">Explanation</span></span>  
 <span data-ttu-id="79277-117">Es wurde versucht, einen Spaltensatz zu ändern.</span><span class="sxs-lookup"><span data-stu-id="79277-117">An attempt was made to modify a column set.</span></span> <span data-ttu-id="79277-118">Der XML-Inhalt eines Spaltensatzes muss die Formateinschränkungen für Spaltensätze erfüllen.</span><span class="sxs-lookup"><span data-stu-id="79277-118">The XML content of a column set must meet the format restrictions of a column set.</span></span> <span data-ttu-id="79277-119">Das allgemeine Format eines Spaltensatzes sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="79277-119">The general format of a column set is as follows:</span></span>  
  
 `<column_name_1>value1</column_name_1><column_name_2>value2</column_name_2>...`  
  
 <span data-ttu-id="79277-120">Weitere Informationen zu Spaltensätzen finden Sie im Thema "Verwenden von Spaltensätzen" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="79277-120">For more information about column sets, see the topic "Using Column Sets" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="79277-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="79277-121">User Action</span></span>  
 <span data-ttu-id="79277-122">Korrigieren Sie das XML-Format für den Spaltensatz in der Anweisung.</span><span class="sxs-lookup"><span data-stu-id="79277-122">Correct the format of the XML for the column set in the statement.</span></span>  
  
  
