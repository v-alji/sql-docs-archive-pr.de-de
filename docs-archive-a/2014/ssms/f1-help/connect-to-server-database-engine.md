---
title: Verbindung mit Server herstellen (Datenbank-Engine) (Datenbank-Engine) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.connectoserverunknownservertype.f1
- sql12.swb.connection.login.sqlserver.f1
- sql12.swb.connection.login.sqlce.f1
- sql12.swb.manageSS2k.f1
- sql12.swb.connecttoce.f1
- sql12.swb.connecttoce.connectionproperties.f1
ms.assetid: ee9017b4-8a19-4360-9003-9e6484082d41
author: stevestein
ms.author: sstein
ms.openlocfilehash: ca227d1a3bbc13160962ba2fcad23ff011c950f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717257"
---
# <a name="connect-to-server-database-engine"></a><span data-ttu-id="b4cad-102">Verbindung mit Server herstellen (Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="b4cad-102">Connect to Server (Database Engine)</span></span>
  <span data-ttu-id="b4cad-103">Verwenden Sie dieses Dialogfeld, um Optionen bei der Verbindungsherstellung mit [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] anzuzeigen oder anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b4cad-103">Use this dialog to view or specify options when connecting to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="b4cad-104">In den meisten Fällen können Sie eine Verbindung herstellen, indem Sie im Feld **Servername** den Computernamen des Datenbankservers eingeben und dann auf **Verbinden**klicken.</span><span class="sxs-lookup"><span data-stu-id="b4cad-104">In most cases, you can connect by entering the computer name of the database server in the **Server name** box and then clicking **Connect**.</span></span> <span data-ttu-id="b4cad-105">Geben Sie beim Herstellen der Verbindung mit [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]den Computernamen gefolgt von **\sqlexpress**an.</span><span class="sxs-lookup"><span data-stu-id="b4cad-105">If you are connecting to [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], use the computer name followed by **\sqlexpress**.</span></span>  
  
 <span data-ttu-id="b4cad-106">Viele Faktoren können Auswirkungen auf die Fähigkeit zum Herstellen der Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]haben.</span><span class="sxs-lookup"><span data-stu-id="b4cad-106">Many factors can affect your ability to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="b4cad-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="b4cad-107">Options</span></span>  
 <span data-ttu-id="b4cad-108">**Servertyp**</span><span class="sxs-lookup"><span data-stu-id="b4cad-108">**Server type**</span></span>  
 <span data-ttu-id="b4cad-109">Wenn Sie einen Server über den Objekt-Explorer registrieren, wählen Sie den Typ des Servers aus, mit dem die Verbindung hergestellt werden soll: [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]oder [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4cad-109">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="b4cad-110">Im verbleibenden Bereich des Dialogfelds werden nur die Optionen angezeigt, die auf den ausgewählten Servertyp zutreffen.</span><span class="sxs-lookup"><span data-stu-id="b4cad-110">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="b4cad-111">Wenn Sie einen Server über „Registrierte Server“ registrieren, ist das Feld **Servertyp** schreibgeschützt, wobei der Feldeintrag mit dem in der Komponente „Registrierte Server“ angezeigten Servertyp übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="b4cad-111">When registering a server from Registered Servers, the **Server type** box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="b4cad-112">Zum Registrieren eines anderen Servertyps wählen Sie auf der Symbolleiste Registrierte Server [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], [!INCLUDE[ssEW](../../includes/ssew-md.md)]oder [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] aus, bevor Sie mit der Registrierung eines neuen Servers beginnen.</span><span class="sxs-lookup"><span data-stu-id="b4cad-112">To register a different type of server, select [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], [!INCLUDE[ssEW](../../includes/ssew-md.md)], or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="b4cad-113">**Servername**</span><span class="sxs-lookup"><span data-stu-id="b4cad-113">**Server name**</span></span>  
 <span data-ttu-id="b4cad-114">Wählen Sie die Serverinstanz aus, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b4cad-114">Select the server instance to connect to.</span></span> <span data-ttu-id="b4cad-115">Standardmäßig wird die Serverinstanz angezeigt, mit der zuletzt eine Verbindung bestanden hat.</span><span class="sxs-lookup"><span data-stu-id="b4cad-115">The server instance last connected to is displayed by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4cad-116">Um eine Verbindung mit einer aktiven Instanz von [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] herzustellen, verwenden Sie das Named Pipes-Protokoll unter Angabe des Pipenamens, z. B. „np:\\\\.\pipe\3C3DF6B1-2262-47\tsql\query“. Weitere Informationen finden Sie in der Dokumentation von [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4cad-116">To connect to an active user instance of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] connect using named pipes protocol specifying the pipe name, such as np:\\\\.\pipe\3C3DF6B1-2262-47\tsql\query For more information, see the [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] documentation.</span></span>  
  
 <span data-ttu-id="b4cad-117">**Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="b4cad-117">**Authentication**</span></span>  
 <span data-ttu-id="b4cad-118">Beim Herstellen einer Verbindung mit einer Instanz von sind zwei Authentifizierungs Modi verfügbar [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4cad-118">Two authentication modes are available when connecting to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="b4cad-119">**Windows-Authentifizierungsmodus (Windows-Authentifizierung)**</span><span class="sxs-lookup"><span data-stu-id="b4cad-119">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="b4cad-120">Der Windows Authentifizierungsmodus ermöglicht Benutzern die Verbindung über ein Windows-Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="b4cad-120">Windows Authentication mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="b4cad-121">**SQL Server-Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="b4cad-121">**SQL Server Authentication**</span></span>  
 <span data-ttu-id="b4cad-122">Wenn ein Benutzer eine Verbindung mit einem angegebenen Benutzernamen und einem Kennwort von einer nicht vertrauenswürdigen Verbindung herstellt, führt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die Authentifizierung durch, indem überprüft wird, ob ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldekonto eingerichtet wurde und ob das angegebene Kennwort mit dem zuvor aufgezeichneten übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="b4cad-122">When a user connects with a specified login name and password from a non-trusted connection, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs the authentication itself by checking to see if a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="b4cad-123">Wenn kein Anmeldekonto in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eingerichtet wurde, schlägt die Authentifizierung fehl, und der Benutzer erhält eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="b4cad-123">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not have a login account set, authentication fails, and the user receives an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b4cad-124">Verwenden Sie nach Möglichkeit die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="b4cad-124">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="b4cad-125">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="b4cad-125">**User name**</span></span>  
 <span data-ttu-id="b4cad-126">Geben Sie den Benutzernamen für die Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="b4cad-126">Enter the user name to connect with.</span></span> <span data-ttu-id="b4cad-127">Diese Option ist nur verfügbar, wenn Sie die Windows-Authentifizierung für die Verbindungsherstellung ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="b4cad-127">This option is only available if you have selected to connect using Windows Authentication.</span></span>  
  
 <span data-ttu-id="b4cad-128">**Anmeldung**</span><span class="sxs-lookup"><span data-stu-id="b4cad-128">**Login**</span></span>  
 <span data-ttu-id="b4cad-129">Geben Sie den Anmeldenamen für die Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="b4cad-129">Enter the login to connect with.</span></span> <span data-ttu-id="b4cad-130">Diese Option ist nur verfügbar, wenn Sie zum Verbinden die Authentifizierung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="b4cad-130">This option is only available if you have selected to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="b4cad-131">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="b4cad-131">**Password**</span></span>  
 <span data-ttu-id="b4cad-132">Geben Sie das Kennwort für die Anmeldung ein.</span><span class="sxs-lookup"><span data-stu-id="b4cad-132">Enter the password for the login.</span></span> <span data-ttu-id="b4cad-133">Sie können diese Option nur bearbeiten, wenn Sie zum Verbinden die Authentifizierung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="b4cad-133">This option is only editable if you have selected to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="b4cad-134">**Herstellen einer Verbindung**</span><span class="sxs-lookup"><span data-stu-id="b4cad-134">**Connect**</span></span>  
 <span data-ttu-id="b4cad-135">Klicken Sie hier, um eine Verbindung mit dem oben ausgewählten Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="b4cad-135">Click to connect to the server selected above.</span></span>  
  
 <span data-ttu-id="b4cad-136">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="b4cad-136">**Options**</span></span>  
 <span data-ttu-id="b4cad-137">Klicken Sie auf diese Schaltfläche, um zusätzliche Optionen für die Serververbindung anzuzeigen, z. B. zum Registrieren eines Servers oder zum Speichern des Kennworts.</span><span class="sxs-lookup"><span data-stu-id="b4cad-137">Click to display additional server connection options, such as registering a server and remembering the password.</span></span>  
  
  
