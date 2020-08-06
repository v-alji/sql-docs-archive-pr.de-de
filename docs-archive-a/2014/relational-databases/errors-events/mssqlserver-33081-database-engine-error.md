---
title: MSSQLSERVER_33081 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33081 (Database Engine error)
ms.assetid: 839705e7-fa37-4c0d-9f3f-95a9eab98bcf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0752220cc20641d9b51a3a66fecc86f9efd63433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617059"
---
# <a name="mssqlserver_33081"></a><span data-ttu-id="f0848-102">MSSQLSERVER_33081</span><span class="sxs-lookup"><span data-stu-id="f0848-102">MSSQLSERVER_33081</span></span>
    
## <a name="details"></a><span data-ttu-id="f0848-103">Details</span><span class="sxs-lookup"><span data-stu-id="f0848-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0848-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="f0848-104">Product Name</span></span>|<span data-ttu-id="f0848-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f0848-105">SQL Server</span></span>|  
|<span data-ttu-id="f0848-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="f0848-106">Event ID</span></span>|<span data-ttu-id="f0848-107">33081</span><span class="sxs-lookup"><span data-stu-id="f0848-107">33081</span></span>|  
|<span data-ttu-id="f0848-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="f0848-108">Event Source</span></span>|<span data-ttu-id="f0848-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f0848-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f0848-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="f0848-110">Component</span></span>|<span data-ttu-id="f0848-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f0848-111">SQLEngine</span></span>|  
|<span data-ttu-id="f0848-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="f0848-112">Symbolic Name</span></span>|<span data-ttu-id="f0848-113">SEC_DLL_TRUST_VERIFICATION_FAILED</span><span class="sxs-lookup"><span data-stu-id="f0848-113">SEC_DLL_TRUST_VERIFICATION_FAILED</span></span>|  
|<span data-ttu-id="f0848-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="f0848-114">Message Text</span></span>|<span data-ttu-id="f0848-115">Fehler beim Laden des Kryptografieanbieters ‚%.\*ls’ aufgrund einer ungültigen Authenticode-Signatur oder eines ungültigen Dateipfades.</span><span class="sxs-lookup"><span data-stu-id="f0848-115">Failed to load cryptographic provider '%.\*ls' due to an invalid Authenticode signature or invalid file path.</span></span>  <span data-ttu-id="f0848-116">Überprüfen Sie vorhergehende Meldungen auf weitere Fehler.</span><span class="sxs-lookup"><span data-stu-id="f0848-116">Check previous messages for other failures.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f0848-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="f0848-117">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f0848-118">konnte den in der Fehlermeldung aufgeführten Kryptografieanbieter nicht laden.</span><span class="sxs-lookup"><span data-stu-id="f0848-118">was unable to load the cryptographic provider listed in the error message.</span></span> <span data-ttu-id="f0848-119">Es sind mehrere Win API-Fehler aufgetreten, die diesen Fehler möglicherweise verursachen.</span><span class="sxs-lookup"><span data-stu-id="f0848-119">There are several Win API failures which might cause this error.</span></span> <span data-ttu-id="f0848-120">Der Ringpuffer enthält den Namen der fehlerhaften API und den von der API zurückgegebenen Windows-Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="f0848-120">The ring buffer contains the name of the failed API and the Windows error code returned by the API.</span></span> <span data-ttu-id="f0848-121">Weitere Informationen erhalten Sie, indem Sie die folgende Abfrage der sys.dm_os_ring_buffers-Sicht ausgeben.</span><span class="sxs-lookup"><span data-stu-id="f0848-121">To get more information, query the sys.dm_os_ring_buffers view using the following query.</span></span>  
  
```  
SELECT * FROM sys.dm_os_ring_buffers   
WHERE ring_buffer_type = 'RING_BUFFER_SECURITY_ERROR';  
```  
  
## <a name="user-action"></a><span data-ttu-id="f0848-122">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="f0848-122">User Action</span></span>  
 <span data-ttu-id="f0848-123">Suchen Sie den Windows-Fehlercode in MSDN (https://msdn.microsoft.com/) ), um das Problem zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="f0848-123">To investigate the problem, search for the Windows error code in MSDN (https://msdn.microsoft.com/).</span></span> <span data-ttu-id="f0848-124">Beheben Sie den Fehler, oder wenden Sie sich an [!INCLUDE[msCoName](../../includes/msconame-md.md)]-CSS für weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="f0848-124">Resolve the error, or contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] CSS for more information.</span></span> <span data-ttu-id="f0848-125">Wenn Sie CSS in Anspruch nehmen möchten, halten Sie bitte die folgenden Informationen für unsere Supportmitarbeiter bereit.</span><span class="sxs-lookup"><span data-stu-id="f0848-125">If you need to contact CSS, collect the following information for our support staff.</span></span>  
  
-   <span data-ttu-id="f0848-126">Das Fehlerprotokoll, das die Meldung über den Fehler beim Laden des Kryptografieanbieters beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="f0848-126">The error log showing the failed to load cryptographic provider error.</span></span>  
  
-   <span data-ttu-id="f0848-127">Die Ausgabe der folgenden Anweisung:</span><span class="sxs-lookup"><span data-stu-id="f0848-127">The output from the following statement:</span></span>  
  
    ```  
    SELECT * FROM sys.dm_os_ring_buffers   
    WHERE ring_buffer_type = 'RING_BUFFER_SECURITY_ERROR';  
    ```  
  
> [!NOTE]  
>  <span data-ttu-id="f0848-128">Versuchen Sie, die Ringpufferinformationen möglichst umgehend zu erfassen, da Ringpufferinformationen während eines Neustarts verloren gehen können.</span><span class="sxs-lookup"><span data-stu-id="f0848-128">Try to collect the ring buffer information promptly as ring buffer information can be lost during a restart.</span></span>  
  
  
