---
title: WMI-Verbindungs-Manager-Editor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmiconnection.f1
helpviewer_keywords:
- WMI Connection Manager Editor
ms.assetid: 0ef2c913-0779-4a07-989e-3361cd83170b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e85cdd2157c8ebe4cb9e6b53f8c3b47ff102a7b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621553"
---
# <a name="wmi-connection-manager-editor"></a><span data-ttu-id="d1be8-102">WMI-Verbindungs-Manager-Editor</span><span class="sxs-lookup"><span data-stu-id="d1be8-102">WMI Connection Manager Editor</span></span>
  <span data-ttu-id="d1be8-103">Mithilfe des Dialogfelds **WMI-Verbindungs-Manager** geben Sie eine WMI-Verbindung (Microsoft Windows Management Instrumentation) mit einem Server an.</span><span class="sxs-lookup"><span data-stu-id="d1be8-103">Use the **WMI Connection Manager** dialog box to specify a Microsoft Windows Management Instrumentation (WMI) connection to a server.</span></span>  
  
 <span data-ttu-id="d1be8-104">Weitere Informationen zum WMI-Verbindungs-Manager finden Sie unter [WMI Connection Manager](connection-manager/wmi-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="d1be8-104">To learn more about the WMI connection manager, see [WMI Connection Manager](connection-manager/wmi-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d1be8-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="d1be8-105">Options</span></span>  
 <span data-ttu-id="d1be8-106">**Name**</span><span class="sxs-lookup"><span data-stu-id="d1be8-106">**Name**</span></span>  
 <span data-ttu-id="d1be8-107">Geben Sie einen eindeutigen Namen für den Verbindungs-Manager an.</span><span class="sxs-lookup"><span data-stu-id="d1be8-107">Provide a unique name for the connection manager.</span></span>  
  
 <span data-ttu-id="d1be8-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d1be8-108">**Description**</span></span>  
 <span data-ttu-id="d1be8-109">Beschreiben Sie den Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="d1be8-109">Describe the connection manager.</span></span> <span data-ttu-id="d1be8-110">Die bewährte Methode ist hierbei, den Verbindungs-Manager zweckbezogen zu beschreiben, sodass Pakete selbsterklärend und leichter zu verwalten sind.</span><span class="sxs-lookup"><span data-stu-id="d1be8-110">As a best practice, describe the connection manager in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="d1be8-111">**Servername**</span><span class="sxs-lookup"><span data-stu-id="d1be8-111">**Server name**</span></span>  
 <span data-ttu-id="d1be8-112">Geben Sie den Namen des Servers an, zu dem die WMI-Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d1be8-112">Provide the name of the server to which you want to make the WMI connection.</span></span>  
  
 <span data-ttu-id="d1be8-113">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="d1be8-113">**Namespace**</span></span>  
 <span data-ttu-id="d1be8-114">Geben Sie den WMI-Namespace an.</span><span class="sxs-lookup"><span data-stu-id="d1be8-114">Specify the WMI namespace.</span></span>  
  
 <span data-ttu-id="d1be8-115">**Windows-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="d1be8-115">**Use Windows authentication**</span></span>  
 <span data-ttu-id="d1be8-116">Wählen Sie diese Option aus, wenn Windows-Authentifizierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d1be8-116">Select to use Windows Authentication.</span></span> <span data-ttu-id="d1be8-117">Wenn Sie Windows-Authentifizierung verwenden, müssen Sie keinen Benutzernamen und kein Kennwort für die Verbindung angeben.</span><span class="sxs-lookup"><span data-stu-id="d1be8-117">If you use Windows Authentication, you do not need to provide a user name or password for the connection.</span></span>  
  
 <span data-ttu-id="d1be8-118">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="d1be8-118">**User name**</span></span>  
 <span data-ttu-id="d1be8-119">Wenn Sie Windows-Authentifizierung nicht verwenden, müssen Sie für die Verbindung einen Benutzernamen angeben.</span><span class="sxs-lookup"><span data-stu-id="d1be8-119">If you do not use Windows Authentication, you must provide a user name for the connection.</span></span>  
  
 <span data-ttu-id="d1be8-120">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="d1be8-120">**Password**</span></span>  
 <span data-ttu-id="d1be8-121">Wenn Sie Windows-Authentifizierung nicht verwenden, müssen Sie für die Verbindung das Kennwort angeben.</span><span class="sxs-lookup"><span data-stu-id="d1be8-121">If you do not use Windows Authentication, you must provide the password for the connection.</span></span>  
  
 <span data-ttu-id="d1be8-122">**Test**</span><span class="sxs-lookup"><span data-stu-id="d1be8-122">**Test**</span></span>  
 <span data-ttu-id="d1be8-123">Testen Sie die Verbindungs-Manager-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="d1be8-123">Test the connection manager settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1be8-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d1be8-124">See Also</span></span>  
 <span data-ttu-id="d1be8-125">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d1be8-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="d1be8-126">[Konzepte des WMI-Anbieters für die Konfigurations Verwaltung](../relational-databases/wmi-provider-configuration/wmi-provider-for-configuration-management.md) </span><span class="sxs-lookup"><span data-stu-id="d1be8-126">[WMI Provider for Configuration Management Concepts](../relational-databases/wmi-provider-configuration/wmi-provider-for-configuration-management.md) </span></span>  
 [<span data-ttu-id="d1be8-127">Konzepte des WMI-Anbieters für Serverereignisse</span><span class="sxs-lookup"><span data-stu-id="d1be8-127">WMI Provider for Server Events Concepts</span></span>](../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md)  
  
  
