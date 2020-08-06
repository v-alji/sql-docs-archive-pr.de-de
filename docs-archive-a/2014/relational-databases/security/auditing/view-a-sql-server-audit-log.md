---
title: Ein SQL Server-Überwachungsprotokoll anzeigen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- audits [SQL Server], viewing logs
- viewing audit logs
- logs [SQL Server], audit
ms.assetid: e8feaca0-7852-422b-895a-319b965d8d9b
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 8f9902a4fc92ef0b35bae62eb80170762c52fdec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609775"
---
# <a name="view-a-sql-server-audit-log"></a><span data-ttu-id="9cfca-102">Anzeigen eines SQL Server-Überwachungsprotokolls</span><span class="sxs-lookup"><span data-stu-id="9cfca-102">View a SQL Server Audit Log</span></span>
  <span data-ttu-id="9cfca-103">In diesem Thema wird beschrieben, wie Sie in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]ein SQL Server-Überwachungsprotokoll anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="9cfca-103">This topic describes how to view a SQL Server audit log in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="9cfca-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="9cfca-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9cfca-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="9cfca-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9cfca-106">Security</span><span class="sxs-lookup"><span data-stu-id="9cfca-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9cfca-107">**So zeigen Sie ein SQL Server-Überwachungsprotokoll an mit**</span><span class="sxs-lookup"><span data-stu-id="9cfca-107">**To view a SQL Server audit log, using:**</span></span>  
  
     [<span data-ttu-id="9cfca-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9cfca-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9cfca-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="9cfca-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9cfca-110">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="9cfca-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9cfca-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9cfca-111">Permissions</span></span>  
 <span data-ttu-id="9cfca-112">Erfordert die `CONTROL SERVER`-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="9cfca-112">Requires the `CONTROL SERVER` permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9cfca-113">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9cfca-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-a-sql-server-audit-log"></a><span data-ttu-id="9cfca-114">So zeigen Sie ein SQL Server-Überwachungsprotokoll an</span><span class="sxs-lookup"><span data-stu-id="9cfca-114">To view a SQL Server audit log</span></span>  
  
1.  <span data-ttu-id="9cfca-115">Erweitern Sie im Objekt-Explorer den Ordner **Sicherheit** .</span><span class="sxs-lookup"><span data-stu-id="9cfca-115">In Object Explorer, expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="9cfca-116">Erweitern Sie den Ordner **Überwachungen** .</span><span class="sxs-lookup"><span data-stu-id="9cfca-116">Expand the **Audits** folder.</span></span>  
  
3.  <span data-ttu-id="9cfca-117">Klicken Sie mit der rechten Maustaste auf das Überwachungsprotokoll, das Sie anzeigen möchten, und klicken Sie auf **Überwachungsprotokolle anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="9cfca-117">Right-click the audit log that you want to view and select **View Audit Logs**.</span></span> <span data-ttu-id="9cfca-118">Dadurch wird das Dialogfeld **Protokolldatei-Viewer-**_server_name_ geöffnet.</span><span class="sxs-lookup"><span data-stu-id="9cfca-118">This opens the **Log File Viewer -**_server_name_ dialog box.</span></span> <span data-ttu-id="9cfca-119">Weitere Informationen finden Sie unter [Log File Viewer F1 Help](../../logs/log-file-viewer-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="9cfca-119">For more information, see [Log File Viewer F1 Help](../../logs/log-file-viewer-f1-help.md).</span></span>  
  
4.  <span data-ttu-id="9cfca-120">Wenn Sie fertig sind, klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="9cfca-120">When finished, click **Close**.</span></span>  
  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="9cfca-121">empfiehlt, das Überwachungsprotokoll mit dem Protokolldatei-Viewer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9cfca-121">recommends viewing the audit log by using the Log File Viewer.</span></span> <span data-ttu-id="9cfca-122">Wenn Sie jedoch ein automatisiertes Überwachungssystem erstellen, können die Informationen in der Überwachungsdatei direkt mit der Funktion [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql) gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="9cfca-122">However, if you are creating an automated monitoring system, the information in the audit file can be read directly by using the [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql) function.</span></span> <span data-ttu-id="9cfca-123">Beim direkten Lesen der Datei werden die Daten in einem etwas anderen (unverarbeiteten) Format zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9cfca-123">Reading the file directly returns data in a slightly different (unprocessed) format.</span></span> <span data-ttu-id="9cfca-124">Weitere Informationen finden Sie unter **sys. fn_get_audit_file**</span><span class="sxs-lookup"><span data-stu-id="9cfca-124">See **sys.fn_get_audit_file** for more information</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cfca-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9cfca-125">See Also</span></span>  
 <span data-ttu-id="9cfca-126">[SQL Server Audit &#40;Datenbank-Engine&#41;](sql-server-audit-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="9cfca-126">[SQL Server Audit &#40;Database Engine&#41;](sql-server-audit-database-engine.md) </span></span>  
 [<span data-ttu-id="9cfca-127">Schreiben von SQL-Serverüberwachungsereignissen in das Sicherheitsprotokoll</span><span class="sxs-lookup"><span data-stu-id="9cfca-127">Write SQL Server Audit Events to the Security Log</span></span>](write-sql-server-audit-events-to-the-security-log.md)  
  
  
