---
title: Identitätswechsel Informationen (Dialog Feld, Tabellen Import-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.impersonationinfo.f1
ms.assetid: bee7eee5-0650-41f1-a372-5076ae97a58c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5300f8b6106a7f29f51018b4e039c2a8c28aa729
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696286"
---
# <a name="impersonation-information-dialog-box-table-import-wizard"></a>Identitätswechselinformationen (Dialogfeld, Tabellenimport-Assistent)
  Verwenden Sie die Seite **Identitätswechselinformationen** , um die Anmeldeinformationen anzugeben, mit denen [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] eine Verbindung mit der Datenquelle herstellt. Weitere Informationen zum Identitätswechsel mit Anmeldeinformationen finden Sie unter [Impersonation &#40;SSAS Tabular&#41;](tabular-models/impersonation-ssas-tabular.md).  
  
## <a name="options"></a>Tastatur  
 **Bestimmter Windows-Benutzername und bestimmtes Kennwort**  
 Wählen Sie diese Option aus, damit vom Tabellenmodell die Sicherheitsanmeldeinformationen eines angegebenen Windows-Benutzerkontos verwendet werden.  
  
 **Benutzername**  
 Geben Sie die Domäne und den Name des zu verwendenden Benutzerkontos ein. Verwenden Sie das folgende Format:  
  
 *\<Domain name>* **\\** *\<User account name>*  
  
 Die Option ist nur verfügbar, wenn die Option **Bestimmten Benutzernamen und bestimmtes Kennwort verwenden** ausgewählt ist.  
  
 **Kennwort**  
 Geben Sie das Kennwort des Benutzerkontos ein, das vom Tabellenmodell verwendet werden soll.  
  
 Die Option ist nur verfügbar, wenn die Option **Bestimmten Benutzernamen und bestimmtes Kennwort verwenden** ausgewählt ist.  
  
 **Dienstkonto**  
 Wählen Sie diese Option aus, damit die Sicherheitsanmeldeinformationen verwendet werden, die dem [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Dienst zugeordnet sind, der das Objekt verwaltet.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Identitätswechsel &#40;SSAS – tabellarisch&#41;](tabular-models/impersonation-ssas-tabular.md)  
  
  
