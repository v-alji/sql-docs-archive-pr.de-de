---
title: Multithreadanwendungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- threads [SQL Server], multithreaded applications
- ODBC applications, multithreaded applications
- asynchronous operations [SQL Server Native Client]
- SQL Server Native Client ODBC driver, multithreaded applications
- multithreaded applications [SQL Server Native Client]
ms.assetid: d352c91a-6e08-4e50-9f3e-a37892d9c2cc
author: rothja
ms.author: jroth
ms.openlocfilehash: b680086f76e0c1a1e8c8cfc2f4ef82099957b3fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620301"
---
# <a name="multithreaded-applications"></a><span data-ttu-id="62a14-102">Multithreadanwendungen</span><span class="sxs-lookup"><span data-stu-id="62a14-102">Multithreaded Applications</span></span>
  <span data-ttu-id="62a14-103">Der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber ist ein Multithreadtreiber.</span><span class="sxs-lookup"><span data-stu-id="62a14-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver is a multithreaded driver.</span></span> <span data-ttu-id="62a14-104">Das Schreiben einer Multithreadanwendung ist eine Alternative zum Verwenden von asynchronen Aufrufen zur Verarbeitung von mehreren ODBC-Aufrufen.</span><span class="sxs-lookup"><span data-stu-id="62a14-104">Writing a multithreaded application is an alternative to using asynchronous calls to process multiple ODBC calls.</span></span> <span data-ttu-id="62a14-105">Ein Thread kann einen synchronen ODBC-Aufruf erstellen, und andere Threads können verarbeitet werden, während der erste Thread blockiert wird und auf die Antwort auf seinen Aufruf wartet.</span><span class="sxs-lookup"><span data-stu-id="62a14-105">A thread can make a synchronous ODBC call, and other threads can process while the first thread is blocked waiting for the response to its call.</span></span> <span data-ttu-id="62a14-106">Dieses Modell ist effizienter als asynchrone Aufrufe, da Verarbeitungsaufwand beseitigt wird, wie Netzwerkverkehr und die wiederholte Erstellung von ODBC-Funktionsaufrufen zum Überprüfen von SQL_STILL_EXECUTING.</span><span class="sxs-lookup"><span data-stu-id="62a14-106">This model is more efficient than making asynchronous calls because it eliminates overhead such as network traffic and making repeated ODBC function calls testing for SQL_STILL_EXECUTING.</span></span>  
  
 <span data-ttu-id="62a14-107">Der asynchrone Modus ist immer noch eine effektive Methode der Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="62a14-107">Asynchronous mode is still an effective method of processing.</span></span> <span data-ttu-id="62a14-108">Die Leistungsverbesserungen eines Multithreadmodells genügen nicht, um das Umschreiben asynchroner Anwendungen zu rechtfertigen.</span><span class="sxs-lookup"><span data-stu-id="62a14-108">The performance improvements of a multithreaded model are not enough to justify rewriting asynchronous applications.</span></span> <span data-ttu-id="62a14-109">Wenn Benutzer DB-Library-Anwendungen konvertieren, die das asynchrone DB-Library-Modell verwenden, empfiehlt sich die Konvertierung in das asynchrone ODBC-Modell.</span><span class="sxs-lookup"><span data-stu-id="62a14-109">If users are converting DB-Library applications that use the DB-Library asynchronous model, it is easier to convert them to the ODBC asynchronous model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62a14-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="62a14-110">See Also</span></span>  
 [<span data-ttu-id="62a14-111">Erstellen einer SQL Server Native Client-ODBC-Treiberanwendung</span><span class="sxs-lookup"><span data-stu-id="62a14-111">Creating a SQL Server Native Client ODBC Driver Application</span></span>](creating-a-driver-application.md)  
  
  
