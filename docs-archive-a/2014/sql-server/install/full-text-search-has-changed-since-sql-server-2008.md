---
title: Die voll Text Suche wurde seit SQL Server 2008 geändert | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: d253bb05-9166-4b50-bd4a-27b818f514e0
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 99d3ed4478f007bbe7f05838250aa33a9c4fe448
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617475"
---
# <a name="full-text-search-has-changed-since-sql-server-2008"></a><span data-ttu-id="64b18-102">Die Volltextsuche wurde seit SQL Server 2008 geändert.</span><span class="sxs-lookup"><span data-stu-id="64b18-102">Full-Text Search has changed since SQL Server 2008</span></span>
  <span data-ttu-id="64b18-103">Der Upgrade Advisor hat erkannt, dass für die Volltextsuche ein Upgrade vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="64b18-103">Upgrade Advisor detected that full-text search is going to be upgraded.</span></span> <span data-ttu-id="64b18-104">Viele Volltextsuchoptionen und -einstellungen haben sich geändert.</span><span class="sxs-lookup"><span data-stu-id="64b18-104">Many full-text search options and settings have changed.</span></span> <span data-ttu-id="64b18-105">Aus diesem Grund kann es erforderlich sein, einige Einstellungen zu ändern, wenn Sie ein Upgrade auf die [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]-Volltextsuche durchführen.</span><span class="sxs-lookup"><span data-stu-id="64b18-105">Therefore, when you upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Full-Text Search, some of your settings might need modification.</span></span>  
  
## <a name="component"></a><span data-ttu-id="64b18-106">Komponente</span><span class="sxs-lookup"><span data-stu-id="64b18-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="64b18-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="64b18-107">Description</span></span>  
 <span data-ttu-id="64b18-108">Seit [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] wurden verschiedene Funktionen, Einstellungen und Objekte der Volltextsuche geändert, und viele bestehende Einstellungen werden beim Upgrade nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="64b18-108">Several full-text search features, settings and objects have been modified since [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and many of your existing settings will not be maintained when you upgrade.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="64b18-109">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="64b18-109">Corrective Action</span></span>  
 <span data-ttu-id="64b18-110">Außerdem ist es ratsam, in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation in der Dokumentation zur Volltextsuche die Informationen zu wichtigen Änderungen und Vorgehensweisen zu lesen, wenn Sie auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="64b18-110">We also recommend reviewing full-text search documentation in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online for breaking changes and best practices when you upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="64b18-111">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="64b18-111">External Resources</span></span>  
 [<span data-ttu-id="64b18-112">Abwärtskompatibilität der Volltextsuche</span><span class="sxs-lookup"><span data-stu-id="64b18-112">Full-Text Search Backward Compatibility</span></span>](../../../2014/database-engine/full-text-search-backward-compatibility.md)  
  
 [<span data-ttu-id="64b18-113">Upgrade der Volltextsuche</span><span class="sxs-lookup"><span data-stu-id="64b18-113">Full-Text Search Upgrade</span></span>](https://go.microsoft.com/fwlink/?LinkId=112291)  
  
 [<span data-ttu-id="64b18-114">Fehlerhafte Änderungen der Volltextsuche</span><span class="sxs-lookup"><span data-stu-id="64b18-114">Breaking Changes to Full-Text Search</span></span>](../../../2014/database-engine/breaking-changes-to-full-text-search.md)  
  
  
