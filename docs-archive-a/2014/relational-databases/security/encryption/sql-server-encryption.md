---
title: SQL Server-Verschlüsselung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], about encryption
- security [SQL Server], encryption
- cryptography [SQL Server], about cryptography
ms.assetid: ead0150e-4943-4ad5-84c8-36f85c7278f4
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 6fc68e6f3280a8e23d6a1bf4f364aadfffd69f85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726830"
---
# <a name="sql-server-encryption"></a><span data-ttu-id="defec-102">SQL Server-Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="defec-102">SQL Server Encryption</span></span>
  <span data-ttu-id="defec-103">Als Verschlüsselung wird der Vorgang bezeichnet, Daten mithilfe eines Schlüssels oder eines Kennworts unlesbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="defec-103">Encryption is the process of obfuscating data by the use of a key or password.</span></span> <span data-ttu-id="defec-104">Die Daten werden dadurch ohne den entsprechenden Entschlüsselungsschlüssel oder das Kennwort unbrauchbar.</span><span class="sxs-lookup"><span data-stu-id="defec-104">This can make the data useless without the corresponding decryption key or password.</span></span> <span data-ttu-id="defec-105">Durch Verschlüsselung werden keine Probleme der Zugriffssteuerung gelöst.</span><span class="sxs-lookup"><span data-stu-id="defec-105">Encryption does not solve access control problems.</span></span> <span data-ttu-id="defec-106">Sie erhöht jedoch die Sicherheit, indem sie den Datenverlust auch dann einschränkt, wenn die Zugriffssteuerung umgangen wird.</span><span class="sxs-lookup"><span data-stu-id="defec-106">However, it enhances security by limiting data loss even if access controls are bypassed.</span></span> <span data-ttu-id="defec-107">Wenn der Hostcomputer einer Datenbank beispielsweise falsch konfiguriert wurde und ein Hacker Zugriff auf vertrauliche Daten erlangt, sind diese gestohlenen Daten sehr wahrscheinlich nutzlos, wenn sie verschlüsselt wurden.</span><span class="sxs-lookup"><span data-stu-id="defec-107">For example, if the database host computer is misconfigured and a hacker obtains sensitive data, that stolen information might be useless if it is encrypted.</span></span>  
  
 <span data-ttu-id="defec-108">Sie können in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Verbindungen, Daten und gespeicherte Prozeduren verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="defec-108">You can use encryption in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] for connections, data, and stored procedures.</span></span> <span data-ttu-id="defec-109">Die folgende Tabelle enthält weitere Informationen zur Verschlüsselung in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="defec-109">The following table contains more information about encryption in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="defec-110">Zwar ist die Verschlüsselung ein wertvolles Mittel, Sicherheit zu gewährleisten, sollte jedoch nicht für alle Daten oder Verbindungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="defec-110">Although encryption is a valuable tool to help ensure security, it should not be considered for all data or connections.</span></span> <span data-ttu-id="defec-111">Bevor Sie sich dafür entscheiden, Verschlüsselung zu verwenden, prüfen Sie, wie Benutzer auf die Daten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="defec-111">When you are deciding whether to implement encryption, consider how users will access data.</span></span> <span data-ttu-id="defec-112">Wenn Benutzer über ein öffentliches Netzwerk auf Daten zugreifen, könnte die Datenverschlüsselung die Sicherheit erhöhen.</span><span class="sxs-lookup"><span data-stu-id="defec-112">If users access data over a public network, data encryption might be required to increase security.</span></span> <span data-ttu-id="defec-113">Wenn sich aber der gesamte Zugriff innerhalb einer sicheren Intranetkonfiguration abspielt, ist eine Verschlüsselung möglicherweise nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="defec-113">However, if all access involves a secure intranet configuration, encryption might not be required.</span></span> <span data-ttu-id="defec-114">Jede Verwendung der Verschlüsselung sollte auch eine Wartungsstrategie für Kennwörter, Schlüssel und Zertifikate einschließen.</span><span class="sxs-lookup"><span data-stu-id="defec-114">Any use of encryption should also include a maintenance strategy for passwords, keys, and certificates.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="defec-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="defec-115">In This Section</span></span>  
 [<span data-ttu-id="defec-116">Verschlüsselungshierarchie</span><span class="sxs-lookup"><span data-stu-id="defec-116">Encryption Hierarchy</span></span>](encryption-hierarchy.md)  
 <span data-ttu-id="defec-117">Informationen zur Verschlüsselungshierarchie in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="defec-117">Information about the encryption hierarchy in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="defec-118">Auswählen eines Verschlüsselungsalgorithmus</span><span class="sxs-lookup"><span data-stu-id="defec-118">Choose an Encryption Algorithm</span></span>](choose-an-encryption-algorithm.md)  
 <span data-ttu-id="defec-119">Informationen zur Auswahl eines wirksamen Verschlüsselungsalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="defec-119">Information about how to select an effective encrypting algorithm.</span></span>  
  
 [<span data-ttu-id="defec-120">Transparente Datenverschlüsselung &#40;TDE&#41;</span><span class="sxs-lookup"><span data-stu-id="defec-120">Transparent Data Encryption &#40;TDE&#41;</span></span>](transparent-data-encryption.md)  
 <span data-ttu-id="defec-121">Allgemeine Informationen über das transparente Verschlüsseln von Daten.</span><span class="sxs-lookup"><span data-stu-id="defec-121">General information about how to encrypt data transparently.</span></span>  
  
 [<span data-ttu-id="defec-122">Verschlüsselungsschlüssel für SQL Server und Datenbank &#40;Datenbank-Engine&#41;</span><span class="sxs-lookup"><span data-stu-id="defec-122">SQL Server and Database Encryption Keys &#40;Database Engine&#41;</span></span>](sql-server-and-database-encryption-keys-database-engine.md)  
 <span data-ttu-id="defec-123">Die Verschlüsselungsschlüssel in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]bestehen aus einer Kombination von öffentlichen, privaten und symmetrischen Schlüsseln, die zum Schutz sensibler Daten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="defec-123">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], encryption keys include a combination of public, private, and symmetric keys that are used to protect sensitive data.</span></span> <span data-ttu-id="defec-124">Dieser Abschnitt erklärt, wie Verschlüsselungsschlüssel implementiert und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="defec-124">This section explains how to implement and manage encryption keys.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="defec-125">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="defec-125">Related Content</span></span>  
 [<span data-ttu-id="defec-126">Sichern von SQL Server</span><span class="sxs-lookup"><span data-stu-id="defec-126">Securing SQL Server</span></span>](../securing-sql-server.md)  
 <span data-ttu-id="defec-127">Überblick über die Absicherung der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Plattform und die Arbeit mit Benutzern und sicherungsfähigen Objekten.</span><span class="sxs-lookup"><span data-stu-id="defec-127">Overview of how to help secure the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] platform, and how to work with users and securable objects.</span></span>  
  
 [<span data-ttu-id="defec-128">Kryptografiefunktionen &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="defec-128">Cryptographic Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/cryptographic-functions-transact-sql)  
 <span data-ttu-id="defec-129">Informationen dazu, wie Kryptografiefunktionen implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="defec-129">Information about how to implement cryptographic functions.</span></span>  
  
 [<span data-ttu-id="defec-130">ENCRYPTBYPASSPHRASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="defec-130">ENCRYPTBYPASSPHRASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbypassphrase-transact-sql)  
 <span data-ttu-id="defec-131">Informationen dazu, wie ein Kennwort zur Verschlüsselung von Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="defec-131">Information about how to use a password to encrypt data.</span></span>  
  
 [<span data-ttu-id="defec-132">ENCRYPTBYKEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="defec-132">ENCRYPTBYKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbykey-transact-sql)  
 <span data-ttu-id="defec-133">Informationen dazu, wie ein symmetrischer Schlüssel zur Verschlüsselung von Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="defec-133">Information about how to use a symmetric key to encrypt data.</span></span>  
  
 [<span data-ttu-id="defec-134">ENCRYPTBYASYMKEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="defec-134">ENCRYPTBYASYMKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbyasymkey-transact-sql)  
 <span data-ttu-id="defec-135">Informationen dazu, wie ein asymmetrischer Schlüssel zur Verschlüsselung von Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="defec-135">Information about how to use an asymmetric key to encrypt data.</span></span>  
  
 [<span data-ttu-id="defec-136">ENCRYPTBYCERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="defec-136">ENCRYPTBYCERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbycert-transact-sql)  
 <span data-ttu-id="defec-137">Informationen dazu, wie ein Zertifikat zur Verschlüsselung von Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="defec-137">Information about how to use a certificate to encrypt data.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="defec-138">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="defec-138">External Resources</span></span>  
 [<span data-ttu-id="defec-139">10 Schritte zum SQL Server 2005-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="defec-139">10 Steps to SQL Server 2005 Security</span></span>](https://www.itprotoday.com/sql-server/10-steps-sql-server-2005-security)  
 <span data-ttu-id="defec-140">Aktuelle Informationen über die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="defec-140">Current information about [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] security.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="defec-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="defec-141">See Also</span></span>  
 <span data-ttu-id="defec-142">[sys.key_encryptions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-key-encryptions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="defec-142">[sys.key_encryptions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-key-encryptions-transact-sql) </span></span>  
 <span data-ttu-id="defec-143">[Verschlüsselungsschlüssel für SQL Server und Datenbank &#40;Datenbank-Engine&#41;](sql-server-and-database-encryption-keys-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="defec-143">[SQL Server and Database Encryption Keys &#40;Database Engine&#41;](sql-server-and-database-encryption-keys-database-engine.md) </span></span>  
 [<span data-ttu-id="defec-144">Sichern und Wiederherstellen von Reporting Services-Verschlüsselungsschlüsseln</span><span class="sxs-lookup"><span data-stu-id="defec-144">Back Up and Restore Reporting Services Encryption Keys</span></span>](../../../reporting-services/install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md)  
  
  
