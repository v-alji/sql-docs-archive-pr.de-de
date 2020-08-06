---
title: SQL Server Prozess interne spezifische Erweiterungen für ADO.net | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- data access [CLR integration]
- ADO.NET [CLR integration]
- common language runtime [SQL Server], ADO.NET
- database objects [CLR integration], in-process extensions
- in-process data access providers [CLR integration]
- extensions [CLR integration]
ms.assetid: 781b812e-eb14-472a-85fa-aa4cdb929bee
author: rothja
ms.author: jroth
ms.openlocfilehash: 37d8aedc1d8f93739c2e9386665adfc67b43e312
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622169"
---
# <a name="sql-server-in-process-specific-extensions-to-adonet"></a><span data-ttu-id="fe17d-102">Von SQL Server verwendete prozessinterne spezifische Erweiterungen für ADO.NET</span><span class="sxs-lookup"><span data-stu-id="fe17d-102">SQL Server In-Process Specific Extensions to ADO.NET</span></span>
  <span data-ttu-id="fe17d-103">Es gibt vier Hauptfunktionserweiterungen für ADO.NET, die speziell der prozessinternen Verwendung dienen.</span><span class="sxs-lookup"><span data-stu-id="fe17d-103">There are four main functional extensions to ADO.NET that are specifically for in-process use.</span></span> <span data-ttu-id="fe17d-104">Die folgenden Themen liefern detaillierte Informationen zu diesen Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="fe17d-104">The following topics will cover these extensions in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fe17d-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="fe17d-105">In This Section</span></span>  
 [<span data-ttu-id="fe17d-106">SqlContext-Objekt</span><span class="sxs-lookup"><span data-stu-id="fe17d-106">SqlContext Object</span></span>](sqlcontext-object.md)  
 <span data-ttu-id="fe17d-107">Diese Klasse bietet Zugriff auf die anderen Erweiterungen, indem sie den Kontext des Aufrufers einer SQL Server-Routine abstrahiert, die verwalteten Code prozessintern ausführt.</span><span class="sxs-lookup"><span data-stu-id="fe17d-107">This class provides access to the other extensions by abstracting the context of a caller of a SQL Server routine that executes managed code in-process.</span></span>  
  
 [<span data-ttu-id="fe17d-108">SqlPipe-Objekt</span><span class="sxs-lookup"><span data-stu-id="fe17d-108">SqlPipe Object</span></span>](sqlpipe-object.md)  
 <span data-ttu-id="fe17d-109">Diese Klasse enthält Routinen, mit denen Tabellenergebnisse und Nachrichten an den Client gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="fe17d-109">This class contains routines to send tabular results and messages to the client.</span></span>  
  
 [<span data-ttu-id="fe17d-110">SqlTriggerContext-Objekt</span><span class="sxs-lookup"><span data-stu-id="fe17d-110">SqlTriggerContext Object</span></span>](sqltriggercontext-object.md)  
 <span data-ttu-id="fe17d-111">Diese Klasse stellt Informationen über den Kontext bereit, in dem ein Trigger ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fe17d-111">This class provides information on the context in which a trigger is run.</span></span>  
  
 [<span data-ttu-id="fe17d-112">SqlDataRecord-Objekt</span><span class="sxs-lookup"><span data-stu-id="fe17d-112">SqlDataRecord Object</span></span>](sqldatarecord-object.md)  
 <span data-ttu-id="fe17d-113">Die SqlDataRecord-Klasse stellt eine einzelne Datenzeile einschließlich der zugehörigen Metadaten dar und ermöglicht es gespeicherten Prozeduren, benutzerdefinierte Resultsets an den Client zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="fe17d-113">The SqlDataRecord class represents a single row of data, along with its related metadata, and allows stored procedures to return custom result sets to the client.</span></span>  
  
  
