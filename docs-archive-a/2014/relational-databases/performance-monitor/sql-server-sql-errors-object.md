---
title: SQL Server, SQL Errors-Objekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQL Errors object
- SQLServer:SQL Errors
ms.assetid: 6e5273ca-29cb-4618-88a2-70b9b8d6cf76
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 11bfb728e79b4fc175fb8a2fe16c9f1662a205ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696757"
---
# <a name="sql-server-sql-errors-object"></a><span data-ttu-id="17226-102">SQL Server, SQL-Fehler-Objekt</span><span class="sxs-lookup"><span data-stu-id="17226-102">SQL Server, SQL Errors Object</span></span>
  <span data-ttu-id="17226-103">Durch das Objekt **SQLServer:SQL Errors** in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] werden Indikatoren zum Überwachen von **SQL-Fehlern**zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="17226-103">The **SQLServer:SQL Errors** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides counters to monitor **SQL Errors**.</span></span>  
  
 <span data-ttu-id="17226-104">Diese Tabelle enthält eine Beschreibung der **SQL Errors**-Zähler in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17226-104">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **SQL Errors** counters.</span></span>  
  
|<span data-ttu-id="17226-105">Leistungsindikatoren von SQL-Fehler bei SQL Server</span><span class="sxs-lookup"><span data-stu-id="17226-105">SQL Server SQL Errors counters</span></span>|<span data-ttu-id="17226-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="17226-106">Description</span></span>|  
|------------------------------------|-----------------|  
|<span data-ttu-id="17226-107">**Fehler/Sekunde**</span><span class="sxs-lookup"><span data-stu-id="17226-107">**Errors/sec**</span></span>|<span data-ttu-id="17226-108">Anzahl der Fehler/Sekunde.</span><span class="sxs-lookup"><span data-stu-id="17226-108">Number of errors/sec.</span></span>|  
  
 <span data-ttu-id="17226-109">Jeder Leistungsindikator in dem Objekt enthält die folgenden Instanzen:</span><span class="sxs-lookup"><span data-stu-id="17226-109">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="17226-110">Element</span><span class="sxs-lookup"><span data-stu-id="17226-110">Item</span></span>|<span data-ttu-id="17226-111">Definition</span><span class="sxs-lookup"><span data-stu-id="17226-111">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="17226-112">**_Total**</span><span class="sxs-lookup"><span data-stu-id="17226-112">**_Total**</span></span>|<span data-ttu-id="17226-113">Informationen zu allen Fehlern.</span><span class="sxs-lookup"><span data-stu-id="17226-113">Information for all errors.</span></span>|  
|<span data-ttu-id="17226-114">**DB Offline Errors**</span><span class="sxs-lookup"><span data-stu-id="17226-114">**DB Offline Errors**</span></span>|<span data-ttu-id="17226-115">Es werden schwere Fehler nachverfolgt, die dazu führen, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die Datenbank offline schaltet.</span><span class="sxs-lookup"><span data-stu-id="17226-115">Tracks severe errors that cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to take the current database offline.</span></span>|  
|<span data-ttu-id="17226-116">**Info Errors**</span><span class="sxs-lookup"><span data-stu-id="17226-116">**Info Errors**</span></span>|<span data-ttu-id="17226-117">Informationen, die sich auf Fehlermeldungen beziehen, die den Benutzern als Informationen zur Verfügung gestellt werden, verursachen jedoch keine Fehler.</span><span class="sxs-lookup"><span data-stu-id="17226-117">Information related to error messages that provide information to users but do not cause errors.</span></span>|  
|<span data-ttu-id="17226-118">**Kill Connection Errors**</span><span class="sxs-lookup"><span data-stu-id="17226-118">**Kill Connection Errors**</span></span>|<span data-ttu-id="17226-119">Es werden schwere Fehler nachverfolgt, die dazu führen, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die aktuelle Verbindung unterbricht.</span><span class="sxs-lookup"><span data-stu-id="17226-119">Tracks severe errors that cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to kill the current connection.</span></span>|  
|<span data-ttu-id="17226-120">**User Errors**</span><span class="sxs-lookup"><span data-stu-id="17226-120">**User Errors**</span></span>|<span data-ttu-id="17226-121">Informationen zu Benutzerfehlern.</span><span class="sxs-lookup"><span data-stu-id="17226-121">Information about user errors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="17226-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="17226-122">See Also</span></span>  
 [<span data-ttu-id="17226-123">Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;</span><span class="sxs-lookup"><span data-stu-id="17226-123">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
