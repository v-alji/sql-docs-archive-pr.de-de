---
title: Entwerfen der Abfrage | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptwizard.designquery.f1
ms.assetid: 2dad800f-10a1-453c-8761-2935b9826d84
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9b56d99ec11b50ce53ef223a01eb5fc2766238ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719678"
---
# <a name="design-the-query"></a>Entwerfen der Abfrage
  Auf dieser Seite des Berichts-Assistenten können Sie eine Abfrage erstellen, indem Sie die Abfrage entweder manuell eingeben, den Abfrage-Generator für die interaktive Erstellung der Abfrage nutzen oder indem Sie eine Abfrage aus einem anderen Bericht importieren.  
  
 Der auf der Seite Datenquelle auswählen, einer vorhergehenden Seite im Berichts-Assistenten, von Ihnen ausgewählte Datenquellentyp bestimmt die Abfrage, die Sie auf dieser Seite eingeben können. Wenn der Daten Quellentyp beispielsweise ist [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , können Sie- [!INCLUDE[tsql](../includes/tsql-md.md)] Anweisungen oder Namen gespeicherter Prozeduren eingeben. Wenn der Daten Quellentyp ist [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , ist der Abfrage Bereich deaktiviert, und Sie können eine Abfrage nicht direkt eingeben. Sie können Abfragen mithilfe des Abfrage-Generators angeben.  
  
## <a name="options"></a>Tastatur  
 **Abfragezeichenfolge**  
 Geben Sie eine Abfrage ein, die die Daten abruft, die Sie in Ihrem Bericht verwenden möchten.  
  
 **Abfrage-Generator**  
 Klicken Sie auf **Abfrage-Generator** , um einen Abfrage-Designer für die Datenquelle zu öffnen oder eine Abfrage aus einem anderen Bericht zu importieren.  
  
 Weitere Informationen zu Abfrage-Designern finden Sie unter [Reporting Services Query Designers](../../2014/reporting-services/reporting-services-query-designers.md).  
  
## <a name="example"></a>Beispiel  
 Für den Daten Quellentyp **Microsoft SQL Server**Ruft die folgende Abfrage eine Liste von Nachnamen aus der [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] Datenbanktabelle ab `Person` .  
  
```  
SELECT LastName FROM Person.Person;  
```  
  
 Für den Daten Quellentyp **Microsoft SQL Server**führt die folgende Abfrage die [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] gespeicherte Prozedur `uspGetEmployeeManagers` für den Mitarbeiter mit der ID 1 aus:  
  
```  
EXEC uspgetEmployeeManagers '1';  
```  
  
## <a name="see-also"></a>Weitere Informationen  
 [Hilfe zum Berichts-Assistenten](../../2014/reporting-services/report-wizard-help.md)   
 [Melden Sie eingebettete Datasets und freigegebene Datasets &#40;Berichts-Generator und SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)   
 [Hinzufügen von Daten zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](report-data/report-datasets-ssrs.md)  
  
  
