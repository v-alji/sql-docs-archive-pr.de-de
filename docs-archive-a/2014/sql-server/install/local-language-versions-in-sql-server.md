---
title: Lokale Sprachversionen in SQL Server | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 20b99363-0490-4aa3-9a3d-262f827d81e8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 646ffaed1e4b709c2c26030379f0a7f223f221e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697397"
---
# <a name="local-language-versions-in-sql-server"></a><span data-ttu-id="96c4e-102">Lokale Sprachversionen in SQL Server</span><span class="sxs-lookup"><span data-stu-id="96c4e-102">Local Language Versions in SQL Server</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="96c4e-103">unterstützt alle Sprachen, die von Windows-Betriebssystemen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="96c4e-103">supports all languages that are supported by Windows operating systems.</span></span>  
  
## <a name="cross-language-support"></a><span data-ttu-id="96c4e-104">Sprachübergreifende Unterstützung</span><span class="sxs-lookup"><span data-stu-id="96c4e-104">Cross-Language Support</span></span>  
  
-   <span data-ttu-id="96c4e-105">Die englische Sprachversion von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird für alle lokalisierten Betriebssystemversionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="96c4e-105">The English-language version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is supported on all localized versions of operating systems.</span></span>  
  
-   <span data-ttu-id="96c4e-106">Lokalisierte Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] werden durch die Verwendung der MUI (Multilingual User Interface Pack)-Einstellungen von Windows unter lokalisierten Betriebssystemen in der entsprechenden Sprache sowie unter englischsprachigen Versionen der unterstützten Betriebssysteme unterstützt.</span><span class="sxs-lookup"><span data-stu-id="96c4e-106">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are supported on localized operating systems with the corresponding language or on English-language versions of supported operating systems by using the Windows Multilingual User Interface Pack (MUI) settings.</span></span> <span data-ttu-id="96c4e-107">Weitere Informationen finden Sie unter [Configure Operating System to Support Localized Versions](../../../2014/sql-server/install/local-language-versions-in-sql-server.md#BK_ConfigureOS).</span><span class="sxs-lookup"><span data-stu-id="96c4e-107">For more information, see [Configure Operating System to Support Localized Versions](../../../2014/sql-server/install/local-language-versions-in-sql-server.md#BK_ConfigureOS).</span></span>  
  
-   <span data-ttu-id="96c4e-108">Lokalisierte Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] können ausschließlich auf lokalisierte Versionen in derselben Sprache aktualisiert werden, nicht jedoch auf die englischsprachige Version.</span><span class="sxs-lookup"><span data-stu-id="96c4e-108">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can only be upgraded to localized versions of the same language, and cannot be upgraded to the English-language version.</span></span>  
  
-   <span data-ttu-id="96c4e-109">Lokalisierte Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] können auch parallel mit englischsprachigen Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]installiert werden.</span><span class="sxs-lookup"><span data-stu-id="96c4e-109">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can also be installed side by side with English-language instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="configure-operating-system-to-support-localized-versions"></a><a name="BK_ConfigureOS"></a> <span data-ttu-id="96c4e-110">Configure Operating System to Support Localized Versions</span><span class="sxs-lookup"><span data-stu-id="96c4e-110">Configure Operating System to Support Localized Versions</span></span>  
 <span data-ttu-id="96c4e-111">Lokalisierte Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] werden in englischsprachigen Versionen der unterstützten Betriebssysteme durch die MUI-Einstellungen (Multilingual User Interface Pack) von Windows unterstützt.</span><span class="sxs-lookup"><span data-stu-id="96c4e-111">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are supported on English-language versions of supported operating systems through the use of Windows Multilingual User Interface Pack (MUI) settings.</span></span>  
  
 <span data-ttu-id="96c4e-112">Sie müssen jedoch bestimmte Betriebssystemeinstellungen überprüfen, bevor Sie eine lokalisierte Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf einem Server installieren, auf dem ein englischsprachiges Betriebssystem mit einer anderen MUI-Einstellung als Englisch ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="96c4e-112">However, you must verify certain operating system settings before installing a localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on a server that is running an English-language operating system with a non-English MUI setting.</span></span> <span data-ttu-id="96c4e-113">Die folgenden Betriebssystemeinstellungen müssen der Sprache der zu installierenden lokalisierten Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] angepasst werden:</span><span class="sxs-lookup"><span data-stu-id="96c4e-113">You need to verify that the following operating system settings match the language of the localized [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to be installed:</span></span>  
  
-   <span data-ttu-id="96c4e-114">Die Einstellung für die Benutzeroberfläche des Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="96c4e-114">The operating system user interface setting</span></span>  
  
-   <span data-ttu-id="96c4e-115">Die Einstellung für das Benutzergebietsschema des Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="96c4e-115">The operating system user locale setting</span></span>  
  
-   <span data-ttu-id="96c4e-116">Die Einstellung für das Systemgebietsschema</span><span class="sxs-lookup"><span data-stu-id="96c4e-116">The system locale setting</span></span>  
  
 <span data-ttu-id="96c4e-117">Legen Sie mithilfe der folgenden Prozeduren diese Betriebssystemeinstellungen richtig fest, wenn die Einstellungen nicht der Sprache der zu installierenden lokalisierten Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] entsprechen.</span><span class="sxs-lookup"><span data-stu-id="96c4e-117">If the settings do not match the language of the localized [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to be installed, then use the following procedures to correctly set these operating system settings.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="96c4e-118">Installationen verschiedener Sprachversionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanzen auf demselben Computer werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="96c4e-118">Installations of different language versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances on the same computer are not supported.</span></span>  
  
#### <a name="to-change-the-operating-system-user-interface-setting"></a><span data-ttu-id="96c4e-119">So ändern Sie die Betriebssystemeinstellung für die Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="96c4e-119">To change the operating system user interface setting</span></span>  
  
1.  <span data-ttu-id="96c4e-120">Installieren Sie ggf. das Betriebssystem-MUI, das Ihrer lokalisierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Version entspricht.</span><span class="sxs-lookup"><span data-stu-id="96c4e-120">If not already installed, install the operating system MUI that matches your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="96c4e-121">Öffnen Sie in der Systemsteuerung **Regions- und Sprachoptionen**.</span><span class="sxs-lookup"><span data-stu-id="96c4e-121">In Control Panel, open **Regional and Language Options**.</span></span>  
  
3.  <span data-ttu-id="96c4e-122">Wählen Sie auf der Registerkarte **Sprachen** für **Sprache für Menüs und Dialogfelder**einen Wert aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="96c4e-122">On the **Languages** tab, for **Language used in menus and dialogs**, select a value from the list.</span></span>  
  
     <span data-ttu-id="96c4e-123">Diese Einstellung hat Auswirkungen auf die Sprache der Benutzeroberfläche von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Sie muss daher Ihrer lokalisierten Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]entsprechen.</span><span class="sxs-lookup"><span data-stu-id="96c4e-123">This setting will affect the user interface language of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], so it must match your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="96c4e-124">Klicken Sie auf **Übernehmen** , um die Änderung zu bestätigen, und dann auf **OK** , um das Fenster zu schließen.</span><span class="sxs-lookup"><span data-stu-id="96c4e-124">Click **Apply** to confirm the change, and **OK** to close the window.</span></span>  
  
#### <a name="to-change-the-operating-system-user-locale-setting"></a><span data-ttu-id="96c4e-125">So ändern Sie die Betriebssystemeinstellung für das Benutzergebietsschema</span><span class="sxs-lookup"><span data-stu-id="96c4e-125">To change the operating system user locale setting</span></span>  
  
1.  <span data-ttu-id="96c4e-126">Installieren Sie ggf. das Betriebssystem-MUI, das Ihrer lokalisierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Version entspricht.</span><span class="sxs-lookup"><span data-stu-id="96c4e-126">If not already installed, install the operating system MUI that matches your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="96c4e-127">Öffnen Sie in der Systemsteuerung **Regions- und Sprachoptionen**.</span><span class="sxs-lookup"><span data-stu-id="96c4e-127">In Control Panel, open **Regional and Language Options**.</span></span>  
  
3.  <span data-ttu-id="96c4e-128">Wählen Sie auf der Registerkarte **Regionale Einstellungen** für **Wählen Sie ein Element, um dessen Einstellungen anzuzeigen**einen Wert aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="96c4e-128">On the **Regional Options** tab, for **Select an item to match its preferences**, select a value from the list.</span></span>  
  
     <span data-ttu-id="96c4e-129">Diese Einstellung betrifft die länderspezifische Datumsformatierung.</span><span class="sxs-lookup"><span data-stu-id="96c4e-129">This setting will affect culture-specific data formatting.</span></span>  
  
4.  <span data-ttu-id="96c4e-130">Klicken Sie auf **Übernehmen** , um die Änderung zu bestätigen, und dann auf **OK** , um das Fenster zu schließen.</span><span class="sxs-lookup"><span data-stu-id="96c4e-130">Click **Apply** to confirm the change, and **OK** to close the window.</span></span>  
  
#### <a name="to-change-the-system-locale-setting"></a><span data-ttu-id="96c4e-131">So ändern Sie die Einstellung für das Systemgebietsschema</span><span class="sxs-lookup"><span data-stu-id="96c4e-131">To change the system locale setting</span></span>  
  
1.  <span data-ttu-id="96c4e-132">Installieren Sie ggf. das Betriebssystem-MUI, das Ihrer lokalisierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Version entspricht.</span><span class="sxs-lookup"><span data-stu-id="96c4e-132">If not already installed, install the operating system MUI that matches your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="96c4e-133">Öffnen Sie in der Systemsteuerung **Regions- und Sprachoptionen**.</span><span class="sxs-lookup"><span data-stu-id="96c4e-133">In Control Panel, open **Regional and Language Options**.</span></span>  
  
3.  <span data-ttu-id="96c4e-134">Wählen Sie auf der Registerkarte **Erweitert** für **Wählen Sie die Sprachversion der Programme aus, die Unicode nicht unterstützen**einen Wert aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="96c4e-134">On the **Advanced** tab, for **Select a language to match the language version of the non-Unicode programs you want to use**, select a value from the list.</span></span>  
  
     <span data-ttu-id="96c4e-135">Diese Einstellung ermöglicht es dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Setup, die beste Standardsortierung für Ihre [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Installation auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="96c4e-135">This setting will allow [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup to choose the best default collation for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span>  
  
4.  <span data-ttu-id="96c4e-136">Klicken Sie auf **Übernehmen** , um die Änderung zu bestätigen, und dann auf **OK** , um das Fenster zu schließen.</span><span class="sxs-lookup"><span data-stu-id="96c4e-136">Click **Apply** to confirm the change, and **OK** to close the window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96c4e-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="96c4e-137">See Also</span></span>  
 <span data-ttu-id="96c4e-138">[Hardware-und Software Anforderungen für die Installation von SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="96c4e-138">[Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md) </span></span>  
 [<span data-ttu-id="96c4e-139">Installieren von SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="96c4e-139">Install SQL Server 2014</span></span>](../../database-engine/install-windows/install-sql-server.md)  
  
  
