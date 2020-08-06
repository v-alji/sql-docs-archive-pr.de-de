---
title: Entfernen Sie Aufrufe des veralteten DBCC-Befehls "". Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 2cc9f6ff-de36-4e94-bd04-59f5c45c4911
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cde04ebfc2ea9996d1c9ed233123e5b66f6e81fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722258"
---
# <a name="remove-calls-to-the-deprecated-dbcc-concurrencyviolation-command"></a><span data-ttu-id="66039-102">Entfernen von Aufrufen des veralteten DBCC CONCURRENCYVIOLATION-Befehls</span><span class="sxs-lookup"><span data-stu-id="66039-102">Remove calls to the deprecated DBCC CONCURRENCYVIOLATION command</span></span>
  <span data-ttu-id="66039-103">Der Upgrade Advisor hat die Verwendung des Befehls DBCC CONCURRENCYVIOLATION erkannt.</span><span class="sxs-lookup"><span data-stu-id="66039-103">Upgrade Advisor detected the use of the DBCC CONCURRENCYVIOLATION command.</span></span> <span data-ttu-id="66039-104">Dieser Befehl ist nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="66039-104">This command is no longer available.</span></span> <span data-ttu-id="66039-105">Wenn Sie diesen Befehl ausführen, wird Fehler 2526 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="66039-105">Executing this command returns error 2526.</span></span>  
  
## <a name="component"></a><span data-ttu-id="66039-106">Komponente</span><span class="sxs-lookup"><span data-stu-id="66039-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="66039-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="66039-107">Description</span></span>  
 <span data-ttu-id="66039-108">Keine aktuelle Version der Edition von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] enthält eine Arbeitsauslastungskontrolle. Deshalb wurde der Befehl entfernt.</span><span class="sxs-lookup"><span data-stu-id="66039-108">No recent version of edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] includes a workload governor; therefore the command has been removed.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="66039-109">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="66039-109">Corrective Action</span></span>  
 <span data-ttu-id="66039-110">Aktualisieren Sie die Anwendungen und Skripts, um Verweise auf diesen veralteten Befehl zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="66039-110">Update applications and scripts to remove references to this deprecated command.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="66039-111">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="66039-111">External Resources</span></span>  
  
