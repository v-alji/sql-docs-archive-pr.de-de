---
title: Ausführen einer Reporting Services-Skriptdatei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- scripts [Reporting Services], running
ms.assetid: 0de4995c-85ec-4d4c-aaef-fbd30edfb20f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c787d860838a57a2bd0f51aac1e9159833f038d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721001"
---
# <a name="run-a-reporting-services-script-file"></a><span data-ttu-id="33940-102">Ausführen einer Reporting Services-Skriptdatei</span><span class="sxs-lookup"><span data-stu-id="33940-102">Run a Reporting Services Script File</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="33940-103">-Skriptdateien werden von der Eingabeaufforderung in der [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Skriptumgebung (RS.exe) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="33940-103">script files are run from the command prompt using the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] script environment (RS.exe).</span></span> <span data-ttu-id="33940-104">In RS.exe stehen Ihnen viele Befehlszeileargumente zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="33940-104">RS.exe has many command prompt arguments available for you to use.</span></span> <span data-ttu-id="33940-105">Weitere Informationen zu den Befehlszeilenoptionen finden Sie unter [Hilfsprogramm „RS.exe“ (SSRS)](rs-exe-utility-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="33940-105">For more information about the command prompt options, see [RS.exe Utility &#40;SSRS&#41;](rs-exe-utility-ssrs.md).</span></span> <span data-ttu-id="33940-106">Weitere Skriptbeispiele finden Sie unter [SQL Server Reporting Services-Produktbeispiele](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="33940-106">For more script samples, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="sample-command-lines"></a><span data-ttu-id="33940-107">Beispielbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="33940-107">Sample Command Lines</span></span>  
  
-   <span data-ttu-id="33940-108">Führen Sie Script.rss in der Skriptumgebung für den Zielberichtsserver aus.</span><span class="sxs-lookup"><span data-stu-id="33940-108">Run Script.rss in the script environment designating the target report server.</span></span> <span data-ttu-id="33940-109">Standardmäßig wird die Windows-Authentifizierung angewendet:</span><span class="sxs-lookup"><span data-stu-id="33940-109">Windows Authentication is applied by default:</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver  
    ```  
  
-   <span data-ttu-id="33940-110">Führen Sie Script.rss in der Skriptumgebung unter Angabe eines Benutzernamens und eines Kennworts für die Authentifizierung der Webdienstaufrufe aus:</span><span class="sxs-lookup"><span data-stu-id="33940-110">Run Script.rss in the script environment specifying a user name and password for authenticating the Web service calls:</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -u myusername -p mypassword  
    ```  
  
-   <span data-ttu-id="33940-111">Führen Sie Script.rss in der Skriptumgebung unter Angabe eines Timeouts von 30 Sekunden für den Server aus:</span><span class="sxs-lookup"><span data-stu-id="33940-111">Run Script.rss in the script environment specifying a server time-out of 30 seconds:</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -l 30  
    ```  
  
-   <span data-ttu-id="33940-112">Führen Sie Script.rss in der Skriptumgebung unter Angabe einer globalen Skriptvariablen mit der Bezeichnung *report*aus:</span><span class="sxs-lookup"><span data-stu-id="33940-112">Run Script.rss in the script environment specifying a global script variable called *report*.</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -v report="Company Sales"  
    ```  
  
-   <span data-ttu-id="33940-113">Führen Sie Script.rss in der Skriptumgebung aus, und geben Sie dabei an, dass die Webdienstvorgänge in der Skriptdatei als Batch ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="33940-113">Run Script.rss in the script environment specifying that the Web service operations in the script file are run as a batch.</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -b  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="33940-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="33940-114">See Also</span></span>  
 [<span data-ttu-id="33940-115">Technische Referenz (SSRS)</span><span class="sxs-lookup"><span data-stu-id="33940-115">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
