---
title: Überprüfen des Datenträger-E/A-Subsystems auf E/A-Verzögerungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 23863340-d8e0-48d6-928b-462745885d37
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a0ae8dc0d1a93f8150ccbeab73ed8aa918d1f495
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699476"
---
# <a name="check-disk-input-and-output-subsystem-for-io-delay-problems"></a><span data-ttu-id="2f07d-102">Check Disk Input and Output Subsystem for IO Delay Problems</span><span class="sxs-lookup"><span data-stu-id="2f07d-102">Check Disk Input and Output Subsystem for IO Delay Problems</span></span>
  <span data-ttu-id="2f07d-103">Diese Regel überprüft das Ereignisprotokoll auf die Fehlermeldung 833.</span><span class="sxs-lookup"><span data-stu-id="2f07d-103">This rule checks the event log for error message 833.</span></span> <span data-ttu-id="2f07d-104">Mit dieser Meldung wird angegeben, dass von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine Lese- oder Schreibanforderung vom Datenträger ausgegeben wurde und dass die Rückgabe der Anforderung länger als 15 Sekunden gedauert hat.</span><span class="sxs-lookup"><span data-stu-id="2f07d-104">This message indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has issued a read or write request from disk, and that the request has taken longer than 15 seconds to return.</span></span> <span data-ttu-id="2f07d-105">Dieser Fehler wird von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gemeldet und deutet auf ein Problem mit dem E/A-Subsystem des Datenträgers hin.</span><span class="sxs-lookup"><span data-stu-id="2f07d-105">This error is reported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and indicates a problem with the disk I/O subsystem.</span></span> <span data-ttu-id="2f07d-106">Verzögerungen dieses Ausmaßes können die Leistung Ihrer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Umgebung erheblich beinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="2f07d-106">Delays this long can severely damage the performance of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environment.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="2f07d-107">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="2f07d-107">Best Practices Recommendations</span></span>  
 <span data-ttu-id="2f07d-108">Sie können diesen Fehler durch Überprüfung des Systemereignisprotokolls auf hardwarebedingte Fehlermeldungen beheben.</span><span class="sxs-lookup"><span data-stu-id="2f07d-108">Troubleshoot this error by examining the system event log for hardware-related error messages.</span></span> <span data-ttu-id="2f07d-109">Sie können zudem hardwarespezifische Protokolle überprüfen, sofern diese verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="2f07d-109">Also, examine hardware-specific logs if they are available.</span></span>  
  
 <span data-ttu-id="2f07d-110">Prüfen Sie mit dem Systemmonitor die folgenden Leistungsindikatoren:</span><span class="sxs-lookup"><span data-stu-id="2f07d-110">Use Performance Monitor to examine the following counters:</span></span>  
  
-   <span data-ttu-id="2f07d-111">Mittlere Sek./Übertragung</span><span class="sxs-lookup"><span data-stu-id="2f07d-111">Average Disk Sec/Transfer</span></span>  
  
-   <span data-ttu-id="2f07d-112">Durchschnittliche Warteschlangenlänge des Datenträgers</span><span class="sxs-lookup"><span data-stu-id="2f07d-112">Average Disk Queue Length</span></span>  
  
-   <span data-ttu-id="2f07d-113">Aktuelle Warteschlangenlänge</span><span class="sxs-lookup"><span data-stu-id="2f07d-113">Current Disk Queue Length</span></span>  
  
 <span data-ttu-id="2f07d-114">Beispielsweise beträgt die Zeit Mittlere Sek./Übertragung für einen Computer mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] normalerweise unter 15 Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="2f07d-114">For example, the Average Disk Sec/Transfer time on a computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is typically less than 15 milliseconds.</span></span> <span data-ttu-id="2f07d-115">Wenn sich der Wert Mittlere Sek./Übertragung erhöht, ist dies ein Hinweis darauf, dass das E/A-Subsystem des Datenträgers den E/A-Bedarf nicht optimal erfüllt.</span><span class="sxs-lookup"><span data-stu-id="2f07d-115">If the Average Disk Sec/Transfer value increases, this indicates that the disk I/O subsystem is not optimally keeping up with the I/O demand.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="2f07d-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f07d-116">For More Information</span></span>  
 [<span data-ttu-id="2f07d-117">MSSQLSERVER_833</span><span class="sxs-lookup"><span data-stu-id="2f07d-117">MSSQLSERVER_833</span></span>](../errors-events/mssqlserver-833-database-engine-error.md)  
  
 [<span data-ttu-id="2f07d-118">Microsoft Knowledge Base-Artikel 897284</span><span class="sxs-lookup"><span data-stu-id="2f07d-118">Microsoft Knowledge Base article 897284</span></span>](https://go.microsoft.com/fwlink/?linkid=117743)  
  
 <span data-ttu-id="2f07d-119">[SQL Server I/O Basics, Chapter 2 (in Englisch)](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="2f07d-119">[SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span></span>  
  
  
