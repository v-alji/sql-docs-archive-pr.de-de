---
title: UTF-16-Unterstützung in SQL Server Native Client 11,0 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: f2520424-8ef4-409f-8147-d83da5076e96
author: rothja
ms.author: jroth
ms.openlocfilehash: af8581071400db888fb508b88f8e8ae93bc71f70
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620312"
---
# <a name="utf-16-support-in-sql-server-native-client-110"></a><span data-ttu-id="6fb44-102">Unterstützung für UTF-16 in SQL Server Native Client 11.0</span><span class="sxs-lookup"><span data-stu-id="6fb44-102">UTF-16 Support in SQL Server Native Client 11.0</span></span>
  <span data-ttu-id="6fb44-103">[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]Wenn Sie ab einen Puffer fester Länge beim Binden eines Spalten Ergebnisses oder Ausgabe Parameters angeben und das Zeichen, das `wchar` vor dem abschließenden Zeichen in den Puffer geschrieben wurde, ein hoher Ersatz Zeichencode Punkt eines Ersatz Zeichen Paars ist, und wenn das nächste `wchar` Zeichen ein niedriger Ersatz Zeichencode Punkt ist, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fügt Native Client dem Puffer keinen hohen Ersatz Zeichencode Punkt hinzu.</span><span class="sxs-lookup"><span data-stu-id="6fb44-103">Beginning in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], if you supply a fixed-length buffer when binding a column result or output parameter and if the `wchar` character written into the buffer before the terminating character is a high surrogate code point of a surrogate pair, and if the next `wchar` character is a low surrogate code point, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client will not add the high surrogate code point to the buffer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fb44-104">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6fb44-104">See Also</span></span>  
 [<span data-ttu-id="6fb44-105">SQL Server Native Client-Funktionen</span><span class="sxs-lookup"><span data-stu-id="6fb44-105">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
