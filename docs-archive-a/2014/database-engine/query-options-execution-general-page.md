---
title: Ausführung von Abfrage Optionen (Seite "Allgemein") | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.query.general.f1
ms.assetid: 858a0263-2f04-4692-b8bf-63e93c998ead
author: rothja
ms.author: jroth
ms.openlocfilehash: ce3848b51b81f111333ba0e9ac12c96432dd9863
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621168"
---
# <a name="query-options-execution-general-page"></a><span data-ttu-id="c8129-102">Abfrageausführung (Seite 'Allgemein')</span><span class="sxs-lookup"><span data-stu-id="c8129-102">Query Options Execution (General Page)</span></span>
  <span data-ttu-id="c8129-103">Auf dieser Seite können Sie die Optionen zum Ausführen von [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Abfragen angeben.</span><span class="sxs-lookup"><span data-stu-id="c8129-103">Use this page to specify the options for running [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="c8129-104">Um auf dieses Dialogfeld zuzugreifen, klicken Sie mit der rechten Maustaste auf den Hauptteil des Abfrage-Editor-Fensters, und klicken Sie anschließend auf **Abfrageoptionen**.</span><span class="sxs-lookup"><span data-stu-id="c8129-104">To access this dialog box, right-click the body of a Query Editor window, and then click **Query Options**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="c8129-105">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="c8129-105">UI element list</span></span>  
 <span data-ttu-id="c8129-106">**SET ROWCOUNT**</span><span class="sxs-lookup"><span data-stu-id="c8129-106">**SET ROWCOUNT**</span></span>  
 <span data-ttu-id="c8129-107">Der Standardwert 0 zeigt an, dass [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] so lange auf die Ergebnisse wartet, bis alle Ergebnisse übermittelt sind.</span><span class="sxs-lookup"><span data-stu-id="c8129-107">The default value of 0 indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will wait for results until all results are received.</span></span> <span data-ttu-id="c8129-108">Geben Sie einen Wert größer 0 an, wenn die Abfrage von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] nach Übermittlung einer bestimmten Anzahl von Zeilen abgebrochen werden soll.</span><span class="sxs-lookup"><span data-stu-id="c8129-108">Provide a value greater than 0 if you want [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to halt the query after obtaining the specified number of rows.</span></span> <span data-ttu-id="c8129-109">Geben Sie SET ROWCOUNT 0 an, um diese Option zu deaktivieren (sodass alle Zeilen zurückgegeben werden).</span><span class="sxs-lookup"><span data-stu-id="c8129-109">To turn this option off (so that all rows are returned), specify SET ROWCOUNT 0.</span></span>  
  
 <span data-ttu-id="c8129-110">**SET TEXTSIZE**</span><span class="sxs-lookup"><span data-stu-id="c8129-110">**SET TEXTSIZE**</span></span>  
 <span data-ttu-id="c8129-111">Der Standardwert von 2.147.483.647 Bytes zeigt an, dass [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ein vollständiges Datenfeld bereitstellt, das maximal der Größe von `text`-, `ntext`-, `nvarchar(max)`- und `varchar(max)`-Datenfeldern entspricht.</span><span class="sxs-lookup"><span data-stu-id="c8129-111">The default value of 2,147,483,647 bytes indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will provide a complete data field up to the limit of `text`, `ntext`, `nvarchar(max)`, and `varchar(max)` data fields.</span></span> <span data-ttu-id="c8129-112">Dies hat keine Auswirkungen auf den XML-Datentyp.</span><span class="sxs-lookup"><span data-stu-id="c8129-112">It does not affect the XML data type.</span></span> <span data-ttu-id="c8129-113">Geben Sie eine kleinere Zahl an, um Ergebnisse mit großen Werten zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="c8129-113">Provide a smaller number to limit results in the case of large values.</span></span> <span data-ttu-id="c8129-114">Spalten, deren Größe die angegebene Zahl übersteigt, werden abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="c8129-114">Columns greater than the number provided will be truncated.</span></span>  
  
 <span data-ttu-id="c8129-115">**Ausführungs Timeout**</span><span class="sxs-lookup"><span data-stu-id="c8129-115">**Execution time-out**</span></span>  
 <span data-ttu-id="c8129-116">Gibt die Wartezeit (in Sekunden) an, nach der die Abfrage abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="c8129-116">Indicates the number of seconds to wait before canceling the query.</span></span> <span data-ttu-id="c8129-117">Der Wert '0' gibt an, dass der Wartevorgang unbegrenzt ist bzw. kein Timeout erfolgt.</span><span class="sxs-lookup"><span data-stu-id="c8129-117">A value of 0 indicates an infinite wait, or no time-out.</span></span>  
  
 <span data-ttu-id="c8129-118">**Batchtrennzeichen**</span><span class="sxs-lookup"><span data-stu-id="c8129-118">**Batch separator**</span></span>  
 <span data-ttu-id="c8129-119">Geben Sie ein Wort ein, das als Trennzeichen zwischen Transact-SQL-Anweisungen in Batches fungieren soll.</span><span class="sxs-lookup"><span data-stu-id="c8129-119">Type a word that you use to separate Transact-SQL statements into batches.</span></span> <span data-ttu-id="c8129-120">Der Standardwert ist GO.</span><span class="sxs-lookup"><span data-stu-id="c8129-120">The default is GO.</span></span>  
  
 <span data-ttu-id="c8129-121">**Standardmäßig neue Abfragen im SQLCMD-Modus öffnen**</span><span class="sxs-lookup"><span data-stu-id="c8129-121">**By default, open new queries in SQLCMD Mode**</span></span>  
 <span data-ttu-id="c8129-122">Aktivieren Sie dieses Kontrollkästchen, um neue Abfragen im SQLCMD-Modus zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c8129-122">Select this check box to open new queries in SQLCMD mode.</span></span> <span data-ttu-id="c8129-123">Dieses Kontrollkästchen ist nur sichtbar, wenn das Dialogfeld über **das Menü Extras** geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="c8129-123">This check box is visible only when the dialog box is opened through the **Tools** menu.</span></span>  
  
 <span data-ttu-id="c8129-124">Beachten Sie die folgenden Einschränkungen, wenn Sie diese Option auswählen:</span><span class="sxs-lookup"><span data-stu-id="c8129-124">When you select this option, be aware of the following limitations:</span></span>  
  
-   <span data-ttu-id="c8129-125">IntelliSense im [!INCLUDE[ssDE](../includes/ssde-md.md)] -Abfrage-Editor ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c8129-125">IntelliSense in the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor is turned off.</span></span>  
  
-   <span data-ttu-id="c8129-126">Da der Abfrage-Editor nicht über die Befehlszeile ausgeführt werden kann, ist es nicht möglich, Befehlszeilenparameter, z. B. Variablen, zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="c8129-126">Because Query Editor does not run from the command line, you cannot pass in command-line parameters such as variables.</span></span>  
  
-   <span data-ttu-id="c8129-127">Da der Abfrage-Editor nicht auf Anforderungen des Betriebssystems reagieren kann, müssen Sie darauf achten, keine interaktiven Anweisungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c8129-127">Because Query Editor cannot respond to operating-system prompts, you must be careful not to run interactive statements.</span></span>  
  
 <span data-ttu-id="c8129-128">**Standard wiederherstellen**</span><span class="sxs-lookup"><span data-stu-id="c8129-128">**Reset to Default**</span></span>  
 <span data-ttu-id="c8129-129">Setzt alle auf dieser Seite verfügbaren Werte auf die ursprünglichen Standardwerte zurück.</span><span class="sxs-lookup"><span data-stu-id="c8129-129">Resets all values on this page to the original default values.</span></span>  
  
  
