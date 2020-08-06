---
title: Gewähren von Zugriff auf ein Datenbankobjekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- granting access to database objects
ms.assetid: a44d9bbf-f58e-4734-b7f4-eb3b492b777b
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 22bd0bb1f01e59ec30f7cf1bbf128c890d3d5d64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621771"
---
# <a name="granting-access-to-a-database-object"></a><span data-ttu-id="aff94-102">Erteilen des Zugriffs auf ein Datenbankobjekt</span><span class="sxs-lookup"><span data-stu-id="aff94-102">Granting Access to a Database Object</span></span>
  <span data-ttu-id="aff94-103"> Als Administrator können Sie die SELECT-Anweisung für die **Products**-Tabelle und die **vw_Names**-Sicht ausführen. Außerdem können Sie die **pr_Names**-Prozedur ausführen. Mary hingegen ist dazu nicht berechtigt.</span><span class="sxs-lookup"><span data-stu-id="aff94-103">As an administrator, you can execute the SELECT from the **Products** table and the **vw_Names** view, and execute the **pr_Names** procedure; however, Mary cannot.</span></span> <span data-ttu-id="aff94-104">Verwenden Sie die GRANT-Anweisung, um Mary die erforderlichen Berechtigungen zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="aff94-104">To grant Mary the necessary permissions, use the GRANT statement.</span></span>  
  
### <a name="procedure-title"></a><span data-ttu-id="aff94-105">Titel der Prozedur</span><span class="sxs-lookup"><span data-stu-id="aff94-105">Procedure Title</span></span>  
  
1.  <span data-ttu-id="aff94-106">Führen Sie die folgende Anweisung aus, um `Mary` die `EXECUTE` -Berechtigung für die gespeicherte Prozedur `pr_Names` zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="aff94-106">Execute the following statement to give `Mary` the `EXECUTE` permission for the `pr_Names` stored procedure.</span></span>  
  
    ```  
    GRANT EXECUTE ON pr_Names TO Mary;  
    GO  
    ```  
  
 <span data-ttu-id="aff94-107">In diesem Szenario kann Mary mithilfe der gespeicherten Prozedur nur auf die **Products** -Tabelle zugreifen.</span><span class="sxs-lookup"><span data-stu-id="aff94-107">In this scenario, Mary can only access the **Products** table by using the stored procedure.</span></span> <span data-ttu-id="aff94-108">Wenn Sie möchten, dass Mary eine SELECT-Anweisung für die Sicht ausführen kann, müssen Sie auch `GRANT SELECT ON vw_Names TO Mary`ausführen.</span><span class="sxs-lookup"><span data-stu-id="aff94-108">If you want Mary to be able to execute a SELECT statement against the view, then you must also execute `GRANT SELECT ON vw_Names TO Mary`.</span></span> <span data-ttu-id="aff94-109">Verwenden Sie die REVOKE-Anweisung, um den Zugriff auf Datenbankobjekte zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="aff94-109">To remove access to database objects, use the REVOKE statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aff94-110">Wenn der Besitzer der Tabelle, Sicht und gespeicherten Prozedur nicht das gleiche Schema ist, wird die Erteilung von Berechtigungen komplexer.</span><span class="sxs-lookup"><span data-stu-id="aff94-110">If the table, the view, and the stored procedure are not owned by the same schema, granting permissions becomes more complex.</span></span>  
  
## <a name="about-grant"></a><span data-ttu-id="aff94-111">Informationen zu GRANT</span><span class="sxs-lookup"><span data-stu-id="aff94-111">About GRANT</span></span>  
 <span data-ttu-id="aff94-112">Sie müssen über die EXECUTE-Berechtigung verfügen, um eine gespeicherte Prozedur auszuführen.</span><span class="sxs-lookup"><span data-stu-id="aff94-112">You must have EXECUTE permission to execute a stored procedure.</span></span> <span data-ttu-id="aff94-113">Sie müssen über die SELECT-, INSERT-, UPDATE- und DELETE-Berechtigungen verfügen, um auf Daten zuzugreifen und sie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="aff94-113">You must have SELECT, INSERT, UPDATE, and DELETE permissions to access and change data.</span></span> <span data-ttu-id="aff94-114">Die GRANT-Anweisung wird auch für andere Berechtigungen wie die zum Erstellen von Tabellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="aff94-114">The GRANT statement is also used for other permissions, such as permission to create tables.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="aff94-115">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="aff94-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="aff94-116">Zusammenfassung: Konfigurieren von Berechtigungen für Datenbankobjekte</span><span class="sxs-lookup"><span data-stu-id="aff94-116">Summary: Configuring Permissions on Database Objects</span></span>](lesson-2-5-summary-configuring-permissions-on-database-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="aff94-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aff94-117">See Also</span></span>  
 <span data-ttu-id="aff94-118">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aff94-118">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span></span>  
 [<span data-ttu-id="aff94-119">REVOKE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="aff94-119">REVOKE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/revoke-transact-sql)  
  
  
