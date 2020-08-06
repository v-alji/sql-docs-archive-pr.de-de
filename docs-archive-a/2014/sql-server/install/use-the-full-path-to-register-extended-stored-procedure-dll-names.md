---
title: Vollständigen Pfad zum Registrieren von DLL-Namen für erweiterte gespeicherte Prozeduren verwenden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- registering DLL names
- extended stored procedures [SQL Server], registering
- DLL names [SQL Server]
- full path DLL name registration [SQL Server]
ms.assetid: f648d57c-af32-4c71-9882-47b6766f3c2b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5ec4ef3fc2e0f2c4834ffa7479a00562ae15d07f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700581"
---
# <a name="use-the-full-path-to-register-extended-stored-procedure-dll-names"></a><span data-ttu-id="f42ff-102">Verwenden Sie beim Registrieren von DLL-Namen für erweiterte gespeicherte Prozeduren den vollständigen Pfad</span><span class="sxs-lookup"><span data-stu-id="f42ff-102">Use the full path to register extended stored procedure DLL names</span></span>
  <span data-ttu-id="f42ff-103">Erweiterte gespeicherte Prozeduren, die zuvor ohne den vollständigen Pfad für den DLL-Namen registriert wurden, sind in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] möglicherweise nicht funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="f42ff-103">Extended stored procedures that were previously registered without the full path for the DLL name may not work in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="component"></a><span data-ttu-id="f42ff-104">Komponente</span><span class="sxs-lookup"><span data-stu-id="f42ff-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="f42ff-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f42ff-105">Description</span></span>  
 <span data-ttu-id="f42ff-106">Erweiterte gespeicherte Prozeduren, die vorher ohne den vollständigen Pfad für den DLL-Namen registriert wurden, sind möglicherweise nach einem Upgrade nicht funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="f42ff-106">Extended stored procedures that were previously registered without the full path for the DLL name may not work after you upgrade.</span></span> <span data-ttu-id="f42ff-107">Dies liegt daran, dass dem neuen Pfad während des Upgradevorgangs nicht das alte BINN-Verzeichnis hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="f42ff-107">This is because the old BINN directory is not added to the new path during the upgrade process.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f42ff-108">kann die erweiterten gespeicherten Prozeduren möglicherweise nicht lokalisieren.</span><span class="sxs-lookup"><span data-stu-id="f42ff-108">may not be able to locate the extended stored procedures.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="f42ff-109">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="f42ff-109">Corrective Action</span></span>  
 <span data-ttu-id="f42ff-110">Führen Sie vor dem Upgrade die folgenden Schritte für jede erweiterte gespeicherte Prozedur aus, die nicht mit einem vollständigen Pfadnamen registriert wurde:</span><span class="sxs-lookup"><span data-stu-id="f42ff-110">Before you upgrade, follow these steps for each extended stored procedure that was not registered with a full path name:</span></span>  
  
1.  <span data-ttu-id="f42ff-111">Führen Sie zum Entfernen der erweiterten gespeicherten Prozedur sp_dropextendedproc aus.</span><span class="sxs-lookup"><span data-stu-id="f42ff-111">Run sp_dropextendedproc to remove the extended stored procedure.</span></span>  
  
2.  <span data-ttu-id="f42ff-112">Führen Sie zum Registrieren der erweiterten gespeicherten Prozedur mit dem vollständigen Pfadnamen sp_addextendedproc aus.</span><span class="sxs-lookup"><span data-stu-id="f42ff-112">Run sp_addextendedproc to register the extended stored procedure with the full path name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f42ff-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f42ff-113">See Also</span></span>  
 <span data-ttu-id="f42ff-114">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="f42ff-114">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="f42ff-115">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="f42ff-115">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
