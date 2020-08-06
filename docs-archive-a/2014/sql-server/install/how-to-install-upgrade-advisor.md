---
title: 'Vorgehensweise: Installieren des Upgrade Advisors | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- Setup [Upgrade Advisor]
- SQL Server Upgrade Advisor, installing
- Upgrade Advisor [SQL Server], installing
ms.assetid: 481b0704-ce79-4543-b141-67306128aa2b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 3ed5b66522126bfabc94bfa8036ec6c31ac04500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621845"
---
# <a name="how-to-install-upgrade-advisor"></a><span data-ttu-id="1f42b-102">Gewusst wie: Installieren des Upgrade Advisors</span><span class="sxs-lookup"><span data-stu-id="1f42b-102">How to: Install Upgrade Advisor</span></span>
  <span data-ttu-id="1f42b-103">Upgrade Advisor unterstützt die Remoteanalyse aller unterstützten Komponenten mit Ausnahme von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f42b-103">Upgrade Advisor supports remote analysis of all supported components except [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="1f42b-104">Wenn Sie keine Instanzen von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] scannen, können Sie den Upgrade Advisor auf einem beliebigen Computer installieren, der eine Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="1f42b-104">If you are not scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can install Upgrade Advisor on any computer that can connect to your instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1f42b-105">Der Computer muss zudem die Voraussetzungen für den Upgrade Advisor erfüllen.</span><span class="sxs-lookup"><span data-stu-id="1f42b-105">The computer must also meet Upgrade Advisor prerequisites.</span></span> <span data-ttu-id="1f42b-106">Wenn Sie Instanzen von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] scannen, müssen Sie den Upgrade Advisor auf dem Berichtsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="1f42b-106">If you are scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must install Upgrade Advisor on the report server.</span></span>  
  
 <span data-ttu-id="1f42b-107">Weitere Informationen finden Sie unter [Installieren des Upgrade Advisors](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="1f42b-107">For more information, see [Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span></span>  
  
### <a name="to-install-upgrade-advisor"></a><span data-ttu-id="1f42b-108">So installieren Sie den Upgrade Advisor</span><span class="sxs-lookup"><span data-stu-id="1f42b-108">To install Upgrade Advisor</span></span>  
  
1.  <span data-ttu-id="1f42b-109">Starten Sie die Installation mithilfe einer der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="1f42b-109">Start the installation using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="1f42b-110">Wenn Sie von der Website installieren [!INCLUDE[msCoName](../../includes/msconame-md.md)] , klicken Sie auf den Link **Download** , und klicken Sie dann auf die Schaltfläche **Ausführen** , um die Installation zu starten.</span><span class="sxs-lookup"><span data-stu-id="1f42b-110">If you are installing from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Web site, click the **Download** link and then click the **Run** button to start the installation.</span></span>  
  
    -   <span data-ttu-id="1f42b-111">Wenn Sie von einem Produkt Medium installieren, öffnen Sie den Ordner **Redist** , öffnen Sie den Ordner **Upgrade Advisor** , und doppelklicken Sie dann auf **SQLUA.msi**.</span><span class="sxs-lookup"><span data-stu-id="1f42b-111">If you are installing from the product media, open the **redist** folder, open the **Upgrade Advisor** folder, and then double-click **SQLUA.msi**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1f42b-112">Für Upgrade Advisor ist [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework 4 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1f42b-112">Upgrade Advisor requires the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework 4.</span></span> <span data-ttu-id="1f42b-113">Wenn die Anwendung nicht installiert ist oder Sie eine Vorabversion verwenden, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f42b-113">If it is not installed, or if you have a pre-release version, an error message will appear.</span></span> <span data-ttu-id="1f42b-114">Deinstallieren Sie frühere Versionen von [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], und installieren Sie dann die aktuelle Version von .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="1f42b-114">Uninstall any earlier version of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] and then install the latest version of .NET Framework 4.</span></span>  
    >   
    >  <span data-ttu-id="1f42b-115">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom ist eine Voraussetzung für die Installation [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] von Upgrade Advisor und wird vom Upgrade Advisor-Setup nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="1f42b-115">The [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom is a prerequisite for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor, and is not installed by Upgrade Advisor Setup.</span></span> <span data-ttu-id="1f42b-116">Das Setup erfordert, dass Sie das [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom aus dem [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="1f42b-116">The Setup requires you to download and install the [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack.</span></span>  
  
2.  <span data-ttu-id="1f42b-117">Klicken Sie auf der Seite \*\*Willkommen [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] \*\* auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="1f42b-117">On the **Welcome to the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor Setup** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="1f42b-118">Lesen Sie auf der Seite **Lizenzvertrag** den Lizenzvertrag.</span><span class="sxs-lookup"><span data-stu-id="1f42b-118">On the **License Agreement** page, read the license agreement.</span></span> <span data-ttu-id="1f42b-119">Wenn Sie zustimmen, wählen Sie **Ich akzeptiere die Lizenzvereinbarung** aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="1f42b-119">If you agree, select **I accept the license agreement** and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="1f42b-120">Geben Sie auf der Seite **Registrierungsinformationen** ihren Namen und Ihr Unternehmen ein.</span><span class="sxs-lookup"><span data-stu-id="1f42b-120">On the **Registration Information** page, enter your name and company.</span></span>  
  
5.  <span data-ttu-id="1f42b-121">Überprüfen Sie auf der Seite **Funktionsauswahl** den Wert für den **Installationspfad** .</span><span class="sxs-lookup"><span data-stu-id="1f42b-121">On the **Feature Selection** page, review the **Installation path** value.</span></span> <span data-ttu-id="1f42b-122">Verwenden Sie ggf. die Schaltfläche **Durchsuchen** , um den Speicherort zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1f42b-122">If necessary, use the **Browse** button to change the location.</span></span> <span data-ttu-id="1f42b-123">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1f42b-123">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="1f42b-124">Klicken Sie auf der Seite **bereit zum Installieren des Programms** auf **Installieren** , um den Upgrade Advisor zu installieren.</span><span class="sxs-lookup"><span data-stu-id="1f42b-124">On the **Ready to Install the Program** page, click **Install** to install Upgrade Advisor.</span></span>  
  
7.  <span data-ttu-id="1f42b-125">Klicken Sie auf **Fertig stellen**, um den Assistenten zu beenden.</span><span class="sxs-lookup"><span data-stu-id="1f42b-125">Click **Finish** to exit the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f42b-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1f42b-126">See Also</span></span>  
 [<span data-ttu-id="1f42b-127">Voraussetzungen für den Upgrade Advisor</span><span class="sxs-lookup"><span data-stu-id="1f42b-127">Upgrade Advisor Prerequisites</span></span>](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md)  
  
  
