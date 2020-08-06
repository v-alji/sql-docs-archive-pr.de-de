---
title: Neue Server Registrierung oder Server Registrierung bearbeiten (Registerkarte Allgemein) (Reporting Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerserver.general.reportserver.f1
ms.assetid: 5f899a8e-52ef-46b5-b7a9-f200ccd9f724
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 195756498dcefe4686d4b06e758dba9919c0b304
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621661"
---
# <a name="new-or-edit-server-registration-general-tab-reporting-services"></a><span data-ttu-id="4060d-102">Neue Serverregistrierung und Serverregistrierung bearbeiten (Registerkarte Allgemein) (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="4060d-102">New or Edit Server Registration (General Tab) (Reporting Services)</span></span>
  <span data-ttu-id="4060d-103">Auf dieser Registerkarte können Optionen festgelegt werden, wenn eine Instanz von [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]registriert wird.</span><span class="sxs-lookup"><span data-stu-id="4060d-103">Use this tab to specify options when registering an instance of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="4060d-104">Um auf die Seite zuzugreifen, klicken Sie auf der Symbolleiste **Registrierte Server** auf **Reporting Services** , klicken Sie mit der rechten Maustaste auf eine registrierte Servergruppe wie **Reporting Services**, zeigen Sie auf **Neu**, und klicken Sie anschließend auf **Serverregistrierung**.</span><span class="sxs-lookup"><span data-stu-id="4060d-104">To access this page, in Registered Servers, click **Reporting Services** on the **Registered Servers** toolbar, right-click any registered servers group such as **Reporting Services**, point to **New**, and then click **Server Registration**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4060d-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="4060d-105">Options</span></span>  
 <span data-ttu-id="4060d-106">**Servertyp**</span><span class="sxs-lookup"><span data-stu-id="4060d-106">**Server type**</span></span>  
 <span data-ttu-id="4060d-107">Wenn Sie einen Server über Registrierte Server registrieren, ist das Feld **Servertyp** schreibgeschützt, wobei der Feldeintrag mit dem im Bereich **Registrierte Server** angezeigten Servertyp übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="4060d-107">When a server is registered from Registered Servers, the **Server type** box is read-only, and it matches the type of server displayed in the **Registered Servers** pane.</span></span> <span data-ttu-id="4060d-108">Um einen anderen Servertyp zu registrieren, klicken Sie auf der Symbolleiste **Registrierte Server** auf den gewünschten Server, bevor Sie mit der Registrierung eines neuen Servers beginnen.</span><span class="sxs-lookup"><span data-stu-id="4060d-108">To register a different type of server, click the server you want on the **Registered Servers** toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="4060d-109">**Servername**</span><span class="sxs-lookup"><span data-stu-id="4060d-109">**Server name**</span></span>  
 <span data-ttu-id="4060d-110">Geben Sie die Berichtsserverinstanz an, zu der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4060d-110">Specify the report server instance to connect to.</span></span> <span data-ttu-id="4060d-111">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]können Sie über den Instanznamen des Berichtsservers auf einen Berichtsserver zugreifen.</span><span class="sxs-lookup"><span data-stu-id="4060d-111">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], you can access a report server through its instance name.</span></span> <span data-ttu-id="4060d-112">Für jede SQL Server-Instanz, die Sie installieren, ist eine Berichtsserverinstanz zulässig.</span><span class="sxs-lookup"><span data-stu-id="4060d-112">You can have one report server instance for each SQL Server instance that you install.</span></span> <span data-ttu-id="4060d-113">Wenn Sie die Standardinstanz verwenden, geben Sie den Namen der SQL Server-Instanz ein.</span><span class="sxs-lookup"><span data-stu-id="4060d-113">If you are using the default instance, type the name of the SQL Server instance.</span></span> <span data-ttu-id="4060d-114">Wenn Sie eine benannte Instanz verwenden, geben Sie zum Verbinden mit dem Berichtsserver die benannte Instanz im Format MSSQL$InstanceName ein.</span><span class="sxs-lookup"><span data-stu-id="4060d-114">If you are using a named instance, specify the named instance to connect to the report server in the format MSSQL$InstanceName.</span></span>  
  
 <span data-ttu-id="4060d-115">**Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="4060d-115">**Authentication**</span></span>  
 <span data-ttu-id="4060d-116">Die Authentifizierung bei einem Berichtsserver erfolgt durch Internetinformationsdienste (IIS).</span><span class="sxs-lookup"><span data-stu-id="4060d-116">Authentication to a report server is made through Internet Information Services (IIS).</span></span> <span data-ttu-id="4060d-117">Wählen Sie beim Herstellen einer Verbindung mit Reporting Services einen der folgenden Authentifizierungsmodi aus:</span><span class="sxs-lookup"><span data-stu-id="4060d-117">Select from one of the following authentication modes when connecting to Reporting Services:</span></span>  
  
 <span data-ttu-id="4060d-118">**Windows-Authentifizierungsmodus (Windows-Authentifizierung)**</span><span class="sxs-lookup"><span data-stu-id="4060d-118">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 <span data-ttu-id="4060d-119">Stellt die Verbindung zur Berichtsserverinstanz mithilfe der Anmeldeinformationen von [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows her.</span><span class="sxs-lookup"><span data-stu-id="4060d-119">Connect to the report server instance using your [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows credentials.</span></span>  
  
 <span data-ttu-id="4060d-120">**Standardauthentifizierung**</span><span class="sxs-lookup"><span data-stu-id="4060d-120">**Basic Authentication**</span></span>  
 <span data-ttu-id="4060d-121">Stellen Sie die Verbindung mit **Standardauthentifizierung** her, wenn die Reporting Services-Installation für die Verwendung der Standardauthentifizierung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="4060d-121">Connect using **Basic Authentication** if your Reporting Services installation is configured to use Basic Authentication.</span></span>  
  
 <span data-ttu-id="4060d-122">**Formularauthentifizierung**</span><span class="sxs-lookup"><span data-stu-id="4060d-122">**Forms Authentication**</span></span>  
 <span data-ttu-id="4060d-123">Stellen Sie die Verbindung mit **Formularauthentifizierung** her, wenn die Reporting Services-Installation für die Verwendung der Formularauthentifizierung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="4060d-123">Connect using **Forms Authentication** if your Reporting Services installation is configured to use a custom authentication extension.</span></span>  
  
 <span data-ttu-id="4060d-124">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="4060d-124">**User Name**</span></span>  
 <span data-ttu-id="4060d-125">Geben Sie den Benutzernamen ein, der für die Verbindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4060d-125">Enter the login name to use for the connection.</span></span> <span data-ttu-id="4060d-126">Diese Option ist nur verfügbar, wenn Sie **Standardauthentifizierung** oder **Formularauthentifizierung**ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="4060d-126">This option is only available if you have selected **Basic** or **Forms Authentication**.</span></span>  
  
 <span data-ttu-id="4060d-127">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="4060d-127">**Password**</span></span>  
 <span data-ttu-id="4060d-128">Geben Sie das Kennwort für den Benutzernamen ein.</span><span class="sxs-lookup"><span data-stu-id="4060d-128">Enter the password for the user name.</span></span> <span data-ttu-id="4060d-129">Diese Option kann nur bearbeitet werden, wenn Sie **Standardauthentifizierung** oder **Formularauthentifizierung**ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="4060d-129">This option is only editable if you have selected **Basic** or **Forms Authentication**.</span></span>  
  
 <span data-ttu-id="4060d-130">**Kennwort speichern**</span><span class="sxs-lookup"><span data-stu-id="4060d-130">**Remember password**</span></span>  
 <span data-ttu-id="4060d-131">Speichert das eingegebene Kennwort.</span><span class="sxs-lookup"><span data-stu-id="4060d-131">Store the password you have entered.</span></span> <span data-ttu-id="4060d-132">Diese Option ist nur verfügbar, wenn Sie **Standardauthentifizierung** oder **Formularauthentifizierung**ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="4060d-132">This option is only available if you have clicked **Basic** or **Forms Authentication**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4060d-133"> Wenn Sie das Kennwort gespeichert haben und es für die Zukunft nicht mehr speichern möchten, deaktivieren Sie das Kontrollkästchen, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4060d-133">If you have stored the password and want to stop storing it, clear this check box and then click **Save**.</span></span>  
  
 <span data-ttu-id="4060d-134">**Name des registrierten Servers**</span><span class="sxs-lookup"><span data-stu-id="4060d-134">**Registered server name**</span></span>  
 <span data-ttu-id="4060d-135">Der Name, der unter Registrierte Server angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4060d-135">The name you want to appear in Registered Servers.</span></span> <span data-ttu-id="4060d-136">Dieser Name muss mit dem Eintrag im Feld **Servername** nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="4060d-136">This name does not have to match the name in the **Server name** box.</span></span>  
  
 <span data-ttu-id="4060d-137">**Beschreibung des registrierten Servers**</span><span class="sxs-lookup"><span data-stu-id="4060d-137">**Registered server description**</span></span>  
 <span data-ttu-id="4060d-138">Geben Sie eine optionale Beschreibung des Servers ein.</span><span class="sxs-lookup"><span data-stu-id="4060d-138">Enter an optional description of the server.</span></span>  
  
 <span data-ttu-id="4060d-139">**Test**</span><span class="sxs-lookup"><span data-stu-id="4060d-139">**Test**</span></span>  
 <span data-ttu-id="4060d-140">Klicken Sie hier, um die Verbindung mit dem unter **Servername**ausgewählten Server zu testen.</span><span class="sxs-lookup"><span data-stu-id="4060d-140">Click to test the connection to the server selected in **Server name**.</span></span>  
  
 <span data-ttu-id="4060d-141">**Speichern**</span><span class="sxs-lookup"><span data-stu-id="4060d-141">**Save**</span></span>  
 <span data-ttu-id="4060d-142">Klicken Sie hier, um die Einstellungen des registrierten Servers zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4060d-142">Click to save the registered server settings.</span></span>  
  
  
