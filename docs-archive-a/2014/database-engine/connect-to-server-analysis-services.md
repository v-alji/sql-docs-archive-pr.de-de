---
title: Verbindung mit Server herstellen (Analysis Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connection.login.analysisserver.f1
ms.assetid: 7e277d22-8d4b-422e-8882-7c5dd7a6d915
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b3530f38534e09ef19e77293880129274dfc211b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694702"
---
# <a name="connect-to-server-analysis-services"></a><span data-ttu-id="60b15-102">Verbindung mit Server herstellen (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="60b15-102">Connect to Server (Analysis Services)</span></span>
  <span data-ttu-id="60b15-103">Verwenden Sie dieses Dialogfeld, um Optionen bei der Verbindungsherstellung mit [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] anzuzeigen oder anzugeben.</span><span class="sxs-lookup"><span data-stu-id="60b15-103">Use this dialog to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="60b15-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="60b15-104">Options</span></span>  
 <span data-ttu-id="60b15-105">**Servertyp**</span><span class="sxs-lookup"><span data-stu-id="60b15-105">**Server type**</span></span>  
 <span data-ttu-id="60b15-106">Wenn Sie einen Server über den Objekt-Explorer registrieren, wählen Sie den Typ des Servers aus, mit dem eine Verbindung hergestellt wird: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services oder Integration Services.</span><span class="sxs-lookup"><span data-stu-id="60b15-106">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services.</span></span> <span data-ttu-id="60b15-107">Im verbleibenden Bereich des Dialogfelds werden nur die Optionen angezeigt, die auf den ausgewählten Servertyp zutreffen.</span><span class="sxs-lookup"><span data-stu-id="60b15-107">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="60b15-108">Wenn Sie einen Server über „Registrierte Server“ registrieren, ist das Feld **Servertyp** schreibgeschützt, wobei der Feldeintrag mit dem in der Komponente „Registrierte Server“ angezeigten Servertyp übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="60b15-108">When registering a server from Registered Servers, the **Server type** box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="60b15-109">Zum Registrieren eines anderen Servertyps wählen Sie auf der Symbolleiste "Registrierte Server" die Option [!INCLUDE[ssDE](../includes/ssde-md.md)], "Analysis Services", "Reporting Services" oder "Integration Services" aus. Anschließend können Sie mit der Registrierung eines neuen Servers beginnen.</span><span class="sxs-lookup"><span data-stu-id="60b15-109">To register a different type of server, select [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="60b15-110">**Servername**</span><span class="sxs-lookup"><span data-stu-id="60b15-110">**Server name**</span></span>  
 <span data-ttu-id="60b15-111">Wählen Sie die Serverinstanz aus, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="60b15-111">Select the server instance to connect to.</span></span> <span data-ttu-id="60b15-112">Standardmäßig wird die Serverinstanz angezeigt, mit der zuletzt eine Verbindung bestanden hat.</span><span class="sxs-lookup"><span data-stu-id="60b15-112">The server instance last connected to is displayed by default.</span></span>  
  
 <span data-ttu-id="60b15-113">**Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="60b15-113">**Authentication**</span></span>  
 <span data-ttu-id="60b15-114">Beim Herstellen einer Verbindung mit einer Instanz von Analysis Services werden die folgenden Authentifizierungsmodi unterstützt: [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="60b15-114">The following authentication modes are supported when connecting to an instance of Analysis Services: [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="60b15-115">**Windows-Authentifizierungsmodus (Windows-Authentifizierung)**</span><span class="sxs-lookup"><span data-stu-id="60b15-115">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 <span data-ttu-id="60b15-116">Der **Windows-Authentifizierungs** Modus ermöglicht Benutzern das Herstellen einer Verbindung über ein Windows-Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="60b15-116">**Windows Authentication** mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="60b15-117">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="60b15-117">**User name**</span></span>  
 <span data-ttu-id="60b15-118">Diese Option steht in dieser Version nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="60b15-118">This option is not available in this release.</span></span> <span data-ttu-id="60b15-119">Geben Sie den Benutzernamen für die Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="60b15-119">Enter the user name to connect with.</span></span> <span data-ttu-id="60b15-120">Diese Option ist nur verfügbar, wenn Sie die **Windows-Authentifizierung**für die Verbindungsherstellung ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="60b15-120">This option is only available if you have selected to connect using **Windows Authentication**.</span></span>  
  
 <span data-ttu-id="60b15-121">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="60b15-121">**Password**</span></span>  
 <span data-ttu-id="60b15-122">Diese Option steht in dieser Version nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="60b15-122">This option is not available in this release.</span></span> <span data-ttu-id="60b15-123">Geben Sie das Kennwort für die Anmeldung ein.</span><span class="sxs-lookup"><span data-stu-id="60b15-123">Enter the password for the login.</span></span> <span data-ttu-id="60b15-124">Sie können diese Option nur bearbeiten, wenn Sie zum Verbinden die Authentifizierung von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="60b15-124">This option is only editable if you have selected to connect using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="60b15-125">**Herstellen einer Verbindung**</span><span class="sxs-lookup"><span data-stu-id="60b15-125">**Connect**</span></span>  
 <span data-ttu-id="60b15-126">Klicken Sie hier, um eine Verbindung mit dem oben ausgewählten Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="60b15-126">Click to connect to the server selected above.</span></span>  
  
 <span data-ttu-id="60b15-127">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="60b15-127">**Options**</span></span>  
 <span data-ttu-id="60b15-128">Klicken Sie auf diese Schaltfläche, um zusätzliche Optionen für die Serververbindung anzuzeigen, z. B. zum Registrieren eines Servers oder zum Speichern des Kennworts.</span><span class="sxs-lookup"><span data-stu-id="60b15-128">Click to display additional server connection options, such as registering a server and remembering the password.</span></span>  
  
  
