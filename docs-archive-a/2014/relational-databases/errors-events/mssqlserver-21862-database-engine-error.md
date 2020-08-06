---
title: MSSQLSERVER_21862 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21862 (Database Engine error)
ms.assetid: a1d393dd-453b-4d45-9aa5-7d371213e32b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b945350d9c7a862d4274f464afbd7fc5472f732c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699669"
---
# <a name="mssqlserver_21862"></a><span data-ttu-id="8af06-102">MSSQLSERVER_21862</span><span class="sxs-lookup"><span data-stu-id="8af06-102">MSSQLSERVER_21862</span></span>
    
## <a name="details"></a><span data-ttu-id="8af06-103">Details</span><span class="sxs-lookup"><span data-stu-id="8af06-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8af06-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="8af06-104">Product Name</span></span>|<span data-ttu-id="8af06-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8af06-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8af06-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="8af06-106">Event ID</span></span>|<span data-ttu-id="8af06-107">21862</span><span class="sxs-lookup"><span data-stu-id="8af06-107">21862</span></span>|  
|<span data-ttu-id="8af06-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="8af06-108">Event Source</span></span>|<span data-ttu-id="8af06-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8af06-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8af06-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="8af06-110">Component</span></span>|<span data-ttu-id="8af06-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8af06-111">SQLEngine</span></span>|  
|<span data-ttu-id="8af06-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="8af06-112">Symbolic Name</span></span>|<span data-ttu-id="8af06-113">SQLErrorNum21862</span><span class="sxs-lookup"><span data-stu-id="8af06-113">SQLErrorNum21862</span></span>|  
|<span data-ttu-id="8af06-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="8af06-114">Message Text</span></span>|<span data-ttu-id="8af06-115">FILESTREAM-Spalten können nicht in einer Veröffentlichung mit der Synchronisierungsmethode 'database snapshot' oder 'database snapshot character' veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="8af06-115">FILESTREAM columns cannot be published in a publication by using a synchronization method of either 'database snapshot' or 'database snapshot character'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8af06-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="8af06-116">Explanation</span></span>  
 <span data-ttu-id="8af06-117">Da der Zugriff auf FILESTREAM-Daten über eine Datenbankmomentaufnahme nicht möglich ist, kann der Momentaufnahme-Agent FILESTREAM-Daten nicht lesen, wenn für die Synchronisierungsmethode der Veröffentlichung der *Datenbankmomentaufnahme* - oder der *database_snapshot_character*-Parameter angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="8af06-117">Because FILESTREAM data cannot be accessed through a database snapshot, the snapshot agent will be unable to read FILESTREAM data when either the *database snapshot* or *database_snapshot_character* parameter is specified for the synchronization method of the publication.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8af06-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="8af06-118">User Action</span></span>  
 <span data-ttu-id="8af06-119">Verwenden Sie für die Veröffentlichung eine andere Synchronisierungsmethode als die *Datenbankmomentaufnahme* oder *database_snapshot_character*, oder schließen Sie die FILESTREAM-Spalte aus der Veröffentlichung aus.</span><span class="sxs-lookup"><span data-stu-id="8af06-119">Change the publication synchronization method to something other than *database snapshot* or *database_snapshot_character*, or just exclude the FILESTREAM column from the publication.</span></span>  
  
  
