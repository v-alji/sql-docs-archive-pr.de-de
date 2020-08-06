---
title: Entladen einer DLL für eine erweiterte gespeicherte Prozedur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], unloading
- unloading extended stored procedures
ms.assetid: 4c75ab14-af54-4965-b376-8d75d385c941
author: rothja
ms.author: jroth
ms.openlocfilehash: 7bd4855390e95d949ab769d6567d6f106959dcde
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607768"
---
# <a name="unloading-an-extended-stored-procedure-dll"></a><span data-ttu-id="d4da5-102">Entfernen der DLL einer erweiterten gespeicherten Prozedur aus dem Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="d4da5-102">Unloading an Extended Stored Procedure DLL</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="d4da5-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="d4da5-103">Use CLR Integration instead.</span></span>  
  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="d4da5-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]lädt eine DLL für eine erweiterte gespeicherte Prozedur, sobald ein-Vorgang an eine der Funktionen der dll erfolgt.</span><span class="sxs-lookup"><span data-stu-id="d4da5-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] loads an extended stored procedure DLL as soon as a call is made to one of the functions of the DLL.</span></span> <span data-ttu-id="d4da5-105">Die DLL bleibt so lange im Arbeitsspeicher, bis der Server heruntergefahren wird oder der Systemadministrator die DLL mit der DBCC-Anweisung aus dem Arbeitsspeicher entfernt.</span><span class="sxs-lookup"><span data-stu-id="d4da5-105">The DLL remains loaded until the server is shut down or until the system administrator uses the DBCC statement to unload it.</span></span> <span data-ttu-id="d4da5-106">Dieser Befehl entlädt z. b. die **xp_hello.dll**und ermöglicht dem Systemadministrator, eine neuere Version dieser Datei in das Verzeichnis zu kopieren, ohne den Server herunterzufahren:</span><span class="sxs-lookup"><span data-stu-id="d4da5-106">For example, this command unloads the **xp_hello.dll**, allowing the system administrator to copy a newer version of this file to the directory without shutting down the server:</span></span>  
  
```  
DBCC xp_hello(FREE)  
```  
  
## <a name="see-also"></a><span data-ttu-id="d4da5-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d4da5-107">See Also</span></span>  
 [<span data-ttu-id="d4da5-108">DBCC dllname &#40;frei&#41; &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="d4da5-108">DBCC dllname &#40;FREE&#41; &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-dllname-free-transact-sql)  
  
  
