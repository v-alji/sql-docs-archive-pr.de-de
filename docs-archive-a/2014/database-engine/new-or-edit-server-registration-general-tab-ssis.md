---
title: Neue Server Registrierung oder Server Registrierung bearbeiten (Registerkarte Allgemein) (SSIS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerserver.general.dts.f1
ms.assetid: b586b736-344b-4e42-83ee-96f66ad433a5
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 4968c3f98b8bab5b2e641e6fb1e30a6d682f9b50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621657"
---
# <a name="new-or-edit-server-registration-general-tab-ssis"></a><span data-ttu-id="fd859-102">Neue Serverregistrierung und Serverregistrierung bearbeiten (Registerkarte Allgemein) (SSIS)</span><span class="sxs-lookup"><span data-stu-id="fd859-102">New or Edit Server Registration (General Tab) (SSIS)</span></span>
  <span data-ttu-id="fd859-103">Auf dieser Registerkarte können Optionen angegeben werden, wenn [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]registriert wird.</span><span class="sxs-lookup"><span data-stu-id="fd859-103">Use this tab to specify options when registering [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="fd859-104">Um auf die Seite zuzugreifen, klicken Sie auf der Symbolleiste **Registrierte Server** auf **Integration Services** , klicken Sie mit der rechten Maustaste auf eine registrierte Servergruppe, zeigen Sie auf **Neu**, und klicken Sie anschließend auf **Serverregistrierung**.</span><span class="sxs-lookup"><span data-stu-id="fd859-104">To access this page, in Registered Servers, click **Integration Services** on the **Registered Servers** toolbar, right-click any registered servers group, point to **New**, and then click **Server Registration**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fd859-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="fd859-105">Options</span></span>  
 <span data-ttu-id="fd859-106">**Servertyp**</span><span class="sxs-lookup"><span data-stu-id="fd859-106">**Server type**</span></span>  
 <span data-ttu-id="fd859-107">Wenn Sie einen Server über „Registrierte Server“ registrieren, ist das Feld **Servertyp** schreibgeschützt, wobei der Feldeintrag mit dem im Bereich für registrierte Server angezeigten Servertyp übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="fd859-107">When a server is registered in Registered Servers, the **Server type** box is read-only, and it matches the type of server displayed in Registered Servers.</span></span> <span data-ttu-id="fd859-108">Wenn Sie einen anderen Servertyp registrieren möchten, klicken Sie, bevor Sie mit dem Registrieren eines neuen Servers beginnen, auf der Symbolleiste **Registrierte Server** auf **Datenbank-Engine**, **Analysis-Server**, **Reporting Services**, **SQL Server Compact** **Edition** oder **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="fd859-108">To register a different type of server, click **Database Engine**, **Analysis Server**, **Reporting Services**, **SQL Server Compact** **Edition**, or **Integration Services** on the **Registered Servers** toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="fd859-109">**Servername**</span><span class="sxs-lookup"><span data-stu-id="fd859-109">**Server name**</span></span>  
 <span data-ttu-id="fd859-110">Wählen Sie den Server aus, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fd859-110">Select the server to which to connect.</span></span> <span data-ttu-id="fd859-111">Standardmäßig wird der Server angezeigt, mit dem zuletzt eine Verbindung hergestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="fd859-111">The server last connected to is displayed by default.</span></span>  
  
 <span data-ttu-id="fd859-112">**Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="fd859-112">**Authentication**</span></span>  
 <span data-ttu-id="fd859-113">Mit dem Windows-Authentifizierungsmodus können Benutzer die Verbindung über ein [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows-Benutzerkonto herstellen.</span><span class="sxs-lookup"><span data-stu-id="fd859-113">Windows Authentication mode allows a user to connect through a [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows user account.</span></span>  
  
 <span data-ttu-id="fd859-114">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="fd859-114">**User name**</span></span>  
 <span data-ttu-id="fd859-115">Diese Option steht in dieser Version nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="fd859-115">This option is not available in this release.</span></span>  
  
 <span data-ttu-id="fd859-116">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="fd859-116">**Password**</span></span>  
 <span data-ttu-id="fd859-117">Diese Option steht in dieser Version nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="fd859-117">This option is not available in this release.</span></span>  
  
 <span data-ttu-id="fd859-118">**Kennwort speichern**</span><span class="sxs-lookup"><span data-stu-id="fd859-118">**Remember password**</span></span>  
 <span data-ttu-id="fd859-119">Diese Option steht in dieser Version nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="fd859-119">This option is not available in this release.</span></span>  
  
 <span data-ttu-id="fd859-120">**Name des registrierten Servers**</span><span class="sxs-lookup"><span data-stu-id="fd859-120">**Registered server name**</span></span>  
 <span data-ttu-id="fd859-121">Der Name, der unter **Registrierte Server**angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fd859-121">The name you want to appear in **Registered Servers**.</span></span> <span data-ttu-id="fd859-122">Dieser Name muss mit dem Eintrag im Feld **Servername** nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="fd859-122">This name does not have to match the **Server name** box.</span></span>  
  
 <span data-ttu-id="fd859-123">**Beschreibung des registrierten Servers**</span><span class="sxs-lookup"><span data-stu-id="fd859-123">**Registered server description**</span></span>  
 <span data-ttu-id="fd859-124">Geben Sie eine optionale Beschreibung des Servers ein.</span><span class="sxs-lookup"><span data-stu-id="fd859-124">Enter an optional description of the server.</span></span>  
  
 <span data-ttu-id="fd859-125">**Test**</span><span class="sxs-lookup"><span data-stu-id="fd859-125">**Test**</span></span>  
 <span data-ttu-id="fd859-126">Klicken Sie hier, um die Verbindung mit dem unter **Servername**ausgewählten Server zu testen.</span><span class="sxs-lookup"><span data-stu-id="fd859-126">Click to test the connection to the server selected in **Server name**.</span></span>  
  
 <span data-ttu-id="fd859-127">**Speichern**</span><span class="sxs-lookup"><span data-stu-id="fd859-127">**Save**</span></span>  
 <span data-ttu-id="fd859-128">Klicken Sie hier, um die Einstellungen für die registrierten Server zu speichern.</span><span class="sxs-lookup"><span data-stu-id="fd859-128">Click to save the Registered Servers settings.</span></span>  
  
  
