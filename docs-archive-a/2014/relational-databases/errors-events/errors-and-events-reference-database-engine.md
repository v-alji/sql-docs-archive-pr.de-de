---
title: Fehler- und Ereignisreferenz (Datenbank-Engine) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- errors [SQL Server Database Engine]
- Database Engine [SQL Server], errors
- events [SQL Server Database Engine]
ms.assetid: ea928535-6fd1-4738-a8ed-ffb602f3825e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e991accfd0e6fdd4fa25746499308455eff85ce3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719975"
---
# <a name="errors-and-events-reference-database-engine"></a><span data-ttu-id="1b750-102">Fehler- und Ereignisreferenz (Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="1b750-102">Errors and Events Reference (Database Engine)</span></span>

<span data-ttu-id="1b750-103">Dieser Abschnitt enthält ausgewählte Datenbank-Engine Fehlermeldungen, die weitere Erläuterungen benötigen.</span><span class="sxs-lookup"><span data-stu-id="1b750-103">This section contains selected Database Engine error messages that need further explanation.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="1b750-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1b750-104">In This Section</span></span>  
 <span data-ttu-id="1b750-105">[Ereignisse und Fehler Datenbank-Engine](database-engine-events-and-errors.md) Beschreibt das Format der [!INCLUDE[ssDE](../../includes/ssde-md.md)] Fehlermeldungen und erläutert, wie Fehlermeldungen angezeigt und Fehlermeldungen an Anwendungen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1b750-105">[Database Engine Events and Errors](database-engine-events-and-errors.md) Describes the format of [!INCLUDE[ssDE](../../includes/ssde-md.md)] error messages and explains how to view error messages and return error messages to applications.</span></span>  
  
 <span data-ttu-id="1b750-106">Erläutert die [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Fehlermeldungen sowie die möglichen Ursachen und die Maßnahmen, die Sie zur Problembehebung ergreifen können.</span><span class="sxs-lookup"><span data-stu-id="1b750-106">Provides an explanation of [!INCLUDE[ssDE](../../includes/ssde-md.md)] error messages, possible causes, and any actions you can take to correct the problem.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="1b750-107">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="1b750-107">External Resources</span></span>  
 <span data-ttu-id="1b750-108">Wenn Sie die gewünschten Informationen nicht in der Produktdokumentation oder im Web gefunden haben, können Sie in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Community eine Frage stellen oder Hilfe vom [!INCLUDE[msCoName](../../includes/msconame-md.md)] -Support anfordern.</span><span class="sxs-lookup"><span data-stu-id="1b750-108">If you have not found the information you are looking for in the product documentation or on the Web, you can either ask a question in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] community or request help from [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1b750-109">In der folgenden Tabelle finden Sie Links und Beschreibungen zu diesen Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="1b750-109">The following table links to and describes these resources.</span></span>  
  
|<span data-ttu-id="1b750-110">Resource</span><span class="sxs-lookup"><span data-stu-id="1b750-110">Resource</span></span>|<span data-ttu-id="1b750-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1b750-111">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="1b750-112">SQL Server-Community</span><span class="sxs-lookup"><span data-stu-id="1b750-112">SQL Server Community</span></span>](https://go.microsoft.com/fwlink/?LinkId=42455)|<span data-ttu-id="1b750-113">Diese Site bietet Links zu Newsgroups und Foren, die von der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Community überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="1b750-113">This site has links to newsgroups and forums monitored by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] community.</span></span> <span data-ttu-id="1b750-114">Hier sind auch Community-Informationsquellen aufgeführt, z. B. Blogs und Websites.</span><span class="sxs-lookup"><span data-stu-id="1b750-114">It also lists community information sources, such as blogs and Web sites.</span></span> <span data-ttu-id="1b750-115">Die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Community ist bei Problemen ausgesprochen hilfreich, obwohl die Beantwortung von Fragen nicht unbedingt sichergestellt ist.</span><span class="sxs-lookup"><span data-stu-id="1b750-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] community is very helpful in answering questions, although an answer cannot be guaranteed.</span></span>|  
|[<span data-ttu-id="1b750-116">SQL Server Developer Center-Community</span><span class="sxs-lookup"><span data-stu-id="1b750-116">SQL Server Developer Center Community</span></span>](https://go.microsoft.com/fwlink/?LinkId=42456)|<span data-ttu-id="1b750-117">Diese Site ist speziell auf Newsgroups, Foren und andere Communityressourcen ausgerichtet, die für Entwickler von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] von Interesse sind.</span><span class="sxs-lookup"><span data-stu-id="1b750-117">This site focuses on the newsgroups, forums, and other community resources that are useful to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] developers.</span></span>|  
|[<span data-ttu-id="1b750-118">Microsoft Hilfe- und Supportcenter</span><span class="sxs-lookup"><span data-stu-id="1b750-118">Microsoft Help and Support</span></span>](https://go.microsoft.com/fwlink/?linkid=16419)|<span data-ttu-id="1b750-119">Verwenden Sie diese Website, um sich mit einer Frage an einen Supportmitarbeiter von [!INCLUDE[msCoName](../../includes/msconame-md.md)] zu wenden.</span><span class="sxs-lookup"><span data-stu-id="1b750-119">You can use this Web site to open a case with a [!INCLUDE[msCoName](../../includes/msconame-md.md)] support professional.</span></span>|  
  
  
