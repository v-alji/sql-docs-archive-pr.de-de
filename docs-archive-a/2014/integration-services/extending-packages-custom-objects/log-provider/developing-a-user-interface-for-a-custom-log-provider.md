---
title: Entwickeln einer Benutzeroberfläche für einen benutzerdefinierten Protokollanbieter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom user interface [Integration Services], custom log providers
- custom log providers [Integration Services], developing custom user interface
ms.assetid: 6fd2d269-d87a-4134-82a1-40a09b3b5453
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c3ce6cf5ad744e307bbb049347047bf94fc5a908
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609368"
---
# <a name="developing-a-user-interface-for-a-custom-log-provider"></a><span data-ttu-id="842ec-102">Entwickeln einer Benutzeroberfläche für einen benutzerdefinierten Protokollanbieter</span><span class="sxs-lookup"><span data-stu-id="842ec-102">Developing a User Interface for a Custom Log Provider</span></span>
  <span data-ttu-id="842ec-103">Viele [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]-Protokollanbieter verfügen über eine benutzerdefinierte Benutzeroberfläche, die <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsLogProviderUI> implementiert und das Textfeld **Konfiguration** im Dialogfeld **SSIS-Protokolle konfigurieren** durch eine gefilterte Dropdownliste der verfügbaren Verbindungs-Manager ersetzt.</span><span class="sxs-lookup"><span data-stu-id="842ec-103">Many [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] log providers have a custom user interface that implements <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsLogProviderUI> and replaces the **Configuration** text box in the **Configure SSIS Logs** dialog box with a filtered dropdown list of available connection managers.</span></span> <span data-ttu-id="842ec-104">Individuelle Benutzeroberflächen für benutzerdefinierte Protokollanbieter werden in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] jedoch nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="842ec-104">However, custom user interfaces for custom log providers are not implemented in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>  
  
<span data-ttu-id="842ec-105">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="842ec-105">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="842ec-106">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="842ec-106">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="842ec-107">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="842ec-107">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="842ec-108">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="842ec-108">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="842ec-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="842ec-109">See Also</span></span>  
 <span data-ttu-id="842ec-110">[Erstellen eines benutzerdefinierten Protokollanbieters](creating-a-custom-log-provider.md) </span><span class="sxs-lookup"><span data-stu-id="842ec-110">[Creating a Custom Log Provider](creating-a-custom-log-provider.md) </span></span>  
 [<span data-ttu-id="842ec-111">Codieren eines benutzerdefinierten Protokollanbieters</span><span class="sxs-lookup"><span data-stu-id="842ec-111">Coding a Custom Log Provider</span></span>](coding-a-custom-log-provider.md)  
  
  
