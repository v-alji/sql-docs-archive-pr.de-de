---
title: Verbindung mit Server herstellen (Integration Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connection.login.dtsserver.f1
ms.assetid: 5be897bd-f36c-4c6a-a91a-13d0d016f8b6
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8821018c45fdd77c4b3b896afc47b8f5b425af88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724142"
---
# <a name="connect-to-server-integration-services"></a><span data-ttu-id="40af8-102">Verbindung mit Server herstellen (Integration Services)</span><span class="sxs-lookup"><span data-stu-id="40af8-102">Connect to Server (Integration Services)</span></span>
  <span data-ttu-id="40af8-103">Verwenden Sie dieses Dialogfeld, um Optionen bei der Verbindungsherstellung mit [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] anzuzeigen oder anzugeben.</span><span class="sxs-lookup"><span data-stu-id="40af8-103">Use this dialog to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="40af8-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="40af8-104">Options</span></span>  
 <span data-ttu-id="40af8-105">**Servertyp**</span><span class="sxs-lookup"><span data-stu-id="40af8-105">**Server type**</span></span>  
 <span data-ttu-id="40af8-106">Wenn Sie einen Server über den Objekt-Explorer registrieren, wählen Sie den Typ des Servers aus, mit dem eine Verbindung hergestellt wird: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services oder Integration Services.</span><span class="sxs-lookup"><span data-stu-id="40af8-106">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services.</span></span> <span data-ttu-id="40af8-107">Im verbleibenden Bereich des Dialogfelds werden nur die Optionen angezeigt, die auf den ausgewählten Servertyp zutreffen.</span><span class="sxs-lookup"><span data-stu-id="40af8-107">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="40af8-108">Wenn Sie einen Server über Registrierte Server registrieren, ist das Feld Servertyp schreibgeschützt, wobei der Feldeintrag mit dem in der Komponente Registrierte Server angezeigten Servertyp übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="40af8-108">When registering a server from Registered Servers, the Server type box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="40af8-109">Zum Registrieren eines anderen Servertyps wählen Sie auf der Symbolleiste "Registrierte Server" die Option [!INCLUDE[ssDE](../includes/ssde-md.md)], "Analysis Services", "Reporting Services" oder "Integration Services" aus. Anschließend können Sie mit der Registrierung eines neuen Servers beginnen.</span><span class="sxs-lookup"><span data-stu-id="40af8-109">To register a different type of server, select [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="40af8-110">**Servername**</span><span class="sxs-lookup"><span data-stu-id="40af8-110">**Server name**</span></span>  
 <span data-ttu-id="40af8-111">Wählen Sie den Server für die Verbindungsherstellung aus.</span><span class="sxs-lookup"><span data-stu-id="40af8-111">Select the server to connect to.</span></span> <span data-ttu-id="40af8-112">Standardmäßig wird die Serverinstanz angezeigt, mit der zuletzt eine Verbindung bestanden hat.</span><span class="sxs-lookup"><span data-stu-id="40af8-112">The server instance last connected to is displayed by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40af8-113">Verwenden Sie nicht *\<servername>* \\ *\<instancename>* , da [!INCLUDE[ssIS](../includes/ssis-md.md)] nicht mehrere Instanzen auf einem Computer unterstützt.</span><span class="sxs-lookup"><span data-stu-id="40af8-113">Do not use *\<servername>*\\*\<instancename>*, because [!INCLUDE[ssIS](../includes/ssis-md.md)] does not support multiple instances on a computer.</span></span>  
  
 <span data-ttu-id="40af8-114">**Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="40af8-114">**Authentication**</span></span>  
 <span data-ttu-id="40af8-115">Für [!INCLUDE[msCoName](../includes/msconame-md.md)] steht nur die [!INCLUDE[ssIS](../includes/ssis-md.md)]Windows-Authentifizierung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="40af8-115">Only [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span> <span data-ttu-id="40af8-116">Der Windows Authentifizierungsmodus ermöglicht Benutzern die Verbindung über ein Windows-Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="40af8-116">Windows Authentication mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="40af8-117">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="40af8-117">**User name**</span></span>  
 <span data-ttu-id="40af8-118">Diese Option ist nicht verfügbar, da für [!INCLUDE[ssIS](../includes/ssis-md.md)]nur die Windows-Authentifizierung zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="40af8-118">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="40af8-119">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="40af8-119">**Password**</span></span>  
 <span data-ttu-id="40af8-120">Diese Option ist nicht verfügbar, da für [!INCLUDE[ssIS](../includes/ssis-md.md)]nur die Windows-Authentifizierung zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="40af8-120">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="40af8-121">**Herstellen einer Verbindung**</span><span class="sxs-lookup"><span data-stu-id="40af8-121">**Connect**</span></span>  
 <span data-ttu-id="40af8-122">Klicken Sie hier, um eine Verbindung mit dem oben ausgewählten Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="40af8-122">Click to connect to the server selected above.</span></span>  
  
 <span data-ttu-id="40af8-123">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="40af8-123">**Options**</span></span>  
 <span data-ttu-id="40af8-124">Klicken Sie auf diese Schaltfläche, um zusätzliche Optionen für die Serververbindung anzuzeigen, z. B. zum Registrieren eines Servers oder zum Speichern des Kennworts.</span><span class="sxs-lookup"><span data-stu-id="40af8-124">Click to display additional server connection options, such as registering a server and remembering the password.</span></span>  
  
  
