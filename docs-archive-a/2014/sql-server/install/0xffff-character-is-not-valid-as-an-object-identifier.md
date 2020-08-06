---
title: Das 0xFFFF-Zeichen ist nicht als Objekt Bezeichner gültig. Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- 0xFFFF character [SQL Server]
ms.assetid: b2c9c8cf-9194-45e0-be6b-2d5ec52e8153
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 4594c1cca0fc183100d927842cc2b533694bf90e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617549"
---
# <a name="0xffff-character-is-not-valid-as-an-object-identifier"></a><span data-ttu-id="5cd05-102">0xFFFF-Zeichen ist als Objektbezeichner nicht gültig</span><span class="sxs-lookup"><span data-stu-id="5cd05-102">0xFFFF character is not valid as an object identifier</span></span>
  <span data-ttu-id="5cd05-103">Der Upgrade Advisor hat das 0xFFFF-Zeichen in einem Objektbezeichner erkannt.</span><span class="sxs-lookup"><span data-stu-id="5cd05-103">Upgrade Advisor has detected the 0xFFFF character in an object identifier.</span></span> <span data-ttu-id="5cd05-104">Wenn der Datenbank-Kompatibilitätsmodus auf 90 oder höher festgelegt ist, kann in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] und höher nicht auf Objekte wie Datenbanken, Tabellen und Spalten verwiesen werden, die dieses Zeichen in ihrem Bezeichner enthalten. Die Objekte können zudem nicht umbenannt werden.</span><span class="sxs-lookup"><span data-stu-id="5cd05-104">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later, objects such as databases, tables, and columns that contain this character in their identifiers cannot be referenced or renamed when the database compatibility mode is set to 90 or later.</span></span> <span data-ttu-id="5cd05-105">Wenn Sie auf [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] aktualisieren, behalten die Benutzerdatenbanken ihren Kompatibilitätsmodus bei.</span><span class="sxs-lookup"><span data-stu-id="5cd05-105">When you upgrade to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], user databases maintain their compatibility mode.</span></span> <span data-ttu-id="5cd05-106">Bevor Sie den Datenbank-Kompatibilitätsmodus in 90 oder höher ändern, benennen Sie das Objekt um, das das Zeichen 0xFFFF enthält.</span><span class="sxs-lookup"><span data-stu-id="5cd05-106">Before you change the database compatibility mode to 90 or later, rename the object that contains the 0xFFFF character.</span></span>  
  
 <span data-ttu-id="5cd05-107">Weitere Informationen über Bezeichner finden Sie unter "Bezeichner" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="5cd05-107">For more information about identifiers, see "Identifiers" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="5cd05-108">Weitere Informationen über Datenbankkompatibilitätsmodi finden Sie unter "sp_dbcmptlevel" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="5cd05-108">For more information about database compatibility modes, see "sp_dbcmptlevel" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="component"></a><span data-ttu-id="5cd05-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="5cd05-109">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5cd05-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5cd05-110">See Also</span></span>  
 <span data-ttu-id="5cd05-111">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="5cd05-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="5cd05-112">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="5cd05-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
