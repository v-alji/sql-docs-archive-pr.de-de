---
title: Systemeigene Fehlernummern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC error handling, native error numbers
- SQL Server Native Client ODBC driver, errors
- native error numbers [SQL Server Native Client]
- messages [ODBC], native error numbers
- errors [ODBC], native error numbers
ms.assetid: 77cbc826-f47f-4803-8e7a-223d6df069b1
author: rothja
ms.author: jroth
ms.openlocfilehash: 7232a921027246c3ceb7d0ae1ffd5efbd3672895
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698180"
---
# <a name="native-error-numbers"></a><span data-ttu-id="f27e7-102">Systemeigene Fehlernummern</span><span class="sxs-lookup"><span data-stu-id="f27e7-102">Native Error Numbers</span></span>
  <span data-ttu-id="f27e7-103">Bei Fehlern, die in der Datenquelle auftreten (von zurückgegeben [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gibt der Native Client-ODBC-Treiber die systemeigene Fehlernummer zurück, die von zurückgegeben wird [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f27e7-103">For errors that occur in the data source (returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]), the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns the native error number returned to it by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f27e7-104">Für Fehler, die vom Treiber erkannt werden, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gibt der Native Client-ODBC-Treiber die systemeigene Fehlernummer 0 (null) zurück.</span><span class="sxs-lookup"><span data-stu-id="f27e7-104">For errors detected by the driver, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns a native error number of 0.</span></span> <span data-ttu-id="f27e7-105">Weitere Informationen zu einer Liste der systemeigenen Fehlernummern finden Sie in der Fehler Spalte der Systemtabelle " **sysmess** " in der **Master** -Datenbank in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f27e7-105">For more information about a list of native error numbers, see the error column of the **sysmessages** system table in the **master** database in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f27e7-106">Informationen zu den Zustands Fehlercodes finden Sie unter [SQLSTATE &#40;ODBC-Fehlercodes&#41;](sqlstate-odbc-error-codes.md).</span><span class="sxs-lookup"><span data-stu-id="f27e7-106">For information about the state error codes, see [SQLSTATE &#40;ODBC Error Codes&#41;](sqlstate-odbc-error-codes.md).</span></span> <span data-ttu-id="f27e7-107">Bei Fehlern, die von der Netzwerkbibliothek zurückgegeben werden, stammt die systemeigene Fehlernummer von der zugrunde liegenden Netzwerksoftware.</span><span class="sxs-lookup"><span data-stu-id="f27e7-107">For errors returned by the Net-Library, the native error number is from the underlying network software.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f27e7-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f27e7-108">See Also</span></span>  
 [<span data-ttu-id="f27e7-109">Behandlung von Fehlern und Meldungen</span><span class="sxs-lookup"><span data-stu-id="f27e7-109">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  
