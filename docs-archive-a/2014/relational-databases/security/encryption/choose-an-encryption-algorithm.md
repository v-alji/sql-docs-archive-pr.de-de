---
title: Auswählen eines Verschlüsselungsalgorithmus | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- cryptography [SQL Server], algorithms
- encryption [SQL Server], algorithms
- security [SQL Server], encryption
- algorithms [SQL Server encryption]
ms.assetid: 8227028c-a9c9-489d-bd27-fbf8242634ae
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 3b2c5292b4a00a3ad81e53fdbc603bb584130613
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725402"
---
# <a name="choose-an-encryption-algorithm"></a><span data-ttu-id="0c92d-102">Auswählen eines Verschlüsselungsalgorithmus</span><span class="sxs-lookup"><span data-stu-id="0c92d-102">Choose an Encryption Algorithm</span></span>
  <span data-ttu-id="0c92d-103">Die Verschlüsselung ist eine von mehreren Maßnahmen zum sicheren Schutz, die dem Administrator zur Verfügung stehen, der eine Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]sichern möchte.</span><span class="sxs-lookup"><span data-stu-id="0c92d-103">Encryption is one of several defenses-in-depth that are available to the administrator who wants to secure an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0c92d-104">Mit Verschlüsselungsalgorithmen werden Datentransformationen definiert, die von unbefugten Benutzern nicht leicht umgekehrt werden können.</span><span class="sxs-lookup"><span data-stu-id="0c92d-104">Encryption algorithms define data transformations that cannot be easily reversed by unauthorized users.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="0c92d-105">ermöglicht Administratoren und Entwicklern die Auswahl aus mehreren Algorithmen, einschließlich DES, Triple DES, TRIPLE_DES_3KEY, RC2, RC4, 128-Bit-RC4, DESX, 128-Bit-AES, 192-Bit-AES und 256-Bit-AES.</span><span class="sxs-lookup"><span data-stu-id="0c92d-105">allows administrators and developers to choose from among several algorithms, including DES, Triple DES, TRIPLE_DES_3KEY, RC2, RC4, 128-bit RC4, DESX, 128-bit AES, 192-bit AES, and 256-bit AES.</span></span>  
  
 <span data-ttu-id="0c92d-106">Keiner der Algorithmen ist für alle Situationen ideal, und Richtlinien zu den Vorteilen der einzelnen Algorithmen würden den Rahmen der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Onlinedokumentation sprengen.</span><span class="sxs-lookup"><span data-stu-id="0c92d-106">No single algorithm is ideal for all situations, and guidance on the merits of each is beyond the scope of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="0c92d-107">Es gelten jedoch die folgenden allgemeinen Prinzipien:</span><span class="sxs-lookup"><span data-stu-id="0c92d-107">However, the following general principles apply:</span></span>  
  
-   <span data-ttu-id="0c92d-108">Eine starke Verschlüsselung verbraucht im Allgemeinen mehr CPU-Ressourcen als eine schwache Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="0c92d-108">Strong encryption generally consumes more CPU resources than weak encryption.</span></span>  
  
-   <span data-ttu-id="0c92d-109">Lange Schlüssel führen in der Regel zu einer stärkeren Verschlüsselung als kurze Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="0c92d-109">Long keys generally yield stronger encryption than short keys.</span></span>  
  
-   <span data-ttu-id="0c92d-110">Eine asymmetrische Verschlüsselung ist schwächer als eine symmetrische Verschlüsselung, wenn beide die gleiche Schlüssellänge verwenden. Dabei ist eine asymmetrische Verschlüsselung relativ langsam.</span><span class="sxs-lookup"><span data-stu-id="0c92d-110">Asymmetric encryption is weaker than symmetric encryption using the same key length, but it is relatively slow.</span></span>  
  
-   <span data-ttu-id="0c92d-111">Blockchiffren mit langen Schlüsseln sind stärker als Datenstromchiffren.</span><span class="sxs-lookup"><span data-stu-id="0c92d-111">Block ciphers with long keys are stronger than stream ciphers.</span></span>  
  
-   <span data-ttu-id="0c92d-112">Lange, komplexe Kennwörter sind stärker als kurze Kennwörter.</span><span class="sxs-lookup"><span data-stu-id="0c92d-112">Long, complex passwords are stronger than short passwords.</span></span>  
  
-   <span data-ttu-id="0c92d-113">Falls Sie viele Daten verschlüsseln, sollten Sie die Daten mithilfe eines symmetrischen Schlüssels verschlüsseln und den symmetrischen Schlüssel mit einem asymmetrischen Schlüssel verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="0c92d-113">If you are encrypting lots of data, you should encrypt the data using a symmetric key, and encrypt the symmetric key with an asymmetric key.</span></span>  
  
-   <span data-ttu-id="0c92d-114">Verschlüsselte Daten können nicht komprimiert werden, aber komprimierte Daten können verschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="0c92d-114">Encrypted data cannot be compressed, but compressed data can be encrypted.</span></span> <span data-ttu-id="0c92d-115">Falls Sie die Komprimierung verwenden, sollten Sie die Daten vor dem Verschlüsseln komprimieren.</span><span class="sxs-lookup"><span data-stu-id="0c92d-115">If you use compression, you should compress data before encrypting it.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0c92d-116">Der RC4-Algorithmus wird nur aus Gründen der Abwärtskompatibilität unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0c92d-116">The RC4 algorithm is only supported for backward compatibility.</span></span> <span data-ttu-id="0c92d-117">Neues Material kann nur mit RC4 oder RC4_128 verschlüsselt werden, wenn die Datenbank den Kompatibilitätsgrad 90 oder 100 besitzt.</span><span class="sxs-lookup"><span data-stu-id="0c92d-117">New material can only be encrypted using RC4 or RC4_128 when the database is in compatibility level 90 or 100.</span></span> <span data-ttu-id="0c92d-118">(Nicht empfohlen.) Verwenden Sie stattdessen einen neueren Algorithmus, z. B. einen der AES-Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="0c92d-118">(Not recommended.) Use a newer algorithm such as one of the AES algorithms instead.</span></span> <span data-ttu-id="0c92d-119">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] und höher kann mit RC4 oder RC4_128 verschlüsseltes Material in jedem Kompatibilitätsgrad entschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="0c92d-119">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] and higher material encrypted using RC4 or RC4_128 can be decrypted in any compatibility level.</span></span>  
>   
>  <span data-ttu-id="0c92d-120">Die wiederholte Verwendung der gleichen RC4- oder RC4_128-KEY_GUID für unterschiedliche Datenblocks führt zum gleichen RC4-Schlüssel, da [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nicht automatisch eine Salt bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="0c92d-120">Repeated use of the same RC4 or RC4_128 KEY_GUID on different blocks of data will result in the same RC4 key because [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not provide a salt automatically.</span></span> <span data-ttu-id="0c92d-121">Die wiederholte Verwendung des gleichen RC4-Schlüssels stellt einen bekannten Fehler dar, der zu einer sehr schwachen Verschlüsselung führt.</span><span class="sxs-lookup"><span data-stu-id="0c92d-121">Using the same RC4 key repeatedly is a well-known error that will result in very weak encryption.</span></span> <span data-ttu-id="0c92d-122">Deshalb wurden das RC4-Schlüsselwort und das RC4_128-Schlüsselwort als veraltet festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0c92d-122">Therefore, we have deprecated the RC4 and RC4_128 keywords.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="0c92d-123">Weitere Informationen zu Verschlüsselungsalgorithmen und der Verschlüsselungstechnologie finden Sie unter [Key Security Concepts](https://go.microsoft.com/fwlink/?LinkId=62082) im .NET Framework Developer's Guide auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="0c92d-123">For more information about encryption algorithms and encryption technology, see [Key Security Concepts](https://go.microsoft.com/fwlink/?LinkId=62082) in the .NET Framework Developer's Guide on MSDN.</span></span>  
  
 <span data-ttu-id="0c92d-124">**Erläuterung der DES-Algorithmen:**</span><span class="sxs-lookup"><span data-stu-id="0c92d-124">**Clarification regarding DES algorithms:**</span></span>  
  
-   <span data-ttu-id="0c92d-125">DESX wurde falsch benannt.</span><span class="sxs-lookup"><span data-stu-id="0c92d-125">DESX was incorrectly named.</span></span> <span data-ttu-id="0c92d-126">Symmetrische Schlüssel, die mit ALGORITHM = DESX erstellt sind, verwenden eigentlich die TRIPLE DES-Chiffre mit einem 192-Bit-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="0c92d-126">Symmetric keys created with ALGORITHM = DESX actually use the TRIPLE DES cipher with a 192-bit key.</span></span> <span data-ttu-id="0c92d-127">Der DESX-Algorithmus wird nicht bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="0c92d-127">The DESX algorithm is not provided.</span></span> [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
-   <span data-ttu-id="0c92d-128">Symmetrische Schlüssel, die mit ALGORITHM = TRIPLE_DES_3KEY erstellt sind, verwenden die TRIPLE DES-Chiffre mit einem 192-Bit-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="0c92d-128">Symmetric keys created with ALGORITHM = TRIPLE_DES_3KEY use TRIPLE DES with a 192-bit key.</span></span>  
  
-   <span data-ttu-id="0c92d-129">Symmetrische Schlüssel, die mit ALGORITHM = TRIPLE_DES erstellt sind, verwenden die TRIPLE DES-Chiffre mit einem 128-Bit-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="0c92d-129">Symmetric keys created with ALGORITHM = TRIPLE_DES use TRIPLE DES with a 128-bit key.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="0c92d-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="0c92d-130">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0c92d-131">Verschlüsseln von Daten mit einem symmetrischen Schlüssel</span><span class="sxs-lookup"><span data-stu-id="0c92d-131">Encrypting using a symmetric key.</span></span>|[<span data-ttu-id="0c92d-132">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0c92d-132">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-symmetric-key-transact-sql)|  
|<span data-ttu-id="0c92d-133">Verschlüsseln von Daten mit einem asymmetrischen Schlüssel</span><span class="sxs-lookup"><span data-stu-id="0c92d-133">Encrypting using an asymmetric key.</span></span>|[<span data-ttu-id="0c92d-134">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0c92d-134">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-asymmetric-key-transact-sql)|  
|<span data-ttu-id="0c92d-135">Verschlüsseln von Daten mit einem Zertifikat</span><span class="sxs-lookup"><span data-stu-id="0c92d-135">Encrypting using a certificate.</span></span>|[<span data-ttu-id="0c92d-136">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0c92d-136">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)|  
|<span data-ttu-id="0c92d-137">Verschlüsseln von Datenbankdateien mit transparenter Datenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="0c92d-137">Encrypting database files using transparent data encryption.</span></span>|[<span data-ttu-id="0c92d-138">Transparente Datenverschlüsselung &#40;TDE&#41;</span><span class="sxs-lookup"><span data-stu-id="0c92d-138">Transparent Data Encryption &#40;TDE&#41;</span></span>](transparent-data-encryption.md)|  
|<span data-ttu-id="0c92d-139">So verschlüsseln sie eine Tabellenspalte</span><span class="sxs-lookup"><span data-stu-id="0c92d-139">How to encrypt one column of a table.</span></span>|[<span data-ttu-id="0c92d-140">Verschlüsseln einer Datenspalte</span><span class="sxs-lookup"><span data-stu-id="0c92d-140">Encrypt a Column of Data</span></span>](encrypt-a-column-of-data.md)|  
  
## <a name="see-also"></a><span data-ttu-id="0c92d-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0c92d-141">See Also</span></span>  
 <span data-ttu-id="0c92d-142">[SQL Server-Verschlüsselung](sql-server-encryption.md) </span><span class="sxs-lookup"><span data-stu-id="0c92d-142">[SQL Server Encryption](sql-server-encryption.md) </span></span>  
 [<span data-ttu-id="0c92d-143">Verschlüsselungshierarchie</span><span class="sxs-lookup"><span data-stu-id="0c92d-143">Encryption Hierarchy</span></span>](encryption-hierarchy.md)  
  
  
