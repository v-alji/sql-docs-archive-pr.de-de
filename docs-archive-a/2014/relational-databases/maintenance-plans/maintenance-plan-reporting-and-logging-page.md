---
title: Wartungsplan (Dialogfeld „Berichterstellung und Protokollierung“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.reportinglogging.f1
ms.assetid: 3a30b17a-3deb-446f-900a-62f88934a90f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c7a95a7092ce2cdac4aa0540a5cb57d86b48497
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616527"
---
# <a name="maintenance-plan-reporting-and-logging-page"></a><span data-ttu-id="196f2-102">Wartungsplan (Dialogfeld 'Berichterstellung und Protokollierung')</span><span class="sxs-lookup"><span data-stu-id="196f2-102">Maintenance Plan (Reporting and Logging Page)</span></span>
  <span data-ttu-id="196f2-103">Mit dem Dialogfeld **Berichterstellung und Protokollierung** können Sie die Berichte und Protokolle konfigurieren, die beim Ausführen von Wartungsplänen generiert werden.</span><span class="sxs-lookup"><span data-stu-id="196f2-103">Use the **Reporting and Logging** dialog box to configure the reports and logs that are generated when maintenance plans are executed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="196f2-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="196f2-104">Options</span></span>  
 <span data-ttu-id="196f2-105">**Textdateibericht generieren**</span><span class="sxs-lookup"><span data-stu-id="196f2-105">**Generate a text file report**</span></span>  
 <span data-ttu-id="196f2-106">Mit dieser Option können Sie angeben, ob [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] einen Textdateibericht erstellen soll.</span><span class="sxs-lookup"><span data-stu-id="196f2-106">Specify if you want [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to write a text file report.</span></span>  
  
 <span data-ttu-id="196f2-107">**Neue Datei erstellen**</span><span class="sxs-lookup"><span data-stu-id="196f2-107">**Create a new file**</span></span>  
 <span data-ttu-id="196f2-108">Erstellt eine neue Berichtsdatei für jede Ausführung des Wartungsplans.</span><span class="sxs-lookup"><span data-stu-id="196f2-108">Create a new report file for each execution of the maintenance plan.</span></span> <span data-ttu-id="196f2-109">Standardmäßig werden die Berichtsdateien auf den Computer geschrieben, der als Host der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fungiert, die diesen Wartungsplan enthält. Die Dateien werden in dem während des Setups von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] festgelegten Standardprotokollordner gespeichert.</span><span class="sxs-lookup"><span data-stu-id="196f2-109">By default, the report files are written to the computer hosting the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that contains this maintenance plan, in the folder established as the default log folder during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup.</span></span> <span data-ttu-id="196f2-110">Wenn Sie einen anderen Ordner angeben möchten, geben Sie im Textfeld **Ordner** den vollständigen Ordnerpfad ein, oder klicken Sie auf die Schaltfläche zum Durchsuchen ( **...** ), und navigieren Sie zum gewünschten Ordner.</span><span class="sxs-lookup"><span data-stu-id="196f2-110">To specify a different folder, enter the full path of the folder in the **Folder** text box, or click the browse button (**...**) and navigate to the desired folder.</span></span>  
  
 <span data-ttu-id="196f2-111">**An Datei anfügen**</span><span class="sxs-lookup"><span data-stu-id="196f2-111">**Append to file**</span></span>  
 <span data-ttu-id="196f2-112">Fügt die jeweiligen Berichte der einzelnen Planausführungen an die Datei an, die im Textfeld **Dateiname** angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="196f2-112">Append the report from each plan execution to the file specified in the **File name** text box.</span></span> <span data-ttu-id="196f2-113">Sie können auch eine Datei angeben, indem Sie auf die Schaltfläche zum Durchsuchen klicken und im angezeigten Dialogfeld eine Datei auswählen.</span><span class="sxs-lookup"><span data-stu-id="196f2-113">You may also specify a file by clicking the browse button and selecting a file from the dialog box.</span></span>  
  
 <span data-ttu-id="196f2-114">**Bericht an einen E-Mail-Empfänger senden**</span><span class="sxs-lookup"><span data-stu-id="196f2-114">**Send report to an e-mail recipient**</span></span>  
 <span data-ttu-id="196f2-115">Übermittelt das Ergebnis einer Wartungsplanausführung per E-Mail.</span><span class="sxs-lookup"><span data-stu-id="196f2-115">Transmit the outcome of a maintenance plan execution via e-mail.</span></span> <span data-ttu-id="196f2-116">Diese Option ist nur verfügbar, wenn Datenbank-E-Mail aktiviert und ordnungsgemäß konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="196f2-116">This option is only available if Database Mail is enabled and properly configured.</span></span>  
  
 <span data-ttu-id="196f2-117">**Agentoperator**</span><span class="sxs-lookup"><span data-stu-id="196f2-117">**Agent operator**</span></span>  
 <span data-ttu-id="196f2-118">Wählen Sie einen Agentoperator aus der Liste aus, der als E-Mail-Empfänger festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="196f2-118">Select an agent operator from the list who will be the recipient of the e-mail.</span></span> <span data-ttu-id="196f2-119">Diese Option ist nur verfügbar, wenn Datenbank-E-Mail aktiviert und ordnungsgemäß konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="196f2-119">This option is only available if mail is enabled and properly</span></span>  
  
 <span data-ttu-id="196f2-120">**Erweiterte Informationen protokollieren**</span><span class="sxs-lookup"><span data-stu-id="196f2-120">**Log extended information**</span></span>  
 <span data-ttu-id="196f2-121">Mit dieser Option enthält das Protokoll mehr Informationen.</span><span class="sxs-lookup"><span data-stu-id="196f2-121">Include more information in the log.</span></span> <span data-ttu-id="196f2-122">Durch Verwenden dieser Option wird der gespeicherte Wartungsplanverlauf umfangreicher.</span><span class="sxs-lookup"><span data-stu-id="196f2-122">Including this option will increase the size of the stored maintenance plan history.</span></span>  
  
 <span data-ttu-id="196f2-123">**Auf Remoteserver protokollieren**</span><span class="sxs-lookup"><span data-stu-id="196f2-123">**Log to remote server**</span></span>  
 <span data-ttu-id="196f2-124">Protokolliert den Wartungsplanverlauf auf einem Remoteserver.</span><span class="sxs-lookup"><span data-stu-id="196f2-124">Logs maintenance plan history to a remote server.</span></span>  
  
 <span data-ttu-id="196f2-125">**Connection**</span><span class="sxs-lookup"><span data-stu-id="196f2-125">**Connection**</span></span>  
 <span data-ttu-id="196f2-126">Gibt die Verbindungsinformationen an, die beim Protokollieren auf einem Remoteserver verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="196f2-126">Specifies the connection information to use when logging to a remote server.</span></span>  
  
 <span data-ttu-id="196f2-127">**Neu**</span><span class="sxs-lookup"><span data-stu-id="196f2-127">**New**</span></span>  
 <span data-ttu-id="196f2-128">Zeigt das Dialogfeld **Verbindungseigenschaften** an.</span><span class="sxs-lookup"><span data-stu-id="196f2-128">Displays the **Connection Properties** dialog box.</span></span> <span data-ttu-id="196f2-129">Dient dem Konfigurieren neuer Verbindungsinformationen zum Protokollieren auf einem Remoteserver.</span><span class="sxs-lookup"><span data-stu-id="196f2-129">Used to configure new connection information for logging to a remote server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="196f2-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="196f2-130">See Also</span></span>  
 <span data-ttu-id="196f2-131">[Wartungspläne](maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="196f2-131">[Maintenance Plans](maintenance-plans.md) </span></span>  
 [<span data-ttu-id="196f2-132">Datenbank-E-Mail</span><span class="sxs-lookup"><span data-stu-id="196f2-132">Database Mail</span></span>](../database-mail/database-mail.md)  
  
  
