---
title: Installieren von Upgrade Advisor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- Setup [Upgrade Advisor]
- Upgrade Advisor [SQL Server], installing
ms.assetid: 1b7d6eca-1df1-47df-bbba-0fc485706a95
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 40f214b01f3e2066708a060c5f3ad1e8aa4a0a23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697406"
---
# <a name="installing-upgrade-advisor"></a><span data-ttu-id="a9d6f-102">Installieren des Upgrade Advisors</span><span class="sxs-lookup"><span data-stu-id="a9d6f-102">Installing Upgrade Advisor</span></span>
  <span data-ttu-id="a9d6f-103">Der Speicherort für das Installieren des Upgrade Advisors für SQL Server 2014 ist abhängig davon, was analysiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="a9d6f-103">Where you install SQL Server 2014 Upgrade Advisor depends on what you will be analyzing.</span></span> <span data-ttu-id="a9d6f-104">Der Upgrade Advisor unterstützt die Remoteanalyse aller [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Komponenten mit Ausnahme von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9d6f-104">Upgrade Advisor supports remote analysis of all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components except [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="a9d6f-105">Wenn Sie keine Instanzen von Scannen [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , können Sie den Upgrade Advisor auf einem beliebigen Computer installieren, der eine Verbindung mit herstellen kann [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und die die [Voraussetzungen des Upgrade Advisors](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md)erfüllt.</span><span class="sxs-lookup"><span data-stu-id="a9d6f-105">If you are not scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can install Upgrade Advisor on any computer that can connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and that meets the [Upgrade Advisor Prerequisites](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md).</span></span> <span data-ttu-id="a9d6f-106">Wenn Sie Instanzen von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] scannen, müssen Sie den Upgrade Advisor auf dem Berichtsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="a9d6f-106">If you are scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must install Upgrade Advisor on the report server.</span></span>  
  
 <span data-ttu-id="a9d6f-107">Führen Sie die **SQLUA.msi** Datei aus, um den Upgrade Advisor zu installieren.</span><span class="sxs-lookup"><span data-stu-id="a9d6f-107">Run the **SQLUA.msi** file to install Upgrade Advisor.</span></span> <span data-ttu-id="a9d6f-108">Sie können über die Eingabeaufforderung für unbeaufsichtigte und automatisierte Installationen installieren.</span><span class="sxs-lookup"><span data-stu-id="a9d6f-108">You can install from the command prompt for unattended and automated installations.</span></span> <span data-ttu-id="a9d6f-109">Syntax und Beispiele finden Sie [unter Installieren von Upgrade Advisor von der Eingabeaufforderung aus](../../../2014/sql-server/install/installing-upgrade-advisor-from-the-command-prompt.md) .</span><span class="sxs-lookup"><span data-stu-id="a9d6f-109">See [Installing Upgrade Advisor from the Command Prompt](../../../2014/sql-server/install/installing-upgrade-advisor-from-the-command-prompt.md) for syntax and examples.</span></span>  
  
 <span data-ttu-id="a9d6f-110">Rufen Sie die SQLUA.msi auf:</span><span class="sxs-lookup"><span data-stu-id="a9d6f-110">Get SQLUA.msi:</span></span>  
  
-   <span data-ttu-id="a9d6f-111">Im Ordner **Redist** des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Produkt Mediums.</span><span class="sxs-lookup"><span data-stu-id="a9d6f-111">In the **redist** folder of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] product media.</span></span>  
  
-   <span data-ttu-id="a9d6f-112">Als Teil des [SQL 2014 Feature Pack-Downloads](https://www.microsoft.com/download/details.aspx?id=42295).</span><span class="sxs-lookup"><span data-stu-id="a9d6f-112">As part of the [SQL 2014 Feature Pack download](https://www.microsoft.com/download/details.aspx?id=42295).</span></span>  
  
## <a name="uninstalling-upgrade-advisor"></a><span data-ttu-id="a9d6f-113">Deinstallieren des Upgrade Advisors</span><span class="sxs-lookup"><span data-stu-id="a9d6f-113">Uninstalling Upgrade Advisor</span></span>  
 <span data-ttu-id="a9d6f-114">Sie können den Upgrade **Advisor mithilfe der**Option Software deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="a9d6f-114">You can uninstall Upgrade Advisor by using **Add or Remove Programs**.</span></span> <span data-ttu-id="a9d6f-115">Die Syntax der Eingabeaufforderung unterstützt auch das Entfernen/Deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="a9d6f-115">The command prompt syntax also supports removal/uninstall.</span></span>  
  
  
