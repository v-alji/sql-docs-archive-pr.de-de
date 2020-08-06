---
title: sqlagent90-Anwendung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- starting SQL Server Agent
- sqlagent90 application
- SQL Server Agent, starting
- command prompt utilities [SQL Server], sqlagent90
ms.assetid: e8b80e8d-d0c9-4500-a868-0ce08233da08
author: stevestein
ms.author: sstein
ms.openlocfilehash: 290cb69f39aa3b08bb290c210b2d37977614a1ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615724"
---
# <a name="sqlagent90-application"></a><span data-ttu-id="d3f1b-102">sqlagent90 (Anwendung)</span><span class="sxs-lookup"><span data-stu-id="d3f1b-102">sqlagent90 Application</span></span>
  <span data-ttu-id="d3f1b-103">Mit der Anwendung **sqlagent90** wird der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agent über die Eingabeaufforderung gestartet.</span><span class="sxs-lookup"><span data-stu-id="d3f1b-103">The **sqlagent90** application starts [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent from the command prompt.</span></span> <span data-ttu-id="d3f1b-104">Normalerweise sollte der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agent über [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] oder mithilfe von SQL-SMO-Methoden in einer Anwendung gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="d3f1b-104">Usually, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should be run from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or by using SQL-SMO methods in an application.</span></span> <span data-ttu-id="d3f1b-105">Führen Sie **sqlagent90** nur dann über die Eingabeaufforderung aus, wenn Sie Probleme im [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agent diagnostizieren, oder wenn Sie von Ihrem primären Anbieter für technischen Support dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="d3f1b-105">Only run **sqlagent90** from the command prompt when you are diagnosing [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent, or when you are directed to it by your primary support provider.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3f1b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3f1b-106">Syntax</span></span>  
  
```  
  
sqlagent90  
-c [-v] [-iinstance_name]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d3f1b-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="d3f1b-107">Arguments</span></span>  
 <span data-ttu-id="d3f1b-108">**-c**</span><span class="sxs-lookup"><span data-stu-id="d3f1b-108">**-c**</span></span>  
 <span data-ttu-id="d3f1b-109">Zeigt an, dass der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agent über die Eingabeaufforderung ausgeführt wird und unabhängig vom Microsoft Windows-Dienststeuerungs-Manager ist.</span><span class="sxs-lookup"><span data-stu-id="d3f1b-109">Indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent is running from the command prompt and is independent of the Microsoft Windows Services Control Manager.</span></span> <span data-ttu-id="d3f1b-110">Wenn **-c** verwendet wird, kann der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agent weder über die Anwendung Dienste in der Verwaltung noch über den [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Konfigurations-Manager gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="d3f1b-110">When **-c** is used, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent cannot be controlled from either the Services application in Administrative Tools or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="d3f1b-111">Dieses Argument ist verbindlich.</span><span class="sxs-lookup"><span data-stu-id="d3f1b-111">This argument is mandatory.</span></span>  
  
 <span data-ttu-id="d3f1b-112">**-v**</span><span class="sxs-lookup"><span data-stu-id="d3f1b-112">**-v**</span></span>  
 <span data-ttu-id="d3f1b-113">Zeigt an, dass der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agent im ausführlichen Modus ausgeführt wird und dass Diagnoseinformationen im Eingabeaufforderungsfenster ausgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d3f1b-113">Indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent runs in verbose mode and writes diagnostic information to the command-prompt window.</span></span> <span data-ttu-id="d3f1b-114">Die Diagnoseinformationen sind mit den Informationen identisch, die in das Fehlerprotokoll des [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agents geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="d3f1b-114">The diagnostic information is the same as the information written to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent error log.</span></span>  
  
 <span data-ttu-id="d3f1b-115">**-i** *Instanzname*</span><span class="sxs-lookup"><span data-stu-id="d3f1b-115">**-i** *instance_name*</span></span>  
 <span data-ttu-id="d3f1b-116">Zeigt an, dass der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agent eine Verbindung mit der benannten [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Instanz herstellt, die mit *Instanzname*angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d3f1b-116">Indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent connects to the named [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance specified by *instance_name*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3f1b-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d3f1b-117">Remarks</span></span>  
 <span data-ttu-id="d3f1b-118">Nach dem Anzeigen einer Copyrightmeldung zeigt **sqlagent90** Ausgaben nur dann im Eingabeaufforderungsfenster an, wenn der Schalter **-v** angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="d3f1b-118">After displaying a copyright message, **sqlagent90** displays output in the command prompt window only when the **-v** switch is specified.</span></span> <span data-ttu-id="d3f1b-119">Zum Beenden von **sqlagent90**drücken Sie STRG+C an der Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="d3f1b-119">To stop **sqlagent90**, press CTRL+C at the command prompt.</span></span> <span data-ttu-id="d3f1b-120">Schließen Sie das Eingabeaufforderungsfenster nicht, bevor Sie **sqlagent90**beendet haben.</span><span class="sxs-lookup"><span data-stu-id="d3f1b-120">Do not close the command-prompt window before stopping **sqlagent90**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3f1b-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d3f1b-121">See Also</span></span>  
 [<span data-ttu-id="d3f1b-122">Automatisierte Administrationstasks &#40;SQL Server-Agent&#41;</span><span class="sxs-lookup"><span data-stu-id="d3f1b-122">Automated Administration Tasks &#40;SQL Server Agent&#41;</span></span>](../ssms/agent/automated-administration-tasks-sql-server-agent.md)  
  
  
