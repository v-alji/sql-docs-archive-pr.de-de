---
title: XSL-Zwischenspeichern (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- registry keys [SQLXML]
- cache [SQLXML]
- XSL caching [SQLXML]
ms.assetid: 91994142-32f0-4d8d-a8cf-eb0d8b1f1999
author: rothja
ms.author: jroth
ms.openlocfilehash: e41f247c34c1b40bedfdf6924a45afe5f63735b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700916"
---
# <a name="xsl-caching-sqlxml-40"></a><span data-ttu-id="b3add-102">XSL-Zwischenspeichern (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="b3add-102">XSL Caching (SQLXML 4.0)</span></span>
  <span data-ttu-id="b3add-103">Das Zwischenspeichern von XSL-Stylesheets verbessert die Leistung.</span><span class="sxs-lookup"><span data-stu-id="b3add-103">Caching XSL style sheets improves performance.</span></span> <span data-ttu-id="b3add-104">Bei der ersten Ausführung bleibt ein XSL-Stylesheet im Arbeitsspeicher, wenn das XSL-Zwischenspeichern auf ON festgelegt wurde. Dies verbessert die Leistung bei der nachfolgenden Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="b3add-104">Upon its first execution, an XSL style sheet remains in memory if XSL caching is set to ON; this improves performance for subsequent processing.</span></span> <span data-ttu-id="b3add-105">Die Standardeinstellung ist ON.</span><span class="sxs-lookup"><span data-stu-id="b3add-105">The default setting is ON.</span></span>  
  
 <span data-ttu-id="b3add-106">Sie können die XSL-Cachegröße festlegen, indem Sie den folgenden Schlüssel in der Registrierung hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="b3add-106">You can set the XSL cache size by adding the following key in the registry:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML4\XSLCacheSize  
```  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="b3add-107">Die XSL-Cachegröße sollte auf Basis des vorhandenen Arbeitsspeichers und der Anzahl der von Ihnen verwendeten XSL-Stylesheets festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b3add-107">The XSL cache size should be set on the basis of the available memory and the number of XSL style sheets you are using.</span></span> <span data-ttu-id="b3add-108">Der Standardwert von **XSLCacheSize** lautet 31.</span><span class="sxs-lookup"><span data-stu-id="b3add-108">The default of **XSLCacheSize** size is 31.</span></span> <span data-ttu-id="b3add-109">Sie können die Cachegröße erhöhen, wenn der XSL-Zugriff langsam erscheint, oder die Cachegröße verringern, wenn der Arbeitsspeicher zu gering ist.</span><span class="sxs-lookup"><span data-stu-id="b3add-109">You can increase the cache size if XSL access seems slow, or decrease the cache size if memory is low.</span></span>  
  
 <span data-ttu-id="b3add-110">Für bessere Leistung wird empfohlen, dass Sie **XSLCacheSize** auf einen höheren Wert als die Anzahl der von Ihnen üblicherweise verwendeten XSL-Stylesheets festlegen.</span><span class="sxs-lookup"><span data-stu-id="b3add-110">For better performance, it is recommended that you set **XSLCacheSize** higher than the number of XSL style sheets you usually use.</span></span> <span data-ttu-id="b3add-111">Wenn **XSLCacheSize** auf einen niedrigeren Wert als die Anzahl Ihrer XSL-Stylesheets festgelegt ist, sinkt die Leistung mit zunehmender Anzahl von XSL-Stylesheets.</span><span class="sxs-lookup"><span data-stu-id="b3add-111">If **XSLCacheSize** is less than the number of XSL style sheets you have, the performance degrades as the number of XSL style sheets increases.</span></span> <span data-ttu-id="b3add-112">Der **XSLCacheSize** kann auf ein Maximum von 128 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b3add-112">The **XSLCacheSize** can be set to a maximum of 128.</span></span>  
  
 <span data-ttu-id="b3add-113">Jedes Mal, wenn das zwischengespeicherte XSL-Stylesheet verwendet wird, wird die Änderungszeit der XSL-Datei überprüft, um festzustellen, ob sie aktualisiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="b3add-113">Every time the cached XSL style sheet is used, the modification time of the XSL file is checked to determine whether it needs to be refreshed.</span></span> <span data-ttu-id="b3add-114">Das liegt daran, dass die Datenträgerkopie neuer als die Cachekopie ist.</span><span class="sxs-lookup"><span data-stu-id="b3add-114">This is because the disk copy is newer than the cache copy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3add-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b3add-115">See Also</span></span>  
 <span data-ttu-id="b3add-116">[Zwischenspeichern von Vorlagen &#40;SQLXML 4,0&#41;](template-caching-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="b3add-116">[Template Caching &#40;SQLXML 4.0&#41;](template-caching-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="b3add-117">Schema Caching &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="b3add-117">Schema Caching &#40;SQLXML 4.0&#41;</span></span>](schema-caching-sqlxml-4-0.md)  
  
  
