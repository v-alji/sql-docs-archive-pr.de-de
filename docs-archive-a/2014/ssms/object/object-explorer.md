---
title: Objekt-Explorer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.objectexplorer.commandsoptions
- SQL12.SWB.SQLSERVEROBJECTEXPLORER.DHELP
- sql12.swb.objectexplorer.scriptingoptions
- sql12.swb.oe.f1
helpviewer_keywords:
- multi-select [SQL Server Management Studio]
- Registered Servers [SQL Server], Object Explorer
- Query Editor [SQL Server Management Studio], Object Explorer
- connections [SQL Server], SQL Server Management Studio
- servers [SQL Server], Registered Servers
- Object Explorer
- SQL Server Management Studio [SQL Server], connections
- viewing objects
- filtering objects [SQL Server]
- Object Explorer, about Object Explorer
ms.assetid: 469ea8e2-79b9-44c8-bb6f-f0e1c5dbf0f2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3acefcd03af1b39d467625800d8837553ff5253b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618440"
---
# <a name="object-explorer"></a><span data-ttu-id="1a9f1-102">Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="1a9f1-102">Object Explorer</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="1a9f1-103">bietet Funktionen zum Verwalten von Objekten in Instanzen von [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]und [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-103">provides features for managing objects in instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
## <a name="benefits-of-object-explorer"></a><span data-ttu-id="1a9f1-104">Vorteile des Objekt-Explorers</span><span class="sxs-lookup"><span data-stu-id="1a9f1-104">Benefits of Object Explorer</span></span>  
 <span data-ttu-id="1a9f1-105">Der Objekt-Explorer stellt eine hierarchische Benutzeroberfläche zum Anzeigen und Verwalten der Objekte in allen Instanzen von SQL Server bereit.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-105">Object Explorer provides a hierarchical user interface to view and manage the objects in each instance of SQL Server.</span></span> <span data-ttu-id="1a9f1-106">Der Bereich "Details zum Objekt-Explorer" stellt eine tabellarische Ansicht der Instanzobjekte sowie eine Funktion zum Suchen bestimmter Objekte zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-106">The Object Explorer Details pane presents a tabular view of instance objects, and the capability to search for specific objects.</span></span> <span data-ttu-id="1a9f1-107">Die Funktionalität des Objekt-Explorers variiert abhängig vom Servertyp, enthält aber im Allgemeinen die Entwicklungsfunktionen für Datenbanken und die Verwaltungsfunktionen für alle Servertypen.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-107">The capabilities of Object Explorer vary slightly depending on the type of server, but generally include the development features for databases, and management features for all server types.</span></span>  
  
## <a name="object-explorer-tasks"></a><span data-ttu-id="1a9f1-108">Objekt-Explorer-Tasks</span><span class="sxs-lookup"><span data-stu-id="1a9f1-108">Object Explorer Tasks</span></span>  
  
|<span data-ttu-id="1a9f1-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1a9f1-109">Description</span></span>|<span data-ttu-id="1a9f1-110">Thema</span><span class="sxs-lookup"><span data-stu-id="1a9f1-110">Topic</span></span>|  
|-----------------|-----------|  
|<span data-ttu-id="1a9f1-111">Beschreibt, wie der Objekt-Explorer geöffnet wird und die Optionen konfiguriert werden, die das Verhalten des Explorers festlegen.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-111">Describes how to open the Object Explorer and configure the options that define the behavior of the explorer.</span></span>|[<span data-ttu-id="1a9f1-112">Öffnen und Konfigurieren des Objekt-Explorers</span><span class="sxs-lookup"><span data-stu-id="1a9f1-112">Open and Configure Object Explorer</span></span>](open-and-configure-object-explorer.md)|  
|<span data-ttu-id="1a9f1-113">Beschreibt, wie der Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]und [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]herstellt.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-113">Describes how to connect Object Explorer to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span>|[<span data-ttu-id="1a9f1-114">Verbinden mit einer Instanz mit dem Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="1a9f1-114">Connect to an Instance From Object Explorer</span></span>](connect-to-an-instance-from-object-explorer.md)|  
|<span data-ttu-id="1a9f1-115">Beschreibt, wie Objekte, die als Knoten in der Objekt-Explorer-Hierarchie dargestellt sind, verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-115">Describes how to manage objects represented as nodes in the Object Explorer hierarchy.</span></span>|[<span data-ttu-id="1a9f1-116">Verwalten von Objekten mittels Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="1a9f1-116">Manage Objects by Using Object Explorer</span></span>](manage-objects-by-using-object-explorer.md)|  
|<span data-ttu-id="1a9f1-117">Beschreibt den Bereich "Details zum Objekt-Explorer", eine tabellarische Ansicht aller Objekte im Server mit einer Benutzeroberfläche zu deren Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-117">Describes the Object Explorer Details Pane, a tabular view of all of the objects in the server with a user interface to manage them.</span></span>|[<span data-ttu-id="1a9f1-118">Bereich mit Details zum Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="1a9f1-118">Object Explorer Details Pane</span></span>](object-explorer-details-pane.md)|  
|<span data-ttu-id="1a9f1-119">Beschreibt Möglichkeiten zum Ausführen benutzerdefinierter Berichte in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-119">Describes ways to run custom reports in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>|[<span data-ttu-id="1a9f1-120">Benutzerdefinierte Berichte in Management Studio</span><span class="sxs-lookup"><span data-stu-id="1a9f1-120">Custom Reports in Management Studio</span></span>](custom-reports-in-management-studio.md)|  
  
  
