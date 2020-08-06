---
title: Gewähren von Zugriff auf eine Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- database access
ms.assetid: 686edfe2-3650-48a6-a2da-9d46fa211ad8
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 45b6d6c8dcd9c04d18489807271802aafee785b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621779"
---
# <a name="granting-access-to-a-database"></a><span data-ttu-id="ceb48-102">Gewähren von Zugriff auf eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="ceb48-102">Granting Access to a Database</span></span>
  <span data-ttu-id="ceb48-103">Mary hat nun Zugriff auf diese Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], verfügt jedoch nicht über die Berechtigung zum Zugriff auf die Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="ceb48-103">Mary now has access to this instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], but does not have permission to access the databases.</span></span> <span data-ttu-id="ceb48-104">Selbst auf die Standarddatenbank **TestData** kann sie erst zugreifen, wenn Sie sie als Datenbankbenutzerin autorisieren.</span><span class="sxs-lookup"><span data-stu-id="ceb48-104">She does not even have access to her default database **TestData** until you authorize her as a database user.</span></span>  
  
 <span data-ttu-id="ceb48-105">Wenn Sie Mary Zugriff gewähren möchten, wechseln Sie zur **TestData** -Datenbank, und ordnen Sie ihren Anmeldenamen mithilfe der CREATE USER-Anweisung einer Benutzerin namens Mary zu.</span><span class="sxs-lookup"><span data-stu-id="ceb48-105">To grant Mary access, switch to the **TestData** database, and then use the CREATE USER statement to map her login to a user named Mary.</span></span>  
  
### <a name="to-create-a-user-in-a-database"></a><span data-ttu-id="ceb48-106">So erstellen Sie einen Benutzer in einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="ceb48-106">To create a user in a database</span></span>  
  
1.  <span data-ttu-id="ceb48-107">Geben Sie die folgenden Anweisungen ein (wobei Sie `computer_name` durch den Namen Ihres Computers ersetzen), und führen Sie sie aus, um `Mary` Zugriff auf die `TestData` -Datenbank zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="ceb48-107">Type and execute the following statements (replacing `computer_name` with the name of your computer) to grant `Mary` access to the `TestData` database.</span></span>  
  
    ```  
    USE [TestData];  
    GO  
  
    CREATE USER [Mary] FOR LOGIN [computer_name\Mary];  
    GO  
  
    ```  
  
     <span data-ttu-id="ceb48-108">Mary hat nun sowohl auf [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] als auch auf die `TestData` -Datenbank Zugriff.</span><span class="sxs-lookup"><span data-stu-id="ceb48-108">Now, Mary has access to both [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and the `TestData` database.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ceb48-109">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="ceb48-109">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ceb48-110">Erstellen von Sichten und gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="ceb48-110">Creating Views and Stored Procedures</span></span>](lesson-2-3-creating-views-and-stored-procedures.md)  
  
  
