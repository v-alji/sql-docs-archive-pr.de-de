---
title: NULL-Behandlung (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- updg:nullvalue attribute
- updategrams [SQLXML], null values
- nullvalue attribute
- null values [SQLXML]
ms.assetid: 5e11eebb-d94e-4ce6-a6d0-870225706bc1
author: rothja
ms.author: jroth
ms.openlocfilehash: 430643e8a6c9bd3dd00b2763990645c6a162ee40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619745"
---
# <a name="null-handling-sqlxml-40"></a><span data-ttu-id="edd33-102">Behandlung von NULL (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="edd33-102">NULL Handling (SQLXML 4.0)</span></span>
  <span data-ttu-id="edd33-103">XML-Syntax deutet NULL als eine Abwesenheit.</span><span class="sxs-lookup"><span data-stu-id="edd33-103">XML syntax denotes NULL as an absence.</span></span> <span data-ttu-id="edd33-104">(Beispiel: Wenn ein Attribut-oder Elementwert NULL ist, ist dieses Attribut oder Element im XML-Dokument nicht vorhanden.) In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML ermöglicht das- `updg:nullvalue` Attribut die Angabe von NULL für einen Element-oder Attribut Wert.</span><span class="sxs-lookup"><span data-stu-id="edd33-104">(For example, if an attribute or element value is NULL, that attribute or element is absent from the XML document.) In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML, the `updg:nullvalue` attribute enables specifying NULL for an element or attribute value.</span></span>  
  
 <span data-ttu-id="edd33-105">Das folgende Update Gram stellt z. b. sicher, dass der **Titelwert** für einen Kontakt mit der **ContactID** 64 NULL ist, und aktualisiert dann den **Title** -Wert auf "Mr."</span><span class="sxs-lookup"><span data-stu-id="edd33-105">For example, the following updategram ensures that the **Title** value for a contact with **ContactID** of 64 is NULL, and then updates the **Title** value to "Mr."</span></span> <span data-ttu-id="edd33-106">auf "Mr.".</span><span class="sxs-lookup"><span data-stu-id="edd33-106">for this contact.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync updg:nullvalue="IsNULL"  >  
    <updg:before>  
       <Person.Contact ContactID="64" Title="IsNULL" />  
    </updg:before>  
    <updg:after>  
       <Person.Contact ContactID="64" Title="Mr." />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="edd33-107">Wenn Parameter an ein Updategram übergeben werden, kann NULL als Parameterwert übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="edd33-107">When parameters are passed to an updategram, NULL can be passed as the parameter value.</span></span> <span data-ttu-id="edd33-108">Dies wird erreicht, indem das `nullvalue`-Attribut im `<updg:header>`-Block angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="edd33-108">This is done by specifying the `nullvalue` attribute in the `<updg:header>` block.</span></span> <span data-ttu-id="edd33-109">Ein Beispiel finden Sie unter [übergeben von Parametern an Update grams &#40;SQLXML 4,0&#41;](passing-parameters-to-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="edd33-109">For an example, see [Passing Parameters to Updategrams &#40;SQLXML 4.0&#41;](passing-parameters-to-updategrams-sqlxml-4-0.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edd33-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="edd33-110">See Also</span></span>  
 [<span data-ttu-id="edd33-111">Sicherheitsüberlegungen zu Update grams &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="edd33-111">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
