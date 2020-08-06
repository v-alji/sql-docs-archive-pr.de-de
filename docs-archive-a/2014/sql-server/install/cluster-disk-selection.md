---
title: Cluster Datenträger Auswahl | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- cluster disk selection
ms.assetid: 0d6b863d-5972-4a20-9990-64ee8016fea6
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0f53d6d3f623254d2b17996be7fd5b8235dca223
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617505"
---
# <a name="cluster-disk-selection"></a><span data-ttu-id="1df9a-102">Datenträgerauswahl für Cluster</span><span class="sxs-lookup"><span data-stu-id="1df9a-102">Cluster Disk Selection</span></span>
  <span data-ttu-id="1df9a-103">Verwenden Sie die Seite **Datenträgerauswahl für Cluster** des Installations-Assistenten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , um die freigegebene Cluster-Datenträgerressource für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Failovercluster auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="1df9a-103">Use the **Cluster Disk Selection** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard to select the shared cluster disk resource for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster.</span></span> <span data-ttu-id="1df9a-104">Auf dem Clusterdatenträger werden die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Daten platziert.</span><span class="sxs-lookup"><span data-stu-id="1df9a-104">The cluster disk is where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data will be placed.</span></span>  
  
 <span data-ttu-id="1df9a-105">Ein frei gegebener Cluster Datenträger ist für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] Cluster Installationen nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1df9a-105">A shared cluster disk is not a requirement for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] cluster installations.</span></span> <span data-ttu-id="1df9a-106">Ein SMB-Dateiserver ist ein unterstützter Speicher für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Failoverclusterinstallationen, der auf der Seite **Datenbank-Engine-Datenverzeichnisse** vor Abschluss der Installation angegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="1df9a-106">An SMB file server is a supported storage for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] failover cluster installations, and can be specified by using the **Database Engine - Data Directories** page before completing the installation.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="1df9a-107">Wenn Sie Analysis Services installieren möchten, müssen Sie einen freigegebenen Clusterdatenträger angeben.</span><span class="sxs-lookup"><span data-stu-id="1df9a-107">If you have selected Analysis Services to be installed, you must specify a shared cluster disk.</span></span>  
>   
>  <span data-ttu-id="1df9a-108">Wenn FILESTREAM in dieser [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Failoverclusterinstanz aktiviert werden soll, müssen Sie einen freigegebenen Clusterdatenträger angeben.</span><span class="sxs-lookup"><span data-stu-id="1df9a-108">If you plan to enable FILESTREAM on this [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster instance, you must specify a shared cluster disk.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1df9a-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="1df9a-109">Options</span></span>  
 <span data-ttu-id="1df9a-110">**Freigegebene Datenträger**</span><span class="sxs-lookup"><span data-stu-id="1df9a-110">**Shared Disks**</span></span>  
 <span data-ttu-id="1df9a-111">Wählen Sie einen Datenträger aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="1df9a-111">Select a single disk from the list.</span></span> <span data-ttu-id="1df9a-112">Auf dem Clusterdatenträger werden die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Daten platziert.</span><span class="sxs-lookup"><span data-stu-id="1df9a-112">The cluster disk is where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data will be placed.</span></span>  
  
 <span data-ttu-id="1df9a-113">Es kann nur ein Datenträger angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1df9a-113">Only one disk can be specified.</span></span> <span data-ttu-id="1df9a-114">Wenn Sie die Gruppe mit der Quorumressource des Clusters auswählen, wird eine Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1df9a-114">If you select the group containing the cluster quorum resource, a warning will be displayed.</span></span> <span data-ttu-id="1df9a-115">Von einer Installation in der Quorumressource des Clusters wird abgeraten.</span><span class="sxs-lookup"><span data-stu-id="1df9a-115">We recommend that you do not install to the cluster quorum resource.</span></span>  
  
 <span data-ttu-id="1df9a-116">**Verfügbare freigegebene Datenträger**</span><span class="sxs-lookup"><span data-stu-id="1df9a-116">**Available Shared Disks**</span></span>  
 <span data-ttu-id="1df9a-117">Zeigt eine Liste der verfügbaren Datenträger, Informationen zur Qualifikation der Datenträger als freigegebene Datenträger und eine Beschreibung der einzelnen Datenträgerressourcen an.</span><span class="sxs-lookup"><span data-stu-id="1df9a-117">Displays a list of available disks, whether each is qualified as a shared disk, and a description of each disk resource.</span></span>  
  
  
