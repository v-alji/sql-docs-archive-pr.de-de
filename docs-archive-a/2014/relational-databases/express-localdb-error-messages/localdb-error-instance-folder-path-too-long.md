---
title: LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: c178a308-8d99-47fc-8a49-5a480dc592f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 32ae8ebe102008d08a6059328ed57cd118ece019
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622130"
---
# <a name="localdb_error_instance_folder_path_too_long"></a><span data-ttu-id="66343-102">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="66343-102">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>
    
## <a name="details"></a><span data-ttu-id="66343-103">Details</span><span class="sxs-lookup"><span data-stu-id="66343-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="66343-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="66343-104">Product Name</span></span>|<span data-ttu-id="66343-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="66343-105">SQL Server</span></span>|  
|<span data-ttu-id="66343-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="66343-106">Event ID</span></span>|<span data-ttu-id="66343-107">260</span><span class="sxs-lookup"><span data-stu-id="66343-107">260</span></span>|  
|<span data-ttu-id="66343-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="66343-108">Event Source</span></span>|<span data-ttu-id="66343-109">Lokale SQL Server-Datenbanklaufzeit 12.0</span><span class="sxs-lookup"><span data-stu-id="66343-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="66343-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="66343-110">Component</span></span>|<span data-ttu-id="66343-111">Laufzeit-API der lokalen Datenbank</span><span class="sxs-lookup"><span data-stu-id="66343-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="66343-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="66343-112">Message Text</span></span>|<span data-ttu-id="66343-113">Die vollständige Pfadlänge des Ordners der lokalen Datenbankinstanz ist länger als MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="66343-113">The full path length of the Local Database instance folder is longer than MAX_PATH.</span></span> <span data-ttu-id="66343-114">Die Instanz muss im folgenden Ordner gespeichert werden:%% localappdata%% \ Microsoft\Microsoft SQL Server Local db\instance \\<Instanzname \> .</span><span class="sxs-lookup"><span data-stu-id="66343-114">The instance must be stored in folder: %%LOCALAPPDATA%%\Microsoft\Microsoft SQL Server Local DB\Instances\\<instance name\>.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="66343-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="66343-115">Explanation</span></span>  
 <span data-ttu-id="66343-116">Der Pfad, unter dem die Instanz gespeichert werden soll, ist länger als MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="66343-116">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="66343-117">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="66343-117">User Action</span></span>  
 <span data-ttu-id="66343-118">Erstellen Sie einen neuen Pfad, der kürzer als MAX_PATH ist.</span><span class="sxs-lookup"><span data-stu-id="66343-118">Create a new path that is shorter than MAX_PATH.</span></span>  
  
  
