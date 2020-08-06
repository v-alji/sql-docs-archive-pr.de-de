---
title: StartMode-Eigenschaft (SqlService-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- StartMode Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- StartMode property
ms.assetid: c0c2c7f8-d4ae-44f2-ad8e-aecfcb7c2878
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: bafffcc3c8f82f69896d0a22e9b0a9060e04cd10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717620"
---
# <a name="startmode-property-sqlservice-class"></a>StartMode-Eigenschaft (SqlService-Klasse)
  Ruft den Startmodus des Dienstes ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
object  
.StartMode [= value]  
```  
  
## <a name="parts"></a>Bestandteile  
 *object*  
 Ein [SqlService-Klassenobjekt](sqlservice-class.md) , das den Dienst darstellt.  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 Ein uint32-Wert, der den Modus des Diensts angibt.  
  
 Folgende Werte sind möglich:  
  
 Start  
 Wert = 0. Dienst wurde durch das Betriebssystemladeprogramm gestartet. Diese Option ist nur für Treiberdienste gültig.  
  
 System  
 Wert = 1. Der Dienst wurde durch die `IoInitSystem`-Methode gestartet. Diese Option ist nur für Treiberdienste gültig.  
  
 Automatisch  
 Wert = 2. Der Dienst soll während des Systemstarts automatisch vom Dienstkontroll-Manager gestartet werden.  
  
 Manuell  
 Wert = 3. Der Dienst soll vom Computer-manager gestartet werden, wenn ein Prozess die `StartService`-Methode aufruft.  
  
 Disabled  
 Wert = 4. Der Dienst kann nicht gestartet werden.  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="see-also"></a>Weitere Informationen  
 [Starten und Beenden von Diensten](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  
