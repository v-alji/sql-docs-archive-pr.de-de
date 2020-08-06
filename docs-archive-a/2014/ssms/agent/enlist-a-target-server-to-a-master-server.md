---
title: Eintragen eines Zielservers bei einem Masterserver | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- enlisting target servers [SQL Server]
- SQL Server Agent jobs, target servers
- master servers [SQL Server], enlisting target servers
- SQL Server Agent jobs, master servers
- target servers [SQL Server], enlisting
ms.assetid: 7633adb5-d140-4e58-a8f2-5b4b50c2f95b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 256f1a78d298d89a36412ee5689695f3ab3fde8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608219"
---
# <a name="enlist-a-target-server-to-a-master-server"></a><span data-ttu-id="cce8d-102">Eintragen eines Zielservers bei einem Masterserver</span><span class="sxs-lookup"><span data-stu-id="cce8d-102">Enlist a Target Server to a Master Server</span></span>
  <span data-ttu-id="cce8d-103">In diesem Thema wird die Vorgehensweise zum Hinzufügen eines Zielservers zu einer Multiserververwaltungskonfiguration beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cce8d-103">This topic describes how to add target servers to a multiserver administration configuration.</span></span> <span data-ttu-id="cce8d-104">Führen Sie die folgenden Schritte auf dem Masterserver aus.</span><span class="sxs-lookup"><span data-stu-id="cce8d-104">Run this procedure from the master server.</span></span> <span data-ttu-id="cce8d-105">Die Schritte können in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]oder SQL Server Management Objects (SMO) ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cce8d-105">in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="cce8d-106">Informationen zu den Auswirkungen des für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst verwendeten Windows-Kontos auf eine Multiserverumgebung finden Sie unter [Erstellen einer Multiserverumgebung](create-a-multiserver-environment.md).</span><span class="sxs-lookup"><span data-stu-id="cce8d-106">For information about how the Windows account used for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service affects a multiserver environment, see [Create a Multiserver Environment](create-a-multiserver-environment.md).</span></span>  
  
 <span data-ttu-id="cce8d-107">Die vollständige SSL-Verschlüsselung (Secure Sockets Layer) und die Zertifikatüberprüfung sind für Verbindungen zwischen Masterservern und Zielservern standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="cce8d-107">Full Secure Sockets Layer (SSL) encryption and certificate validation is enabled for connections between master servers and target servers by default.</span></span> <span data-ttu-id="cce8d-108">Weitere Informationen finden Sie unter [Festlegen von Verschlüsselungsoptionen auf Zielservern](set-encryption-options-on-target-servers.md).</span><span class="sxs-lookup"><span data-stu-id="cce8d-108">For more information, see [Set Encryption Options on Target Servers](set-encryption-options-on-target-servers.md).</span></span>  
  
 <span data-ttu-id="cce8d-109">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="cce8d-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cce8d-110">**Eintragen eines Zielservers mit:**</span><span class="sxs-lookup"><span data-stu-id="cce8d-110">**To enlist a target server, using:**</span></span>  
  
     [<span data-ttu-id="cce8d-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cce8d-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="cce8d-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cce8d-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="cce8d-113">SMO</span><span class="sxs-lookup"><span data-stu-id="cce8d-113">SMO</span></span>](#PowerShellProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cce8d-114">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cce8d-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enlist-a-target-server"></a><span data-ttu-id="cce8d-115">So tragen Sie einen Zielserver ein</span><span class="sxs-lookup"><span data-stu-id="cce8d-115">To enlist a target server</span></span>  
  
1.  <span data-ttu-id="cce8d-116">Erweitern Sie im **Objekt-Explorer**einen Server, der als Masterserver konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="cce8d-116">In **Object Explorer**, expand a server that is configured as a master server.</span></span>  
  
2.  <span data-ttu-id="cce8d-117">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent**, zeigen Sie auf **Multiserveradministration**, und klicken Sie dann auf **Zielserver hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="cce8d-117">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Add Target Servers**.</span></span>  
  
3.  <span data-ttu-id="cce8d-118">Schließen Sie den Zielservererstellungs-Assistenten ab, in dem Sie durch den Prozess geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="cce8d-118">Complete the Target Server Wizard, which guides you through the process.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cce8d-119">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cce8d-119">Using Transact-SQL</span></span>  
  
#### <a name="to-enlist-a-target-server"></a><span data-ttu-id="cce8d-120">So tragen Sie einen Zielserver ein</span><span class="sxs-lookup"><span data-stu-id="cce8d-120">To enlist a target server</span></span>  
  
1.  <span data-ttu-id="cce8d-121">Verwenden Sie die gespeicherte Prozedur `sp_msx_enlist`.</span><span class="sxs-lookup"><span data-stu-id="cce8d-121">Use the `sp_msx_enlist` stored procedure.</span></span>  <span data-ttu-id="cce8d-122">Weitere Informationen finden Sie unter [sp_msx_enlist &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="cce8d-122">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql)</span></span>  
  
##  <a name="using-sql-server-management-objects-smo"></a><a name="PowerShellProcedure"></a><span data-ttu-id="cce8d-123">Verwenden von SQL Server Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="cce8d-123">Using SQL Server Management Objects (SMO)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cce8d-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cce8d-124">See Also</span></span>  
 [<span data-ttu-id="cce8d-125">Automatisierte Verwaltung in einem Unternehmen</span><span class="sxs-lookup"><span data-stu-id="cce8d-125">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
  
  
