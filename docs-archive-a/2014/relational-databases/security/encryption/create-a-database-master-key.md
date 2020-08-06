---
title: Erstellen eines Datenbank-Hauptschlüssels | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/12/2019
ms.prod: sql-server-2014
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- database master key [SQL Server], creating
ms.assetid: 8cb24263-e97d-4e4d-9429-6cf494a4d5eb
author: jaszymas
ms.author: jaszymas
ms.reviewer: carlrab
ms.openlocfilehash: cb8305d9d5a3c72e6dffafd231f21110a5abdd14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725397"
---
# <a name="create-a-database-master-key"></a><span data-ttu-id="b437b-102">Erstellen eines Datenbank-Hauptschlüssels</span><span class="sxs-lookup"><span data-stu-id="b437b-102">Create a Database Master Key</span></span>

<span data-ttu-id="b437b-103">In diesem Thema wird beschrieben, wie `master` Sie in mithilfe von einen Datenbank-Hauptschlüssel in der-Datenbank erstellen [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b437b-103">This topic describes how to create a database master key in the `master` database in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>

<span data-ttu-id="b437b-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="b437b-104">**In This Topic**</span></span>

- <span data-ttu-id="b437b-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="b437b-105">**Before you begin:**</span></span>

  [<span data-ttu-id="b437b-106">Security</span><span class="sxs-lookup"><span data-stu-id="b437b-106">Security</span></span>](#Security)

- [<span data-ttu-id="b437b-107">So erstellen Sie mithilfe von Transact-SQL einen Datenbank-Hauptschlüssel</span><span class="sxs-lookup"><span data-stu-id="b437b-107">To create a database master key using Transact-SQL</span></span>](#TsqlProcedure)

## <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b437b-108">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="b437b-108">Before You Begin</span></span>

### <a name="security"></a><a name="Security"></a> <span data-ttu-id="b437b-109">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b437b-109">Security</span></span>

#### <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b437b-110">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b437b-110">Permissions</span></span>

<span data-ttu-id="b437b-111">Erfordert die CONTROL-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="b437b-111">Requires CONTROL permission on the database.</span></span>

## <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b437b-112">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b437b-112">Using Transact-SQL</span></span>

### <a name="to-create-a-database-master-key"></a><span data-ttu-id="b437b-113">So erstellen Sie einen Datenbank-Hauptschlüssel</span><span class="sxs-lookup"><span data-stu-id="b437b-113">To create a database master key</span></span>

1. <span data-ttu-id="b437b-114">Wählen Sie ein Kennwort aus, mit dem die in der Datenbank gespeicherte Kopie des Datenbank-Hauptschlüssels verschlüsselt wird.</span><span class="sxs-lookup"><span data-stu-id="b437b-114">Choose a password for encrypting the copy of the master key that will be stored in the database.</span></span>
2. <span data-ttu-id="b437b-115">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="b437b-115">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>
3. <span data-ttu-id="b437b-116">Erweitern Sie **Systemdatenbanken**, klicken Sie mit der rechten Maustaste auf `master`, und klicken Sie anschließend auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="b437b-116">Expand **System Databases**, right-click `master` and then click **New Query**.</span></span>
4. <span data-ttu-id="b437b-117">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b437b-117">Copy and paste the following example into the query window and click **Execute**.</span></span>

  ```sql
  -- Creates the master key.
  -- The key is encrypted using the password "23987hxJ#KL95234nl0zBe."
  CREATE MASTER KEY ENCRYPTION BY PASSWORD = '23987hxJ#KL95234nl0zBe';
```

<span data-ttu-id="b437b-118">Weitere Informationen finden Sie unter [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b437b-118">For more information, see [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql).</span></span>
