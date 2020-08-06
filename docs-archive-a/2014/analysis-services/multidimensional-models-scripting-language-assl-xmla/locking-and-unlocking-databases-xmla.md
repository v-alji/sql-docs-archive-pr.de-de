---
title: Sperren und Entsperren von Datenbanken (XMLA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- locking [XML for Analysis]
- XML for Analysis, locking
- XMLA, locking
- unlocking objects
ms.assetid: 451afa58-ce03-4ecc-8dd3-9e7e8559b5f1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 96afa94f7c9c20072ae88b09a436d079ce0478ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720368"
---
# <a name="locking-and-unlocking-databases-xmla"></a><span data-ttu-id="cd0f1-102">Sperren und Entsperren von Datenbanken (XMLA)</span><span class="sxs-lookup"><span data-stu-id="cd0f1-102">Locking and Unlocking Databases (XMLA)</span></span>
  <span data-ttu-id="cd0f1-103">Sie können Datenbanken Sperren und entsperren, indem Sie die Befehle [Lock](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/lock-element-xmla) und [Unlock](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/lock-element-xmla) in XML for Analysis (XMLA) verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd0f1-103">You can lock and unlock databases using, respectively, the [Lock](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/lock-element-xmla) and [Unlock](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/lock-element-xmla) commands in XML for Analysis (XMLA).</span></span> <span data-ttu-id="cd0f1-104">In der Regel sperren und entsperren andere XMLA-Befehle Objekte je nach Bedarf automatisch, um den Befehl während der Ausführung abschließen zu können.</span><span class="sxs-lookup"><span data-stu-id="cd0f1-104">Typically, other XMLA commands automatically lock and unlock objects as needed to complete the command during execution.</span></span> <span data-ttu-id="cd0f1-105">Sie können eine Datenbank explizit sperren oder entsperren, um mehrere Befehle innerhalb einer einzelnen Transaktion (z. b. eines [Batch](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/batch-element-xmla) -Befehls) auszuführen, und gleichzeitig verhindern, dass andere Anwendungen eine Schreib Transaktion an die Datenbank übergeben.</span><span class="sxs-lookup"><span data-stu-id="cd0f1-105">You can explicitly lock or unlock a database to perform multiple commands within a single transaction, such as a [Batch](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/batch-element-xmla) command, while preventing other applications from committing a write transaction to the database.</span></span>  
  
## <a name="locking-databases"></a><span data-ttu-id="cd0f1-106">Sperren von Datenbanken</span><span class="sxs-lookup"><span data-stu-id="cd0f1-106">Locking Databases</span></span>  
 <span data-ttu-id="cd0f1-107">Der `Lock`-Befehl sperrt die gemeinsame oder exklusive Nutzung eines Objekts im Rahmen der derzeit aktiven Transaktion.</span><span class="sxs-lookup"><span data-stu-id="cd0f1-107">The `Lock` command locks an object, either for shared or exclusive use, within the context of the currently active transaction.</span></span> <span data-ttu-id="cd0f1-108">Eine Sperre in einem Objekt verhindert, dass ein Commit für Transaktionen ausgeführt wird, bevor die Sperre entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="cd0f1-108">A lock on an object prevents transactions from committing until the lock is removed.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="cd0f1-109">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] unterstützt zwei Arten von Sperren: gemeinsame Sperren und exklusive Sperren.</span><span class="sxs-lookup"><span data-stu-id="cd0f1-109">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] supports two types of locks, shared locks and exclusive locks.</span></span> <span data-ttu-id="cd0f1-110">Weitere Informationen zu den von unterstützten Sperr Typen [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] finden Sie unter [Mode-Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/mode-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="cd0f1-110">For more information about the lock types supported by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], see [Mode Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/mode-element-xmla).</span></span>  
  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="cd0f1-111">ermöglicht nur die Sperrung von Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="cd0f1-111">allows only databases to be locked.</span></span> <span data-ttu-id="cd0f1-112">Der [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) -Element muss einen Objektverweis zu einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank enthalten.</span><span class="sxs-lookup"><span data-stu-id="cd0f1-112">The [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) element must contain an object reference to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="cd0f1-113">Wenn das `Object`-Element nicht angegeben ist oder wenn das `Object`-Element auf ein Objekt verweist, bei dem es sich nicht um eine Datenbank handelt, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="cd0f1-113">If the `Object` element is not specified or if the `Object` element refers to an object other than a database, an error occurs.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cd0f1-114">Nur Datenbankadministratoren oder Serveradministratoren können explizit einen `Lock`-Befehl ausgeben.</span><span class="sxs-lookup"><span data-stu-id="cd0f1-114">Only database administrators or server administrators can explicitly issue a `Lock` command.</span></span>  
  
 <span data-ttu-id="cd0f1-115">Andere Befehle geben implizit auf einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Datenbank einen `Lock`-Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="cd0f1-115">Other commands implicitly issue a `Lock` command on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="cd0f1-116">Jeder Vorgang, der Daten oder Metadaten aus einer Datenbank einliest (z. B. jede [Discover](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) -Methode oder eine [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) -Methode, die einen [Statement](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) -Befehl ausführt), gibt implizit eine gemeinsame Sperre der Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="cd0f1-116">Any operation that reads data or metadata from a database, such as any [Discover](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) method or an [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) method running a [Statement](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) command, implicitly issues a shared lock on the database.</span></span> <span data-ttu-id="cd0f1-117">Jede Transaktion, die Änderungen an Daten oder Metadaten für ein Objekt in einer- [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Datenbank ausführt, z. b. eine-Methode, die `Execute` einen [Alter](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) -Befehl ausführt, gibt implizit eine exklusive Sperre für die Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="cd0f1-117">Any transaction that commits changes in data or metadata to an object on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, such as an `Execute` method running an [Alter](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) command, implicitly issues an exclusive lock on the database.</span></span>  
  
## <a name="unlocking-objects"></a><span data-ttu-id="cd0f1-118">Entsperren von Objekten</span><span class="sxs-lookup"><span data-stu-id="cd0f1-118">Unlocking Objects</span></span>  
 <span data-ttu-id="cd0f1-119">Der Befehl `Unlock` entfernt eine innerhalb des Kontexts der gerade aktiven Transaktion begründete Sperre.</span><span class="sxs-lookup"><span data-stu-id="cd0f1-119">The `Unlock` command removes a lock established within the context of the currently active transaction.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cd0f1-120">Nur Datenbankadministratoren oder Server Administratoren können explizit einen `Unlock` Befehl ausgeben.</span><span class="sxs-lookup"><span data-stu-id="cd0f1-120">Only database administrators or server administrators can explicitly issue an `Unlock` command.</span></span>  
  
 <span data-ttu-id="cd0f1-121">Alle Sperren werden im Kontext der aktuellen Transaktion abgehalten.</span><span class="sxs-lookup"><span data-stu-id="cd0f1-121">All locks are held in the context of the current transaction.</span></span> <span data-ttu-id="cd0f1-122">Wenn die aktuelle Transaktion ausgeführt oder für diese ein Rollback durchgeführt wird, werden alle Sperren, die innerhalb der Transaktion definiert sind, automatisch aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="cd0f1-122">When the current transaction is committed or rolled back, all locks defined within the transaction are automatically released.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd0f1-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cd0f1-123">See Also</span></span>  
 <span data-ttu-id="cd0f1-124">[Lock-Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/lock-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="cd0f1-124">[Lock Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/lock-element-xmla) </span></span>  
 <span data-ttu-id="cd0f1-125">[Element &#40;XMLA entsperren&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/lock-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="cd0f1-125">[Unlock Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/lock-element-xmla) </span></span>  
 [<span data-ttu-id="cd0f1-126">Entwickeln mit XMLA in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="cd0f1-126">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  