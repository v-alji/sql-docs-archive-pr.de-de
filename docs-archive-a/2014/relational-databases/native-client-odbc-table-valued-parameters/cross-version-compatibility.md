---
title: Versions übergreifende Kompatibilität | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), cross-version compatibility
ms.assetid: 5f14850b-b85c-41e2-8116-6f5b3f5e0856
author: rothja
ms.author: jroth
ms.openlocfilehash: af434713946f5c568ee71644a7403f9496a8c16f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620857"
---
# <a name="cross-version-compatibility"></a><span data-ttu-id="7cb5b-102">Versionsübergreifende Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="7cb5b-102">Cross-Version Compatibility</span></span>
  <span data-ttu-id="7cb5b-103">Konflikte zwischen Versionen können auftreten, wenn Client- oder Serverinstanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vor [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] Tabellenwertparameter verarbeiten sollen.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-103">Cross-version conflicts can occur when client or server instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] are expected to process table-valued parameters.</span></span>  
  
 <span data-ttu-id="7cb5b-104">Im Allgemeinen ist die Tabellenwertparameter-Funktionalität nur für [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]-Clients oder höher verfügbar (unter Verwendung von SQL Server Native Client 10.0), die mit [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]-Servern (oder höher) verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-104">In general, table-valued parameter functionality is only available to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] clients (using SQL Server Native Client 10.0) or later that are connected to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (or later) servers.</span></span> <span data-ttu-id="7cb5b-105">Neue Spalten in Resultsets von Katalog Funktionen sind nur vorhanden, wenn eine Verbindung mit einem- [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] Server (oder höher) besteht.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-105">New columns in catalog function result sets will only be present when connected to a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (or later) server.</span></span>  
  
 <span data-ttu-id="7cb5b-106">Wenn eine mit einer früheren Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client kompilierte Clientanwendung Anweisungen ausführt, für die Tabellenwertparameter erwartet werden, wird dies vom Server als Datenkonvertierungsfehler erkannt, und ODBC gibt einen SQLSTATE 07006-Fehler und die Meldung "Attributverletzung beschränkter Datentypen" zurück.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-106">If a client application compiled with an earlier version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client executes statements that expect table-valued parameters, the server detects this condition through a data conversion error, and ODBC returns this as a SQLSTATE 07006 and the message "Restricted data type attribute violation".</span></span>  
  
 <span data-ttu-id="7cb5b-107">Wenn eine Client Anwendung, die mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 10,0 oder höher kompiliert wurde, versucht, Tabellenwert Parameter zu verwenden, wenn eine Verbindung mit einer Serverinstanz vor hergestellt wurde [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Dies wird von Native Client erkannt, und die Aufrufe SQLBindCol, SQLBindParameter, sqlsetdescfields und SQLSetDescRec schlagen mit SQLState 07006 und der Meldung "Attribut Verletzung eingeschränkter Datentypen (die Version von SQL Server für diese Verbindung unterstützt keine Tabellenwert Parameter)" fehl.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-107">If a client application that was compiled with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 10.0 or later tries to use table-valued parameters when connected to a server instance earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client will detect this, and SQLBindCol, SQLBindParameter, SQLSetDescFields, and SQLSetDescRec calls will fail with SQLSTATE 07006 and the message "Restricted data type attribute violation (the version of SQL Server for this connection does not support table-valued parameters)".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cb5b-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7cb5b-108">See Also</span></span>  
 [<span data-ttu-id="7cb5b-109">Tabellenwert Parameter &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="7cb5b-109">Table-Valued Parameters &#40;ODBC&#41;</span></span>](table-valued-parameters-odbc.md)  
  
  
