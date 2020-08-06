---
title: Diensthauptschlüssel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- service master key [SQL Server]
- service master key [SQL Server], about service master key
ms.assetid: 85f2095d-2590-4f59-8a29-7e100edd02bb
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: baeeffd49ac89ce85cf64932fbfd4982d7243887
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726841"
---
# <a name="service-master-key"></a><span data-ttu-id="ea3fe-102">Diensthauptschlüssel</span><span class="sxs-lookup"><span data-stu-id="ea3fe-102">Service Master Key</span></span>
  <span data-ttu-id="ea3fe-103">Der Diensthauptschlüssel ist der Stamm der Verschlüsselungshierarchie von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ea3fe-103">The Service Master Key is the root of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption hierarchy.</span></span> <span data-ttu-id="ea3fe-104">Er wird automatisch dann generiert, wenn er erstmals zum Verschlüsseln eines anderen Schlüssels benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="ea3fe-104">It is generated automatically the first time it is needed to encrypt another key.</span></span> <span data-ttu-id="ea3fe-105">Standardmäßig wird der Diensthauptschlüssel mit der Windows-Datenschutz-API und dem Schlüssel für den lokalen Computer verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="ea3fe-105">By default, the Service Master Key is encrypted using the Windows data protection API and using the local machine key.</span></span> <span data-ttu-id="ea3fe-106">Der Diensthauptschlüssel kann nur durch das Windows-Dienstkonto geöffnet werden, unter dem er erstellt wurde, oder durch einen Prinzipal mit Zugriff auf den Namen des Dienstkontos und sein Kennwort.</span><span class="sxs-lookup"><span data-stu-id="ea3fe-106">The Service Master Key can only be opened by the Windows service account under which it was created or by a principal with access to both the service account name and its password.</span></span>  
  
 <span data-ttu-id="ea3fe-107">Das erneute Generieren oder Wiederherstellen des Diensthauptschlüssels umfasst das Entschlüsseln und erneute Verschlüsseln der gesamten Verschlüsselungshierarchie.</span><span class="sxs-lookup"><span data-stu-id="ea3fe-107">Regenerating or restoring the Service Master Key involves decrypting and re-encrypting the complete encryption hierarchy.</span></span> <span data-ttu-id="ea3fe-108">Wenn der Schlüssel nicht beschädigt wurde, sollte dieser ressourcenintensive Vorgang für einen Zeitraum mit geringem Bedarf geplant werden.</span><span class="sxs-lookup"><span data-stu-id="ea3fe-108">Unless the key has been compromised, this resource-intensive operation should be scheduled during a period of low demand.</span></span>  
  
 [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] <span data-ttu-id="ea3fe-109">SQL Server 2016 schützt den Diensthauptschlüssel (Service Master Key, SMK) und den Datenbank-Hauptschlüssel (Database Master Key, DMK) mithilfe des AES-Verschlüsselungsalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="ea3fe-109">uses the AES encryption algorithm to protect the service master key (SMK) and the database master key (DMK).</span></span> <span data-ttu-id="ea3fe-110">AES ist ein neuerer Verschlüsselungsalgorithmus als der in früheren Versionen verwendete 3DES-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="ea3fe-110">AES is a newer encryption algorithm than 3DES used in earlier versions.</span></span> <span data-ttu-id="ea3fe-111">Nach dem Aktualisieren einer Instanz von [!INCLUDE[ssDE](../../../includes/ssde-md.md)] auf [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] sollten SMK und DMK erneut generiert werden, um die Hauptschlüssel auf AES zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ea3fe-111">After upgrading an instance of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] the SMK and DMK should be regenerated in order to upgrade the master keys to AES.</span></span> <span data-ttu-id="ea3fe-112">Weitere Informationen zum Neugenerieren des SMK finden Sie unter [ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-service-master-key-transact-sql) und [ALTER MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ea3fe-112">For more information about regenerating the SMK, see [ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-service-master-key-transact-sql) and [ALTER MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-master-key-transact-sql).</span></span>  
  
## <a name="best-practice"></a><span data-ttu-id="ea3fe-113">Bewährte Methode</span><span class="sxs-lookup"><span data-stu-id="ea3fe-113">Best Practice</span></span>  
 <span data-ttu-id="ea3fe-114">Sichern Sie den Diensthauptschlüssel, und lagern Sie die Sicherungskopie an einem separaten, sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="ea3fe-114">Back up the Service Master Key and store the backed up copy in a secure, off-site location.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="ea3fe-115">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="ea3fe-115">Related Tasks</span></span>  
 [<span data-ttu-id="ea3fe-116">BACKUP SERVICE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ea3fe-116">BACKUP SERVICE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-service-master-key-transact-sql)  
  
 [<span data-ttu-id="ea3fe-117">RESTORE SERVICE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ea3fe-117">RESTORE SERVICE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-service-master-key-transact-sql)  
  
 [<span data-ttu-id="ea3fe-118">ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ea3fe-118">ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-service-master-key-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="ea3fe-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ea3fe-119">See Also</span></span>  
 [<span data-ttu-id="ea3fe-120">Verschlüsselungshierarchie</span><span class="sxs-lookup"><span data-stu-id="ea3fe-120">Encryption Hierarchy</span></span>](encryption-hierarchy.md)  
  
  
