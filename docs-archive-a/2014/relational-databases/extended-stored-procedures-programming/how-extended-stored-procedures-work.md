---
title: Funktionsweise erweiterter gespeicherter Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], about extended stored procedures
ms.assetid: 6e946d8c-3268-4b59-8a1c-1637909cd701
author: rothja
ms.author: jroth
ms.openlocfilehash: 75082fed6b70c214b4f55b85034ffa371824d24f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620393"
---
# <a name="how-extended-stored-procedures-work"></a><span data-ttu-id="4d8cc-102">Funktionsweise erweiterter gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="4d8cc-102">How Extended Stored Procedures Work</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="4d8cc-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="4d8cc-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="4d8cc-104">Der Funktionsablauf einer erweiterten gespeicherten Prozedur kann folgendermaßen beschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="4d8cc-104">The process by which an extended stored procedure works is:</span></span>  
  
1.  <span data-ttu-id="4d8cc-105">Wenn ein Client eine erweiterte gespeicherte Prozedur ausführt, wird die Anforderung in Tabular Data Stream (TDS) oder im SOAP-Format (Simple Object Access Protocol) von der Client Anwendung an übertragen [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d8cc-105">When a client executes an extended stored procedure, the request is transmitted in tabular data stream (TDS) or Simple Object Access Protocol (SOAP) format from the client application to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4d8cc-106">sucht nach der mit der erweiterten gespeicherten Prozedur verknüpften DLL und lädt diese DLL, falls dies nicht bereits geschehen ist.</span><span class="sxs-lookup"><span data-stu-id="4d8cc-106">searches for the DLL associated with the extended stored procedure, and loads the DLL if it is not already loaded.</span></span>  
  
3.  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4d8cc-107">ruft die angeforderte erweiterte gespeicherte Prozedur, die als Funktion in der DLL implementiert ist, auf.</span><span class="sxs-lookup"><span data-stu-id="4d8cc-107">calls the requested extended stored procedure (implemented as a function inside the DLL).</span></span>  
  
4.  <span data-ttu-id="4d8cc-108">Die erweiterte gespeicherte Prozedur übergibt über die API für erweiterte gespeicherte Prozeduren Resultsets und Rückgabeparameter an den Server zurück.</span><span class="sxs-lookup"><span data-stu-id="4d8cc-108">The extended stored procedure passes result sets and return parameters back to the server by through the Extended Stored Procedure API.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d8cc-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4d8cc-109">See Also</span></span>  
 [<span data-ttu-id="4d8cc-110">Datenbank-Engine – Programmierung der erweiterten gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="4d8cc-110">Database Engine Extended Stored Procedure Programming</span></span>](../database-engine-extended-stored-procedure-programming.md)  
  
  
