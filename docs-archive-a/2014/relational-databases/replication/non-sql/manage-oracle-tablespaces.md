---
title: Verwalten von Oracle-Tabellenbereichen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Oracle publishing [SQL Server replication], managing tablespaces
- tablespaces [SQL Server replication]
ms.assetid: b8ea6c3b-01d6-4efc-bbfb-03b264530bbd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a3624aed38a7a5bf75e0c0807aa8d3657156264f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717923"
---
# <a name="manage-oracle-tablespaces"></a><span data-ttu-id="7d2ec-102">Verwalten von Oracle-Tabellenbereichen</span><span class="sxs-lookup"><span data-stu-id="7d2ec-102">Manage Oracle Tablespaces</span></span>
  <span data-ttu-id="7d2ec-103">Ein Tabellenbereich ist eine Einheit des Datenbankspeicherplatzes, die in etwa einer Dateigruppe in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] entspricht.</span><span class="sxs-lookup"><span data-stu-id="7d2ec-103">A tablespace is a unit of database storage that is roughly equivalent to a file group in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7d2ec-104">Tabellenbereiche ermöglichen das Speichern und Verwalten von Datenbankobjekten innerhalb einzelner Gruppen.</span><span class="sxs-lookup"><span data-stu-id="7d2ec-104">Tablespaces allow storage and management of database objects within individual groups.</span></span> <span data-ttu-id="7d2ec-105">Weitere Informationen finden Sie in der Oracle-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="7d2ec-105">For more information, see the Oracle documentation.</span></span>  
  
 <span data-ttu-id="7d2ec-106">Wenn Sie eine Tabelle als Teil einer Oracle-Veröffentlichung konfigurieren, können Sie optional einen vorhandenen Oracle-Tabellenbereich angeben, der beim Speichern der Replikations-Protokollinformationen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7d2ec-106">When you configure a table as part of an Oracle publication, you can optionally specify an existing Oracle tablespace to be used when storing replication logging information.</span></span> <span data-ttu-id="7d2ec-107">Wird kein spezifischer Tabellenbereich angegeben, wird für die Replikationsobjekte der Standardtabellenbereich verwendet, der mit dem Schema für den administrativen Replikationsbenutzer verknüpft ist, das beim Konfigurieren des Verlegers konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="7d2ec-107">If unspecified, the tablespace for the replication objects is the default tablespace associated with the replication administrative user schema that was configured when configuring the Publisher.</span></span>  
  
 <span data-ttu-id="7d2ec-108">**So geben Sie einen Tabellenbereich für eine Artikelprotokolltabelle an**:</span><span class="sxs-lookup"><span data-stu-id="7d2ec-108">**To specify a tablespace for an article logging table**:</span></span>  
  
-   <span data-ttu-id="7d2ec-109">Geben Sie im Dialogfeld **Artikeleigenschaften** einen Tabellenbereich an.</span><span class="sxs-lookup"><span data-stu-id="7d2ec-109">Specify a tablespace in the **Article Properties** dialog box.</span></span> <span data-ttu-id="7d2ec-110">Weitere Informationen zum Zugreifen auf dieses Dialogfeld finden Sie unter [View and Modify Publication Properties](../publish/view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="7d2ec-110">For more information about accessing this dialog box, see [View and Modify Publication Properties](../publish/view-and-modify-publication-properties.md).</span></span>  
  
-   <span data-ttu-id="7d2ec-111">Verwenden Sie [sp_changearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changearticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7d2ec-111">Use [sp_changearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changearticle-transact-sql).</span></span> <span data-ttu-id="7d2ec-112">Soll **sp_changearticle**verwendet werden, geben Sie Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="7d2ec-112">To use **sp_changearticle**, specify the following:</span></span>  
  
    -   <span data-ttu-id="7d2ec-113">Der Name des Oracle-Verlegers für den Parameter **@publisher** .</span><span class="sxs-lookup"><span data-stu-id="7d2ec-113">The name of the Oracle Publisher for the parameter **@publisher**.</span></span>  
  
    -   <span data-ttu-id="7d2ec-114">Der Name der Oracle-Veröffentlichung für den Parameter **@publication** .</span><span class="sxs-lookup"><span data-stu-id="7d2ec-114">The name of the Oracle publication for the parameter **@publication**.</span></span>  
  
    -   <span data-ttu-id="7d2ec-115">Der Name des Artikels für den Parameter **@article** .</span><span class="sxs-lookup"><span data-stu-id="7d2ec-115">The name of the article for the parameter **@article**.</span></span>  
  
    -   <span data-ttu-id="7d2ec-116">Der Wert ' Tablespace ' für den Parameter **@property** .</span><span class="sxs-lookup"><span data-stu-id="7d2ec-116">A value of 'tablespace' for the parameter **@property**.</span></span>  
  
    -   <span data-ttu-id="7d2ec-117">Der Name des Tabellen Bereichs für den Parameter **@value** .</span><span class="sxs-lookup"><span data-stu-id="7d2ec-117">The name of the tablespace for the parameter **@value**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d2ec-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d2ec-118">See Also</span></span>  
 <span data-ttu-id="7d2ec-119">[Konfigurieren eines Oracle-Verlegers](configure-an-oracle-publisher.md) </span><span class="sxs-lookup"><span data-stu-id="7d2ec-119">[Configure an Oracle Publisher](configure-an-oracle-publisher.md) </span></span>  
 [<span data-ttu-id="7d2ec-120">Auf dem Oracle-Verleger erstellte Objekte</span><span class="sxs-lookup"><span data-stu-id="7d2ec-120">Objects Created on the Oracle Publisher</span></span>](objects-created-on-the-oracle-publisher.md)  
  
  
