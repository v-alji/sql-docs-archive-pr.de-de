---
title: SetValue-Methode (ServerSettingsGeneralFlag-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetValue Method (ServerSettingsGeneralFlag Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetValue method
ms.assetid: a889feac-c0e0-4635-b506-843863d86967
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 74c4c189b72b7a469794e0828faf062a88cdf46f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726809"
---
# <a name="setvalue-method-serversettingsgeneralflag-class"></a>SetValue-Methode (ServerSettingsGeneralFlag-Klasse)
  Legt alle Werte des Flags fest, auf das verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
object  
.SetValue(  
Value  
)  
  
```  
  
## <a name="parts"></a>Bestandteile  
 *object*  
 Ein [ServerSettingsGeneralFlag-Klassenobjekt](serversettingsgeneralflag-class.md) , das ein allgemeines Flag für die Servereinstellungen darstellt.  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|BESCHREIBUNG|  
|---------------|-----------------|  
|*Wert*|Ein boleescher Wert, der den Wert des Flags angibt.|  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="see-also"></a>Weitere Informationen  
 [Konfigurieren von Servernetzwerkprotokollen und Netzwerkbibliotheken](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)  
  
  
