---
title: SqlXmlAdapter-Objekt (verwaltete SQLXML-Klassen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- void Update(DataSet ds) method
- SqlXmlAdapter object
- void Fill(DataSet ds) method
- SQLXML Managed Classes, SqlXmlAdapter object
- Managed Classes [SQLXML], SqlXmlAdapter object
ms.assetid: 0a16eddf-fc26-4d92-82d4-359b5fb905d5
author: rothja
ms.author: jroth
ms.openlocfilehash: 1357ab7d070c7c2e451e31bccfda22c58eac42d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608500"
---
# <a name="sqlxmladapter-object-sqlxml-managed-classes"></a><span data-ttu-id="8fbb6-102">SqlXmlAdapter-Objekt (Verwaltete SQLXML-Klassen)</span><span class="sxs-lookup"><span data-stu-id="8fbb6-102">SqlXmlAdapter Object (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="8fbb6-103">Dieses Objekt stellt Methoden bereit, welche die Interaktion mit dem Dataset in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework erleichtern.</span><span class="sxs-lookup"><span data-stu-id="8fbb6-103">This object provides methods that facilitate interaction with the dataset in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span></span> <span data-ttu-id="8fbb6-104">Ein funktionierendes Beispiel finden Sie unter [zugreifen auf die SQLXML-Funktionalität in der .NET-Umgebung](accessing-sqlxml-functionality-in-the-net-environment.md).</span><span class="sxs-lookup"><span data-stu-id="8fbb6-104">For a working sample, see [Accessing SQLXML Functionality in the .NET Environment](accessing-sqlxml-functionality-in-the-net-environment.md).</span></span>  
  
 <span data-ttu-id="8fbb6-105">Das SqlXmlAdapter-Objekt unterstützt diese Methoden:</span><span class="sxs-lookup"><span data-stu-id="8fbb6-105">The SqlXmlAdapter object supports these methods:</span></span>  
  
 <span data-ttu-id="8fbb6-106">void Fill (DataSet DS)</span><span class="sxs-lookup"><span data-stu-id="8fbb6-106">void Fill(DataSet ds)</span></span>  
 <span data-ttu-id="8fbb6-107">Füllt das Dataset in .NET Framework mit den von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] abgerufenen XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="8fbb6-107">Fills the dataset in the .NET Framework with the XML data retrieved from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8fbb6-108">void Update (DataSet-DS)</span><span class="sxs-lookup"><span data-stu-id="8fbb6-108">void Update(DataSet ds)</span></span>  
 <span data-ttu-id="8fbb6-109">Übernimmt Updates aus den Daten im Dataset und wendet sie auf Datensätze in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] an.</span><span class="sxs-lookup"><span data-stu-id="8fbb6-109">Applies updates to records in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] from the data in the dataset.</span></span>  
  
 <span data-ttu-id="8fbb6-110">Das SqlXmlAdapter-Objekt unterstützt diese Konstruktoren:</span><span class="sxs-lookup"><span data-stu-id="8fbb6-110">The SqlXmlAdapter object supports these constructors:</span></span>  
  
```  
public SqlXmlAdapter(SqlXmlCommand  cmd)   
  
public SqlXmlAdapter(  
                     string commandText,   
                     SqlXmlCommandType cmdType,   
                     string connectionString  
                      )   
  
public SqlXmlAdapter(  
                     Stream commandStream,   
                     SqlXmlCommandType cmdType,   
                     string connectionString  
                     )   
```  
  
## <a name="see-also"></a><span data-ttu-id="8fbb6-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8fbb6-111">See Also</span></span>  
 <span data-ttu-id="8fbb6-112">[SqlXmlCommand-Objekt &#40;verwalteten SQLXML-Klassen&#41;](sqlxml-4-0-net-framework-support-managed-classes.md) </span><span class="sxs-lookup"><span data-stu-id="8fbb6-112">[SqlXmlCommand Object &#40;SQLXML Managed Classes&#41;](sqlxml-4-0-net-framework-support-managed-classes.md) </span></span>  
 [<span data-ttu-id="8fbb6-113">SqlXmlParameter-Objekt &#40;verwalteten SQLXML-Klassen&#41;</span><span class="sxs-lookup"><span data-stu-id="8fbb6-113">SqlXmlParameter Object &#40;SQLXML Managed Classes&#41;</span></span>](sqlxml-managed-classes-sqlxmlparameter-object.md)  
  
  
