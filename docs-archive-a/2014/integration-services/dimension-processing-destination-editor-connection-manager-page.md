---
title: Ziel-Editor für Dimensions Verarbeitung (Seite Verbindungs-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dimprocessingtransformation.connection.f1
helpviewer_keywords:
- Dimension Processing Destination Editor
ms.assetid: 44aab631-d62d-4895-8fc7-7f1f3b1b68ce
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 50ba42292c1f48c9b1cdf2ba00c709dacd2f9675
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622230"
---
# <a name="dimension-processing-destination-editor-connection-manager-page"></a>Ziel-Editor für Dimensionsverarbeitung (Seite Verbindungs-Manager)
  Verwenden Sie die Seite **Verbindungs-Manager** des Dialogfelds **Ziel-Editor für Dimensionsverarbeitung**, um eine Verbindung mit einem [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Projekt oder einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Instanz anzugeben.  
  
 Weitere Informationen zum Ziel für Dimensionsverarbeitung finden Sie unter [Dimension Processing Destination](data-flow/dimension-processing-destination.md).  
  
## <a name="options"></a>Tastatur  
 **Connection manager**  
 Wählen Sie einen vorhandenen Verbindungs-Manager aus der Liste aus, oder klicken Sie auf **Neu** , um einen neuen Verbindungs-Manager zu erstellen.  
  
 **Neu**  
 Erstellen Sie mithilfe des Dialogfelds **Analysis Services-Verbindungs-Manager hinzufügen** eine neue Verbindung.  
  
 **Liste der verfügbaren Dimensionen**  
 Wählen Sie die zu verarbeitende Dimension aus.  
  
 **Verarbeitungsmethode**  
 Wählen Sie die Verarbeitungsmethode aus, die auf die in der Liste ausgewählte Dimension angewendet werden soll. Der Standardwert für diese Option ist **Vollständig**.  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|**Hinzufügen (inkrementell)**|Führt eine inkrementelle Verarbeitung der Dimension aus.|  
|**Vollständig**|Führt eine vollständige Verarbeitung der Dimension aus.|  
|**Aktualisieren**|Führt eine Verarbeitung der Updates für die Dimension aus.|  
  
## <a name="see-also"></a>Weitere Informationen  
 [Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Ziel-Editor für Dimensions Verarbeitung &#40;Seite Zuordnungen&#41;](../../2014/integration-services/dimension-processing-destination-editor-mappings-page.md)   
 [Ziel-Editor für Dimensionsverarbeitung &#40;Seite „Erweitert“&#41;](../../2014/integration-services/dimension-processing-destination-editor-advanced-page.md)  
  
  
