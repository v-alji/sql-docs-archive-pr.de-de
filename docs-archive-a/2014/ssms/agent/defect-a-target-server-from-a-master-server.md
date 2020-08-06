---
title: Vollziehen des Austritts eines Zielservers aus einem Masterserver | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- target servers [SQL Server], defecting
- SQL Server Agent jobs, master servers
- master servers [SQL Server], defecting target servers
- defecting target servers
ms.assetid: a6da262b-7b38-4ce4-bfd6-6a557c6e8a84
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2b17703fa87f5c0d3e7146a1660ac1ca7c7c1d81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699237"
---
# <a name="defect-a-target-server-from-a-master-server"></a><span data-ttu-id="c8772-102">Vollziehen des Austritts eines Zielservers aus einem Masterserver</span><span class="sxs-lookup"><span data-stu-id="c8772-102">Defect a Target Server from a Master Server</span></span>
  <span data-ttu-id="c8772-103">In diesem Thema wird beschrieben, wie Sie den Austritt eines Zielservers aus einem Masterserver in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] oder SQL Server Management Objects (SMO) vollziehen.</span><span class="sxs-lookup"><span data-stu-id="c8772-103">This topic describes how to defect a target server from a master server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="c8772-104">Führen Sie die folgenden Schritte auf dem Zielserver aus.</span><span class="sxs-lookup"><span data-stu-id="c8772-104">Run this procedure from the target server.</span></span>  
  
 <span data-ttu-id="c8772-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="c8772-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c8772-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="c8772-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c8772-107">Security</span><span class="sxs-lookup"><span data-stu-id="c8772-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c8772-108">**Vollziehen des Austritts eines Zielservers mit:**</span><span class="sxs-lookup"><span data-stu-id="c8772-108">**To defect a target server, using:**</span></span>  
  
     [<span data-ttu-id="c8772-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c8772-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c8772-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c8772-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="c8772-111">SMO</span><span class="sxs-lookup"><span data-stu-id="c8772-111">SMO</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c8772-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="c8772-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c8772-113">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c8772-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c8772-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c8772-114">Permissions</span></span>  
 <span data-ttu-id="c8772-115">Zum Ausführen dieser gespeicherten Prozedur muss ein Benutzer Mitglied der festen Serverrolle `sysadmin` sein.</span><span class="sxs-lookup"><span data-stu-id="c8772-115">To execute this stored procedure, a user must be a member of the `sysadmin` fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c8772-116">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c8772-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-defect-a-target-server-from-a-master-server"></a><span data-ttu-id="c8772-117">So tragen Sie bei einem Masterserver einen Zielserver aus</span><span class="sxs-lookup"><span data-stu-id="c8772-117">To defect a target server from a master server</span></span>  
  
1.  <span data-ttu-id="c8772-118">Erweitern Sie in **Objekt-Explorer**einen Server, der als Zielserver konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="c8772-118">In **Object Explorer**, expand a server that is configured as a target server.</span></span>  
  
2.  <span data-ttu-id="c8772-119">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent**, zeigen Sie auf **Multiserveradministration**, und klicken Sie dann auf **Austragen**.</span><span class="sxs-lookup"><span data-stu-id="c8772-119">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Defect**.</span></span>  
  
3.  <span data-ttu-id="c8772-120">Klicken Sie auf **Ja** , um zu bestätigen, dass Sie diesen Zielserver bei einem Masterserver austragen möchten.</span><span class="sxs-lookup"><span data-stu-id="c8772-120">Click **Yes** to confirm that you want to defect this target server from a master server.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c8772-121">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c8772-121">Using Transact-SQL</span></span>  
  
#### <a name="to-defect-a-target-server-from-a-master-server"></a><span data-ttu-id="c8772-122">So tragen Sie bei einem Masterserver einen Zielserver aus</span><span class="sxs-lookup"><span data-stu-id="c8772-122">To defect a target server from a master server</span></span>  
  
1.  <span data-ttu-id="c8772-123">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="c8772-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c8772-124">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="c8772-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c8772-125">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c8772-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
```sql
sp_msx_defect ;  
```  
  
 <span data-ttu-id="c8772-126">Weitere Informationen finden Sie unter [sp_msx_defect &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-defect-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c8772-126">For more information, see [sp_msx_defect &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-defect-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects-smo"></a><a name="PowerShellProcedure"></a><span data-ttu-id="c8772-127">Verwenden von SQL Server Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="c8772-127">Using SQL Server Management Objects (SMO)</span></span>  
 <span data-ttu-id="c8772-128">Verwenden Sie `MsxDefect Method`.</span><span class="sxs-lookup"><span data-stu-id="c8772-128">Use the `MsxDefect Method`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8772-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8772-129">See Also</span></span>  
 <span data-ttu-id="c8772-130">[Erstellen einer Multiserverumgebung](create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="c8772-130">[Create a Multiserver Environment](create-a-multiserver-environment.md) </span></span>  
 <span data-ttu-id="c8772-131">[Automatisierte Verwaltung in einem Unternehmen](automated-administration-across-an-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="c8772-131">[Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md) </span></span>  
 [<span data-ttu-id="c8772-132">Vollziehen des Austritts mehrerer Zielserver aus einem Masterserver</span><span class="sxs-lookup"><span data-stu-id="c8772-132">Defect Multiple Target Servers from a Master Server</span></span>](defect-multiple-target-servers-from-a-master-server.md)  
