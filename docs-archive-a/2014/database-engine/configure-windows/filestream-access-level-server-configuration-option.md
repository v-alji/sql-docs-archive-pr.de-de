---
title: Filestream-Zugriffsebene (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], access level
- filestream access level
ms.assetid: b88f6ff2-795e-4730-bfb8-dbc6a958f2ad
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dfa43b8e6e1762e87dd9c2abbdf7a583963e196e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622246"
---
# <a name="filestream-access-level-server-configuration-option"></a><span data-ttu-id="61dac-102">Filestream-Zugriffsebene (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="61dac-102">filestream access level Server Configuration Option</span></span>
  <span data-ttu-id="61dac-103">Verwenden Sie die Option FILESTREAM-Zugriffsebene, um die FILESTREAM-Zugriffsebene für diese Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]zu ändern.</span><span class="sxs-lookup"><span data-stu-id="61dac-103">Use the filestream_access_level option to change the FILESTREAM access level for this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61dac-104">Damit diese Option wirksam wird, müssen die Windows-Verwaltungseinstellungen für FILESTREAM aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="61dac-104">Before this option has any effect, the Windows administration settings for FILESTREAM must be enabled.</span></span> <span data-ttu-id="61dac-105">Sie können diese Einstellungen bei der Installation von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oder über den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager aktivieren.</span><span class="sxs-lookup"><span data-stu-id="61dac-105">You can enable these settings when you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
|<span data-ttu-id="61dac-106">Wert</span><span class="sxs-lookup"><span data-stu-id="61dac-106">Value</span></span>|<span data-ttu-id="61dac-107">Definition</span><span class="sxs-lookup"><span data-stu-id="61dac-107">Definition</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="61dac-108">0</span><span class="sxs-lookup"><span data-stu-id="61dac-108">0</span></span>|<span data-ttu-id="61dac-109">Deaktiviert die FILESTREAM-Unterstützung für diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="61dac-109">Disables FILESTREAM support for this instance.</span></span>|  
|<span data-ttu-id="61dac-110">1</span><span class="sxs-lookup"><span data-stu-id="61dac-110">1</span></span>|<span data-ttu-id="61dac-111">Aktiviert FILESTREAM für den [!INCLUDE[tsql](../../includes/tsql-md.md)] -Zugriff.</span><span class="sxs-lookup"><span data-stu-id="61dac-111">Enables FILESTREAM for [!INCLUDE[tsql](../../includes/tsql-md.md)] access.</span></span>|  
|<span data-ttu-id="61dac-112">2</span><span class="sxs-lookup"><span data-stu-id="61dac-112">2</span></span>|<span data-ttu-id="61dac-113">Aktiviert FILESTREAM für [!INCLUDE[tsql](../../includes/tsql-md.md)] und für den Win32-Streamingzugriff.</span><span class="sxs-lookup"><span data-stu-id="61dac-113">Enables FILESTREAM for [!INCLUDE[tsql](../../includes/tsql-md.md)] and Win32 streaming access.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61dac-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61dac-114">See Also</span></span>  
 <span data-ttu-id="61dac-115">[Konfiguration der Datenbank-Engine - Filestream](../../sql-server/install/database-engine-configuration-filestream.md) </span><span class="sxs-lookup"><span data-stu-id="61dac-115">[Database Engine Configuration - Filestream](../../sql-server/install/database-engine-configuration-filestream.md) </span></span>  
 [<span data-ttu-id="61dac-116">Aktivieren und Konfigurieren von FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="61dac-116">Enable and Configure FILESTREAM</span></span>](../../relational-databases/blob/enable-and-configure-filestream.md)  
  
  
