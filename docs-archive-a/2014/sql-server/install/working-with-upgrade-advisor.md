---
title: Arbeiten mit Upgrade Advisor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server], when to use
- SQL Server Upgrade Advisor, when to use
- when to use Upgrade Advisor
ms.assetid: 5f26a7b9-1ac2-442c-8316-87b078db3baf
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 75a16e57734493cdd7ac00e7bad3124eb7a99d84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617374"
---
# <a name="working-with-upgrade-advisor"></a><span data-ttu-id="844bf-102">Arbeiten mit dem Upgrade Advisor</span><span class="sxs-lookup"><span data-stu-id="844bf-102">Working with Upgrade Advisor</span></span>
  <span data-ttu-id="844bf-103">Um sicherzustellen, dass das Upgrade auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] erfolgreich ist, stellt der Upgrade Advisor eine zentrale Konsole zum Identifizieren zu behebender Probleme in Ihren Installationen bereit, bevor Sie ein Upgrade auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] durchführen.</span><span class="sxs-lookup"><span data-stu-id="844bf-103">To help ensure that your upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] is successful, Upgrade Advisor provides a central console to identify issues to address in your installations before upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="844bf-104">Mit dem Upgrade Advisor können die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="844bf-104">You can use Upgrade Advisor to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="844bf-105">Analysieren Sie Komponenten früherer Versionen auf lokalen oder Remoteservern.</span><span class="sxs-lookup"><span data-stu-id="844bf-105">Analyze previous version's components on local or remote servers.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="844bf-106">Sie können keine Remoteinstanzen von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] analysieren.</span><span class="sxs-lookup"><span data-stu-id="844bf-106">You cannot analyze remote instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="844bf-107">Zeigen Sie die Ergebnisse der Analyse an.</span><span class="sxs-lookup"><span data-stu-id="844bf-107">View the results of the analysis.</span></span>  
  
 <span data-ttu-id="844bf-108">Der Upgrade Advisor umfasst einen Analyzer und einen Viewer.</span><span class="sxs-lookup"><span data-stu-id="844bf-108">Upgrade Advisor includes an analyzer and a viewer.</span></span> <span data-ttu-id="844bf-109">Der Analyse-Assistent des Upgrade Advisors analysiert die Komponenten, die Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="844bf-109">The Upgrade Advisor Analysis Wizard analyzes the components you select.</span></span> <span data-ttu-id="844bf-110">Der Analyzer generiert dann benutzerdefinierte Berichte über Probleme, die Sie beheben müssen, bevor Sie auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="844bf-110">The analyzer then generates custom reports about issues that you must handle before you can upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="844bf-111">Mit dem Berichts-Viewer des Upgrade Advisors zeigen Sie die benutzerdefinierten Berichte an.</span><span class="sxs-lookup"><span data-stu-id="844bf-111">You use the Upgrade Advisor Report Viewer to view the custom reports.</span></span> <span data-ttu-id="844bf-112">Weitere Informationen zu den von der Analyse des Upgrade Advisors erkannten Informationen finden Sie unter [Beheben von Upgradeproblemen](../../../2014/sql-server/install/resolving-upgrade-issues.md).</span><span class="sxs-lookup"><span data-stu-id="844bf-112">For more information about what Upgrade Advisor analysis detects, see [Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md).</span></span>  
  
 <span data-ttu-id="844bf-113">Die Themen in diesem Abschnitt bieten eine Übersicht über die Funktionen des Upgrade Advisors und Informationen zur Verwendung von Upgrade Advisor-und Upgrade Advisor-Berichten.</span><span class="sxs-lookup"><span data-stu-id="844bf-113">The topics in this section provide an overview of Upgrade Advisor functionality and information about how to use Upgrade Advisor and Upgrade Advisor reports.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="844bf-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="844bf-114">In This Section</span></span>  
  
|<span data-ttu-id="844bf-115">Thema</span><span class="sxs-lookup"><span data-stu-id="844bf-115">Topic</span></span>|<span data-ttu-id="844bf-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="844bf-116">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="844bf-117">Übersicht über den Upgrade Advisor</span><span class="sxs-lookup"><span data-stu-id="844bf-117">Overview of Upgrade Advisor</span></span>](../../../2014/sql-server/install/overview-of-upgrade-advisor.md)|<span data-ttu-id="844bf-118">Liefert eine Überblick über den Upgradeprozess, den Analyse-Assistenten und den Berichts-Viewer des Upgrade Advisors.</span><span class="sxs-lookup"><span data-stu-id="844bf-118">Provides an overview of the upgrade process, the Upgrade Advisor Analysis Wizard, and the Upgrade Advisor Report Viewer.</span></span>|  
|[<span data-ttu-id="844bf-119">Themen zur Vorgehensweise für den Upgrade Advisor</span><span class="sxs-lookup"><span data-stu-id="844bf-119">Upgrade Advisor How-to Topics</span></span>](../../../2014/sql-server/install/upgrade-advisor-how-to-topics.md)|<span data-ttu-id="844bf-120">Enthält Anweisungen zur Durchführung allgemeiner Upgrade Advisor-Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="844bf-120">Provides instructions to perform common Upgrade Advisor procedures.</span></span>|  
|[<span data-ttu-id="844bf-121">Benutzeroberflächenreferenz des Upgrade Advisors</span><span class="sxs-lookup"><span data-stu-id="844bf-121">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)|<span data-ttu-id="844bf-122">Enthält Themen, die angezeigt werden, wenn Sie die F1-Taste drücken oder auf den Seiten des Analyse-Assistenten des Upgrade Advisors auf **Hilfe** klicken.</span><span class="sxs-lookup"><span data-stu-id="844bf-122">Contains topics that appear if you press the F1 key or click **Help** on the Upgrade Advisor Analysis Wizard pages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="844bf-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="844bf-123">See Also</span></span>  
 <span data-ttu-id="844bf-124">[Installieren von Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="844bf-124">[Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="844bf-125">Beheben von Upgradeproblemen</span><span class="sxs-lookup"><span data-stu-id="844bf-125">Resolving Upgrade Issues</span></span>](../../../2014/sql-server/install/resolving-upgrade-issues.md)  
  
  
