---
title: SQL Server-Agent-Eigenschaften (Seite Allgemein)|Microsoft-Dokumente
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.general.f1
ms.assetid: b51601e9-5454-43c6-bb5e-24eb2ff043c8
author: stevestein
ms.author: sstein
ms.openlocfilehash: a67d5431be4025c18b11d6791b016fa83e957810
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621307"
---
# <a name="sql-server-agent-properties-general-page"></a><span data-ttu-id="584c7-102">SQL Server-Agent-Eigenschaften (Seite Allgemein)</span><span class="sxs-lookup"><span data-stu-id="584c7-102">SQL Server Agent Properties (General Page)</span></span>
  <span data-ttu-id="584c7-103">Verwenden Sie diese Seite, um die allgemeinen Eigenschaften des- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Dienstanbieter anzuzeigen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="584c7-103">Use this page to view and modify the general properties of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="584c7-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="584c7-104">Options</span></span>  
 <span data-ttu-id="584c7-105">**Dienstzustand**</span><span class="sxs-lookup"><span data-stu-id="584c7-105">**Service state**</span></span>  
 <span data-ttu-id="584c7-106">Zeigt den aktuellen Status des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienstes an.</span><span class="sxs-lookup"><span data-stu-id="584c7-106">Displays the current state of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
 <span data-ttu-id="584c7-107">**SQL Server nach unerwartetem Beenden automatisch neu starten**</span><span class="sxs-lookup"><span data-stu-id="584c7-107">**Auto restart SQL Server if it stops unexpectedly**</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="584c7-108">Agent startet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] neu, wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unerwartet beendet wird.</span><span class="sxs-lookup"><span data-stu-id="584c7-108">Agent restarts [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stops unexpectedly.</span></span>  
  
 <span data-ttu-id="584c7-109">**SQL Server-Agent nach unerwartetem Beenden automatisch neu starten**</span><span class="sxs-lookup"><span data-stu-id="584c7-109">**Auto restart SQL Server Agent if it stops unexpectedly**</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="584c7-110">startet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent neu, wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent unerwartet beendet wird.</span><span class="sxs-lookup"><span data-stu-id="584c7-110">restarts [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent stops unexpectedly.</span></span>  
  
 <span data-ttu-id="584c7-111">**Filename**</span><span class="sxs-lookup"><span data-stu-id="584c7-111">**Filename**</span></span>  
 <span data-ttu-id="584c7-112">Geben Sie den Dateinamen für das Fehlerprotokoll an.</span><span class="sxs-lookup"><span data-stu-id="584c7-112">Specify the file name for the error log.</span></span>  
  
 <span data-ttu-id="584c7-113">**...**</span><span class="sxs-lookup"><span data-stu-id="584c7-113">**...**</span></span>  
 <span data-ttu-id="584c7-114">Mit dieser Schaltfläche können Sie nach der Fehlerprotokolldatei suchen.</span><span class="sxs-lookup"><span data-stu-id="584c7-114">Browse to the error log file.</span></span>  
  
 <span data-ttu-id="584c7-115">**Meldungen zur Ablaufverfolgung einschließen**</span><span class="sxs-lookup"><span data-stu-id="584c7-115">**Include execution trace messages**</span></span>  
 <span data-ttu-id="584c7-116">Meldungen zur Ablaufverfolgung werden in das Fehlerprotokoll eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="584c7-116">Includes execution trace messages in the error log.</span></span> <span data-ttu-id="584c7-117">Meldungen zur Ablaufverfolgung stellen detaillierte Informationen zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Vorgängen bereit.</span><span class="sxs-lookup"><span data-stu-id="584c7-117">Trace messages provide detailed information on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operation.</span></span> <span data-ttu-id="584c7-118">Deshalb benötigt die Protokolldatei mehr Datenträgerspeicherplatz, wenn diese Option ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="584c7-118">Therefore, the log file requires more disk space when this option is selected.</span></span> <span data-ttu-id="584c7-119">Diese Option sollte nur bei der Behandlung eines Problems ausgewählt werden, bei dem der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent eine Rolle spielt.</span><span class="sxs-lookup"><span data-stu-id="584c7-119">This option should only be selected while troubleshooting a problem that may involve [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
 <span data-ttu-id="584c7-120">**OEM-Datei schreiben**</span><span class="sxs-lookup"><span data-stu-id="584c7-120">**Write OEM file**</span></span>  
 <span data-ttu-id="584c7-121">Speichert die Fehlerprotokolldatei als Nicht-Unicode-Datei.</span><span class="sxs-lookup"><span data-stu-id="584c7-121">Writes the error log file as a non-Unicode file.</span></span> <span data-ttu-id="584c7-122">Dadurch wird der für die Protokolldatei erforderliche Datenträgerspeicherplatz reduziert.</span><span class="sxs-lookup"><span data-stu-id="584c7-122">This reduces the amount of disk space consumed by the log file.</span></span> <span data-ttu-id="584c7-123">Meldungen, die Unicode enthalten, können jedoch schwieriger lesbar sein, wenn diese Option aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="584c7-123">However, messages that include Unicode data may be more difficult to read when this option is enabled.</span></span>  
  
 <span data-ttu-id="584c7-124">**NET SEND-Empfänger**</span><span class="sxs-lookup"><span data-stu-id="584c7-124">**Net send recipient**</span></span>  
 <span data-ttu-id="584c7-125">Geben Sie den Namen eines Operators ein, der NET SEND-Benachrichtigungen von Meldungen empfängt, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent in die Protokolldatei schreibt.</span><span class="sxs-lookup"><span data-stu-id="584c7-125">Type the name of an operator to receive net send notification of messages that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent writes to the log file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="584c7-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="584c7-126">See Also</span></span>  
 <span data-ttu-id="584c7-127">[Veranstalter](operators.md) </span><span class="sxs-lookup"><span data-stu-id="584c7-127">[Operators](operators.md) </span></span>  
 [<span data-ttu-id="584c7-128">SQL Server-Agent-Fehlerprotokoll</span><span class="sxs-lookup"><span data-stu-id="584c7-128">SQL Server Agent Error Log</span></span>](sql-server-agent-error-log.md)  
  
  
