---
title: Vornehmen von Teilupdates an FILESTREAM-Daten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT
- FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT
ms.assetid: d6f7661e-6c14-4d31-9541-4520ca0f82b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 696c1a6421e14568877e24f015e5094395f1051b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723918"
---
# <a name="make-partial-updates-to-filestream-data"></a><span data-ttu-id="1444d-102">Vornehmen von Teilupdates an FILESTREAM-Daten</span><span class="sxs-lookup"><span data-stu-id="1444d-102">Make Partial Updates to FILESTREAM Data</span></span>
  <span data-ttu-id="1444d-103">Eine Anwendung verwendet FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT, um Teilaktualisierungen für FILESTREAM-BLOB-Daten vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="1444d-103">An application uses FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT to make partial updates to FILESTREAM BLOB data.</span></span> <span data-ttu-id="1444d-104">Die Funktion [DeviceIoControl](https://go.microsoft.com/fwlink/?LinkId=105527) übergibt diesen Wert und das Handle, das von [OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) zurückgegeben wird, an den FILESTREAM-Treiber.</span><span class="sxs-lookup"><span data-stu-id="1444d-104">The [DeviceIoControl](https://go.microsoft.com/fwlink/?LinkId=105527) function passes this value and the handle that is returned from [OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) to the FILESTREAM driver.</span></span> <span data-ttu-id="1444d-105">Der Treiber erzwingt dann eine serverseitige Kopie der aktuellen FILESTREAM-Daten in die Datei, auf die das Handle verweist.</span><span class="sxs-lookup"><span data-stu-id="1444d-105">The driver then forces a server-side copy of the current FILESTREAM data into the file that is referenced by the handle.</span></span> <span data-ttu-id="1444d-106">Wenn die Anwendung den FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT-Wert ausgibt, nachdem in die durch das Handle bezeichnete Datei geschrieben wurde, werden die Daten des letzten Schreibvorgangs persistent gespeichert und alle für das Handle zuvor geschriebenen Daten gehen verloren.</span><span class="sxs-lookup"><span data-stu-id="1444d-106">If the application issues the FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT value after the handle has been written to, the last write operation persists and previous write operations that were made to the handle are lost.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1444d-107">FILESTREAM benötigt für den Remotezugriff das [SMB-Protokoll](https://go.microsoft.com/fwlink/?LinkId=112454) .</span><span class="sxs-lookup"><span data-stu-id="1444d-107">FILESTREAM relies on the [SMB protocol](https://go.microsoft.com/fwlink/?LinkId=112454) for remote access.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1444d-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1444d-108">Example</span></span>  
 <span data-ttu-id="1444d-109">Das folgende Beispiel zeigt, wie Sie den `FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT` -Wert verwenden, um ein Teilupdate eines eingefügten FILESTREAM-BLOB-Elements durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="1444d-109">The following example shows you how to use the `FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT` value to perform a partial update of an inserted FILESTREAM BLOB.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1444d-110">Für dieses Beispiel sind die FILESTREAM-aktivierte Datenbank und die Tabelle erforderlich, die unter [Erstellen einer FILESTREAM-aktivierten Datenbank](create-a-filestream-enabled-database.md) und [Erstellen einer Tabelle zum Speichern von FILESTREAM-Daten](create-a-table-for-storing-filestream-data.md)erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="1444d-110">This example requires the FILESTREAM-enabled database and table that are created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md) and [Create a Table for Storing FILESTREAM Data](create-a-table-for-storing-filestream-data.md).</span></span>  
  
 [!code-cpp[FILESTREAM#FS_CPP_FSCTL](../../snippets/tsql/SQL15/tsql/filestream/cpp/filestream.cpp#fs_cpp_fsctl)]  
  
## <a name="see-also"></a><span data-ttu-id="1444d-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1444d-111">See Also</span></span>  
 <span data-ttu-id="1444d-112">[ZUgreifen auf FILESTREAM-Daten mit OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) </span><span class="sxs-lookup"><span data-stu-id="1444d-112">[Access FILESTREAM Data with OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) </span></span>  
 [<span data-ttu-id="1444d-113">Erstellen von Clientanwendungen für FILESTREAM-Daten</span><span class="sxs-lookup"><span data-stu-id="1444d-113">Create Client Applications for FILESTREAM Data</span></span>](create-client-applications-for-filestream-data.md)  
  
  
