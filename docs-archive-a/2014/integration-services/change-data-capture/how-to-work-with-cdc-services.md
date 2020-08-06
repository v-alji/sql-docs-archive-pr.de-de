---
title: Verwenden von CDC Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: db5c718a-6e7f-48ec-82a3-9d5b131716e5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7cfb5a0ed0e9ded8e0be118deb3c819626448896
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616637"
---
# <a name="how-to-work-with-cdc-services"></a><span data-ttu-id="e96ba-102">Verwenden von CDC Services</span><span class="sxs-lookup"><span data-stu-id="e96ba-102">How to Work with CDC Services</span></span>
  <span data-ttu-id="e96ba-103">In diesem Verfahren wird beschrieben, wie Sie mithilfe der CDC Service Configuration Console eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz für die Verwendung von Oracle CDC Services vorbereiten und einen neuen CDC-Dienst erstellen.</span><span class="sxs-lookup"><span data-stu-id="e96ba-103">This procedure describes how to use the CDC Service Configuration Console to prepare a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to work with Oracle CDC Services and to create a new CDC service.</span></span>  
  
### <a name="to-work-with-cdc-services"></a><span data-ttu-id="e96ba-104">So verwenden Sie CDC-Dienste</span><span class="sxs-lookup"><span data-stu-id="e96ba-104">To work with CDC services</span></span>  
  
1.  <span data-ttu-id="e96ba-105">Wählen Sie im Menü **Start** die Option **CDC Service Configuration for Oracle**.</span><span class="sxs-lookup"><span data-stu-id="e96ba-105">From the **Start** menu, select the **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="e96ba-106">Wählen Sie im linken Bereich die Option **Local CDC Services** (Stammebene).</span><span class="sxs-lookup"><span data-stu-id="e96ba-106">From the left pane, select **Local CDC Services** (the root level).</span></span>  
  
3.  <span data-ttu-id="e96ba-107">Führen Sie eine oder beide der folgenden Tasks aus:</span><span class="sxs-lookup"><span data-stu-id="e96ba-107">You carry out the one or both of the following tasks:</span></span>  
  
    -   <span data-ttu-id="e96ba-108">**Prepare SQL Server**</span><span class="sxs-lookup"><span data-stu-id="e96ba-108">**Prepare SQL Server**</span></span>  
  
         <span data-ttu-id="e96ba-109">Aktivieren Sie diese Option im **Aktionsbereich** rechts in der CDC Service Configuration Console.</span><span class="sxs-lookup"><span data-stu-id="e96ba-109">Select this option from the **Actions** pane on the right side of the CDC Service Configuration Console.</span></span>  
  
         <span data-ttu-id="e96ba-110">Sie können auch mit der rechten Maustaste auf **Local CDC Services** klicken und **Prepare SQL Server**wählen.</span><span class="sxs-lookup"><span data-stu-id="e96ba-110">You can also right-click **Local CDC Services** and select **Prepare SQL Server**.</span></span>  
  
         <span data-ttu-id="e96ba-111">Das Dialogfeld Preparing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Instance for Oracle CDC wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e96ba-111">The Preparing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Instance for Oracle CDC dialog box opens.</span></span>  
  
         <span data-ttu-id="e96ba-112">Zum Vorbereiten der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz auf Oracle CDC-Dienste muss die Anmeldung über eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung mit der festen Serverrolle `dbcreator` verfügen.</span><span class="sxs-lookup"><span data-stu-id="e96ba-112">To prepare the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance for Oracle CDC services, the login must have a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with the `dbcreator` fixed server role.</span></span> <span data-ttu-id="e96ba-113">Diese Anmeldung wird verwendet, um die MSXDBCDC-Datenbank zu erstellen, die zum Hinzufügen von Oracle CDC Services und im weiteren Verlauf von Oracle CDC-Instanzen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e96ba-113">This login is used to create the MSXDBCDC database that is required for adding Oracle CDC Services and, later on, Oracle CDC Instances.</span></span>  
  
         <span data-ttu-id="e96ba-114">Informationen zur Verwendung dieses Dialogfelds finden Sie unter [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span><span class="sxs-lookup"><span data-stu-id="e96ba-114">For information on how to use this dialog box, see [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span></span> <span data-ttu-id="e96ba-115">Informationen zum Aktivieren einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz für CDC finden Sie unter [Vorbereiten von SQL Server für CDC](how-to-prepare-sql-server-for-cdc.md).</span><span class="sxs-lookup"><span data-stu-id="e96ba-115">For information on how to enable a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance for CDC, see [How to Prepare SQL Server for CDC](how-to-prepare-sql-server-for-cdc.md).</span></span>  
  
    -   <span data-ttu-id="e96ba-116">**Erstellen eines neuen CDC-Diensts**</span><span class="sxs-lookup"><span data-stu-id="e96ba-116">**Create a new CDC service**</span></span>  
  
         <span data-ttu-id="e96ba-117">Klicken Sie auf der rechten Seite der CDC Service Configuration Console im **Aktionsbereich** auf **Neuer Dienst** .</span><span class="sxs-lookup"><span data-stu-id="e96ba-117">Click **New Service** from the **Actions** pane on the right side of the CDC Service Configuration Console.</span></span>  
  
         <span data-ttu-id="e96ba-118">Sie können auch mit der rechten Maustaste auf **Local CDC Services** klicken und **Neuer Dienst**auswählen.</span><span class="sxs-lookup"><span data-stu-id="e96ba-118">You can also right-Click **Local CDC Services** and select **New Service**.</span></span>  
  
         <span data-ttu-id="e96ba-119">Das Dialogfeld New Oracle CDC Service wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e96ba-119">The New Oracle CDC Service dialog box opens.</span></span>  
  
         <span data-ttu-id="e96ba-120">Informationen zur Verwendung dieses Dialogfelds finden Sie unter [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md).</span><span class="sxs-lookup"><span data-stu-id="e96ba-120">For information on how to use this dialog box, see [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md).</span></span> <span data-ttu-id="e96ba-121">Informationen zum Erstellen oder Bearbeiten eines CDC-Diensts finden Sie unter [Erstellen und Bearbeiten eines CDC Service](how-to-create-and-edit-a-cdc-service.md).</span><span class="sxs-lookup"><span data-stu-id="e96ba-121">For information on how to create or edit a CDC service, see [How to Create and Edit a CDC Service](how-to-create-and-edit-a-cdc-service.md).</span></span>  
  
         <span data-ttu-id="e96ba-122">Die vom Oracle CDC Service verwendete [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung muss lediglich Mitglied der festen Serverrolle `public` sein. Es sind keine anderen Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e96ba-122">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used by the Oracle CDC Service only needs to be a member of the `public` fixed-server role, no other privileges are needed.</span></span> <span data-ttu-id="e96ba-123">Um den Oracle CDC Service zu erstellen, muss die Anmeldung jedoch die Schreibberechtigung für die MSXDBCDC-Datenbank besitzen, z. B. muss der Anmeldung die Datenbankrolle **db_owner** zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="e96ba-123">However, to create the Oracle CDC Service, the login must have write permission to the MSXDBCDC database, for example the **db_owner** database role must be assigned to the login.</span></span> <span data-ttu-id="e96ba-124">Wenn mit einer Anmeldung ohne Schreibberechtigung für die MSXDBDCDC-Datenbank versucht wird, eine neue Oracle CDC-Instanz zu erstellen, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e96ba-124">When a login without write permission to the MSXDBDCDC database attempts to create a new Oracle CDC instance an error message is displayed.</span></span> <span data-ttu-id="e96ba-125">Klicken Sie in diesem Dialogfeld auf **OK** , um das Dialogfeld Verbindung mit SQL Server herstellen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e96ba-125">Click **OK** in that dialog box to display the Connect to SQL Server dialog box.</span></span>  
  
         <span data-ttu-id="e96ba-126">Informationen zum Eingeben der Anmeldeinformationen für eine Anmeldung, die über die Schreibberechtigung für die MSXDBCDC-Datenbank verfügt, z. B. die Datenbankrolle **db_owner** , finden Sie unter [Erstellen und Bearbeiten eines CDC Service](create-and-edit-an-oracle-cdc-service.md) und [Verbindung mit SQL Server](connection-to-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e96ba-126">For information on how to enter the credentials for a login that has write permission to the MSXDBCDC database, such the **db_owner** database role, see [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) and [Connection to SQL Server](connection-to-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e96ba-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e96ba-127">See Also</span></span>  
 [<span data-ttu-id="e96ba-128">Verwenden von CDC Services</span><span class="sxs-lookup"><span data-stu-id="e96ba-128">Work with CDC Services</span></span>](work-with-cdc-services.md)  
  
  
