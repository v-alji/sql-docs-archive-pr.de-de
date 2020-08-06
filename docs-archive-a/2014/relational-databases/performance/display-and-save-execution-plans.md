---
title: Anzeigen und Speichern von Ausführungsplänen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Showplan results
- execution plans [SQL Server]
- queries [SQL Server], tuning
- execution plans [SQL Server], how-to topics
- SQL Server Management Studio [SQL Server], execution plans
- tuning queries [SQL Server]
ms.assetid: bcd6f094-c613-4835-ae19-4caaadb4bb17
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e236ed2a298bc8fc9a829948a864f6f5c27a2ba2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698013"
---
# <a name="display-and-save-execution-plans"></a><span data-ttu-id="0d238-102">Anzeigen und Speichern von Ausführungsplänen</span><span class="sxs-lookup"><span data-stu-id="0d238-102">Display and Save Execution Plans</span></span>
  <span data-ttu-id="0d238-103">In diesem Abschnitt erfahren Sie, wie Ausführungspläne mithilfe von Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]angezeigt und in einer Datei im XML-Format gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="0d238-103">This section explains how to display execution plans and how to save execution plans to a file in XML format by using Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="0d238-104">Ausführungspläne zeigen grafisch an, welche Datenabrufmethoden vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Abfrageoptimierer gewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="0d238-104">Execution plans graphically display the data retrieval methods chosen by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] query optimizer.</span></span> <span data-ttu-id="0d238-105">Ausführungspläne stellen die Ausführungskosten bestimmter Anweisungen und Abfragen in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe von Symbolen dar und nicht in der tabellarischen Form, die von den SET SHOWPLAN_ALL- oder SET SHOWPLAN_TEXT-Anweisungen erzeugt wird.</span><span class="sxs-lookup"><span data-stu-id="0d238-105">Execution plans represent the execution cost of specific statements and queries in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using icons rather than the tabular representation produced by the SET SHOWPLAN_ALL or SET SHOWPLAN_TEXT statements.</span></span> <span data-ttu-id="0d238-106">Durch diese grafische Darstellung sind die Leistungsmerkmale einer Abfrage wesentlich leichter zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="0d238-106">This graphical approach is very useful for understanding the performance characteristics of a query.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0d238-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0d238-107">In This Section</span></span>  
  
-   [<span data-ttu-id="0d238-108">Anzeigen des geschätzten Ausführungsplans</span><span class="sxs-lookup"><span data-stu-id="0d238-108">Display the Estimated Execution Plan</span></span>](display-the-estimated-execution-plan.md)  
  
-   [<span data-ttu-id="0d238-109">Anzeigen eines tatsächlichen Ausführungsplans</span><span class="sxs-lookup"><span data-stu-id="0d238-109">Display an Actual Execution Plan</span></span>](display-an-actual-execution-plan.md)  
  
-   [<span data-ttu-id="0d238-110">Speichern eines Ausführungsplans im XML-Format</span><span class="sxs-lookup"><span data-stu-id="0d238-110">Save an Execution Plan in XML Format</span></span>](save-an-execution-plan-in-xml-format.md)  
  
  
