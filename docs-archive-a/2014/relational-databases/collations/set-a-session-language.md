---
title: Festlegen einer Sitzungssprache | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- errors [SQL Server], international considerations
- globalization [SQL Server], sessions
- time [SQL Server]
- sessions [SQL Server], languages
- international considerations [SQL Server], sessions
- dates [SQL Server], session languages
- global considerations [SQL Server], sessions
- client-side session language
- time [SQL Server], session languages
- messages [SQL Server], international considerations
- server-side session language
ms.assetid: de7f2c90-8f4f-4cfc-94cc-4933a7fd2bde
author: stevestein
ms.author: sstein
ms.openlocfilehash: da8d6adce66ac5b97e533b5afaefabda40e4b966
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622701"
---
# <a name="set-a-session-language"></a><span data-ttu-id="e7312-102">Festlegen einer Sitzungssprache</span><span class="sxs-lookup"><span data-stu-id="e7312-102">Set a Session Language</span></span>
  <span data-ttu-id="e7312-103">Die Sitzungssprache kann verwendet werden, um festzulegen, wie die folgenden Elemente abhängig von Sprache und Kultur auf dem Server angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="e7312-103">The session language can be used to set how the following elements are displayed on the server, based on language and cultural preference:</span></span>  
  
-   <span data-ttu-id="e7312-104">Die Sprache, die für Fehlermeldungen und andere Systemmeldungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e7312-104">The language that will be used for error and other system messages.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e7312-105">unterstützt das Vorhandensein mehrerer Kopien aller Systemfehler-Zeichenfolgen und Meldungen in allen Sprachen, in denen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e7312-105">supports having multiple copies of all system error strings and messages in all the languages in which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is available.</span></span> <span data-ttu-id="e7312-106">Diese Meldungen können mithilfe der [sys.messages](/sql/relational-databases/system-catalog-views/messages-for-errors-catalog-views-sys-messages) -Katalogsicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e7312-106">These messages can be viewed in the [sys.messages](/sql/relational-databases/system-catalog-views/messages-for-errors-catalog-views-sys-messages) catalog view.</span></span> <span data-ttu-id="e7312-107">Wenn Sie eine lokalisierte Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]installieren, sind diese Systemmeldungen für die installierte Sprachversion übersetzt.</span><span class="sxs-lookup"><span data-stu-id="e7312-107">When you install a localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], these system messages are translated for the language version that you install.</span></span> <span data-ttu-id="e7312-108">Standardmäßig erhalten Sie auch die US-englischen Meldungen .</span><span class="sxs-lookup"><span data-stu-id="e7312-108">By default, you also obtain the U.S. English set of these messages.</span></span> <span data-ttu-id="e7312-109">Außerdem können Sie benutzerdefinierte Meldungen in einer bestimmten Sprache mithilfe von [sp_addmessage](/sql/relational-databases/system-stored-procedures/sp-addmessage-transact-sql)hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e7312-109">Additionally, you can add user-defined messages in a specific language by using [sp_addmessage](/sql/relational-databases/system-stored-procedures/sp-addmessage-transact-sql).</span></span>  
  
-   <span data-ttu-id="e7312-110">Das Format von Datums- und Zeitdaten.</span><span class="sxs-lookup"><span data-stu-id="e7312-110">The format of date and time data.</span></span>  
  
-   <span data-ttu-id="e7312-111">Die Namen von Tagen und Monaten, einschließlich Abkürzungen.</span><span class="sxs-lookup"><span data-stu-id="e7312-111">The names of days and months, including abbreviations.</span></span>  
  
-   <span data-ttu-id="e7312-112">Der erste Tag der Woche.</span><span class="sxs-lookup"><span data-stu-id="e7312-112">The first day of the week.</span></span>  
  
-   <span data-ttu-id="e7312-113">Währungsdaten.</span><span class="sxs-lookup"><span data-stu-id="e7312-113">Currency data.</span></span>  
  
 <span data-ttu-id="e7312-114">Für die Sitzungseinstellungen sind 33 Sprachen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e7312-114">There are 33 languages available for use as session settings.</span></span> <span data-ttu-id="e7312-115">Eine Liste der Sprachen finden Sie unter [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e7312-115">For a list of languages, see [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql).</span></span>  
  
## <a name="setting-the-session-language-from-the-server"></a><span data-ttu-id="e7312-116">Festlegen der Sitzungssprache auf dem Server</span><span class="sxs-lookup"><span data-stu-id="e7312-116">Setting the Session Language from the Server</span></span>  
 <span data-ttu-id="e7312-117">So legen Sie die Sitzungssprache serverseitig fest. Verwenden Sie [SET LANGUAGE](/sql/t-sql/statements/set-language-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e7312-117">To set the session language from the server side, use [SET LANGUAGE](/sql/t-sql/statements/set-language-transact-sql).</span></span>  
  
## <a name="setting-the-session-language-from-the-client"></a><span data-ttu-id="e7312-118">Festlegen der Sitzungssprache auf dem Client</span><span class="sxs-lookup"><span data-stu-id="e7312-118">Setting the Session Language from the Client</span></span>  
 <span data-ttu-id="e7312-119">Die Sitzungssprache kann clientseitig mit OLE DB, ODBC oder ADO.NET festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="e7312-119">The session language can be set on the client side by using OLE DB, ODBC or ADO.NET.</span></span> <span data-ttu-id="e7312-120">Verwenden Sie für OLE DB die Eigenschaft SSPROP_INIT_CURRENTLANGUAGE.</span><span class="sxs-lookup"><span data-stu-id="e7312-120">For OLE DB, use the SSPROP_INIT_CURRENTLANGUAGE property.</span></span> <span data-ttu-id="e7312-121">Weitere Informationen hierzu finden Sie unter [Initialisierungs- und Autorisierungseigenschaften](../native-client-ole-db-data-source-objects/initialization-and-authorization-properties.md).</span><span class="sxs-lookup"><span data-stu-id="e7312-121">For more information, see [Initialization and Authorization Properties](../native-client-ole-db-data-source-objects/initialization-and-authorization-properties.md).</span></span>  
  
 <span data-ttu-id="e7312-122">Verwenden Sie für ODBC das programmiersprachliche Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="e7312-122">For ODBC, use the Language keyword.</span></span> <span data-ttu-id="e7312-123">Weitere Informationen finden Sie unter [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span><span class="sxs-lookup"><span data-stu-id="e7312-123">For more information, see [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span></span>  
  
 <span data-ttu-id="e7312-124">Verwenden Sie für ADO.NET den **Current Language** -Parameter des Objekts **ConnectionString** .</span><span class="sxs-lookup"><span data-stu-id="e7312-124">For ADO.NET, use the **Current Language** parameter of the **ConnectionString** object.</span></span> <span data-ttu-id="e7312-125">Weitere Informationen finden Sie in der Dokumentation zu [!INCLUDE[msCoName](../../includes/msconame-md.md)] Data Access Components (MDAC) Software Development Kit (SDK).</span><span class="sxs-lookup"><span data-stu-id="e7312-125">For more information, see the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Data Access Components (MDAC) software development kit (SDK) documentation.</span></span>  
  
  
