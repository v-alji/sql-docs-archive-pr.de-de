---
title: Datenquellen Namen und 64-Bit-Betriebssysteme | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: c2f86810-2775-4ddd-8df7-e8373785a7fc
author: rothja
ms.author: jroth
ms.openlocfilehash: ae31584ca3c076919f688d1ef9bdef80706c6940
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615358"
---
# <a name="data-source-names-and-64-bit-operating-systems"></a><span data-ttu-id="f7c08-102">Datenquellennamen und 64-Bit-Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="f7c08-102">Data Source Names and 64-Bit Operating Systems</span></span>
  <span data-ttu-id="f7c08-103">Wenn Sie eine Anwendung als 32-Bit-Anwendung entwickeln und unter einem 64-Bit-Betriebssystem ausführen möchten, müssen Sie die ODBC-Datenquelle mit dem ODBC-Administrator in %windir%\SysWOW64\odbcad32.exe erstellen.</span><span class="sxs-lookup"><span data-stu-id="f7c08-103">To build and run an application as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7c08-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f7c08-104">Remarks</span></span>  
 <span data-ttu-id="f7c08-105">Ein 64-Bit-Windows-Betriebssystem verfügt über zwei odbcad32.exe-Dateien:</span><span class="sxs-lookup"><span data-stu-id="f7c08-105">A 64-bit Windows operating system has two odbcad32.exe files:</span></span>  
  
-   <span data-ttu-id="f7c08-106">%SystemRoot%\system32\odbcad32.exe wird verwendet, um Datenquellennamen für 64-Bit-Anwendungen zu erstellen und zu warten.</span><span class="sxs-lookup"><span data-stu-id="f7c08-106">%SystemRoot%\system32\odbcad32.exe is used to create and maintain data source names for 64-bit applications.</span></span>  
  
-   <span data-ttu-id="f7c08-107">%SystemRoot%\SysWOW64\odbcad32.exe wird verwendet, um Datenquellennamen für 32-Bit-Anwendungen, einschließlich 32-Bit-Anwendungen, die auf 64-Bit-Betriebssystemen ausgeführt werden, zu erstellen und zu warten.</span><span class="sxs-lookup"><span data-stu-id="f7c08-107">%SystemRoot%\SysWOW64\odbcad32.exe is used to create and maintain data source names for 32-bit applications, including 32-bit applications that run on 64-bit operating systems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7c08-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7c08-108">See Also</span></span>  
 [<span data-ttu-id="f7c08-109">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="f7c08-109">SQL Server Native Client &#40;ODBC&#41;</span></span>](sql-server-native-client-odbc.md)  
  
  
