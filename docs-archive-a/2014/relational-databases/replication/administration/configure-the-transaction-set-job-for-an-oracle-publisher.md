---
title: Konfigurieren des Transaktions Satz-Auftrags für einen Oracle-Verleger (Replikations Programmierung mit Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- sp_publisherproperty
- Oracle publishing [SQL Server replication], configuring
ms.assetid: beea1a5c-0053-4971-a68f-0da53063fcbb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 43a25ce755a505f0efd7c25243b8969a962ea701
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725570"
---
# <a name="configure-the-transaction-set-job-for-an-oracle-publisher-replication-transact-sql-programming"></a><span data-ttu-id="8a46f-102">Konfigurieren des Transaktionssatz-Auftrags für einen Oracle-Verleger (Replikationsprogrammierung mit Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8a46f-102">Configure the Transaction Set Job for an Oracle Publisher (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="8a46f-103">Der **Xactset** -Auftrag ist ein Oracle-Datenbankauftrag, der bei der Replikation erstellt und auf einem Oracle-Verleger ausgeführt wird, um Transaktionssätze zu erstellen, wenn der Protokolllese-Agent nicht mit dem Verleger verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="8a46f-103">The **Xactset** job is an Oracle database job created by replication that runs at an Oracle Publisher to create transaction sets when the Log Reader Agent is not connected to the Publisher.</span></span> <span data-ttu-id="8a46f-104">Sie können diesen Auftrag auf dem Verteiler programmgesteuert mithilfe gespeicherter Replikationsprozeduren aktivieren und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8a46f-104">You can enable and configure this job from the Distributor programmatically using replication stored procedures.</span></span> <span data-ttu-id="8a46f-105">Weitere Informationen finden Sie unter [Leistungsoptimierung für Oracle-Verleger](../non-sql/performance-tuning-for-oracle-publishers.md).</span><span class="sxs-lookup"><span data-stu-id="8a46f-105">For more information, see [Performance Tuning for Oracle Publishers](../non-sql/performance-tuning-for-oracle-publishers.md).</span></span>  
  
### <a name="to-enable-the-transaction-set-job"></a><span data-ttu-id="8a46f-106">So aktivieren Sie den Transaktionssatz-Auftrag</span><span class="sxs-lookup"><span data-stu-id="8a46f-106">To enable the transaction set job</span></span>  
  
1.  <span data-ttu-id="8a46f-107">Legen Sie auf dem Oracle-Verleger den **job_queue_processes** -Initialisierungsparameter auf einen Wert fest, der die Ausführung des Xactset-Auftrags zulässt.</span><span class="sxs-lookup"><span data-stu-id="8a46f-107">At the Oracle Publisher, set the **job_queue_processes** initialization parameter to a sufficient value to allow the Xactset job run.</span></span> <span data-ttu-id="8a46f-108">Weitere Informationen zu diesem Parameter finden Sie in der Datenbankdokumentation für den Oracle-Verleger.</span><span class="sxs-lookup"><span data-stu-id="8a46f-108">For more information about this parameter, see the database documentation for the Oracle Publisher.</span></span>  
  
2.  <span data-ttu-id="8a46f-109">Führen Sie auf dem Verteiler [Sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql) aus.</span><span class="sxs-lookup"><span data-stu-id="8a46f-109">At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="8a46f-110">Geben Sie den Namen des Oracle-Verlegers für \*\* \@ Publisher**, den Wert `xactsetbatching` für \*\* \@ propertyName**und den Wert `enabled` für \*\* \@ PropertyValue\*\*an.</span><span class="sxs-lookup"><span data-stu-id="8a46f-110">Specify the name of the Oracle Publisher for **\@publisher**, a value of `xactsetbatching` for **\@propertyname**, and a value of `enabled` for **\@propertyvalue**.</span></span>  
  
3.  <span data-ttu-id="8a46f-111">Führen Sie auf dem Verteiler [Sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql) aus.</span><span class="sxs-lookup"><span data-stu-id="8a46f-111">At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="8a46f-112">Geben Sie den Namen des Oracle-Verlegers für den \*\* \@ Verleger**, den Wert `xactsetjobinterval` für \*\* \@ propertyName**und das Auftrags Intervall in Minuten für \*\* \@ PropertyValue\*\*an.</span><span class="sxs-lookup"><span data-stu-id="8a46f-112">Specify the name of the Oracle Publisher for **\@publisher**, a value of `xactsetjobinterval` for **\@propertyname**, and the job interval, in minutes, for **\@propertyvalue**.</span></span>  
  
4.  <span data-ttu-id="8a46f-113">Führen Sie auf dem Verteiler [Sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql) aus.</span><span class="sxs-lookup"><span data-stu-id="8a46f-113">At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="8a46f-114">Geben Sie den Namen des Oracle-Verlegers für \*\* \@ Publisher**, den Wert `xactsetjob` für \*\* \@ propertyName**und den Wert `enabled` für \*\* \@ PropertyValue\*\*an.</span><span class="sxs-lookup"><span data-stu-id="8a46f-114">Specify the name of the Oracle Publisher for **\@publisher**, a value of `xactsetjob` for **\@propertyname**, and a value of `enabled` for **\@propertyvalue**.</span></span>  
  
### <a name="to-configure-the-transaction-set-job"></a><span data-ttu-id="8a46f-115">So konfigurieren Sie den Transaktionssatz-Auftrag</span><span class="sxs-lookup"><span data-stu-id="8a46f-115">To configure the transaction set job</span></span>  
  
1.  <span data-ttu-id="8a46f-116">(Optional) Führen Sie auf dem Verteiler [Sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql) aus.</span><span class="sxs-lookup"><span data-stu-id="8a46f-116">(Optional) At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="8a46f-117">Geben Sie für **\@publisher** den Namen des Oracle-Verlegers an.</span><span class="sxs-lookup"><span data-stu-id="8a46f-117">Specify the name of the Oracle Publisher for **\@publisher**.</span></span> <span data-ttu-id="8a46f-118">Dadurch werden die Eigenschaften des **Xactset** -Auftrags auf dem Verleger zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8a46f-118">This returns properties of the **Xactset** job at the Publisher.</span></span>  
  
2.  <span data-ttu-id="8a46f-119">Führen Sie auf dem Verteiler [Sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql) aus.</span><span class="sxs-lookup"><span data-stu-id="8a46f-119">At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="8a46f-120">Geben Sie den Namen des Oracle-Verlegers für \*\* \@ Publisher**, den Namen der Xactset-Auftrags Eigenschaft, die für \*\* \@ propertyName**festgelegt wird, und eine neue Einstellung für \*\* \@ PropertyValue\*\*an.</span><span class="sxs-lookup"><span data-stu-id="8a46f-120">Specify the name of the Oracle Publisher for **\@publisher**, the name of the Xactset job property being set for **\@propertyname**, and new setting for **\@propertyvalue**.</span></span>  
  
3.  <span data-ttu-id="8a46f-121">(Optional) Wiederholen Sie Schritt 2 für jede festgelegte Xactset-Auftragseigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8a46f-121">(Optional) Repeat step 2 for each Xactset job property being set.</span></span> <span data-ttu-id="8a46f-122">Wenn Sie die- `xactsetjobinterval` Eigenschaft ändern, müssen Sie den Auftrag auf dem Oracle-Verleger neu starten, damit das neue Intervall wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="8a46f-122">When changing the `xactsetjobinterval` property, you must restart the job on the Oracle Publisher for the new interval to take effect.</span></span>  
  
### <a name="to-view-properties-of-the-transaction-set-job"></a><span data-ttu-id="8a46f-123">So zeigen Sie die Eigenschaften des Transaktionssatz-Auftrags an</span><span class="sxs-lookup"><span data-stu-id="8a46f-123">To view properties of the transaction set job</span></span>  
  
1.  <span data-ttu-id="8a46f-124">Führen Sie auf dem Verteiler [sp_helpxactsetjob](/sql/relational-databases/system-stored-procedures/sp-helpxactsetjob-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="8a46f-124">At the Distributor, execute [sp_helpxactsetjob](/sql/relational-databases/system-stored-procedures/sp-helpxactsetjob-transact-sql).</span></span> <span data-ttu-id="8a46f-125">Geben Sie für **\@publisher** den Namen des Oracle-Verlegers an.</span><span class="sxs-lookup"><span data-stu-id="8a46f-125">Specify the name of the Oracle Publisher for **\@publisher**.</span></span>  
  
### <a name="to-disable-the-transaction-set-job"></a><span data-ttu-id="8a46f-126">So deaktivieren Sie den Transaktionssatz-Auftrag</span><span class="sxs-lookup"><span data-stu-id="8a46f-126">To disable the transaction set job</span></span>  
  
1.  <span data-ttu-id="8a46f-127">Führen Sie auf dem Verteiler [Sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql) aus.</span><span class="sxs-lookup"><span data-stu-id="8a46f-127">At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="8a46f-128">Geben Sie den Namen des Oracle-Verlegers für \*\* \@ Publisher**, den Wert `xactsetjob` für \*\* \@ propertyName**und den Wert `disabled` für \*\* \@ PropertyValue\*\*an.</span><span class="sxs-lookup"><span data-stu-id="8a46f-128">Specify the name of the Oracle Publisher for **\@publisher**, a value of `xactsetjob` for **\@propertyname**, and a value of `disabled` for **\@propertyvalue**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a46f-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8a46f-129">Example</span></span>  
 <span data-ttu-id="8a46f-130">Im folgenden Beispiel wird der `Xactset` -Auftrag aktiviert und ein Intervall von drei Minuten zwischen den Ausführungen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8a46f-130">The following example enables the `Xactset` job and sets an interval of three minutes between runs.</span></span>  
  
 [!code-sql[HowTo#sp_enable_xactsetjob](../../../snippets/tsql/SQL15/replication/howto/tsql/enablexactsetjob.sql#sp_enable_xactsetjob)]  
  
## <a name="see-also"></a><span data-ttu-id="8a46f-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8a46f-131">See Also</span></span>  
 <span data-ttu-id="8a46f-132">[Leistungsoptimierung für Oracle-Verleger](../non-sql/performance-tuning-for-oracle-publishers.md) </span><span class="sxs-lookup"><span data-stu-id="8a46f-132">[Performance Tuning for Oracle Publishers](../non-sql/performance-tuning-for-oracle-publishers.md) </span></span>  
 [<span data-ttu-id="8a46f-133">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="8a46f-133">Replication System Stored Procedures Concepts</span></span>](../concepts/replication-system-stored-procedures-concepts.md)  
  
  
