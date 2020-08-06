---
title: Dateien und Versionsnummern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, versions
- components [SMO]
- files [SMO], components
- SMO [SQL Server], versions
- versions [SMO]
ms.assetid: 510907b6-e7a9-41bd-b892-d6d99a5118e1
author: stevestein
ms.author: sstein
ms.openlocfilehash: f1a7286f15af28f97e488b8b40fd745a0d320108
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617910"
---
# <a name="files-and-version-numbers"></a><span data-ttu-id="eca6c-102">Dateien und Versionsnummern</span><span class="sxs-lookup"><span data-stu-id="eca6c-102">Files and Version Numbers</span></span>
  <span data-ttu-id="eca6c-103">Alle erforderlichen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects-Komponenten (SMO) werden als Teil einer Instanz des- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Clients oder-Servers installiert.</span><span class="sxs-lookup"><span data-stu-id="eca6c-103">All required [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO) components are installed as part of an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client or server.</span></span> <span data-ttu-id="eca6c-104">SMO ist in mehreren verwalteten Assemblys implementiert.</span><span class="sxs-lookup"><span data-stu-id="eca6c-104">SMO is implemented in several managed assemblies.</span></span> <span data-ttu-id="eca6c-105">Sie können SMO-Anwendungen entweder auf einem Client oder auf einem Server entwickeln.</span><span class="sxs-lookup"><span data-stu-id="eca6c-105">You can develop SMO applications on either a client or a server.</span></span>  
  
|<span data-ttu-id="eca6c-106">Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="eca6c-106">Directory</span></span>|<span data-ttu-id="eca6c-107">Datei</span><span class="sxs-lookup"><span data-stu-id="eca6c-107">File</span></span>|<span data-ttu-id="eca6c-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="eca6c-108">Description</span></span>|  
|---------------|----------|-----------------|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="eca6c-109">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="eca6c-109">Microsoft.SqlServer.ConnectionInfo.dll</span></span>|<span data-ttu-id="eca6c-110">Unterstützt das Herstellen von Verbindungen mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eca6c-110">Contains support for connecting to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="eca6c-111">Microsoft.SqlServer.ServiceBrokerEnum.dll</span><span class="sxs-lookup"><span data-stu-id="eca6c-111">Microsoft.SqlServer.ServiceBrokerEnum.dll</span></span>|<span data-ttu-id="eca6c-112">Unterstützt die Programmierung des [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service Broker.</span><span class="sxs-lookup"><span data-stu-id="eca6c-112">Contains support for programming the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service Broker.</span></span> <span data-ttu-id="eca6c-113">Dies ist nur in Programmen erforderlich, die auf Service Broker zugreifen.</span><span class="sxs-lookup"><span data-stu-id="eca6c-113">This is required only in programs that access the Service Broker.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="eca6c-114">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="eca6c-114">Microsoft.SqlServer.Smo.dll</span></span>|<span data-ttu-id="eca6c-115">Enthält einen Großteil der SMO-Klassen.</span><span class="sxs-lookup"><span data-stu-id="eca6c-115">Contains the most of the SMO classes.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="eca6c-116">Microsoft.SqlServer.SmoExtended.dll</span><span class="sxs-lookup"><span data-stu-id="eca6c-116">Microsoft.SqlServer.SmoExtended.dll</span></span><br /><br /> <span data-ttu-id="eca6c-117">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span><span class="sxs-lookup"><span data-stu-id="eca6c-117">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span></span><br /><br /> <span data-ttu-id="eca6c-118">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="eca6c-118">Microsoft.SqlServer.SqlEnum.dll</span></span>|<span data-ttu-id="eca6c-119">Unterstützt die SMO-Klassen.</span><span class="sxs-lookup"><span data-stu-id="eca6c-119">Contains support for the SMO classes.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="eca6c-120">Microsoft.SqlServer.WmiEnum.dll</span><span class="sxs-lookup"><span data-stu-id="eca6c-120">Microsoft.SqlServer.WmiEnum.dll</span></span>|<span data-ttu-id="eca6c-121">Enthält die WMI-Anbieterklassen (Windows Management Instrumentation, Windows-Verwaltungsinstrumentation).</span><span class="sxs-lookup"><span data-stu-id="eca6c-121">Contains the Windows Management Instrumentation (WMI) Provider classes.</span></span> <span data-ttu-id="eca6c-122">Dies ist nur für Programme erforderlich, die die WMI-Anbieterklassen verwenden.</span><span class="sxs-lookup"><span data-stu-id="eca6c-122">This is required only for programs that use the WMI Provider classes.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="eca6c-123">Microsoft.SqlServer.RegSvrEnum.dll</span><span class="sxs-lookup"><span data-stu-id="eca6c-123">Microsoft.SqlServer.RegSvrEnum.dll</span></span>|<span data-ttu-id="eca6c-124">Enthält die Klassen, die den registrierten Server darstellen.</span><span class="sxs-lookup"><span data-stu-id="eca6c-124">Contains the Registered Server classes.</span></span> <span data-ttu-id="eca6c-125">Dies ist nur für Programme erforderlich, die die Klassen für den registrierten Server enthalten.</span><span class="sxs-lookup"><span data-stu-id="eca6c-125">This is required only for programs that use the Registered Server classes.</span></span>|  
  
  
