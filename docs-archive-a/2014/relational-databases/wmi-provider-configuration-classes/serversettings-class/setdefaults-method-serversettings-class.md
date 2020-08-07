---
title: SetDefaults-Methode (ServerSettings-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (ServerSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: 76e4cfab-4b15-4da4-bb2f-8aac6f927f79
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 93dd2eee5a395d4d7463ebf9b85530fcf82d1888
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699338"
---
# <a name="setdefaults-method-serversettings-class"></a>SetDefaults-Methode (ServerSettings-Klasse)
  Legt alle Standardwerte für die Instanz von fest [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , wobei die Option zum Überschreiben vorhandener Daten vorhanden ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a>Bestandteile  
 *object*  
 Ein [ServerSettings-Klassenobjekt](serversettings-class.md) , das Einstellungen eine [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Clientinstanz darstellt.  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|BESCHREIBUNG|  
|---------------|-----------------|  
|*Overschreiteall*|Ein boleescher Wert, der angibt, ob vorhandene Werte in der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] überschreiben werden sollen: `true` zum Überschreiben bestehender Daten oder `false`, wenn vorhandene Daten nicht überschrieben werden sollen.|  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 Ein u`int32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="see-also"></a>Weitere Informationen  
 [Konfigurieren von Servernetzwerkprotokollen und Netzwerkbibliotheken](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)  
  
  
