---
title: Erstellen der SQL Server-Änderungsdatenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- oraIns
ms.assetid: 4f79c24a-e99a-4a06-8637-51eeec406259
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0eaeb26d5bea4c9e50db29aaa45297ba763dbbfa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724041"
---
# <a name="create-the-sql-server-change-database"></a><span data-ttu-id="6e6eb-102">Erstellen der SQL Server-Änderungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="6e6eb-102">Create the SQL Server Change Database</span></span>
  <span data-ttu-id="6e6eb-103">Wenn Sie den Assistenten für neue Instanzen starten, wird die Seite Create CDC Database geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6e6eb-103">When you start the New Instance wizard, the Create CDC Database page opens.</span></span> <span data-ttu-id="6e6eb-104">Verwenden Sie die Seite Create CDC Database, um Informationen zur neuen CDC-Instanz bereitzustellen und eine neue Änderungsdatenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6e6eb-104">Use the Create CDC Database page to provide information about the new CDC instance and create a new Change database.</span></span>  
  
 <span data-ttu-id="6e6eb-105">Wenn Sie eine neue CDC-Datenbank erstellen, wird diese für SQL Server CDC aktiviert. Für diese Aktivierung ist eine Anmeldung durch einen Benutzer erforderlich, der Mitglied der festen Serverrolle `sysadmin` ist.</span><span class="sxs-lookup"><span data-stu-id="6e6eb-105">When you create a new CDC database it is enabled for SQL Server CDC and this enablement requires a login that is a member of the `sysadmin` fixed-server role.</span></span>  
  
 <span data-ttu-id="6e6eb-106">Wenn ein Benutzer, der den Assistenten zum Erstellen einer Oracle CDC-Instanz startet, kein Mitglied der festen Serverrolle `sysadmin` ist, wird das Dialogfeld Verbindung mit SQL Server herstellen geöffnet. Darin werden die Anmeldeinformationen für ein Mitglied der Rolle sysadmin angefordert, damit der Task Enable the database for SQL Server CDC ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="6e6eb-106">When a user that starts the Create an Oracle CDC Instance wizard is not a member of the `sysadmin` fixed-server role, the Connect to SQL Server dialog box opens and requests the credentials for a member of the sysadmin role to carry out the Enable the database for SQL Server CDC task.</span></span> <span data-ttu-id="6e6eb-107">Wenn die CDC-Datenbank erstellt wird, wird die `sysadmin` -Anmeldung verworfen, und der Vorgang wird mit der ursprünglichen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung fortgesetzt, die beim Zugreifen auf die Oracle Designer Console verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="6e6eb-107">When the CDC database is created, the `sysadmin` login is discarded and work resumes with the original [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used when the Oracle Designer Console was entered.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6e6eb-108">Für andere Tasks als „Datenbank für SQL Server CDC aktivieren“ muss die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung, die zum Ausführen des Assistenten für neue Instanzen verwendet wird, über die feste Serverrolle `dbcreator` und die UPDATE-Berechtigungen für die MSXDBCDC-Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="6e6eb-108">For tasks other than Enable the database for SQL Server CDC of, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used for running the New Instance Wizard must have the `dbcreator` fixed-server role and UPDATE permissions on the MSXDBCDC database.</span></span>  
  
 <span data-ttu-id="6e6eb-109">Informationen zum Eingeben der Daten im Dialogfeld Verbindung mit SQL Server herstellen finden Sie unter [SQL Server Connection for Instance Creation](sql-server-connection-for-instance-creation.md).</span><span class="sxs-lookup"><span data-stu-id="6e6eb-109">For information on entering the data in the Connect to SQL Server dialog box, see [SQL Server Connection for Instance Creation](sql-server-connection-for-instance-creation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6e6eb-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="6e6eb-110">Options</span></span>  
 <span data-ttu-id="6e6eb-111">**Oracle CDC-Instanz**</span><span class="sxs-lookup"><span data-stu-id="6e6eb-111">**Oracle CDC Instance**</span></span>  
 <span data-ttu-id="6e6eb-112">Geben Sie die folgenden Informationen zur CDC-Instanz an, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="6e6eb-112">Type the following information about the CDC instance you are creating.</span></span>  
  
-   <span data-ttu-id="6e6eb-113">**Name**: Geben Sie einen Namen für den neuen Dienst ein.</span><span class="sxs-lookup"><span data-stu-id="6e6eb-113">**Name**: Type a name for the new service.</span></span> <span data-ttu-id="6e6eb-114">Dieser Name wird auch als Name der neuen Änderungsdatenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="6e6eb-114">This will also be the name of the new Change database.</span></span>  
  
-   <span data-ttu-id="6e6eb-115">**Beschreibung**: Geben Sie eine Beschreibung für die neue Instanz ein, um sie besser identifizieren zu können.</span><span class="sxs-lookup"><span data-stu-id="6e6eb-115">**Description**: Type a description for the new instance to help you identify it.</span></span> <span data-ttu-id="6e6eb-116">Diese Eingabe ist optional.</span><span class="sxs-lookup"><span data-stu-id="6e6eb-116">This is optional.</span></span>  
  
 <span data-ttu-id="6e6eb-117">**SQL Server Change Database**</span><span class="sxs-lookup"><span data-stu-id="6e6eb-117">**SQL Server Change Database**</span></span>  
 <span data-ttu-id="6e6eb-118">Dieser Abschnitt wird verwendet, um die Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6e6eb-118">This section is used to create the database.</span></span>  
  
1.  <span data-ttu-id="6e6eb-119">**Change Database**: Der Name der neuen Änderungsdatenbank.</span><span class="sxs-lookup"><span data-stu-id="6e6eb-119">**Change Database**: The name of the new Change database.</span></span> <span data-ttu-id="6e6eb-120">Der Name der Datenbank entspricht dem Namen, den Sie der Instanz gegeben haben.</span><span class="sxs-lookup"><span data-stu-id="6e6eb-120">The name of the database is the same as the name that you gave to the instance.</span></span> <span data-ttu-id="6e6eb-121">In diesem schreibgeschützten Feld wird der vollständige Pfad zur Datenbank angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6e6eb-121">This read-only field displays the full path to the database.</span></span>  
  
2.  <span data-ttu-id="6e6eb-122">**Datenbank erstellen**: Klicken Sie auf **Datenbank erstellen** , um die Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6e6eb-122">**Create Database**: Click **Create Database** to create the database.</span></span>  
  
     <span data-ttu-id="6e6eb-123">Zum Erstellen der Datenbank muss die Anmeldung über die Serverrolle `sysasmin` verfügen.</span><span class="sxs-lookup"><span data-stu-id="6e6eb-123">To create the database, the login must have the `sysasmin` server role.</span></span> <span data-ttu-id="6e6eb-124">Weitere Informationen finden Sie oben unter dem Sicherheitshinweis.</span><span class="sxs-lookup"><span data-stu-id="6e6eb-124">See the security note above for more information.</span></span>  
  
     <span data-ttu-id="6e6eb-125">Nachdem Sie die Datenbank erstellt haben, können Sie auf **Weiter** klicken, um den Schritt [Connect to an Oracle Source Database](connect-to-an-oracle-source-database.md)auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6e6eb-125">After you create the database, you can click **Next** to [Connect to an Oracle Source Database](connect-to-an-oracle-source-database.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e6eb-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6e6eb-126">See Also</span></span>  
 <span data-ttu-id="6e6eb-127">[Erstellen der Instanz für die SQL Server-Änderungsdatenbank](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="6e6eb-127">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="6e6eb-128">Oracle CDC Service</span><span class="sxs-lookup"><span data-stu-id="6e6eb-128">The Oracle CDC Service</span></span>](the-oracle-cdc-service.md)  
  
  
