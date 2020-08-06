---
title: Reparieren einer Distributed Replay-Installation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 6fcd8ca8-1ceb-457d-9545-096c74e274d7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 57f5b2bde308e48dbf14b52a8b159b30f6a98bc8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620143"
---
# <a name="repair-a-distributed-replay-installation"></a><span data-ttu-id="61f98-102">Reparieren einer Distributed Replay-Installation</span><span class="sxs-lookup"><span data-stu-id="61f98-102">Repair a Distributed Replay Installation</span></span>
  <span data-ttu-id="61f98-103">Zur Reparatur einer Distributed Replay-Komponente (Controller oder Client) gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="61f98-103">Repairing a Distributed Replay component (controller or client) will do the following:</span></span>  
  
1.  <span data-ttu-id="61f98-104">Installieren Sie alle zugehörigen Dateien erneut auf dem Datenträger, und ersetzen Sie dabei alle vorhandenen Dateien.</span><span class="sxs-lookup"><span data-stu-id="61f98-104">Install all associated files on disk again, and replace any existing files.</span></span>  
  
2.  <span data-ttu-id="61f98-105">Wenn das entsprechende Windows-Dienstkonto entfernt wurde, erstellen Sie dieses erneut.</span><span class="sxs-lookup"><span data-stu-id="61f98-105">Recreate the Windows service account if the corresponding service account was removed.</span></span>  
  
 <span data-ttu-id="61f98-106">Über den Reparaturvorgang können Sie Komponenten nicht hinzuzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="61f98-106">You cannot use the Repair operation to add or remove components.</span></span> <span data-ttu-id="61f98-107">Um Komponenten hinzuzufügen oder zu entfernen, aktivieren oder deaktivieren Sie die entsprechende Komponente in der Funktionsstruktur auf der Seite **Funktionsauswahl** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup.</span><span class="sxs-lookup"><span data-stu-id="61f98-107">To add or remove components, check or uncheck the corresponding component in the Feature tree on the **Feature Selection** page in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup.</span></span>  
  
### <a name="to-repair-a-failed-installation-of-distributed-replay"></a><span data-ttu-id="61f98-108">So reparieren Sie eine fehlerhafte Distributed Replay-Installation</span><span class="sxs-lookup"><span data-stu-id="61f98-108">To repair a failed installation of Distributed Replay</span></span>  
  
1.  <span data-ttu-id="61f98-109">Klicken Sie im **Startmenü** auf **Systemsteuerung**, und doppelklicken Sie dann auf **Software.**</span><span class="sxs-lookup"><span data-stu-id="61f98-109">From the **Start** menu, click **Control Panel**, and then double-click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="61f98-110">Wählen Sie [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] im Fenster **Programm deinstallieren oder ändern** aus, und [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Klicken Sie dann im Dialogfeld auf **Reparieren**.</span><span class="sxs-lookup"><span data-stu-id="61f98-110">Select [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in the **Uninstall or change a program** window, and then in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] dialog box, click **Repair**.</span></span>  
  
3.  <span data-ttu-id="61f98-111">Führen Sie die Schritte im [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Assistenten aus, und wählen Sie auf der Seite **Features auswählen** die Distributed Replay Komponenten aus, die Sie reparieren möchten, und klicken Sie dann auf **Weiter.**</span><span class="sxs-lookup"><span data-stu-id="61f98-111">Follow the steps in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] wizard, and on the **Select Features** page, select the Distributed Replay components you want to repair, and then click **Next.**.</span></span>  
  
4.  <span data-ttu-id="61f98-112">Schließen Sie den [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]-Installations-Assistenten ab, um die ausgewählten Distributed Replay-Funktionen zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="61f98-112">Complete the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Installation Wizard to repair the selected Distributed Replay features.</span></span>  
  
  
