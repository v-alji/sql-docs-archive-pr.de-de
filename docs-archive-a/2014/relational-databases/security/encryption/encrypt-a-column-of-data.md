---
title: Verschlüsseln einer Datenspalte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], columns
- cryptography [SQL Server], columns
ms.assetid: 38e9bf58-10c6-46ed-83cb-e2d76cda0adc
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 00f8b06296b3407ac070cd40378f3ff1039a0b93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725385"
---
# <a name="encrypt-a-column-of-data"></a><span data-ttu-id="175bf-102">Verschlüsseln einer Datenspalte</span><span class="sxs-lookup"><span data-stu-id="175bf-102">Encrypt a Column of Data</span></span>
  <span data-ttu-id="175bf-103">In diesem Thema wird beschrieben, wie Sie eine Datenspalte mithilfe der symmetrischen Verschlüsselung in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[tsql](../../../includes/tsql-md.md)]verschlüsseln können.</span><span class="sxs-lookup"><span data-stu-id="175bf-103">This topic describes how to encrypt a column of data by using symmetric encryption in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="175bf-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="175bf-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="175bf-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="175bf-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="175bf-106">Security</span><span class="sxs-lookup"><span data-stu-id="175bf-106">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="175bf-107">So verschlüsseln Sie eine Datenspalte mithilfe von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="175bf-107">To encrypt a column of data, using Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="175bf-108">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="175bf-108">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="175bf-109">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="175bf-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="175bf-110">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="175bf-110">Permissions</span></span>  
 <span data-ttu-id="175bf-111">Die folgenden Berechtigungen sind notwendig, um die Schritte unten auszuführen:</span><span class="sxs-lookup"><span data-stu-id="175bf-111">The following permissions are necessary to perform the steps below:</span></span>  
  
-   <span data-ttu-id="175bf-112">CONTROL-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="175bf-112">CONTROL permission on the database.</span></span>  
  
-   <span data-ttu-id="175bf-113">CREATE CERTIFICATE-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="175bf-113">CREATE CERTIFICATE permission on the database.</span></span> <span data-ttu-id="175bf-114">Nur Windows-Anmeldenamen, SQL Server-Anmeldenamen und Anwendungsrollen können eigene Zertifikate besitzen.</span><span class="sxs-lookup"><span data-stu-id="175bf-114">Only Windows logins, SQL Server logins, and application roles can own certificates.</span></span> <span data-ttu-id="175bf-115">Gruppen und Rollen können keine Zertifikate besitzen.</span><span class="sxs-lookup"><span data-stu-id="175bf-115">Groups and roles cannot own certificates.</span></span>  
  
-   <span data-ttu-id="175bf-116">ALTER-Berechtigung für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="175bf-116">ALTER permission on the table.</span></span>  
  
-   <span data-ttu-id="175bf-117">Einige Berechtigungen für den Schlüssel und die VIEW DEFINITION-Berechtigung dürfen nicht verweigert worden sein.</span><span class="sxs-lookup"><span data-stu-id="175bf-117">Some permission on the key and must not have been denied VIEW DEFINITION permission.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="175bf-118">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="175bf-118">Using Transact-SQL</span></span>  
  
#### <a name="to-encrypt-a-column-of-data-using-a-simple-symmetric-encryption"></a><span data-ttu-id="175bf-119">So verschlüsseln Sie eine Datenspalte mithilfe einer einfachen symmetrischen Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="175bf-119">To encrypt a column of data using a simple symmetric encryption</span></span>  
  
1.  <span data-ttu-id="175bf-120">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="175bf-120">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="175bf-121">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="175bf-121">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="175bf-122">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="175bf-122">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    --If there is no master key, create one now.   
    IF NOT EXISTS   
        (SELECT * FROM sys.symmetric_keys WHERE symmetric_key_id = 101)  
        CREATE MASTER KEY ENCRYPTION BY   
        PASSWORD = '23987hxJKL95QYV4369#ghf0%lekjg5k3fd117r$$#1946kcj$n44ncjhdlj'  
    GO  
  
    CREATE CERTIFICATE Sales09  
       WITH SUBJECT = 'Customer Credit Card Numbers';  
    GO  
  
    CREATE SYMMETRIC KEY CreditCards_Key11  
        WITH ALGORITHM = AES_256  
        ENCRYPTION BY CERTIFICATE Sales09;  
    GO  
  
    -- Create a column in which to store the encrypted data.  
    ALTER TABLE Sales.CreditCard   
        ADD CardNumber_Encrypted varbinary(128);   
    GO  
  
    -- Open the symmetric key with which to encrypt the data.  
    OPEN SYMMETRIC KEY CreditCards_Key11  
       DECRYPTION BY CERTIFICATE Sales09;  
  
    -- Encrypt the value in column CardNumber using the  
    -- symmetric key CreditCards_Key11.  
    -- Save the result in column CardNumber_Encrypted.    
    UPDATE Sales.CreditCard  
    SET CardNumber_Encrypted = EncryptByKey(Key_GUID('CreditCards_Key11')  
        , CardNumber, 1, HashBytes('SHA1', CONVERT( varbinary  
        , CreditCardID)));  
    GO  
  
    -- Verify the encryption.  
    -- First, open the symmetric key with which to decrypt the data.  
  
    OPEN SYMMETRIC KEY CreditCards_Key11  
       DECRYPTION BY CERTIFICATE Sales09;  
    GO  
  
    -- Now list the original card number, the encrypted card number,  
    -- and the decrypted ciphertext. If the decryption worked,  
    -- the original number will match the decrypted number.  
  
    SELECT CardNumber, CardNumber_Encrypted   
        AS 'Encrypted card number', CONVERT(nvarchar,  
        DecryptByKey(CardNumber_Encrypted, 1 ,   
        HashBytes('SHA1', CONVERT(varbinary, CreditCardID))))  
        AS 'Decrypted card number' FROM Sales.CreditCard;  
    GO  
    ```  
  
#### <a name="to-encrypt-a-column-of-data-using-symmetric-encryption-that-includes-an-authenticator"></a><span data-ttu-id="175bf-123">So verschlüsseln Sie Datenspalten mithilfe der symmetrischen Verschlüsselung unter Einbeziehung eines Authentifikators</span><span class="sxs-lookup"><span data-stu-id="175bf-123">To encrypt a column of data using symmetric encryption that includes an authenticator</span></span>  
  
1.  <span data-ttu-id="175bf-124">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="175bf-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="175bf-125">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="175bf-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="175bf-126">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="175bf-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
  
    --If there is no master key, create one now.   
    IF NOT EXISTS   
        (SELECT * FROM sys.symmetric_keys WHERE symmetric_key_id = 101)  
        CREATE MASTER KEY ENCRYPTION BY   
        PASSWORD = '23987hxJKL969#ghf0%94467GRkjg5k3fd117r$$#1946kcj$n44nhdlj'  
    GO  
  
    CREATE CERTIFICATE HumanResources037  
       WITH SUBJECT = 'Employee Social Security Numbers';  
    GO  
  
    CREATE SYMMETRIC KEY SSN_Key_01  
        WITH ALGORITHM = AES_256  
        ENCRYPTION BY CERTIFICATE HumanResources037;  
    GO  
  
    USE [AdventureWorks2012];  
    GO  
  
    -- Create a column in which to store the encrypted data.  
    ALTER TABLE HumanResources.Employee  
        ADD EncryptedNationalIDNumber varbinary(128);   
    GO  
  
    -- Open the symmetric key with which to encrypt the data.  
    OPEN SYMMETRIC KEY SSN_Key_01  
       DECRYPTION BY CERTIFICATE HumanResources037;  
  
    -- Encrypt the value in column NationalIDNumber with symmetric   
    -- key SSN_Key_01. Save the result in column EncryptedNationalIDNumber.  
    UPDATE HumanResources.Employee  
    SET EncryptedNationalIDNumber = EncryptByKey(Key_GUID('SSN_Key_01'), NationalIDNumber);  
    GO  
  
    -- Verify the encryption.  
    -- First, open the symmetric key with which to decrypt the data.  
    OPEN SYMMETRIC KEY SSN_Key_01  
       DECRYPTION BY CERTIFICATE HumanResources037;  
    GO  
  
    -- Now list the original ID, the encrypted ID, and the   
    -- decrypted ciphertext. If the decryption worked, the original  
    -- and the decrypted ID will match.  
    SELECT NationalIDNumber, EncryptedNationalIDNumber   
        AS 'Encrypted ID Number',  
        CONVERT(nvarchar, DecryptByKey(EncryptedNationalIDNumber))   
        AS 'Decrypted ID Number'  
        FROM HumanResources.Employee;  
    GO  
    ```  
  
 <span data-ttu-id="175bf-127">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="175bf-127">For more information, see the following:</span></span>  
  
-   [<span data-ttu-id="175bf-128">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="175bf-128">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)  
  
-   [<span data-ttu-id="175bf-129">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="175bf-129">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-symmetric-key-transact-sql)  
  
-   [<span data-ttu-id="175bf-130">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="175bf-130">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
-   [<span data-ttu-id="175bf-131">OPEN SYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="175bf-131">OPEN SYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/open-symmetric-key-transact-sql)  
  
  
