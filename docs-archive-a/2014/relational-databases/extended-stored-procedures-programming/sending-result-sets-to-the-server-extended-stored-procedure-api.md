---
title: Senden von Resultsets an den Server (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], sending result sets
- result sets [SQL Server], extended stored procedures
ms.assetid: 9d54673d-ea9d-4ac6-825a-f216ad8b0e34
author: rothja
ms.author: jroth
ms.openlocfilehash: 82984440f96416189eb18f900764ee7bdaf05a01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607774"
---
# <a name="sending-result-sets-to-the-server-extended-stored-procedure-api"></a><span data-ttu-id="b27f4-102">Senden von Resultsets an den Server (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="b27f4-102">Sending Result Sets to the Server (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="b27f4-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="b27f4-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="b27f4-104">Beim Senden eines Resultsets an [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sollte die erweiterte gespeicherte Prozedur wie folgt die entsprechende API abrufen:</span><span class="sxs-lookup"><span data-stu-id="b27f4-104">When sending a result set to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the extended stored procedure should call the appropriate API as follows:</span></span>  
  
-   <span data-ttu-id="b27f4-105">Die **srv_sendmsg** -Funktion kann in beliebiger Reihenfolge aufgerufen werden, bevor oder nachdem alle Zeilen (sofern vorhanden) mit **srv_sendrow**gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="b27f4-105">The **srv_sendmsg** function may be called in any order before or after all rows (if any) have been sent with **srv_sendrow**.</span></span> <span data-ttu-id="b27f4-106">Alle Nachrichten müssen an den Client gesendet werden, bevor der Abschluss Status mit **srv_senddone**gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="b27f4-106">All messages must be sent to the client before the completion status is sent with **srv_senddone**.</span></span>  
  
-   <span data-ttu-id="b27f4-107">Die **srv_sendrow** -Funktion wird einmal für jede an den Client gesendete Zeile aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b27f4-107">The **srv_sendrow** function is called once for each row sent to the client.</span></span> <span data-ttu-id="b27f4-108">Alle Zeilen müssen an den Client gesendet werden, bevor Nachrichten, Statuswerte oder Abschluss Status mit **srv_sendmsg**, dem **srv_status** -Argument von **srv_pfield**oder **srv_senddone**gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="b27f4-108">All rows must be sent to the client before any messages, status values, or completion statuses are sent with **srv_sendmsg**, the **srv_status** argument of **srv_pfield**, or **srv_senddone**.</span></span>  
  
-   <span data-ttu-id="b27f4-109">Beim Senden einer Zeile, für die nicht alle Spalten mit **srv_describe** definiert wurden, wird von der Anwendung eine Informations Fehlermeldung ausgegeben, und es wird ein Fehler an den Client zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b27f4-109">Sending a row that has not had all its columns defined with **srv_describe** causes the application to raise an informational error message and return FAIL to the client.</span></span> <span data-ttu-id="b27f4-110">In diesem Fall wird die Zeile nicht gesendet.</span><span class="sxs-lookup"><span data-stu-id="b27f4-110">In this case, the row is not sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b27f4-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b27f4-111">See Also</span></span>  
 [<span data-ttu-id="b27f4-112">Erstellen erweiterter gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="b27f4-112">Creating Extended Stored Procedures</span></span>](creating-extended-stored-procedures.md)  
  
  
