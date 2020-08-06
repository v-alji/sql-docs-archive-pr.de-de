---
title: Installieren von SQL Server 2014-Wartungs Updates | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 7d6c962b-c8d0-49f7-a2ac-00ad8dca930a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ace0fd187386d9a9d96e82f61d1efaa254f08c6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697114"
---
# <a name="install-sql-server-2014-servicing-updates"></a><span data-ttu-id="7cef7-102">Installieren von SQL Server 2014-Wartungsupdates</span><span class="sxs-lookup"><span data-stu-id="7cef7-102">Install SQL Server 2014 Servicing Updates</span></span>
  <span data-ttu-id="7cef7-103">Dieses Thema enthält Informationen zum Installieren von Updates für [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7cef7-103">This topic provides information about installing updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="7cef7-104">In diesem Abschnitt finden Sie Informationen zu den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="7cef7-104">This section provides information about the following:</span></span>  
  
-   <span data-ttu-id="7cef7-105">Installieren von Updates für [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] während einer neuen Installation</span><span class="sxs-lookup"><span data-stu-id="7cef7-105">Installing updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] during a new installation</span></span>  
  
-   <span data-ttu-id="7cef7-106">Installieren von Updates für [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , nachdem es bereits installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7cef7-106">Installing updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] after it has already been installed.</span></span>  
  
 <span data-ttu-id="7cef7-107">Es empfiehlt sich, dass Kunden neue [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Updates zeitnah bewerten und installieren, um sicherzustellen, dass Systeme mit den letzten Sicherheitsupdates aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="7cef7-107">We recommend that customers evaluate and install latest [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] updates in a timely manner to make sure that systems are up-to-date with the most recent security updates.</span></span>  
  
## <a name="installing-updates-for-sscurrent-during-a-new-installation"></a><span data-ttu-id="7cef7-108">Installieren von Updates für [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] während einer neuen Installation</span><span class="sxs-lookup"><span data-stu-id="7cef7-108">Installing Updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] During a New Installation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7cef7-109">-Setup integriert die neuesten Produktupdates in die Installation des Hauptprodukts, sodass das Hauptprodukt und geeignete Updates gleichzeitig installiert werden.</span><span class="sxs-lookup"><span data-stu-id="7cef7-109">setup integrates the latest product updates with the main product installation so that the main product and its applicable updates are installed at the same time.</span></span> <span data-ttu-id="7cef7-110">Das Produktupdate kann an folgenden Orten nach anwendbaren Updates suchen:</span><span class="sxs-lookup"><span data-stu-id="7cef7-110">Product Update can search for the applicable updates from:</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="7cef7-111">Update</span><span class="sxs-lookup"><span data-stu-id="7cef7-111">Update</span></span>  
  
-   <span data-ttu-id="7cef7-112">Windows Server Update Services (WSUS)</span><span class="sxs-lookup"><span data-stu-id="7cef7-112">Windows Server Update Services (WSUS)</span></span>  
  
-   <span data-ttu-id="7cef7-113">Ein lokaler Ordner</span><span class="sxs-lookup"><span data-stu-id="7cef7-113">A local folder</span></span>  
  
-   <span data-ttu-id="7cef7-114">Eine Netzwerkfreigabe</span><span class="sxs-lookup"><span data-stu-id="7cef7-114">A network share</span></span>  
  
 <span data-ttu-id="7cef7-115">Nachdem Setup die neuesten Versionen der anwendbaren Updates gefunden hat, lädt es diese herunter und integriert sie in den aktuellen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Installationsvorgang.</span><span class="sxs-lookup"><span data-stu-id="7cef7-115">After Setup finds the latest versions of the applicable updates, it downloads and integrates them with the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup process.</span></span> <span data-ttu-id="7cef7-116">Produktupdate kann ein kumulatives Update, Service Pack oder Service Pack plus kumulatives Update enthalten.</span><span class="sxs-lookup"><span data-stu-id="7cef7-116">Product Update can include a cumulative update, service pack, or service pack plus cumulative update.</span></span> <span data-ttu-id="7cef7-117">Die Produkt Update Funktionalität ist eine Erweiterung der [slipstreamfunktionalität](https://go.microsoft.com/fwlink/?LinkId=219945) , die in PCU1 verfügbar war [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7cef7-117">Product Update functionality is an extension of the [Slipstream Functionality](https://go.microsoft.com/fwlink/?LinkId=219945) that was available in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] PCU1.</span></span>  
  
## <a name="installing-updates-for-sscurrent-after-it-has-already-been-installed"></a><span data-ttu-id="7cef7-118">Installieren von Updates für [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , nachdem es bereits installiert wurde</span><span class="sxs-lookup"><span data-stu-id="7cef7-118">Installing Updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] after it has already been installed</span></span>  
 <span data-ttu-id="7cef7-119">Auf einer installierten Instanz von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] empfiehlt es sich, alle verfügbaren Updates anzuwenden: allgemeine Verteilungs Releases (Updates der DDR-Sicherheit/kritisch), Service Packs (SP) und das neueste verfügbare kumulative Update (Cu).</span><span class="sxs-lookup"><span data-stu-id="7cef7-119">On an installed instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], we recommend that you apply all available updates: General Distribution Releases (GDR - security/critical updates), Service Packs (SP), as well as the latest available Cumulative Update (CU).</span></span>  
  
 <span data-ttu-id="7cef7-120">Abhängig vom Typ der Wartungsversion sind SQL Server Updates über Microsoft Update (MU), das Microsoft Download Center und/oder den Support Services-hotfixserver verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7cef7-120">Depending on the type of servicing release, SQL Server updates are available via Microsoft Update (MU), the Microsoft Download Center, and/or the Customer Support Services hotfix Server.</span></span> <span data-ttu-id="7cef7-121">Sicherheits-und kritische Updates für SQL Server werden automatisch von Microsoft Update bereitgestellt (damit Sie diese Updates anzeigen können, müssen Sie sich in mu durch Windows Update in der Systemsteuerung anmelden).</span><span class="sxs-lookup"><span data-stu-id="7cef7-121">Security and Critical updates for SQL Server are automatically provided by Microsoft Update (to be able to see these updates you need to opt-in to MU through Windows Update in Control panel).</span></span> <span data-ttu-id="7cef7-122">Service Packs sind auf Mu als optionale/wichtige Downloads und im Download Center verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7cef7-122">Service Packs are available on MU as Optional/Important downloads as well as the Download Center.</span></span> <span data-ttu-id="7cef7-123">Kumulative Updates sind auf dem Microsoft Hotfix-Download Server verfügbar, der in Cu Knowledge Base-Artikeln bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7cef7-123">Cumulative updates are available on the Microsoft hotfix download server provided in CU Knowledge Base articles.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cef7-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7cef7-124">See Also</span></span>  
 <span data-ttu-id="7cef7-125">[Installieren Sie SQL Server 2014 über den Installations-Assistenten &#40;Setup&#41;](install-sql-server-from-the-installation-wizard-setup.md) </span><span class="sxs-lookup"><span data-stu-id="7cef7-125">[Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](install-sql-server-from-the-installation-wizard-setup.md) </span></span>  
 <span data-ttu-id="7cef7-126">[Durch das Installieren von Updates von der Eingabeaufforderung](installing-updates-from-the-command-prompt.md) werden [Funktionen zu einer Instanz von SQL Server 2014 &#40;Setup hinzugefügt&#41;](add-features-to-an-instance-of-sql-server-setup.md) </span><span class="sxs-lookup"><span data-stu-id="7cef7-126">[Installing updates from the command prompt](installing-updates-from-the-command-prompt.md) [Add Features to an Instance of SQL Server 2014 &#40;Setup&#41;](add-features-to-an-instance-of-sql-server-setup.md) </span></span>  
 [<span data-ttu-id="7cef7-127">Entfernen einer SQL Server 2014-Installation</span><span class="sxs-lookup"><span data-stu-id="7cef7-127">Drop a SQL Server 2014 Installation</span></span>](repair-a-failed-sql-server-installation.md)  
  
  
