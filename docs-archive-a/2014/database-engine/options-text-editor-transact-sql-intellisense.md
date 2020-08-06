---
title: Optionen (Text-Editor-Transact-SQL-IntelliSense) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.SQL.Advanced
- VS.ToolsOptionsPages.Text_Editor.SQL_Server_Tools.Advanced
dev_langs:
- TSQL
ms.assetid: 1855d916-5bf9-4d94-b0fb-9f9bb05ff950
author: rothja
ms.author: jroth
ms.openlocfilehash: 2d8f9c865516dc5e4c0ddadbdc908a9b4c8ec366
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619992"
---
# <a name="options-text-editor-transact-sql-intellisense"></a><span data-ttu-id="eb012-102">Optionen (Text-Editor-Transact-SQL-IntelliSense)</span><span class="sxs-lookup"><span data-stu-id="eb012-102">Options (Text Editor-Transact-SQL-IntelliSense)</span></span>
  <span data-ttu-id="eb012-103">Im Dialogfeld **Optionen** können Sie die IntelliSense-Einstellungen für den [!INCLUDE[ssDE](../includes/ssde-md.md)]-Abfrage-Editor ändern.</span><span class="sxs-lookup"><span data-stu-id="eb012-103">The **Options** dialog box lets you change the IntelliSense settings for the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor.</span></span> <span data-ttu-id="eb012-104">Diese Einstellungen sind verfügbar, wenn Sie im Menü **Extras** auf **Optionen** klicken. Erweitern Sie den Ordner **Text-Editor**, erweitern Sie den Ordner **Transact-SQL**, und klicken Sie anschließend auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="eb012-104">These settings are available when, on the **Tools** menu, you click **Options**, expand the **Text Editor** folder, expand the **Transact-SQL** folder, and then click **Advanced**.</span></span>  
  
## <a name="transact-sql-intellisense-settings"></a><span data-ttu-id="eb012-105">IntelliSense-Einstellungen für Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="eb012-105">Transact-SQL IntelliSense Settings</span></span>  
 <span data-ttu-id="eb012-106">Gibt die IntelliSense-Optionen für den [!INCLUDE[ssDE](../includes/ssde-md.md)]-Abfrage-Editor an.</span><span class="sxs-lookup"><span data-stu-id="eb012-106">Specifies the IntelliSense options for the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor.</span></span>  
  
### <a name="enable-intellisense"></a><span data-ttu-id="eb012-107">IntelliSense aktivieren</span><span class="sxs-lookup"><span data-stu-id="eb012-107">Enable IntelliSense</span></span>  
 <span data-ttu-id="eb012-108">Aktiviert die IntelliSense-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="eb012-108">Enables the IntelliSense features.</span></span> <span data-ttu-id="eb012-109">Wenn dieses Kontrollkästchen nicht aktiviert ist, sind die angegebenen IntelliSense-Optionen nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="eb012-109">When this box is not selected, the specific IntelliSense options are unavailable.</span></span> <span data-ttu-id="eb012-110">Standardmäßig ist dieses Kontrollkästchen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="eb012-110">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="eb012-111">**Fehler unterstreichen**</span><span class="sxs-lookup"><span data-stu-id="eb012-111">**Underline errors**</span></span>  
 <span data-ttu-id="eb012-112">Identifiziert Syntax- und Semantikfehler in [!INCLUDE[tsql](../includes/tsql-md.md)]-Anweisungen im Abfragefenster.</span><span class="sxs-lookup"><span data-stu-id="eb012-112">Identifies syntax and semantic errors in [!INCLUDE[tsql](../includes/tsql-md.md)] statements in the query window.</span></span> <span data-ttu-id="eb012-113">Alle Fehler und Warnungen werden in roter Schrift angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eb012-113">All errors and warnings appear in red.</span></span> <span data-ttu-id="eb012-114">Fehler und Warnungen werden nur für die [!INCLUDE[tsql](../includes/tsql-md.md)] -Anweisungen unterstützt, für die IntelliSense implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="eb012-114">Errors and warnings are supported only for the [!INCLUDE[tsql](../includes/tsql-md.md)] statements for which IntelliSense has been implemented.</span></span> <span data-ttu-id="eb012-115">Standardmäßig ist dieses Kontrollkästchen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="eb012-115">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="eb012-116">**Gliederungsanweisungen**</span><span class="sxs-lookup"><span data-stu-id="eb012-116">**Outline statements**</span></span>  
 <span data-ttu-id="eb012-117">Aktiviert die Gliederungsfunktion beim Öffnen von Dateien.</span><span class="sxs-lookup"><span data-stu-id="eb012-117">Enables the outlining feature when a file is opened.</span></span> <span data-ttu-id="eb012-118">Dadurch werden reduzierbare Blöcke von [!INCLUDE[tsql](../includes/tsql-md.md)] -Code erstellt.</span><span class="sxs-lookup"><span data-stu-id="eb012-118">This creates collapsible blocks of [!INCLUDE[tsql](../includes/tsql-md.md)] code.</span></span> <span data-ttu-id="eb012-119">Standardmäßig ist dieses Kontrollkästchen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="eb012-119">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="eb012-120">**Maximale Skriptgröße**</span><span class="sxs-lookup"><span data-stu-id="eb012-120">**Maximum script size**</span></span>  
 <span data-ttu-id="eb012-121">Gibt die Größe an, bei der IntelliSense-Funktionalität deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="eb012-121">Specifies the size at which IntelliSense functionality is disabled.</span></span> <span data-ttu-id="eb012-122">Wenn ein Skript die angegebene Größe überschreitet, wird eine Warnmeldung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="eb012-122">If a script exceeds the specified size, a warning message is issued.</span></span> <span data-ttu-id="eb012-123">Alle IntelliSense-Funktionen mit Ausnahme von Farbcodierung werden für dieses Editorfenster deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="eb012-123">All IntelliSense features, except color coding, are disabled for that editor window.</span></span> <span data-ttu-id="eb012-124">IntelliSense wird erneut aktiviert, wenn genug Text gelöscht wurde, um die Skriptgröße auf die maximale Größe zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="eb012-124">IntelliSense is reenabled when enough text is deleted to reduce the script size to under the limit.</span></span> <span data-ttu-id="eb012-125">Das Aktivieren von IntelliSense für große Skripts kann bei langsamen Computern zu Leistungseinbußen führen.</span><span class="sxs-lookup"><span data-stu-id="eb012-125">Enabling IntelliSense for large script sizes can decrease performance on slow computers.</span></span> <span data-ttu-id="eb012-126">Die zulässigen Größen sind 100 KB, 500 KB, 1 MB, 2 MB und Unbegrenzt.</span><span class="sxs-lookup"><span data-stu-id="eb012-126">The allowed sizes are 100 KB, 500 KB, 1 MB, 2 MB, and Unlimited.</span></span> <span data-ttu-id="eb012-127">Die Standardeinstellung ist 1 MB.</span><span class="sxs-lookup"><span data-stu-id="eb012-127">The default is 1 MB.</span></span>  
  
 <span data-ttu-id="eb012-128">**Schreibweise für integrierte Funktionsnamen**</span><span class="sxs-lookup"><span data-stu-id="eb012-128">**Casing for built-in function names**</span></span>  
 <span data-ttu-id="eb012-129">Gibt an, ob die Namen integrierter [!INCLUDE[tsql](../includes/tsql-md.md)]-Funktionen, die in Vervollständigungslisten enthalten sind, Großbuchstaben verwenden, wie z.B. DATEADD, oder Kleinbuchstaben, wie z.B. dateadd.</span><span class="sxs-lookup"><span data-stu-id="eb012-129">Specifies whether the names of built-in [!INCLUDE[tsql](../includes/tsql-md.md)] functions that are included in completion lists use uppercase letters, such as DATEADD; or lowercase letters, such as dateadd.</span></span> <span data-ttu-id="eb012-130">Wählen Sie die Option aus, die mit den von Ihnen verwendeten [!INCLUDE[tsql](../includes/tsql-md.md)] -Codierungskonventionen am besten übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="eb012-130">Select the option that best matches the [!INCLUDE[tsql](../includes/tsql-md.md)] coding conventions that you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb012-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb012-131">See Also</span></span>  
 [<span data-ttu-id="eb012-132">Problembehandlung bei IntelliSense &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="eb012-132">Troubleshooting IntelliSense &#40;SQL Server Management Studio&#41;</span></span>](../relational-databases/scripting/troubleshooting-intellisense.md)  
  
  
