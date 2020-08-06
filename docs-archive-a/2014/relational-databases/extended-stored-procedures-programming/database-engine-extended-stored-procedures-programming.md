---
title: Programmierung von erweiterten gespeicherten Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- gateway applications [SQL Server]
- extended stored procedures [SQL Server], about extended stored procedures
- Open Data Services [SQL Server]
- ODS [SQL Server]
ms.assetid: 561305cd-c803-48af-9eec-2c19f4d311ce
author: rothja
ms.author: jroth
ms.openlocfilehash: 30792cc2b431e35a8f7df5ff7bbb2c228892d5c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620396"
---
# <a name="programming-extended-stored-procedures"></a><span data-ttu-id="4bc19-102">Programmieren erweiterter gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="4bc19-102">Programming Extended Stored Procedures</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="4bc19-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="4bc19-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="4bc19-104">In der Vergangenheit wurde Open Data Services verwendet, um Serveranwendungen zu schreiben, z. B. Gateways zu anderen Datenbankumgebungen als SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4bc19-104">In the past, Open Data Services was used to write server applications, such as gateways to non-SQL Server database environments.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="4bc19-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]die veralteten Teile der Open Data Services-API werden von nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4bc19-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not support the obsolete portions of the Open Data Services API.</span></span> <span data-ttu-id="4bc19-106">Der einzige weiterhin von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützte Bereich der ursprünglichen Open Data Services-API betrifft die Funktionen für erweiterte gespeicherte Prozeduren. Daher wurde die API umbenannt in "API für erweiterte gespeicherte Prozeduren".</span><span class="sxs-lookup"><span data-stu-id="4bc19-106">The only part of the original Open Data Services API still supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are the extended stored procedure functions, so the API has been renamed to the Extended Stored Procedure API.</span></span>  
  
 <span data-ttu-id="4bc19-107">Mit dem Erscheinen neuerer und leistungsfähigerer Technologien wie beispielsweise der verteilten Abfragen oder der CLR-Integration ist der Bedarf an Anwendungen, die auf die API für erweiterte gespeicherte Prozeduren zurückgreifen, weitgehend verschwunden.</span><span class="sxs-lookup"><span data-stu-id="4bc19-107">With the emergence of newer and more powerful technologies, such as distributed queries and CLR Integration, the need for Extended Stored Procedure API applications has largely been replaced.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4bc19-108">Für bereits bestehende Gateway-Anwendungen können Sie die in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] enthaltene Datei opends60.dll nicht verwenden, um die Anwendungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4bc19-108">If you have existing gateway applications, you cannot use the opends60.dll that ships with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to run the applications.</span></span> <span data-ttu-id="4bc19-109">Gateway-Anwendungen werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4bc19-109">Gateway applications are no longer supported.</span></span>  
  
## <a name="extended-stored-procedures-vs-clr-integration"></a><span data-ttu-id="4bc19-110">Erweiterte gespeicherte Prozeduren im Vergleich zur CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="4bc19-110">Extended Stored Procedures vs. CLR Integration</span></span>  
 <span data-ttu-id="4bc19-111">In früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] boten erweiterte gespeicherte Prozeduren (XPs) den einzigen für Datenbankentwickler verfügbaren Mechanismus zum Erstellen serverseitiger Logik, die in [!INCLUDE[tsql](../../includes/tsql-md.md)] entweder schwierig auszudrücken oder unmöglich zu schreiben war.</span><span class="sxs-lookup"><span data-stu-id="4bc19-111">In earlier releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], extended stored procedures (XPs) provided the only mechanism that was available for database application developers to write server-side logic that was either hard to express or impossible to write in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="4bc19-112">Die CLR-Integration bietet eine robustere Alternative zum Schreiben von solchen gespeicherten Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="4bc19-112">CLR Integration provides a more robust alternative to writing such stored procedures.</span></span> <span data-ttu-id="4bc19-113">Des Weiteren kann mit der CLR-Integration die Logik, die zuvor in der Form von gespeicherten Prozeduren geschrieben wurde, oft besser in Tabellenwertfunktionen ausgedrückt werden. So können die von der Funktion konstruierten Ergebnisse in SELECT-Anweisungen abgefragt werden, indem sie in die FROM-Klausel eingebettet werden.</span><span class="sxs-lookup"><span data-stu-id="4bc19-113">Furthermore, with CLR Integration, logic that used to be written in the form of stored procedures is often better expressed as table-valued functions, which allow the results constructed by the function to be queried in SELECT statements by embedding them in the FROM clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bc19-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4bc19-114">See Also</span></span>  
 <span data-ttu-id="4bc19-115">[Übersicht über die CLR-&#41; Integration in Common Language Runtime &#40;](../clr-integration/common-language-runtime-integration-overview.md) </span><span class="sxs-lookup"><span data-stu-id="4bc19-115">[Common Language Runtime &#40;CLR&#41; Integration Overview](../clr-integration/common-language-runtime-integration-overview.md) </span></span>  
 [<span data-ttu-id="4bc19-116">CLR-Tabellenwertfunktionen</span><span class="sxs-lookup"><span data-stu-id="4bc19-116">CLR Table-Valued Functions</span></span>](../clr-integration-database-objects-user-defined-functions/clr-table-valued-functions.md)  
  
  
