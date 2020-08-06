---
title: Zwischenspeichern von Vorlagen (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- registry keys [SQLXML]
- cache [SQLXML]
- templates [SQLXML], caching
ms.assetid: 73e151c6-b24e-4422-a116-51e0846bc6f5
author: rothja
ms.author: jroth
ms.openlocfilehash: b2ea8a539086ada1b15abbb9cff4f838af45818c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617879"
---
# <a name="template-caching-sqlxml-40"></a><span data-ttu-id="16ec8-102">Zwischenspeichern von Vorlagen (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="16ec8-102">Template Caching (SQLXML 4.0)</span></span>
  <span data-ttu-id="16ec8-103">Das Zwischenspeichern von Vorlagen verbessert die Leistung erheblich.</span><span class="sxs-lookup"><span data-stu-id="16ec8-103">Template caching significantly improves performance.</span></span> <span data-ttu-id="16ec8-104">Wenn das Zwischenspeichern von Vorlagen festgelegt ist, verbleibt die Vorlage nach ihrer ersten Ausführung im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="16ec8-104">If template caching is set, the template remains in memory upon its first execution.</span></span> <span data-ttu-id="16ec8-105">Auf diese Weise wird die Leistung der nächsten Vorlagenausführung verbessert.</span><span class="sxs-lookup"><span data-stu-id="16ec8-105">This improves the performance for the subsequent execution of the template.</span></span>  
  
 <span data-ttu-id="16ec8-106">Sie können die Cachegröße für Vorlagen festlegen, indem Sie den folgenden Schlüssel in der Registrierung hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="16ec8-106">You can set the template cache size by adding the following key in the registry:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML4\TemplateCacheSize  
```  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="16ec8-107">Die Größe sollte auf Basis des vorhandenen Arbeitsspeichers und der Anzahl der von Ihnen verwendeten Vorlagen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="16ec8-107">The template size should be set on the basis of the available memory and the number of templates you are using.</span></span> <span data-ttu-id="16ec8-108">Der Standardwert für die **TemplateCacheSize** -Größe ist 31.</span><span class="sxs-lookup"><span data-stu-id="16ec8-108">The default of **TemplateCacheSize** size is 31.</span></span> <span data-ttu-id="16ec8-109">Sie können die Cachegröße erhöhen, wenn der Vorlagenzugriff langsam erscheint, oder die Cachegröße verringern, wenn der Arbeitsspeicher zu gering ist.</span><span class="sxs-lookup"><span data-stu-id="16ec8-109">You can increase the cache size if template access seems slow, or decrease the cache size if memory is low.</span></span>  
  
 <span data-ttu-id="16ec8-110">Um eine bessere Leistung zu erzielen, empfiehlt es sich, **TemplateCacheSize** auf eine höhere Anzahl von Vorlagen festzulegen, die Sie normalerweise verwenden.</span><span class="sxs-lookup"><span data-stu-id="16ec8-110">For better performance, it is recommended that you set **TemplateCacheSize** higher than the number of templates you usually use.</span></span> <span data-ttu-id="16ec8-111">Wenn **temlatecachesize** kleiner ist als die Anzahl der Vorlagen, die Sie besitzen, wird die Leistung beeinträchtigt, wenn sich die Anzahl der Vorlagen erhöht.</span><span class="sxs-lookup"><span data-stu-id="16ec8-111">If **TemlateCacheSize** is less than the number of templates you have, performance degrades as the number of templates increase.</span></span> <span data-ttu-id="16ec8-112">**TemplateCacheSize** kann auf ein Maximum von 128 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="16ec8-112">The **TemplateCacheSize** can be set to a maximum of 128.</span></span>  
  
 <span data-ttu-id="16ec8-113">Jedes Mal, wenn eine zwischengespeicherte Vorlage verwendet wird, wird die Änderungszeit der Vorlagendatei überprüft, um festzustellen, ob sie aktualisiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="16ec8-113">Every time a cached template is used, the modification time of the template file is checked to see whether it needs to be refreshed.</span></span> <span data-ttu-id="16ec8-114">Das liegt daran, dass die Datenträgerkopie neuer als die Cachekopie ist.</span><span class="sxs-lookup"><span data-stu-id="16ec8-114">This is because the disk copy is newer than the cache copy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="16ec8-115">Vorlagenparameter und Befehlseigenschaften werden nicht zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="16ec8-115">Template parameters and command properties are not cached.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16ec8-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="16ec8-116">See Also</span></span>  
 <span data-ttu-id="16ec8-117">[Schema Caching &#40;SQLXML 4,0&#41;](schema-caching-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="16ec8-117">[Schema Caching &#40;SQLXML 4.0&#41;](schema-caching-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="16ec8-118">XSL-Caching &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="16ec8-118">XSL Caching &#40;SQLXML 4.0&#41;</span></span>](xsl-caching-sqlxml-4-0.md)  
  
  
