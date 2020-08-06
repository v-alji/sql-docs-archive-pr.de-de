---
title: Verbinden mit SQL Server Integration Services (Seite Anmeldung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttodtsserver.login.f1
- sql12.swb.connecttodts.login.f1
ms.assetid: 402c2de4-f4ea-40b0-909f-3ddf3bd59950
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 285518f4a1f3d9180d2c3c07a41bf75a00ea3593
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724138"
---
# <a name="connect-to-server-login-page-integration-services"></a><span data-ttu-id="c9cd9-102">Verbinden mit SQL Server Integration Services (Seite Anmeldung)</span><span class="sxs-lookup"><span data-stu-id="c9cd9-102">Connect to Server (Login Page) Integration Services</span></span>
  <span data-ttu-id="c9cd9-103">Mit dieser Registerkarte können Sie die folgenden Optionen anzeigen oder angeben, wenn Sie eine Verbindung mit herstellen [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9cd9-103">Use this tab to view or specify the following options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="c9cd9-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="c9cd9-104">Options</span></span>  
 <span data-ttu-id="c9cd9-105">**Servertyp**</span><span class="sxs-lookup"><span data-stu-id="c9cd9-105">**Server type**</span></span>  
 <span data-ttu-id="c9cd9-106">Wenn Sie einen Server über den Objekt-Explorer registrieren, wählen Sie den Typ des Servers aus, mit dem eine Verbindung hergestellt wird: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services oder Integration Services.</span><span class="sxs-lookup"><span data-stu-id="c9cd9-106">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services.</span></span> <span data-ttu-id="c9cd9-107">Im verbleibenden Bereich des Dialogfelds werden nur die Optionen angezeigt, die auf den ausgewählten Servertyp zutreffen.</span><span class="sxs-lookup"><span data-stu-id="c9cd9-107">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="c9cd9-108">Wenn Sie einen Server über „Registrierte Server“ registrieren, ist das Feld **Servertyp** schreibgeschützt, wobei der Feldeintrag mit dem in der Komponente „Registrierte Server“ angezeigten Servertyp übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="c9cd9-108">When registering a server from Registered Servers, the **Server type** box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="c9cd9-109">Zum Registrieren eines anderen Servertyps wählen Sie auf der Symbolleiste "Registrierte Server" die Option [!INCLUDE[ssDE](../includes/ssde-md.md)], "Analysis Services", "Reporting Services" oder "Integration Services" aus. Anschließend können Sie mit der Registrierung eines neuen Servers beginnen.</span><span class="sxs-lookup"><span data-stu-id="c9cd9-109">To register a different type of server, select [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="c9cd9-110">**Servername**</span><span class="sxs-lookup"><span data-stu-id="c9cd9-110">**Server name**</span></span>  
 <span data-ttu-id="c9cd9-111">Wählen Sie den Server für die Verbindungsherstellung aus.</span><span class="sxs-lookup"><span data-stu-id="c9cd9-111">Select the server to connect to.</span></span> <span data-ttu-id="c9cd9-112">Standardmäßig wird die Serverinstanz angezeigt, mit der zuletzt eine Verbindung bestanden hat.</span><span class="sxs-lookup"><span data-stu-id="c9cd9-112">The server instance last connected to is displayed by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9cd9-113">Verwenden Sie nicht *\<servername>* \\ *\<instancename>* , da [!INCLUDE[ssIS](../includes/ssis-md.md)] nicht mehrere Instanzen auf einem Computer unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c9cd9-113">Do not use *\<servername>*\\*\<instancename>*, because [!INCLUDE[ssIS](../includes/ssis-md.md)] does not support multiple instances on a computer.</span></span>  
  
 <span data-ttu-id="c9cd9-114">**Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="c9cd9-114">**Authentication**</span></span>  
 <span data-ttu-id="c9cd9-115">Für [!INCLUDE[msCoName](../includes/msconame-md.md)] steht nur die [!INCLUDE[ssIS](../includes/ssis-md.md)]Windows-Authentifizierung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c9cd9-115">Only [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span> <span data-ttu-id="c9cd9-116">Der Windows Authentifizierungsmodus ermöglicht Benutzern die Verbindung über ein Windows-Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="c9cd9-116">Windows Authentication mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="c9cd9-117">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="c9cd9-117">**User name**</span></span>  
 <span data-ttu-id="c9cd9-118">Diese Option ist nicht verfügbar, da für [!INCLUDE[ssIS](../includes/ssis-md.md)]nur die Windows-Authentifizierung zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="c9cd9-118">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="c9cd9-119">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="c9cd9-119">**Password**</span></span>  
 <span data-ttu-id="c9cd9-120">Diese Option ist nicht verfügbar, da für [!INCLUDE[ssIS](../includes/ssis-md.md)]nur die Windows-Authentifizierung zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="c9cd9-120">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="c9cd9-121">**Kennwort speichern**</span><span class="sxs-lookup"><span data-stu-id="c9cd9-121">**Remember password**</span></span>  
 <span data-ttu-id="c9cd9-122">Diese Option ist nicht verfügbar, da für [!INCLUDE[ssIS](../includes/ssis-md.md)]nur die Windows-Authentifizierung zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="c9cd9-122">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="c9cd9-123">**Herstellen einer Verbindung**</span><span class="sxs-lookup"><span data-stu-id="c9cd9-123">**Connect**</span></span>  
 <span data-ttu-id="c9cd9-124">Stellt eine Verbindung zu dem oben ausgewählten Server her.</span><span class="sxs-lookup"><span data-stu-id="c9cd9-124">Connect to the server selected above.</span></span>  
  
 <span data-ttu-id="c9cd9-125">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="c9cd9-125">**Options**</span></span>  
 <span data-ttu-id="c9cd9-126">Klicken Sie hier, um die Anzeige des Dialogfelds zu ändern und die zusätzlichen Serververbindungsoptionen, z. B. Speichern des Kennworts, auszublenden.</span><span class="sxs-lookup"><span data-stu-id="c9cd9-126">Click to change the dialog and hide the additional server connection options, such as remembering the password.</span></span>  
  
  
