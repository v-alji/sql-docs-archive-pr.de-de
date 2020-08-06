---
title: Verbinden mit SQL Server Analysis Services (Seite Anmeldung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttoas.login.f1
ms.assetid: fb012bc8-5105-438a-afcc-74264ebae035
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0cdbb890693c6f00d8515194804b96b6483cb956
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724141"
---
# <a name="connect-to-server-login-page-analysis-services"></a><span data-ttu-id="38653-102">Verbinden mit SQL Server Analysis Services (Seite Anmeldung)</span><span class="sxs-lookup"><span data-stu-id="38653-102">Connect to Server (Login Page) Analysis Services</span></span>
  <span data-ttu-id="38653-103">Mit dieser Registerkarte können Sie die folgenden Optionen anzeigen oder angeben, wenn Sie eine Verbindung mit herstellen [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38653-103">Use this tab to view or specify the following options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="38653-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="38653-104">Options</span></span>  
 <span data-ttu-id="38653-105">**Servertyp**</span><span class="sxs-lookup"><span data-stu-id="38653-105">**Server type**</span></span>  
 <span data-ttu-id="38653-106">Wenn Sie einen Server über den Objekt-Explorer registrieren, wählen Sie den Typ des Servers aus, mit dem eine Verbindung hergestellt wird: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services oder Integration Services.</span><span class="sxs-lookup"><span data-stu-id="38653-106">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services.</span></span> <span data-ttu-id="38653-107">Im verbleibenden Bereich des Dialogfelds werden nur die Optionen angezeigt, die auf den ausgewählten Servertyp zutreffen.</span><span class="sxs-lookup"><span data-stu-id="38653-107">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="38653-108">Wenn Sie einen Server über „Registrierte Server“ registrieren, ist das Feld **Servertyp** schreibgeschützt, wobei der Feldeintrag mit dem in der Komponente „Registrierte Server“ angezeigten Servertyp übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="38653-108">When registering a server from Registered Servers, the **Server type** box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="38653-109">Zum Registrieren eines anderen Servertyps wählen Sie auf der Symbolleiste "Registrierte Server" die Option [!INCLUDE[ssDE](../includes/ssde-md.md)], "Analysis Services", "Reporting Services" oder "Integration Services" aus. Anschließend können Sie mit der Registrierung eines neuen Servers beginnen.</span><span class="sxs-lookup"><span data-stu-id="38653-109">To register a different type of server, select [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="38653-110">**Servername**</span><span class="sxs-lookup"><span data-stu-id="38653-110">**Server name**</span></span>  
 <span data-ttu-id="38653-111">Wählen Sie die Serverinstanz aus, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="38653-111">Select the server instance to connect to.</span></span> <span data-ttu-id="38653-112">Standardmäßig wird die Serverinstanz angezeigt, mit der zuletzt eine Verbindung bestanden hat.</span><span class="sxs-lookup"><span data-stu-id="38653-112">The server instance last connected to is displayed by default.</span></span>  
  
 <span data-ttu-id="38653-113">**Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="38653-113">**Authentication**</span></span>  
 <span data-ttu-id="38653-114">Beim Herstellen einer Verbindung mit einer Instanz von Analysis Services werden die folgenden Authentifizierungsmodi unterstützt: [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="38653-114">The following authentication modes are supported when connecting to an instance of Analysis Services: [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="38653-115">**Windows-Authentifizierungsmodus (Windows-Authentifizierung)**</span><span class="sxs-lookup"><span data-stu-id="38653-115">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 <span data-ttu-id="38653-116">Der Windows Authentifizierungsmodus ermöglicht Benutzern die Verbindung über ein Windows-Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="38653-116">Windows Authentication mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="38653-117">**Herstellen einer Verbindung**</span><span class="sxs-lookup"><span data-stu-id="38653-117">**Connect**</span></span>  
 <span data-ttu-id="38653-118">Stellt eine Verbindung zu dem oben ausgewählten Server her.</span><span class="sxs-lookup"><span data-stu-id="38653-118">Connect to the server selected above.</span></span>  
  
 <span data-ttu-id="38653-119">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="38653-119">**Options**</span></span>  
 <span data-ttu-id="38653-120">Klicken Sie hier, um die Anzeige des Dialogfelds zu ändern und die zusätzlichen Serververbindungsoptionen, z. B. Speichern des Kennworts, auszublenden.</span><span class="sxs-lookup"><span data-stu-id="38653-120">Click to change the dialog and hide the additional server connection options, such as remembering the password.</span></span>  
  
  
