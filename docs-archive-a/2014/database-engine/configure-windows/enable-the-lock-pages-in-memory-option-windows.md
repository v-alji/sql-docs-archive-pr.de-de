---
title: Aktivieren der Option „Sperren von Seiten im Speicher“ (Windows) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Lock Pages in Memory option
ms.assetid: cd581fbc-4747-439e-87f9-2f18e39c5bb9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 13290940c3a94a7ba79582d892a5e28670f24b29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618273"
---
# <a name="enable-the-lock-pages-in-memory-option-windows"></a><span data-ttu-id="6d090-102">Aktivieren der Option Sperren von Seiten im Speicher (Windows)</span><span class="sxs-lookup"><span data-stu-id="6d090-102">Enable the Lock Pages in Memory Option (Windows)</span></span>
  <span data-ttu-id="6d090-103">Mit dieser Windows-Richtlinie werden die Konten bestimmt, die einen Prozess zum Speichern von Daten im physischen Speicher verwenden können, um das systemgesteuerte Auslagern der Daten in den virtuellen Arbeitsspeicher zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="6d090-103">This Windows policy determines which accounts can use a process to keep data in physical memory, preventing the system from paging the data to virtual memory on disk.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6d090-104">Durch Sperren von Seiten im Arbeitsspeicher kann die Leistung bei der Auslagerung von Arbeitsspeicherdaten auf die Festplatte gesteigert werden.</span><span class="sxs-lookup"><span data-stu-id="6d090-104">Locking pages in memory may boost performance when paging memory to disk is expected.</span></span>  
  
 <span data-ttu-id="6d090-105">Verwenden Sie das Windows-Tool für Gruppenrichtlinien (gpedit.msc), um diese Richtlinie für das von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verwendete Konto zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6d090-105">Use the Windows Group Policy tool (gpedit.msc) to enable this policy for the account used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6d090-106">Diese Richtlinie können Sie nur ändern, wenn Sie als Systemadministrator angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="6d090-106">You must be a system administrator to change this policy.</span></span>  
  
### <a name="to-enable-the-lock-pages-in-memory-option"></a><span data-ttu-id="6d090-107">So aktivieren Sie die Option "Sperren von Seiten im Speicher"</span><span class="sxs-lookup"><span data-stu-id="6d090-107">To enable the lock pages in memory option</span></span>  
  
1.  <span data-ttu-id="6d090-108">Klicken Sie im Menü **Start** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6d090-108">On the **Start** menu, click **Run**.</span></span> <span data-ttu-id="6d090-109">Geben Sie im Feld **Öffnen** den Text ein `gpedit.msc` .</span><span class="sxs-lookup"><span data-stu-id="6d090-109">In the **Open** box, type `gpedit.msc`.</span></span>  
  
2.  <span data-ttu-id="6d090-110">Erweitern Sie in der Konsole **Editor für lokale Gruppenrichtlinien** die Option **Computerkonfiguration**und dann **Windows-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="6d090-110">On the **Local Group Policy Editor** console, expand **Computer Configuration**, and then expand **Windows Settings**.</span></span>  
  
3.  <span data-ttu-id="6d090-111">Erweitern Sie **Sicherheitseinstellungen**und dann **Lokale Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="6d090-111">Expand **Security Settings**, and then expand **Local Policies**.</span></span>  
  
4.  <span data-ttu-id="6d090-112">Wählen Sie den Ordner **Zuweisen von Benutzerrechten** aus.</span><span class="sxs-lookup"><span data-stu-id="6d090-112">Select the **User Rights Assignment** folder.</span></span>  
  
     <span data-ttu-id="6d090-113">Die Richtlinien werden im Detailbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d090-113">The policies will be displayed in the details pane.</span></span>  
  
5.  <span data-ttu-id="6d090-114">Doppelklicken Sie im Detailbereich auf **Sperren von Seiten im Speicher**.</span><span class="sxs-lookup"><span data-stu-id="6d090-114">In the pane, double-click **Lock pages in memory**.</span></span>  
  
6.  <span data-ttu-id="6d090-115">Klicken Sie im Dialogfeld **Lokale Sicherheitseinstellung > Sperren von Seiten im Speicher** auf **Benutzer oder Gruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="6d090-115">In the **Local Security Setting - Lock pages in memory** dialog box, click **Add User or Group**.</span></span>  
  
7.  <span data-ttu-id="6d090-116">Fügen Sie im Dialogfeld zum Auswählen von Benutzern, Dienstkonten oder Gruppen ein Konto mit Privilegien zum Ausführen von **sqlservr.exe** hinzu.</span><span class="sxs-lookup"><span data-stu-id="6d090-116">In the **Select Users, Service Accounts, or Groups** dialog box, add an account with privileges to run sqlservr.exe.</span></span>  
  
8.  <span data-ttu-id="6d090-117">Melden Sie sich ab und anschließend erneut an, damit die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="6d090-117">Log out and then log back in for this change to take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d090-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6d090-118">See Also</span></span>  
 [<span data-ttu-id="6d090-119">Serverkonfigurationsoptionen für den Serverarbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="6d090-119">Server Memory Server Configuration Options</span></span>](server-memory-server-configuration-options.md)  
  
  
