---
title: MSSQLSERVER_1803 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1803 (Database Engine error)
ms.assetid: d4315390-82f1-4c4c-8d1b-1a4989537cca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 11302f882846c49c6e9998608967e7042ac9860c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619153"
---
# <a name="mssqlserver_1803"></a><span data-ttu-id="c8022-102">MSSQLSERVER_1803</span><span class="sxs-lookup"><span data-stu-id="c8022-102">MSSQLSERVER_1803</span></span>
    
## <a name="details"></a><span data-ttu-id="c8022-103">Details</span><span class="sxs-lookup"><span data-stu-id="c8022-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c8022-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="c8022-104">Product Name</span></span>|<span data-ttu-id="c8022-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c8022-105">SQL Server</span></span>|  
|<span data-ttu-id="c8022-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c8022-106">Event ID</span></span>|<span data-ttu-id="c8022-107">1803</span><span class="sxs-lookup"><span data-stu-id="c8022-107">1803</span></span>|  
|<span data-ttu-id="c8022-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="c8022-108">Event Source</span></span>|<span data-ttu-id="c8022-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c8022-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c8022-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="c8022-110">Component</span></span>|<span data-ttu-id="c8022-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c8022-111">SQLEngine</span></span>|  
|<span data-ttu-id="c8022-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="c8022-112">Symbolic Name</span></span>|<span data-ttu-id="c8022-113">NO_SPACE</span><span class="sxs-lookup"><span data-stu-id="c8022-113">NO_SPACE</span></span>|  
|<span data-ttu-id="c8022-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="c8022-114">Message Text</span></span>|<span data-ttu-id="c8022-115">Fehler bei CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="c8022-115">CREATE DATABASE failed.</span></span> <span data-ttu-id="c8022-116">Die primäre Datei muss mindestens %d MB haben, um eine Kopie der model-Datenbank aufnehmen zu können.</span><span class="sxs-lookup"><span data-stu-id="c8022-116">Primary file must be at least %d MB to accommodate a copy of the model database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c8022-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="c8022-117">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c8022-118">erstellt eine Datenbank aus einer Kopie der Modelldatenbank.</span><span class="sxs-lookup"><span data-stu-id="c8022-118">creates a database by making a copy of the model database.</span></span> <span data-ttu-id="c8022-119">Die Kopie wird in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] umbenannt, und die neue Datenbank wird auf die angeforderte Größe vergrößert.</span><span class="sxs-lookup"><span data-stu-id="c8022-119">Then [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] renames the copy, and enlarges the new database to the requested size.</span></span> <span data-ttu-id="c8022-120">In diesem Fall versuchte der Benutzer, eine Datenbank zu erstellen, die kleiner als die Modelldatenbank war.</span><span class="sxs-lookup"><span data-stu-id="c8022-120">In this case, the user tried to create a database smaller than the model database.</span></span> <span data-ttu-id="c8022-121">Der Vorgang ist fehlgeschlagen, da die Kopie der Modelldatenbank nicht in die primäre Datendatei gepasst hat, da die Datei kleiner als die Modelldatenbank war.</span><span class="sxs-lookup"><span data-stu-id="c8022-121">The operation failed because the copy of the model database could not fit on the primary data file, because the file was smaller than the model database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c8022-122">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="c8022-122">User Action</span></span>  
 <span data-ttu-id="c8022-123">Erstellen Sie die Datenbank, und geben Sie eine größere Datenbankdateigröße an.</span><span class="sxs-lookup"><span data-stu-id="c8022-123">Create the database by using a larger database file size.</span></span> <span data-ttu-id="c8022-124">Verkleinern Sie dann ggf. die Datenbank mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder der DBCC SHRINKDATABASE-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c8022-124">Then shrink the database if you want by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], or the DBCC SHRINKDATABASE statement.</span></span>  
  
  
