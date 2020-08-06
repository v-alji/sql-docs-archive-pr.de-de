---
title: MSSQLSERVER_15599 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15599 (Database Engine error)
ms.assetid: 97e427a9-8587-46ea-954b-974b5df9c223
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 15f1b3eb6d97837f1c1c4a9944535cade5b31300
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620944"
---
# <a name="mssqlserver_15599"></a><span data-ttu-id="c7083-102">MSSQLSERVER_15599</span><span class="sxs-lookup"><span data-stu-id="c7083-102">MSSQLSERVER_15599</span></span>
    
## <a name="details"></a><span data-ttu-id="c7083-103">Details</span><span class="sxs-lookup"><span data-stu-id="c7083-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c7083-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="c7083-104">Product Name</span></span>|<span data-ttu-id="c7083-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c7083-105">SQL Server</span></span>|  
|<span data-ttu-id="c7083-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c7083-106">Event ID</span></span>|<span data-ttu-id="c7083-107">15599</span><span class="sxs-lookup"><span data-stu-id="c7083-107">15599</span></span>|  
|<span data-ttu-id="c7083-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="c7083-108">Event Source</span></span>|<span data-ttu-id="c7083-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c7083-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c7083-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="c7083-110">Component</span></span>|<span data-ttu-id="c7083-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c7083-111">SQLEngine</span></span>|  
|<span data-ttu-id="c7083-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="c7083-112">Symbolic Name</span></span>|<span data-ttu-id="c7083-113">SEC_LOCAL_TEMP_AUDIT_PERMISSIONS</span><span class="sxs-lookup"><span data-stu-id="c7083-113">SEC_LOCAL_TEMP_AUDIT_PERMISSIONS</span></span>|  
|<span data-ttu-id="c7083-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="c7083-114">Message Text</span></span>|<span data-ttu-id="c7083-115">Überwachung und Berechtigungen können nicht für lokale temporäre Objekte festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c7083-115">Auditing and permissions can't be set on local temporary objects.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c7083-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="c7083-116">Explanation</span></span>  
 <span data-ttu-id="c7083-117">Überwachung und Berechtigungen haben keine Auswirkungen, wenn sie für lokale oder globale temp-Objekte festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c7083-117">Auditing and permissions do not have any effect when set for local or global temp objects.</span></span> <span data-ttu-id="c7083-118">Die Anweisungen haben keinem Fehler zur Folge (die Vorgänge geben Erfolg zurück), sie haben lediglich keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="c7083-118">The statements do not result in an error (the operations will return success), but have no effect.</span></span>  
  
 <span data-ttu-id="c7083-119">Dieses Verhalten hat sich nicht geändert. Seit [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] wird der Benutzer jedoch in einer Informationsmeldung hierüber informiert.</span><span class="sxs-lookup"><span data-stu-id="c7083-119">This behavior has not changed, however beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], this informational message alerts the user.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c7083-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="c7083-120">User Action</span></span>  
 <span data-ttu-id="c7083-121">Es ist keine Aktion notwendig. Sie sollten jedoch das Entfernen von Anweisungen in Erwägung ziehen, durch die Überwachung oder Berechtigungen für lokale oder globale temp-Objekte festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c7083-121">No action is necessary, but consider removing statements that attempt to set auditing or permissions on local or global temp objects.</span></span>  
  
  
