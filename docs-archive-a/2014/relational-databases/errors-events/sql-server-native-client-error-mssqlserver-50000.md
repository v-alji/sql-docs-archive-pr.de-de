---
title: MSSQLSERVER_50000 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 50000 [SQL Server Native Client setup error]
ms.assetid: 5426d87a-d5d9-4984-b211-b07d69e834a2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3cc805042bff7259a311ca3f2acf4c26db59381b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701216"
---
# <a name="mssqlserver_50000"></a><span data-ttu-id="c9c28-102">MSSQLSERVER_50000</span><span class="sxs-lookup"><span data-stu-id="c9c28-102">MSSQLSERVER_50000</span></span>
    
## <a name="details"></a><span data-ttu-id="c9c28-103">Details</span><span class="sxs-lookup"><span data-stu-id="c9c28-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c9c28-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="c9c28-104">Product Name</span></span>|<span data-ttu-id="c9c28-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c9c28-105">SQL Server</span></span>|  
|<span data-ttu-id="c9c28-106">Produktversion</span><span class="sxs-lookup"><span data-stu-id="c9c28-106">Product Version</span></span>|<span data-ttu-id="c9c28-107">11.0</span><span class="sxs-lookup"><span data-stu-id="c9c28-107">11.0</span></span>|  
|<span data-ttu-id="c9c28-108">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c9c28-108">Event ID</span></span>|<span data-ttu-id="c9c28-109">50000</span><span class="sxs-lookup"><span data-stu-id="c9c28-109">50000</span></span>|  
|<span data-ttu-id="c9c28-110">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="c9c28-110">Event Source</span></span>|<span data-ttu-id="c9c28-111">SETUP</span><span class="sxs-lookup"><span data-stu-id="c9c28-111">SETUP</span></span>|  
|<span data-ttu-id="c9c28-112">Komponente</span><span class="sxs-lookup"><span data-stu-id="c9c28-112">Component</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c9c28-113">Native Client</span><span class="sxs-lookup"><span data-stu-id="c9c28-113">Native Client</span></span>|  
|<span data-ttu-id="c9c28-114">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="c9c28-114">Symbolic Name</span></span>||  
|<span data-ttu-id="c9c28-115">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="c9c28-115">Message Text</span></span>|<span data-ttu-id="c9c28-116">Netzwerkfehler beim Lesen der Datei '% \* ls'.</span><span class="sxs-lookup"><span data-stu-id="c9c28-116">A network error occurred while attempting to read from the file '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c9c28-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="c9c28-117">Explanation</span></span>  
 <span data-ttu-id="c9c28-118">Es wurde versucht, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client auf einem Computer zu installieren (oder zu aktualisieren), auf dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client bereits installiert ist und die vorhandene Installation über eine MSI-Datei ausgeführt wurde, die ursprünglich den Namen sqlncli.msi hatte und dann umbenannt wurde.</span><span class="sxs-lookup"><span data-stu-id="c9c28-118">An attempt was made to install (or update) [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client on a computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client is already installed, and where the existing installation was from an MSI file that was renamed from sqlncli.msi.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c9c28-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="c9c28-119">User Action</span></span>  
 <span data-ttu-id="c9c28-120">Um diesen Fehler zu beheben, deinstallieren Sie die vorhandene Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="c9c28-120">To resolve this error, uninstall the existing version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="c9c28-121">Um den Fehler zu verhindern, installieren Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client über eine MSI-Datei, die nicht sqlncli.msi heißt.</span><span class="sxs-lookup"><span data-stu-id="c9c28-121">To prevent this error, do not install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client from an MSI file that is not named sqlncli.msi.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="c9c28-122">Nur intern</span><span class="sxs-lookup"><span data-stu-id="c9c28-122">Internal-Only</span></span>  
  
