---
title: Erstellen und Bearbeiten eines CDC Service | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1b3d47a5-dc89-482d-bbc7-fff04f194c43
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d90534b475901b08fcd2e09acdc0f7976f0fb6e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695978"
---
# <a name="how-to-create-and-edit-a-cdc-service"></a><span data-ttu-id="ca62d-102">Erstellen und Bearbeiten eines CDC Service</span><span class="sxs-lookup"><span data-stu-id="ca62d-102">How to Create and Edit a CDC Service</span></span>
  <span data-ttu-id="ca62d-103">In diesen Verfahren wird beschrieben, wie Sie über die CDC Service Configuration Console einen neuen Oracle CDC Service erstellen und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="ca62d-103">These procedures describe how to create and edit a new Oracle CDC Service from the CDC Service Configuration Console.</span></span>  
  
 <span data-ttu-id="ca62d-104">Für dieses Verfahren ist ein Windows-Benutzer mit Administratorrechten für den Computer erforderlich, auf dem der Oracle CDC Service konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="ca62d-104">This procedure requires a Windows user with administrator privileges on the computer where the Oracle CDC service is configured.</span></span>  
  
### <a name="to-create-a-new-cdc-service"></a><span data-ttu-id="ca62d-105">So erstellen Sie einen neuen CDC-Dienst</span><span class="sxs-lookup"><span data-stu-id="ca62d-105">To create a new CDC service</span></span>  
  
1.  <span data-ttu-id="ca62d-106">Wählen Sie im Menü **Start** die Option **CDC Service Configuration for Oracle**.</span><span class="sxs-lookup"><span data-stu-id="ca62d-106">From the **Start** menu, select **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="ca62d-107">Klicken im linken Bereich mit der rechten Maustaste auf Local CDC Services und wählen Sie Neuer Dienst aus.</span><span class="sxs-lookup"><span data-stu-id="ca62d-107">From the left pane, right click Local CDC Services and select New Service</span></span>  
  
     <span data-ttu-id="ca62d-108">Sie können auch im **Aktionsbereich** auf **Neuer Dienst** klicken.</span><span class="sxs-lookup"><span data-stu-id="ca62d-108">You can also click **New Service** from the **Actions** pane.</span></span>  
  
3.  <span data-ttu-id="ca62d-109">Geben Sie die erforderlichen Informationen im Dialogfeld New Oracle CDC Service ein.</span><span class="sxs-lookup"><span data-stu-id="ca62d-109">Type or enter the required information in the New Oracle CDC Service dialog box.</span></span> <span data-ttu-id="ca62d-110">Informationen zum Eingeben von Informationen im Dialogfeld New Oracle CDC Service finden Sie unter [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) .</span><span class="sxs-lookup"><span data-stu-id="ca62d-110">See [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) for information on how to enter information in the New Oracle CDC Service dialog box.</span></span>  
  
     <span data-ttu-id="ca62d-111">Die im Dialogfeld New Oracle CDC Service angegebenen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldeinformationen werden vom Oracle CDC Service verwendet, wenn der Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ca62d-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login provided in the New Oracle CDC Service dialog box is used by the Oracle CDC Service when the service runs.</span></span> <span data-ttu-id="ca62d-112">Diese Anmeldung muss lediglich Mitglied der festen Serverrolle public sein. Es sind keine weiteren Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ca62d-112">This login only needs to be a member of the public fixed-server role, no other privileges are needed.</span></span> <span data-ttu-id="ca62d-113">Nachdem neue Oracle CDC-Instanzen hinzugefügt wurden, wird über diese Anmeldung der **db_owner** -Zugriff auf die zugeordneten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC-Datenbanken gewährt.</span><span class="sxs-lookup"><span data-stu-id="ca62d-113">Once new Oracle CDC Instances are added, that login receives **db_owner** access to the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC databases.</span></span>  
  
4.  <span data-ttu-id="ca62d-114">Klicken Sie auf **OK**, nachdem Sie die erforderlichen Informationen eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="ca62d-114">When you finish entering the required information, click **OK**.</span></span>  
  
     <span data-ttu-id="ca62d-115">Zum Erstellen der Definition des Oracle CDC-Windows-Diensts benötigt das Programm Aktualisierungszugriff auf die MSXDBCDC-Datenbank in der zugeordneten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz.</span><span class="sxs-lookup"><span data-stu-id="ca62d-115">To create the Oracle CDC Windows Service definition, the program needs update access to the MSXDBCDC database in the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="ca62d-116">Wenn Sie auf **OK**klicken, wird der Benutzer in einem Dialogfeld aufgefordert, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldeinformationen mit Aktualisierungszugriff auf die MSXDBCDC-Datenbank einzugeben.</span><span class="sxs-lookup"><span data-stu-id="ca62d-116">When you click **OK**, a dialog box prompts the user to enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with an update access to the MSXDBCDC database.</span></span>  
  
     <span data-ttu-id="ca62d-117">Informationen zu den Daten, die Sie im Dialogfeld Verbindung mit SQL Server herstellen eingeben müssen, finden Sie unter [Connection to SQL Server](connection-to-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ca62d-117">For information about the data you must type into the Connect to SQL Server dialog box, see [Connection to SQL Server](connection-to-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="ca62d-118">Klicken Sie auf **OK** , um das Dialogfeld New Oracle CDC Service zu schließen.</span><span class="sxs-lookup"><span data-stu-id="ca62d-118">Click **OK** to close the New Oracle CDC Service dialog box.</span></span>  
  
### <a name="to-edit-a-cdc-service"></a><span data-ttu-id="ca62d-119">So bearbeiten Sie einen CDC-Dienst</span><span class="sxs-lookup"><span data-stu-id="ca62d-119">To edit a CDC service</span></span>  
  
1.  <span data-ttu-id="ca62d-120">Wählen Sie im Menü **Start** die Option **CDC Service Configuration for Oracle**.</span><span class="sxs-lookup"><span data-stu-id="ca62d-120">From the **Start** menu, select **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="ca62d-121">Wählen Sie im linken Bereich **Local CDC Services** , klicken Sie anschließend mit der rechten Maustaste auf den lokalen Dienst, den Sie bearbeiten möchten, und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ca62d-121">From the left pane, select **Local CDC Services** then right-click the local service you want to edit and select **Properties**.</span></span>  
  
     <span data-ttu-id="ca62d-122">Sie können den Dienst, den Sie verwenden möchten, auch im mittleren Bereich auswählen und dann im **Aktionsbereich** auf **Eigenschaften**klicken.</span><span class="sxs-lookup"><span data-stu-id="ca62d-122">You can also select the service you are working with in the middle and then from the **Actions** pane, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="ca62d-123">Geben Sie die erforderlichen Informationen im Dialogfeld CDC Service Properties ein.</span><span class="sxs-lookup"><span data-stu-id="ca62d-123">Type or enter the required information in the CDC Service Properties dialog box.</span></span> <span data-ttu-id="ca62d-124">Informationen zum Eingeben von Informationen im Dialogfeld CDC Service Properties finden Sie unter [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) .</span><span class="sxs-lookup"><span data-stu-id="ca62d-124">See [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) for information on how to enter information in the CDC Service Properties dialog box.</span></span>  
  
4.  <span data-ttu-id="ca62d-125">Klicken Sie nach dem Eingeben der erforderlichen Informationen auf **OK**, um das Dialogfeld Verbindung mit SQL Server herstellen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ca62d-125">When you finish entering the required information, Click **OK**, the Connect to SQL Server dialog box opens.</span></span>  
  
     <span data-ttu-id="ca62d-126">Wenn mit einer Anmeldung ohne Schreibberechtigung für die MSXDBDCDC-Datenbank versucht wird, eine neue Oracle CDC-Instanz zu erstellen, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ca62d-126">When a login without write permission to the MSXDBDCDC database attempts to create a new Oracle CDC instance an error message is displayed.</span></span> <span data-ttu-id="ca62d-127">Klicken Sie in diesem Dialogfeld auf **OK** , um das Dialogfeld Verbindung mit SQL Server herstellen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ca62d-127">Click **OK** in that dialog box to display the Connect to SQL Server dialog box.</span></span> <span data-ttu-id="ca62d-128">In diesem Dialogfeld müssen Sie die Anmeldeinformationen für eine Anmeldung eingeben, die über die Schreibberechtigung für die MSXDBCDC-Datenbank verfügt, z.B. die Datenbankrolle **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="ca62d-128">In this dialog box you must enter the credentials for a login that has write permission to the MSXDBCDC database, such the **db_owner** database role.</span></span>  
  
     <span data-ttu-id="ca62d-129">Informationen zu den Daten, die Sie im Dialogfeld Verbindung mit SQL Server herstellen eingeben müssen, finden Sie unter [Connection to SQL Server](connection-to-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ca62d-129">For information about the data you must type into the Connect to SQL Server dialog box, see [Connection to SQL Server](connection-to-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="ca62d-130">Klicken Sie im Dialogfeld Verbindung mit Oracle herstellen auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="ca62d-130">Click **OK** in the Connect to Oracle dialog box.</span></span> <span data-ttu-id="ca62d-131">Beide Dialogfelder werden geschlossen, und der Dienst wird aktualisiert und registriert.</span><span class="sxs-lookup"><span data-stu-id="ca62d-131">Both dialog boxes close and the service is updated and registered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca62d-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ca62d-132">See Also</span></span>  
 <span data-ttu-id="ca62d-133">[Change Data Capture Designer für Oracle von Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span><span class="sxs-lookup"><span data-stu-id="ca62d-133">[Change Data Capture Designer for Oracle by Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span></span>  
 [<span data-ttu-id="ca62d-134">Erstellen und Bearbeiten eines Oracle CDC Service</span><span class="sxs-lookup"><span data-stu-id="ca62d-134">Create and Edit an Oracle CDC Service</span></span>](create-and-edit-an-oracle-cdc-service.md)  
  
  
