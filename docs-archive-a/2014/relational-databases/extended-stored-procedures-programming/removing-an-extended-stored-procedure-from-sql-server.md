---
title: Entfernen einer erweiterten gespeicherten Prozedur aus SQL Server | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- deleting extended stored procedures
- removing extended stored procedures
- extended stored procedures [SQL Server], removing
- dropping extended stored procedures
ms.assetid: 7827e574-3f59-4279-9a9b-532582e041cb
author: rothja
ms.author: jroth
ms.openlocfilehash: 284da815de073248669da032c06ddeeb68c697a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726937"
---
# <a name="removing-an-extended-stored-procedure-from-sql-server"></a><span data-ttu-id="5bf5e-102">Entfernen einer erweiterten gespeicherten Prozedur aus SQL Server</span><span class="sxs-lookup"><span data-stu-id="5bf5e-102">Removing an Extended Stored Procedure from SQL Server</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="5bf5e-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="5bf5e-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="5bf5e-104">Um jede Funktion der erweiterten gespeicherten Prozedur in einer benutzerdefinierten DLL einer benutzerdefinierten erweiterten gespeicherten Prozedur zu löschen, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] muss ein Systemadministrator die gespeicherte Prozedur des **sp_dropextendedproc** -Systems ausführen und dabei den Namen der Funktion und den Namen der DLL angeben, in der sich die Funktion befindet.</span><span class="sxs-lookup"><span data-stu-id="5bf5e-104">To drop each extended stored procedure function in a user-defined extended stored procedure DLL, a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator must run the **sp_dropextendedproc** system stored procedure, specifying the name of the function and the name of the DLL in which that function resides.</span></span> <span data-ttu-id="5bf5e-105">Beispielsweise entfernt dieser Befehl die Funktion **xp_hello**, die sich in einer DLL mit dem Namen xp_hello.dll befindet, aus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="5bf5e-105">For example, this command removes the function **xp_hello**, located in a DLL named xp_hello.dll, from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
```  
sp_dropextendedproc 'xp_hello'  
```  
  
 <span data-ttu-id="5bf5e-106">Ab [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] **sp_dropextendedproc** keine erweiterten gespeicherten Prozeduren für das System ablegen.</span><span class="sxs-lookup"><span data-stu-id="5bf5e-106">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], **sp_dropextendedproc** does not drop system extended stored procedures.</span></span> <span data-ttu-id="5bf5e-107">Stattdessen sollte der Systemadministrator die EXECUTE-Berechtigung für die erweiterte gespeicherte Prozedur der **Public** -Rolle verweigern.</span><span class="sxs-lookup"><span data-stu-id="5bf5e-107">Instead, the system administrator should deny EXECUTE permission on the extended stored procedure to the **public** role.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bf5e-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5bf5e-108">See Also</span></span>  
 [<span data-ttu-id="5bf5e-109">sp_dropextendedproc &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5bf5e-109">sp_dropextendedproc &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropextendedproc-transact-sql)  
  
  
