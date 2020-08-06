---
title: Reporting Services der Authentifizierung im SharePoint-Modus | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade SharePoint Mode [Reporting Services]
- SharePoint integration
- SharePoint Mode
ms.assetid: 2c19794a-dd55-4fe5-b901-6dd93e9f6beb
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3b1316a1a49726ab0754f39160125425fec116d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722253"
---
# <a name="reporting-services-sharepoint-mode-authentication"></a><span data-ttu-id="9080f-102">Authentifizierung im SharePoint-Modus von Reporting Services</span><span class="sxs-lookup"><span data-stu-id="9080f-102">Reporting Services SharePoint Mode Authentication</span></span>
  <span data-ttu-id="9080f-103">Verwenden Sie die Seite für die \*\*\*\* Authentifizierung im SharePoint-Modus von Reporting Services des Installations-Assistenten für [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , um die Anmeldeinformationen des in der aktuellen [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Installation verwendeten Dienstkontos anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9080f-103">Use the **Reporting Services SharePoint Mode Authentication** page of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard to specify the credentials of the service account that is used in the current [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation.</span></span> <span data-ttu-id="9080f-104">Die Anmeldeinformationen werden zum Erstellen eines neuen SharePoint-Anwendungspools verwendet.</span><span class="sxs-lookup"><span data-stu-id="9080f-104">The credentials will be used to create a new SharePoint application pool.</span></span> <span data-ttu-id="9080f-105">Darüber hinaus wird eine neue [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -SharePoint-Dienstanwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="9080f-105">Also, one new [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint service application will be created.</span></span> <span data-ttu-id="9080f-106">Der Name der Dienstanwendung enthält den Namen der vorherigen [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Instanz.</span><span class="sxs-lookup"><span data-stu-id="9080f-106">The service application name will contain the name of the previous [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance name.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9080f-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="9080f-107">Options</span></span>  
  
-   <span data-ttu-id="9080f-108">Die Option **Name des SSRS-Anwendungspoolkontos:** ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="9080f-108">The **SSRS Application Pool Account Name:** option is read only.</span></span> <span data-ttu-id="9080f-109">Der Wert wird automatisch durch den aktuellen Wert aus der vorhandenen [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Installation ersetzt, die Sie aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="9080f-109">The value is automatically populated with the current value from the existing [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation that you are upgrading.</span></span>  
  
-   <span data-ttu-id="9080f-110">Falls das Anwendungspoolkonto kein Kennwort erfordert, ist die Option **Kennwort des SSRS-Anwendungspoolkontos:** deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9080f-110">The **SSRS Application Pool Account Password:** option will be disabled if the application pool account does not require a password.</span></span> <span data-ttu-id="9080f-111">Beispiel: "NT-Autorität \ NetworkService".</span><span class="sxs-lookup"><span data-stu-id="9080f-111">For example, "NT Authority\NetworkService".</span></span> <span data-ttu-id="9080f-112">Falls für das Anwendungspoolkonto ein Kennwort erforderlich ist, kann das Upgrade erst nach Eingabe des richtigen Kennworts fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="9080f-112">If the application pool account does require a password, you cannot continue with upgrade until you type the correct password.</span></span>  
  
 <span data-ttu-id="9080f-113">Weitere Informationen finden Sie unter [aktualisieren und Migrieren von Reporting Services](https://go.microsoft.com/fwlink/?LinkID=245628) () https://go.microsoft.com/fwlink/?LinkID=245628) .</span><span class="sxs-lookup"><span data-stu-id="9080f-113">For more information, see [Upgrade and Migrate Reporting Services](https://go.microsoft.com/fwlink/?LinkID=245628) (https://go.microsoft.com/fwlink/?LinkID=245628).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9080f-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9080f-114">See Also</span></span>  
 [<span data-ttu-id="9080f-115">Aktualisieren und Migrieren von Reporting Services</span><span class="sxs-lookup"><span data-stu-id="9080f-115">Upgrade and Migrate Reporting Services</span></span>](https://go.microsoft.com/fwlink/?LinkID=245628)  
  
  
