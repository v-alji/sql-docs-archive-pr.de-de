---
title: Unterstützte Konstrukte für nativ kompilierte gespeicherte Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 6b21f47e-bceb-4054-8b3c-9d39bb9583c0
author: rothja
ms.author: jroth
ms.openlocfilehash: f3bc7e28fa2a868ac39c6adbb2dea3cc5c3ace73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616552"
---
# <a name="supported-constructs-on-natively-compiled-stored-procedures"></a><span data-ttu-id="97970-102">Unterstützte Konstrukte für systemintern kompilierte gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="97970-102">Supported Constructs on Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="97970-103">In diesem Thema werden die unterstützten Konstrukte für systemintern kompilierte gespeicherte Prozeduren aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="97970-103">This topic lists the supported constructs on natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="97970-104">Informationen zu nicht unterstützten Konstrukten finden Sie unter [Von In-Memory OLTP nicht unterstützte Transact-SQL-Konstrukte](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="97970-104">For information about unsupported constructs, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
## <a name="procedure-ddl"></a><span data-ttu-id="97970-105">Prozedur-DDL</span><span class="sxs-lookup"><span data-stu-id="97970-105">Procedure DDL</span></span>  
 <span data-ttu-id="97970-106">Folgende werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="97970-106">The following are supported:</span></span>  
  
-   <span data-ttu-id="97970-107">CREATE PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="97970-107">CREATE PROCEDURE</span></span>  
  
-   <span data-ttu-id="97970-108">DROP PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="97970-108">DROP PROCEDURE</span></span>  
  
-   <span data-ttu-id="97970-109">SCHEMABINDING (in systemintern kompilierten gespeicherten Prozeduren erforderlich)</span><span class="sxs-lookup"><span data-stu-id="97970-109">SCHEMABINDING (required for natively compiled stored procedures)</span></span>  
  
-   <span data-ttu-id="97970-110">NATIVE_COMPILATION</span><span class="sxs-lookup"><span data-stu-id="97970-110">NATIVE_COMPILATION</span></span>  
  
-   <span data-ttu-id="97970-111">Parameter können als NOT NULL deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="97970-111">Parameters can be declared as NOT NULL.</span></span>  
  
-   <span data-ttu-id="97970-112">Tabellenwertparameter.</span><span class="sxs-lookup"><span data-stu-id="97970-112">Table-valued parameters.</span></span>  
  
## <a name="security"></a><span data-ttu-id="97970-113">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="97970-113">Security</span></span>  
 <span data-ttu-id="97970-114">Folgende werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="97970-114">The following are supported:</span></span>  
  
-   <span data-ttu-id="97970-115">Für Prozeduren: EXECUTE AS SELF, OWNER und Benutzer.</span><span class="sxs-lookup"><span data-stu-id="97970-115">For procedures: EXECUTE AS OWNER, SELF, and user.</span></span>  
  
-   <span data-ttu-id="97970-116">GRANT- und DENY-Berechtigungen in Tabellen und Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="97970-116">GRANT and DENY permissions on tables and procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97970-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="97970-117">See Also</span></span>  
 [<span data-ttu-id="97970-118">Nativ kompilierte gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="97970-118">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
