---
title: Replizieren von Daten in verschlüsselten Spalten (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], replicating data
- encryption [SQL Server replication]
- publishing [SQL Server replication], encrypted columns
ms.assetid: d1f8f586-e5a3-4a71-9391-11198d42bfa3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2e1528d81faa352fdcdf37abe9ad93fda190445c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701037"
---
# <a name="replicate-data-in-encrypted-columns-sql-server-management-studio"></a><span data-ttu-id="61c11-102">Replizieren von Daten in verschlüsselten Spalten (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="61c11-102">Replicate Data in Encrypted Columns (SQL Server Management Studio)</span></span>
  <span data-ttu-id="61c11-103">Mithilfe der Replikation können Sie verschlüsselte Spaltendaten veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="61c11-103">Replication enables you to publish encrypted column data.</span></span> <span data-ttu-id="61c11-104">Zum Entschlüsseln und Verwenden dieser Daten auf dem Abonnenten muss der zum Verschlüsseln der Daten auf dem Verleger verwendete Schlüssel auch auf dem Abonnenten vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="61c11-104">To decrypt and use this data at the Subscriber, the key that was used to encrypt the data at the Publisher must also be present on the Subscriber.</span></span> <span data-ttu-id="61c11-105">Die Replikation bietet keinen sicheren Mechanismus zum Transportieren von Verschlüsselungsschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="61c11-105">Replication does not provide a secure mechanism to transport encryption keys.</span></span> <span data-ttu-id="61c11-106">Sie müssen den Verschlüsselungsschlüssel auf dem Abonnenten manuell neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="61c11-106">You must manually re-create the encryption key at the Subscriber.</span></span> <span data-ttu-id="61c11-107">In diesem Thema wird veranschaulicht, wie Sie eine Spalte auf dem Verleger verschlüsseln und wie Sie sicherstellen, dass der Verschlüsselungsschlüssel auf dem Abonnenten verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="61c11-107">This topic shows you how to encrypt a column at the Publisher and make sure that the encryption key is available at the Subscriber.</span></span>  
  
 <span data-ttu-id="61c11-108">Die grundlegenden Schritte lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="61c11-108">The basic steps are as follows:</span></span>  
  
1.  <span data-ttu-id="61c11-109">Erstellen Sie den symmetrischen Schlüssel auf dem Verleger.</span><span class="sxs-lookup"><span data-stu-id="61c11-109">Create the symmetric key at the Publisher.</span></span>  
  
2.  <span data-ttu-id="61c11-110">Verschlüsseln Sie Spaltendaten mit dem symmetrischen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="61c11-110">Encrypt column data with the symmetric key.</span></span>  
  
3.  <span data-ttu-id="61c11-111">Veröffentlichen Sie die Tabelle mit der verschlüsselten Spalte.</span><span class="sxs-lookup"><span data-stu-id="61c11-111">Publish the table with the encrypted column.</span></span>  
  
4.  <span data-ttu-id="61c11-112">Abonnieren Sie die Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="61c11-112">Subscribe to the publication.</span></span>  
  
5.  <span data-ttu-id="61c11-113">Initialisieren Sie das Abonnement.</span><span class="sxs-lookup"><span data-stu-id="61c11-113">Initialize the subscription.</span></span>  
  
6.  <span data-ttu-id="61c11-114">Erstellen Sie den symmetrischen Schlüssel auf dem Abonnenten neu, indem Sie für ALGORITHM, KEY_SOURCE und IDENTITY_VALUE dieselben Werte wie in Schritt 1 verwenden.</span><span class="sxs-lookup"><span data-stu-id="61c11-114">Recreate the symmetric key at the Subscriber using same values for ALGORITHM, KEY_SOURCE, and IDENTITY_VALUE as in step 1.</span></span>  
  
7.  <span data-ttu-id="61c11-115">Greifen Sie auf die verschlüsselten Spaltendaten zu.</span><span class="sxs-lookup"><span data-stu-id="61c11-115">Access the encrypted column data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61c11-116">Verwenden Sie zum Verschlüsseln von Spaltendaten einen symmetrischen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="61c11-116">You should use a symmetric key to encrypt column data.</span></span> <span data-ttu-id="61c11-117">Der symmetrische Schlüssel kann auf unterschiedliche Weise auf dem Verleger und dem Abonnenten gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="61c11-117">The symmetric key itself can be secured by different means at the Publisher and Subscriber.</span></span>  
  
### <a name="to-create-and-replicate-encrypted-column-data"></a><span data-ttu-id="61c11-118">So erstellen und replizieren Sie verschlüsselte Spaltendaten</span><span class="sxs-lookup"><span data-stu-id="61c11-118">To create and replicate encrypted column data</span></span>  
  
1.  <span data-ttu-id="61c11-119">Führen Sie [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql)auf dem Verleger aus.</span><span class="sxs-lookup"><span data-stu-id="61c11-119">At the Publisher, execute [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="61c11-120">Der Wert von KEY_SOURCE stellt wichtige Daten dar, die verwendet werden können, um den symmetrischen Schlüssel neu zu erstellen und Daten zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="61c11-120">The value of KEY_SOURCE is valuable data that can be used to re-create the symmetric key and decrypt data.</span></span> <span data-ttu-id="61c11-121">KEY_SOURCE muss immer sicher gespeichert und transportiert werden.</span><span class="sxs-lookup"><span data-stu-id="61c11-121">KEY_SOURCE must always be stored and transported securely.</span></span>  
  
2.  <span data-ttu-id="61c11-122">Führen Sie [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) aus, um den neuen Schlüssel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="61c11-122">Execute [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) to open the new key.</span></span>  
  
3.  <span data-ttu-id="61c11-123">Verwenden Sie die [EncryptByKey](/sql/t-sql/functions/encryptbykey-transact-sql) -Funktion, um Spaltendaten auf dem Verleger zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="61c11-123">Use the [EncryptByKey](/sql/t-sql/functions/encryptbykey-transact-sql) function to encrypt column data at the Publisher.</span></span>  
  
4.  <span data-ttu-id="61c11-124">Führen Sie [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) aus, um den Schlüssel zu schließen.</span><span class="sxs-lookup"><span data-stu-id="61c11-124">Execute [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) to close the key.</span></span>  
  
5.  <span data-ttu-id="61c11-125">Veröffentlichen Sie die Tabelle, die die verschlüsselte Spalte enthält.</span><span class="sxs-lookup"><span data-stu-id="61c11-125">Publish the table that contains the encrypted column.</span></span> <span data-ttu-id="61c11-126">Weitere Informationen finden Sie unter [Create a Publication](../publish/create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="61c11-126">For more information, see [Create a Publication](../publish/create-a-publication.md).</span></span>  
  
6.  <span data-ttu-id="61c11-127">Abonnieren Sie die Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="61c11-127">Subscribe to the publication.</span></span> <span data-ttu-id="61c11-128">Weitere Informationen finden Sie unter [Erstellen eines Pullabonnnements](../create-a-pull-subscription.md) und [Erstellen eines Pushabonnements](../create-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="61c11-128">For more information, see [Create a Pull Subscription](../create-a-pull-subscription.md) or [Create a Push Subscription](../create-a-push-subscription.md).</span></span>  
  
7.  <span data-ttu-id="61c11-129">Initialisieren Sie das Abonnement.</span><span class="sxs-lookup"><span data-stu-id="61c11-129">Initialize the subscription.</span></span> <span data-ttu-id="61c11-130">Weitere Informationen finden Sie unter [Create and Apply the Initial Snapshot](../create-and-apply-the-initial-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="61c11-130">For more information, see [Create and Apply the Initial Snapshot](../create-and-apply-the-initial-snapshot.md).</span></span>  
  
8.  <span data-ttu-id="61c11-131">Führen Sie auf dem Abonnenten [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql) aus, indem Sie für ALGORITHM, KEY_SOURCE und IDENTITY_VALUE die gleichen Werte wie in Schritt 1 verwenden.</span><span class="sxs-lookup"><span data-stu-id="61c11-131">At the Subscriber, execute [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql) using the same values for ALGORITHM, KEY_SOURCE, and IDENTITY_VALUE as in step 1.</span></span> <span data-ttu-id="61c11-132">Für ENCRYPTION BY können Sie einen anderen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="61c11-132">You can specify a different value for ENCRYPTION BY.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="61c11-133">Der Wert von KEY_SOURCE stellt wichtige Daten dar, die verwendet werden können, um den symmetrischen Schlüssel neu zu erstellen und Daten zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="61c11-133">The value of KEY_SOURCE is valuable data that can be used to re-create the symmetric key and decrypt data.</span></span> <span data-ttu-id="61c11-134">KEY_SOURCE muss immer sicher gespeichert und transportiert werden.</span><span class="sxs-lookup"><span data-stu-id="61c11-134">KEY_SOURCE must always be stored and transported securely.</span></span>  
  
9. <span data-ttu-id="61c11-135">Führen Sie [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) aus, um den neuen Schlüssel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="61c11-135">Execute [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) to open the new key.</span></span>  
  
10. <span data-ttu-id="61c11-136">Verwenden Sie die [DecryptByKey](/sql/t-sql/functions/decryptbykey-transact-sql) -Funktion, um replizierte Daten auf dem Verleger zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="61c11-136">Use the [DecryptByKey](/sql/t-sql/functions/decryptbykey-transact-sql) function to decrypt replicated data at the Subscriber.</span></span>  
  
11. <span data-ttu-id="61c11-137">Führen Sie [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) aus, um den Schlüssel zu schließen.</span><span class="sxs-lookup"><span data-stu-id="61c11-137">Execute [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) to close the key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61c11-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="61c11-138">Example</span></span>  
 <span data-ttu-id="61c11-139">In diesem Beispiel werden ein symmetrischer Schlüssel, ein Zertifikat zum Sichern des symmetrischen Schlüssels und ein Hauptschlüssel erstellt.</span><span class="sxs-lookup"><span data-stu-id="61c11-139">This example creates a symmetric key, a certificate that is used to help secure the symmetric key, and a master key.</span></span> <span data-ttu-id="61c11-140">Diese Schlüssel werden in der Veröffentlichungsdatenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="61c11-140">These keys are created in the publication database.</span></span> <span data-ttu-id="61c11-141">Sie werden dann verwendet, um eine verschlüsselte Spalte (EncryptedCreditCardApprovalCode) in der `SalesOrderHeader` -Tabelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="61c11-141">They are then used to create an encrypted column (EncryptedCreditCardApprovalCode) in the `SalesOrderHeader` table.</span></span> <span data-ttu-id="61c11-142">Diese Spalte wird in der AdvWorksSalesOrdersMerge-Veröffentlichung anstelle der nicht verschlüsselten CreditCardApprovalCode-Spalte veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="61c11-142">This column is published in the AdvWorksSalesOrdersMerge publication instead of the unencrypted CreditCardApprovalCode column.</span></span> <span data-ttu-id="61c11-143">Benutzer sollten nach Möglichkeit dazu aufgefordert werden, Anmeldeinformationen zur Laufzeit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="61c11-143">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="61c11-144">Wenn Anmeldeinformationen in einer Skriptdatei gespeichert werden müssen, muss die Datei an einem sicheren Ort gespeichert werden, um unberechtigten Zugriff zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="61c11-144">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
 [!code-sql[HowTo#sp_PublishEncryptedColumn](../../../snippets/tsql/SQL15/replication/howto/tsql/publishencryptedcolumn.sql#sp_publishencryptedcolumn)]  
  
 [!code-sql[HowTo#sp_AddMergeArticle](../../../snippets/tsql/SQL15/replication/howto/tsql/createmergepub.sql#sp_addmergearticle)]  
  
## <a name="example"></a><span data-ttu-id="61c11-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="61c11-145">Example</span></span>  
 <span data-ttu-id="61c11-146">In diesem Beispiel wird derselbe symmetrische Schlüssel in der Abonnementdatenbank mithilfe derselben Werte für ALGORITHM, KEY_SOURCE und IDENTITY_VALUE aus dem ersten Beispiel neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="61c11-146">This example recreates the same symmetric key in the subscription database using the same values for ALGORITHM, KEY_SOURCE, and IDENTITY_VALUE from the first example.</span></span> <span data-ttu-id="61c11-147">Bei diesem Beispiel wird davon ausgegangen, dass Sie bereits ein Abonnement der AdvWorksSalesOrdersMerge-Veröffentlichung initialisiert haben, um die verschlüsselte Spalte zu replizieren.</span><span class="sxs-lookup"><span data-stu-id="61c11-147">This example assumes that you have already initialized a subscription to the AdvWorksSalesOrdersMerge publication to replicate the encrypted column.</span></span> <span data-ttu-id="61c11-148">Benutzer sollten nach Möglichkeit dazu aufgefordert werden, Anmeldeinformationen zur Laufzeit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="61c11-148">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="61c11-149">Wenn Anmeldeinformationen in einer Skriptdatei gespeichert werden müssen, muss die Datei während des Speicherns und des Transports gesichert werden, um unberechtigten Zugriff zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="61c11-149">If you must store credentials in a script file, you must secure the file during storage and transport to prevent unauthorized access.</span></span>  
  
 [!code-sql[HowTo#sp_SubscriberEncryptedColumn](../../../snippets/tsql/SQL15/replication/howto/tsql/subscriberencryptedcolumn.sql#sp_subscriberencryptedcolumn)]  
  
## <a name="see-also"></a><span data-ttu-id="61c11-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61c11-150">See Also</span></span>  
 <span data-ttu-id="61c11-151">[SQL Server-Replikation Sicherheit](view-and-modify-replication-security-settings.md) </span><span class="sxs-lookup"><span data-stu-id="61c11-151">[SQL Server Replication Security](view-and-modify-replication-security-settings.md) </span></span>  
 [<span data-ttu-id="61c11-152">Erstellen identischer symmetrischer Schlüssel auf zwei Servern</span><span class="sxs-lookup"><span data-stu-id="61c11-152">Create Identical Symmetric Keys on Two Servers</span></span>](../../security/encryption/create-identical-symmetric-keys-on-two-servers.md)  
  
  
