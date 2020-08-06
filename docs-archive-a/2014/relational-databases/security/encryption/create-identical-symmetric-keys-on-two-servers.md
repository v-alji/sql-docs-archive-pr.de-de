---
title: Erstellen identischer symmetrischer Schlüssel auf zwei Servern | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- symmetric keys [SQL Server], creating
ms.assetid: a13d0b21-a43b-43c0-9c22-7ba8f3d15e80
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 38eaccffff89b0be7e59f628fcfb9b6e772a02b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725398"
---
# <a name="create-identical-symmetric-keys-on-two-servers"></a><span data-ttu-id="92bcf-102">Erstellen identischer symmetrischer Schlüssel auf zwei Servern</span><span class="sxs-lookup"><span data-stu-id="92bcf-102">Create Identical Symmetric Keys on Two Servers</span></span>
  <span data-ttu-id="92bcf-103">In diesem Thema wird beschrieben, wie identische symmetrische Schlüssel in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mit [!INCLUDE[tsql](../../../includes/tsql-md.md)]auf zwei verschiedenen Servern erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="92bcf-103">This topic describes how to create identical symmetric keys on two different servers in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="92bcf-104">Zum Entschlüsseln von verschlüsseltem Text benötigen Sie den Schlüssel, der beim Verschlüsseln verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="92bcf-104">In order to decrypt ciphertext, you need the key that was used to encrypt it.</span></span> <span data-ttu-id="92bcf-105">Wenn eine Datenbank sowohl Verschlüsselungen als auch Entschlüsselungen enthält, ist der Schlüssel in der Datenbank gespeichert, und er ist entsprechend den Berechtigungen sowohl für die Verschlüsselung als auch für die Entschlüsselung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="92bcf-105">When both encryption and decryption occur in a single database, the key is stored in the database and it is available, depending on permissions, for both encryption and decryption.</span></span> <span data-ttu-id="92bcf-106">Wenn sich Verschlüsselung und Entschlüsselung jedoch in separaten Datenbanken oder auf separaten Servern vorkommt, kann der in einer Datenbank gespeicherte Schlüssel nicht für die zweite Datenbank verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="92bcf-106">But when encryption and decryption occur in separate databases or on separate servers, the key stored in one database is not available for use on the second database</span></span>  
  
 <span data-ttu-id="92bcf-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="92bcf-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="92bcf-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="92bcf-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="92bcf-109">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="92bcf-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="92bcf-110">Security</span><span class="sxs-lookup"><span data-stu-id="92bcf-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="92bcf-111">So erstellen Sie identische symmetrische Schlüssel auf zwei unterschiedlichen Servern mit Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="92bcf-111">To create identical symmetric keys on two different servers, using Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="92bcf-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="92bcf-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="92bcf-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="92bcf-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="92bcf-114">Beim Erstellen eines symmetrischen Schlüssels muss der symmetrische Schlüssel mithilfe mindestens eines der folgenden Elemente verschlüsselt werden: Zertifikat, Kennwort, symmetrischer Schlüssel, asymmetrischer Schlüssel oder PROVIDER.</span><span class="sxs-lookup"><span data-stu-id="92bcf-114">When a symmetric key is created, the symmetric key must be encrypted by using at least one of the following: certificate, password, symmetric key, asymmetric key, or PROVIDER.</span></span> <span data-ttu-id="92bcf-115">Der Schlüssel kann mehrere Verschlüsselungen jedes Typs aufweisen.</span><span class="sxs-lookup"><span data-stu-id="92bcf-115">The key can have more than one encryption of each type.</span></span> <span data-ttu-id="92bcf-116">Ein einzelner symmetrischer Schlüssel kann demnach mit mehreren Zertifikaten, Kennwörtern, symmetrischen Schlüsseln und asymmetrischen Schlüsseln gleichzeitig verschlüsselt sein.</span><span class="sxs-lookup"><span data-stu-id="92bcf-116">In other words, a single symmetric key can be encrypted by using multiple certificates, passwords, symmetric keys, and asymmetric keys at the same time.</span></span>  
  
-   <span data-ttu-id="92bcf-117">Wenn ein symmetrischer Schlüssel mit einem Kennwort anstatt mit einem öffentlichen Schlüssel des Datenbank-Hauptschlüssels verschlüsselt ist, wird der TRIPLE_DES-Verschlüsselungsalgorithmus verwendet.</span><span class="sxs-lookup"><span data-stu-id="92bcf-117">When a symmetric key is encrypted with a password instead of the public key of the database master key, the TRIPLE DES encryption algorithm is used.</span></span> <span data-ttu-id="92bcf-118">Daher werden Schlüssel, die mit einem starken Verschlüsselungsalgorithmus wie z. B. AES erstellt werden, selbst mit einem schwächeren Algorithmus verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="92bcf-118">Because of this, keys that are created with a strong encryption algorithm, such as AES, are themselves secured by a weaker algorithm.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="92bcf-119">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="92bcf-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="92bcf-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="92bcf-120">Permissions</span></span>  
 <span data-ttu-id="92bcf-121">Erfordert die ALTER ANY SYMMETRIC KEY-Berechtigung in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="92bcf-121">Requires ALTER ANY SYMMETRIC KEY permission on the database.</span></span> <span data-ttu-id="92bcf-122">Falls die AUTHORIZATION-Klausel angegeben ist, ist die IMPERSONATE-Berechtigung für den Datenbankbenutzer oder die ALTER-Berechtigung für die Anwendungsrolle erforderlich.</span><span class="sxs-lookup"><span data-stu-id="92bcf-122">If AUTHORIZATION is specified, requires IMPERSONATE permission on the database user or ALTER permission on the application role.</span></span> <span data-ttu-id="92bcf-123">Falls die Verschlüsselung mit einem Zertifikat oder asymmetrischen Schlüssel erfolgt, ist die VIEW DEFINITION-Berechtigung für das Zertifikat oder den asymmetrischen Schlüssel erforderlich.</span><span class="sxs-lookup"><span data-stu-id="92bcf-123">If encryption is by certificate or asymmetric key, requires VIEW DEFINITION permission on the certificate or asymmetric key.</span></span> <span data-ttu-id="92bcf-124">Nur Windows-Anmeldungen, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Anmeldungen und Anwendungsrollen können symmetrische Schlüssel besitzen.</span><span class="sxs-lookup"><span data-stu-id="92bcf-124">Only Windows logins, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins, and application roles can own symmetric keys.</span></span> <span data-ttu-id="92bcf-125">Gruppen und Rollen können keine symmetrischen Schlüssel besitzen.</span><span class="sxs-lookup"><span data-stu-id="92bcf-125">Groups and roles cannot own symmetric keys.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="92bcf-126">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="92bcf-126">Using Transact-SQL</span></span>  
  
#### <a name="to-create-identical-symmetric-keys-on-two-different-servers"></a><span data-ttu-id="92bcf-127">So erstellen Sie identische symmetrische Schlüssel auf zwei verschiedenen Servern</span><span class="sxs-lookup"><span data-stu-id="92bcf-127">To create identical symmetric keys on two different servers</span></span>  
  
1.  <span data-ttu-id="92bcf-128">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="92bcf-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="92bcf-129">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="92bcf-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="92bcf-130">Erstellen Sie einen Schlüssel, indem Sie die folgenden CREATE MASTER KEY-, CREATE CERTIFICATE- und CREATE SYMMETRIC KEY-Anweisungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="92bcf-130">Create a key by running the following CREATE MASTER KEY, CREATE CERTIFICATE, and CREATE SYMMETRIC KEY statements.</span></span>  
  
    ```  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'My p@55w0Rd';  
    GO  
    CREATE CERTIFICATE [cert_keyProtection] WITH SUBJECT = 'Key Protection';  
    GO  
    CREATE SYMMETRIC KEY [key_DataShare] WITH  
        KEY_SOURCE = 'My key generation bits. This is a shared secret!',  
        ALGORITHM = AES_256,   
        IDENTITY_VALUE = 'Key Identity generation bits. Also a shared secret'  
        ENCRYPTION BY CERTIFICATE [cert_keyProtection];  
    GO  
    ```  
  
4.  <span data-ttu-id="92bcf-131">Stellen Sie eine Verbindung mit einer separaten Serverinstanz her, öffnen Sie ein anderes Abfragefenster, und führen Sie die oben erwähnten SQL-Anweisungen aus, um den gleichen Schlüssel auf dem zweiten Server zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="92bcf-131">Connect to a separate server instance, open a different Query Window, and run the SQL statements above to create the same key on the second server.</span></span>  
  
5.  <span data-ttu-id="92bcf-132">Testen Sie die Schlüssel, indem Sie zunächst die OPEN SYMMETRIC KEY-Anweisung und die SELECT-Anweisung unten auf dem ersten Server ausführen.</span><span class="sxs-lookup"><span data-stu-id="92bcf-132">Test the keys by first running the OPEN SYMMETRIC KEY statement and the SELECT statement below on the first server.</span></span>  
  
    ```  
    OPEN SYMMETRIC KEY [key_DataShare]   
        DECRYPTION BY CERTIFICATE cert_keyProtection;  
    GO  
    SELECT encryptbykey(key_guid('key_DataShare'), 'MyData' )  
    GO  
    -- For example, the output might look like this: 0x2152F8DA8A500A9EDC2FAE26D15C302DA70D25563DAE7D5D1102E3056CE9EF95CA3E7289F7F4D0523ED0376B155FE9C3  
    ```  
  
6.  <span data-ttu-id="92bcf-133">Fügen Sie auf dem zweiten Server das Ergebnis der vorherigen SELECT-Anweisung als Wert für `@blob` in den folgenden Code ein, und führen Sie den folgenden Code aus, um zu überprüfen, ob der verschlüsselte Text mit dem doppelten Schlüssel entschlüsselt werden kann.</span><span class="sxs-lookup"><span data-stu-id="92bcf-133">On the second server, paste the result of the previous SELECT statement into the following code as the value of `@blob` and run the following code to verify that the duplicate key can decrypt the ciphertext.</span></span>  
  
    ```  
    OPEN SYMMETRIC KEY [key_DataShare]   
        DECRYPTION BY CERTIFICATE cert_keyProtection;  
    GO  
    DECLARE @blob varbinary(8000);  
    SET @blob = SELECT CONVERT(varchar(8000), decryptbykey(@blob));  
    GO  
    ```  
  
7.  <span data-ttu-id="92bcf-134">Schließen Sie den symmetrischen Schlüssel auf beiden Servern.</span><span class="sxs-lookup"><span data-stu-id="92bcf-134">Close the symmetric key on both servers.</span></span>  
  
    ```  
    CLOSE SYMMETRIC KEY [key_DataShare];  
    GO  
    ```  
  
 <span data-ttu-id="92bcf-135">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="92bcf-135">For more information, see the following:</span></span>  
  
-   [<span data-ttu-id="92bcf-136">CREATE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="92bcf-136">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)  
  
-   [<span data-ttu-id="92bcf-137">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="92bcf-137">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)  
  
-   [<span data-ttu-id="92bcf-138">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="92bcf-138">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-symmetric-key-transact-sql)  
  
-   [<span data-ttu-id="92bcf-139">ENCRYPTBYKEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="92bcf-139">ENCRYPTBYKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbykey-transact-sql)  
  
-   [<span data-ttu-id="92bcf-140">DECRYPTBYKEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="92bcf-140">DECRYPTBYKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/decryptbykey-transact-sql)  
  
-   [<span data-ttu-id="92bcf-141">OPEN SYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="92bcf-141">OPEN SYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/open-symmetric-key-transact-sql)  
  
  
