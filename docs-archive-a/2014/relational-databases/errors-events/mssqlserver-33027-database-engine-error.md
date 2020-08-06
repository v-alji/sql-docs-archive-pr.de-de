---
title: MSSQLSERVER_33027 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33027 (Database Engine error)
ms.assetid: bfdc626e-7958-4511-987d-3b687824e8af
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f6bb461b42b66368224fffd2c14f9b4da61abf5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617061"
---
# <a name="mssqlserver_33027"></a><span data-ttu-id="bd212-102">MSSQLSERVER_33027</span><span class="sxs-lookup"><span data-stu-id="bd212-102">MSSQLSERVER_33027</span></span>
    
## <a name="details"></a><span data-ttu-id="bd212-103">Details</span><span class="sxs-lookup"><span data-stu-id="bd212-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bd212-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="bd212-104">Product Name</span></span>|<span data-ttu-id="bd212-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bd212-105">SQL Server</span></span>|  
|<span data-ttu-id="bd212-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="bd212-106">Event ID</span></span>|<span data-ttu-id="bd212-107">33027</span><span class="sxs-lookup"><span data-stu-id="bd212-107">33027</span></span>|  
|<span data-ttu-id="bd212-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="bd212-108">Event Source</span></span>|<span data-ttu-id="bd212-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bd212-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bd212-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="bd212-110">Component</span></span>|<span data-ttu-id="bd212-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bd212-111">SQLEngine</span></span>|  
|<span data-ttu-id="bd212-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="bd212-112">Symbolic Name</span></span>|<span data-ttu-id="bd212-113">SEC_CRYPTOPROV_CANTLOADDLL</span><span class="sxs-lookup"><span data-stu-id="bd212-113">SEC_CRYPTOPROV_CANTLOADDLL</span></span>|  
|<span data-ttu-id="bd212-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="bd212-114">Message Text</span></span>|<span data-ttu-id="bd212-115">Fehler beim Laden des Kryptografieanbieters ‚%.\*ls’ aufgrund einer ungültigen Authenticode-Signatur oder eines ungültigen Dateipfades.</span><span class="sxs-lookup"><span data-stu-id="bd212-115">Failed to load cryptographic provider '%.\*ls' due to an invalid Authenticode signature or invalid file path.</span></span> <span data-ttu-id="bd212-116">Überprüfen Sie vorhergehende Meldungen auf weitere Fehler.</span><span class="sxs-lookup"><span data-stu-id="bd212-116">Check previous messages for other failures.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bd212-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="bd212-117">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bd212-118">konnte den in der Fehlermeldung aufgelisteten Kryptografieanbieter nicht verwenden, da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die DLL nicht laden konnte.</span><span class="sxs-lookup"><span data-stu-id="bd212-118">was unable to use the cryptographic provider listed in the error message, because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] could not load the DLL.</span></span> <span data-ttu-id="bd212-119">Entweder ist der Name ungültig, oder die Authenticode-Signatur ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="bd212-119">Either the name is invalid or the Authenticode signature is invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bd212-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="bd212-120">User Action</span></span>  
 <span data-ttu-id="bd212-121">Überprüfen Sie, ob die Datei vorhanden ist und [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die Berechtigung hat, auf diesen Speicherort zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="bd212-121">Check that the file is present and that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has permission to access that location.</span></span> <span data-ttu-id="bd212-122">Überprüfen Sie das Fehlerprotokoll auf zusätzliche verwandte Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="bd212-122">Check the error log for additional related messages.</span></span> <span data-ttu-id="bd212-123">Anderenfalls wenden Sie sich an den Kryptografieanbieter, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="bd212-123">Otherwise, contact the cryptographic provider for more information.</span></span>  
  
  
