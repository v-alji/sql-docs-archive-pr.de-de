---
title: Problembehandlung bei IntelliSense
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- unavailable options [IntelliSense]
- IntelliSense [SQL Server], troubleshooting
- IntelliSense [SQL Server], unavailable options
- troubleshooting [IntelliSense]
ms.assetid: 4b72ffc6-aea2-4e11-ab36-fa2de4d7bcc5
author: rothja
ms.author: jroth
ms.openlocfilehash: 087baf616fc215c480ae78621623cbe1ed512b57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717752"
---
# <a name="troubleshooting-intellisense-sql-server-management-studio"></a><span data-ttu-id="6d5a5-102">Problembehandlung von IntelliSense (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="6d5a5-102">Troubleshooting IntelliSense (SQL Server Management Studio)</span></span>
  <span data-ttu-id="6d5a5-103">Es gibt bestimmte Fälle, in denen die IntelliSense-Optionen unter Umständen nicht erwartungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-103">There are certain cases when the IntelliSense options might not work as you expect.</span></span>  
  
## <a name="conditions-that-affect-intellisense"></a><span data-ttu-id="6d5a5-104">Bedingungen, die Auswirkungen auf IntelliSense haben</span><span class="sxs-lookup"><span data-stu-id="6d5a5-104">Conditions That Affect IntelliSense</span></span>  
 <span data-ttu-id="6d5a5-105">Die folgenden Bedingungen können das Verhalten von IntelliSense beeinflussen:</span><span class="sxs-lookup"><span data-stu-id="6d5a5-105">The following conditions might affect the behavior of IntelliSense:</span></span>  
  
-   <span data-ttu-id="6d5a5-106">Über dem Cursor wird ein Codefehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-106">There is a code error above the cursor.</span></span>  
  
     <span data-ttu-id="6d5a5-107">Wenn sich über der Position der Einfügemarke eine unvollständige Anweisung oder ein anderer Codierungsfehler befindet, kann IntelliSense die Codeelemente möglicherweise nicht analysieren und funktioniert daher nicht.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-107">If there is an incomplete statement or other coding error above the location of the insertion point, IntelliSense may be unable to parse the code elements, and therefore will not work.</span></span> <span data-ttu-id="6d5a5-108">Sie können den verfügbaren Code auskommentieren, um IntelliSense erneut zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-108">You can comment out the applicable code to enable IntelliSense again.</span></span>  
  
-   <span data-ttu-id="6d5a5-109">Die Einfügemarke befindet sich innerhalb eines Codekommentars.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-109">The insertion point is inside a code comment.</span></span>  
  
     <span data-ttu-id="6d5a5-110">Wenn sich die Einfügemarke innerhalb eines Kommentars in der Quelldatei befindet, sind IntelliSense-Optionen nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-110">IntelliSense options are not available when the insertion point is within a comment in your source file.</span></span>  
  
-   <span data-ttu-id="6d5a5-111">Die Einfügemarke befindet sich innerhalb eines Zeichenfolgenliterals.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-111">The insertion point is inside a string literal.</span></span>  
  
     <span data-ttu-id="6d5a5-112">Wenn sich die Einfügemarke innerhalb der Anführungszeichen eines Zeichenfolgenliterals befindet, sind IntelliSense-Optionen nicht verfügbar, z. B. in:</span><span class="sxs-lookup"><span data-stu-id="6d5a5-112">IntelliSense options are not available when the insertion point is inside the quotation marks around a string literal, for example:</span></span>  
  
     `WHERE FirstName LIKE 'Patri%|'`  
  
-   <span data-ttu-id="6d5a5-113">Die automatischen Optionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-113">The automatic options are turned off.</span></span>  
  
     <span data-ttu-id="6d5a5-114">Viele IntelliSense-Funktionen funktionieren standardmäßig automatisch. Sie können die einzelnen Funktionen deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-114">Many IntelliSense features work automatically by default, but you can disable any feature.</span></span>  
  
     <span data-ttu-id="6d5a5-115">Auch wenn die automatische Anweisungsvervollständigung deaktiviert ist, können Sie eine IntelliSense-Funktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-115">Even when automatic statement completion is disabled, you can use an IntelliSense feature.</span></span> <span data-ttu-id="6d5a5-116">Weitere Informationen finden Sie unter [Konfigurieren von IntelliSense &#40;SQL Server Management Studio&#41;](configure-intellisense-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="6d5a5-116">For more information, see [Configure IntelliSense &#40;SQL Server Management Studio&#41;](configure-intellisense-sql-server-management-studio.md).</span></span>  
  
## <a name="database-engine-query-intellisense"></a><span data-ttu-id="6d5a5-117">IntelliSense in der Datenbank-Engine-Abfrage</span><span class="sxs-lookup"><span data-stu-id="6d5a5-117">Database Engine Query IntelliSense</span></span>  
 <span data-ttu-id="6d5a5-118">Die folgenden Probleme gelten für den [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] -Abfrage-Editor:</span><span class="sxs-lookup"><span data-stu-id="6d5a5-118">The following issues apply to the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] Query Editor:</span></span>  
  
-   <span data-ttu-id="6d5a5-119">Die IntelliSense-Funktionalität des [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editors unterstützt nicht alle [!INCLUDE[tsql](../../includes/tsql-md.md)] -Syntaxelemente.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-119">The IntelliSense functionality of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor does not support all [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax elements.</span></span> <span data-ttu-id="6d5a5-120">Die Parameterhilfe unterstützt nicht die Parameter in manchen Objekten, z. B. in erweiterten gespeicherten Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-120">Parameter help does not support the parameters in some objects, such as extended stored procedures.</span></span> <span data-ttu-id="6d5a5-121">Weitere Informationen finden Sie unter [Von IntelliSense unterstützte Transact-SQL-Syntax](transact-sql-syntax-supported-by-intellisense.md).</span><span class="sxs-lookup"><span data-stu-id="6d5a5-121">For more information, see [Transact-SQL Syntax Supported by IntelliSense](transact-sql-syntax-supported-by-intellisense.md).</span></span>  
  
-   <span data-ttu-id="6d5a5-122">IntelliSense ist nur verfügbar, wenn der [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)][!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] oder höher verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-122">IntelliSense is only available when the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor is connected to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] from [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later.</span></span> <span data-ttu-id="6d5a5-123">IntelliSense ist nicht verfügbar, wenn der Abfrage-Editor mit früheren Versionen von [!INCLUDE[ssDE](../../includes/ssde-md.md)]verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-123">IntelliSense is not available when the Query Editor is connected to earlier versions of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="6d5a5-124">IntelliSense wird im [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor deaktiviert, wenn der SQLCMD-Modus aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-124">IntelliSense is turned off in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor when the SQLCMD mode is set on.</span></span>  
  
-   <span data-ttu-id="6d5a5-125">Die IntelliSense-Funktionalität deckt keine von einer anderen Verbindung erstellten Datenbankobjekte ab, nachdem das Editorfenster eine Verbindung mit der Datenbank hergestellt hat.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-125">IntelliSense functionality does not cover database objects created by another connection after your editor window connected to the database.</span></span> <span data-ttu-id="6d5a5-126">Wenn Objekte in IntelliSense-Funktionen, beispielsweise Vervollständigungslisten fehlen, können Sie einen dieser drei Mechanismen auswählen, um den Cache von Objekten für das Editor-Fenster zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="6d5a5-126">If objects are missing from IntelliSense features such as completion lists, you can choose one of these three mechanisms to refresh the cache of objects for your editor window:</span></span>  
  
    -   <span data-ttu-id="6d5a5-127">Wählen Sie das Menü **Bearbeiten** , **IntelliSense**und dann **Lokalen Cache aktualisieren**aus.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-127">Select the **Edit** menu, select **IntelliSense**, then select **Refresh Local Cache**.</span></span>  
  
    -   <span data-ttu-id="6d5a5-128">Verwenden Sie die Tastenkombination STRG+UMSCHALT+R.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-128">Use the CTRL+Shift+R keyboard shortcut.</span></span>  
  
    -   <span data-ttu-id="6d5a5-129">Trennen Sie die Verbindung des Editorfensters von der [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Instanz, und stellen Sie erneut eine Verbindung her.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-129">Disconnect your editor window from the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and reconnect.</span></span>  
  
-   <span data-ttu-id="6d5a5-130">Vervollständigungslisten enthalten keine Datenbankobjekte, für die Sie keine Berechtigungen haben.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-130">Completion lists do not include database objects for which you do not have permissions.</span></span> <span data-ttu-id="6d5a5-131">IntelliSense kennzeichnet Verweise auf Objekte, für die Sie Berechtigungen haben.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-131">IntelliSense flags references to objects for which you do have permissions.</span></span> <span data-ttu-id="6d5a5-132">Wenn Sie z. B. ein Skript öffnen, das von einer anderen Person geschrieben wurde, werden alle Verweise auf Objekte, für die diese Person über Berechtigungen verfügt, Sie dagegen nicht, als inkorrekt gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-132">For example, if you open a script that is written by someone else, any references to objects for which that person has permissions and you do not are flagged as incorrect.</span></span>  
  
-   <span data-ttu-id="6d5a5-133">Vervollständigungslisten funktionieren möglicherweise nicht mehr, wenn die Verbindung zur Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)]verloren geht.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-133">Completion lists might stop working if you lose the connection to the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="6d5a5-134">Stellen Sie erneut eine Verbindung zur Instanz her.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-134">Reconnect to the instance.</span></span>  
  
  
