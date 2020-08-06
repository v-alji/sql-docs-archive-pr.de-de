---
title: OData-Verbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3caa4372-aff3-4c0f-9ecd-97870948b8d0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 46eedaa008b284661fd1d364d2e2bc87c373a9f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619266"
---
# <a name="odata-connection-manager"></a>OData-Verbindungs-Manager
  Mithilfe eines OData-Verbindungs-Managers kann ein Paket eine Verbindung mit einer OData-Quelle herstellen. Eine OData-Quellkomponente stellt über einen OData-Verbindungs-Manager eine Verbindung mit einer OData-Quelle her und verwendet die Daten des Diensts. Ausführliche Informationen einschließlich Installationsanweisungen für diese Komponenten finden Sie im Abschnitt [odata-Quelle](../data-flow/odata-source.md).  
  
## <a name="adding-connection-manager-to-an-ssis-package"></a>Hinzufügen des Verbindungs-Managers zu einem SSIS-Paket  
 Sie können einem SSIS-Paket einen neuen OData-Verbindungs-Manager auf drei Arten hinzufügen:  
  
-   Klicken Sie im **Quellen-Editor für OData** auf die Schaltfläche **Neu...** .  
  
-   Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Verbindungs-Manager** , und klicken Sie auf **neuer Verbindungs-Manager**. Wählen Sie unter **Typ des Verbindungs-Managers** die Option **ODATA**aus.  
  
-   Klicken Sie mit der rechten Maustaste auf den Bereich **Verbindungs-Manager** unten im Paket-Designer, und wählen Sie **neue Verbindung...** aus. Wählen Sie **odata** als **Typ des Verbindungs-Managers**aus.  
  
## <a name="connection-manager-authentication"></a>Verbindungs-Manager-Authentifizierung  
 Der OData-Verbindungs-Manager unterstützt zwei Authentifizierungsmodi.  
  
-   Windows-Authentifizierung  
  
-   Standardauthentifizierung (Benutzername und Kennwort)  
  
 Für den anonymen Zugriff wählen Sie die Option Windows-Authentifizierung aus.  
  
### <a name="specifying-and-securing-credentials"></a>Festlegen und Sichern von Anmeldeinformationen  
 Wenn der odata-Dienst die Standard Authentifizierung erfordert, können Sie im [odata-Verbindungs-Manager-Editor](../odata-connection-manager-editor.md)einen Benutzernamen und ein Kennwort angeben. Die Werte, die Sie in den Editor eingeben, werden im Paket beibehalten. Der Kennwortwert wird gemäß der Schutzebene des Pakets verschlüsselt.  
  
 Es gibt mehrere Möglichkeiten, den Benutzernamen- und Kennwortwert zu externalisieren/parametrisieren. Die beiden Hauptmethoden in [!INCLUDE[ssISversion11](../../includes/ssisversion11-md.md)] bestehen darin, Parameter zu verwenden oder die Eigenschaften des Verbindungs-Managers beim Ausführen des Pakets in SQL Server Management Studio direkt festzulegen.  
  
## <a name="odata-connection-manager-properties"></a>Eigenschaften des OData-Verbindungs-Managers  
 In der folgenden Liste sind einige Eigenschaften des OData-Verbindungs-Managers beschrieben, die Sie ändern können.  
  
|||  
|-|-|  
|Eigenschaft|BESCHREIBUNG|  
|url|Die URL zum Dienstdokument.|  
|UserName|Der Benutzername, der für die Standardauthentifizierung verwendet wird.|  
|Kennwort|Das Kennwort, das für die Standardauthentifizierung verwendet wird.|  
|ConnectionString|Stellt weitere Eigenschaften des Verbindungs-Managers dar.|  
  
## <a name="see-also"></a>Weitere Informationen  
 [OData-Verbindungs-Manager-Editor](../odata-connection-manager-editor.md)  
  
  
