---
title: Erstellen von Synonymen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
f1_keywords:
- sql12.swb.synonym.general.f1
helpviewer_keywords:
- creating synonyms
- synonyms [SQL Server], creating
ms.assetid: fedfa7a5-d0b6-4e2b-90f4-a08122958e33
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3dc18c9d0d6048c4190ba56725dd332f2dfb629e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607604"
---
# <a name="create-synonyms"></a><span data-ttu-id="18c01-102">Erstellen von Synonymen</span><span class="sxs-lookup"><span data-stu-id="18c01-102">Create Synonyms</span></span>
  <span data-ttu-id="18c01-103">In diesem Thema wird beschrieben, wie ein Synonym in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="18c01-103">This topic describes how to create a synonym in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="18c01-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="18c01-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="18c01-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="18c01-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="18c01-106">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="18c01-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="18c01-107">**So erstellen Sie ein Synonym mit:**</span><span class="sxs-lookup"><span data-stu-id="18c01-107">**To create a synonym, using:**</span></span>  
  
     [<span data-ttu-id="18c01-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="18c01-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="18c01-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="18c01-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="18c01-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="18c01-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="18c01-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="18c01-111">Security</span></span>  
 <span data-ttu-id="18c01-112">Zum Erstellen eines Synonyms in einem Schema muss ein Benutzer über die CREATE SYNONYM-Berechtigung verfügen und entweder der Besitzer des Schemas sein oder über die ALTER SCHEMA-Berechtigung verfügen.</span><span class="sxs-lookup"><span data-stu-id="18c01-112">To create a synonym in a given schema, a user must have CREATE SYNONYM permission and either own the schema or have ALTER SCHEMA permission.</span></span> <span data-ttu-id="18c01-113">Die CREATE SYNONYM-Berechtigung ist eine erteilbare Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="18c01-113">The CREATE SYNONYM permission is a grantable permission.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="18c01-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="18c01-114">Permissions</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="18c01-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="18c01-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-synonym"></a><span data-ttu-id="18c01-116">So erstellen Sie ein Synonym</span><span class="sxs-lookup"><span data-stu-id="18c01-116">To Create a Synonym</span></span>  
  
1.  <span data-ttu-id="18c01-117">Erweitern Sie im **Objekt-Explorer**die Datenbank, in der Sie die neue Sicht erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="18c01-117">In **Object Explorer**, expand the database where you want to create your new view.</span></span>  
  
2.  <span data-ttu-id="18c01-118">Klicken Sie mit der rechten Maustaste auf den Ordner **Synonyme**, und klicken Sie dann auf **Neues Synonym…** .</span><span class="sxs-lookup"><span data-stu-id="18c01-118">Right-click the **Synonyms** folder, then click **New Synonym...**.</span></span>  
  
3.  <span data-ttu-id="18c01-119">Geben Sie im Dialogfeld **Synonym hinzufügen** die folgenden Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="18c01-119">In the **Add Synonym** dialog box, enter the following information.</span></span>  
  
     <span data-ttu-id="18c01-120">**Synonymname**</span><span class="sxs-lookup"><span data-stu-id="18c01-120">**Synonym name**</span></span>  
     <span data-ttu-id="18c01-121">Geben Sie den neuen Namen ein, den Sie für dieses Objekt verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="18c01-121">Type the new name you will use for this object.</span></span>  
  
     <span data-ttu-id="18c01-122">**Synonymschema**</span><span class="sxs-lookup"><span data-stu-id="18c01-122">**Synonym schema**</span></span>  
     <span data-ttu-id="18c01-123">Geben Sie das Schema des neuen Namens ein, das Sie für dieses Objekt verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="18c01-123">Type the schema of the new name you will use for this object.</span></span>  
  
     <span data-ttu-id="18c01-124">**Servername**</span><span class="sxs-lookup"><span data-stu-id="18c01-124">**Server name**</span></span>  
     <span data-ttu-id="18c01-125">Geben Sie die Serverinstanz ein, zu der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="18c01-125">Type the server instance to connect to.</span></span>  
  
     <span data-ttu-id="18c01-126">**Datenbankname**</span><span class="sxs-lookup"><span data-stu-id="18c01-126">**Database name**</span></span>  
     <span data-ttu-id="18c01-127">Geben Sie die Datenbank ein, die das Objekt enthält, bzw. wählen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="18c01-127">Type or select the database containing the object.</span></span>  
  
     <span data-ttu-id="18c01-128">**Schema**</span><span class="sxs-lookup"><span data-stu-id="18c01-128">**Schema**</span></span>  
     <span data-ttu-id="18c01-129">Geben Sie das Schema ein, das das Objekt besitzt, bzw. wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="18c01-129">Type or select the schema that owns the object.</span></span>  
  
     <span data-ttu-id="18c01-130">**Objekttyp**</span><span class="sxs-lookup"><span data-stu-id="18c01-130">**Object type**</span></span>  
     <span data-ttu-id="18c01-131">Wählen Sie den Objekttyp aus.</span><span class="sxs-lookup"><span data-stu-id="18c01-131">Select the type of object.</span></span>  
  
     <span data-ttu-id="18c01-132">**Objektname**</span><span class="sxs-lookup"><span data-stu-id="18c01-132">**Object name**</span></span>  
     <span data-ttu-id="18c01-133">Geben Sie den Namen des Objekts ein, auf das das Synonym verweist.</span><span class="sxs-lookup"><span data-stu-id="18c01-133">Type the name of the object to which the synonym refers.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="18c01-134">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="18c01-134">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-synonym"></a><span data-ttu-id="18c01-135">So erstellen Sie ein Synonym</span><span class="sxs-lookup"><span data-stu-id="18c01-135">To Create a Synonym</span></span>  
  
1.  <span data-ttu-id="18c01-136">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="18c01-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="18c01-137">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="18c01-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="18c01-138">Kopieren Sie die folgenden Beispiele, fügen Sie sie in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="18c01-138">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="18c01-139">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="18c01-139">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="18c01-140">Im folgenden Beispiel wird ein Synonym für eine vorhandene Tabelle in der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="18c01-140">The following example creates a synonym for an existing table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="18c01-141">Das Synonym wird dann in nachfolgenden Beispielen verwendet.</span><span class="sxs-lookup"><span data-stu-id="18c01-141">The synonym is then used in subsequent examples.</span></span>  
  
```  
USE tempdb;  
GO  
CREATE SYNONYM MyAddressType  
FOR AdventureWorks2012.Person.AddressType;  
GO  
```  
  
 <span data-ttu-id="18c01-142">Das folgende Beispiel fügt eine Zeile in die Basistabelle ein, auf die vom `MyAddressType` -Synonym verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="18c01-142">The following example inserts a row into the base table that is referenced by the `MyAddressType` synonym.</span></span>  
  
```  
USE tempdb;  
GO  
INSERT INTO MyAddressType (Name)  
VALUES ('Test');  
GO  
```  
  
 <span data-ttu-id="18c01-143">Das folgende Beispiel veranschaulicht, wie in dynamischem SQL auf ein Synonym verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="18c01-143">The following example demonstrates how a synonym can be referenced in dynamic SQL.</span></span>  
  
```  
USE tempdb;  
GO  
EXECUTE ('SELECT Name FROM MyAddressType');  
GO  
```  
  
  
