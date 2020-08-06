---
title: MSSQLSERVER_102 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 102 (Database Engine error)
ms.assetid: 264dc1a2-c8a0-4c89-b5f6-951baf950299
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 18c330b8d6a534ca11e2ad2c03f89793f8c832e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608745"
---
# <a name="mssqlserver_102"></a><span data-ttu-id="0728f-102">MSSQLSERVER_102</span><span class="sxs-lookup"><span data-stu-id="0728f-102">MSSQLSERVER_102</span></span>
    
## <a name="details"></a><span data-ttu-id="0728f-103">Details</span><span class="sxs-lookup"><span data-stu-id="0728f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0728f-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="0728f-104">Product Name</span></span>|<span data-ttu-id="0728f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0728f-105">SQL Server</span></span>|  
|<span data-ttu-id="0728f-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="0728f-106">Event ID</span></span>|<span data-ttu-id="0728f-107">102</span><span class="sxs-lookup"><span data-stu-id="0728f-107">102</span></span>|  
|<span data-ttu-id="0728f-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="0728f-108">Event Source</span></span>|<span data-ttu-id="0728f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0728f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0728f-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="0728f-110">Component</span></span>|<span data-ttu-id="0728f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0728f-111">SQLEngine</span></span>|  
|<span data-ttu-id="0728f-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="0728f-112">Symbolic Name</span></span>|<span data-ttu-id="0728f-113">P_SYNTAXERR2</span><span class="sxs-lookup"><span data-stu-id="0728f-113">P_SYNTAXERR2</span></span>|  
|<span data-ttu-id="0728f-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="0728f-114">Message Text</span></span>|<span data-ttu-id="0728f-115">Falsche Syntax in der Nähe von '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="0728f-115">Incorrect syntax near '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0728f-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="0728f-116">Explanation</span></span>  
 <span data-ttu-id="0728f-117">Gibt einen Syntaxfehler an.</span><span class="sxs-lookup"><span data-stu-id="0728f-117">Indicates a syntax error.</span></span> <span data-ttu-id="0728f-118">Weitere Informationen sind nicht verfügbar, da der Fehler verhindert, dass das [!INCLUDE[ssDE](../../includes/ssde-md.md)] die Anweisung verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="0728f-118">Additional information is not available because the error prevents the [!INCLUDE[ssDE](../../includes/ssde-md.md)] from processing the statement.</span></span>  
  
 <span data-ttu-id="0728f-119">Eine mögliche Ursache ist, dass versucht wurde, mit der veralteten RC4- oder RC4_128-Verschlüsselung einen symmetrischen Schlüssel zu erstellen und der Kompatibilitätsmodus nicht auf 90 oder 100 festgelegt war.</span><span class="sxs-lookup"><span data-stu-id="0728f-119">Can be caused by attempting to create a symmetric key using the deprecated RC4 or RC4_128 encryption, when not in 90 or 100 compatibility mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0728f-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="0728f-120">User Action</span></span>  
 <span data-ttu-id="0728f-121">Suchen Sie in der [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung nach Syntaxfehlern.</span><span class="sxs-lookup"><span data-stu-id="0728f-121">Search the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement for syntax errors.</span></span>  
  
 <span data-ttu-id="0728f-122">Wenn Sie mit RC4 oder RC4_128 einen symmetrischen Schlüssel erstellen, wählen Sie eine neuere Verschlüsselung aus, z. B. einen der AES-Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="0728f-122">If creating a symmetric key using the RC4 or RC4_128, select a newer encryption such as one of the AES algorithms.</span></span> <span data-ttu-id="0728f-123">(Empfohlen.) Wenn RC4 erforderlich ist, verwenden Sie die Anweisung ALTER DATABASE SET COMPATIBILITY_LEVEL, um den Kompatibilitätsgrad der Datenbank auf 90 oder 100 festzulegen.</span><span class="sxs-lookup"><span data-stu-id="0728f-123">(Recommended.) If you must use RC4, use ALTER DATABASE SET COMPATIBILITY_LEVEL to set the database to compatibility level 90 or 100.</span></span> <span data-ttu-id="0728f-124">(Nicht empfohlen.)</span><span class="sxs-lookup"><span data-stu-id="0728f-124">(Not recommended.)</span></span>  
  
  
