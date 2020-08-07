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
# <a name="setdefaults-method-serversettings-class"></a><span data-ttu-id="e1885-102">SetDefaults-Methode (ServerSettings-Klasse)</span><span class="sxs-lookup"><span data-stu-id="e1885-102">SetDefaults Method (ServerSettings Class)</span></span>
  <span data-ttu-id="e1885-103">Legt alle Standardwerte für die Instanz von fest [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , wobei die Option zum Überschreiben vorhandener Daten vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e1885-103">Sets all the default values for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1885-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1885-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="e1885-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="e1885-105">Parts</span></span>  
 <span data-ttu-id="e1885-106">*object*</span><span class="sxs-lookup"><span data-stu-id="e1885-106">*object*</span></span>  
 <span data-ttu-id="e1885-107">Ein [ServerSettings-Klassenobjekt](serversettings-class.md) , das Einstellungen eine [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Clientinstanz darstellt.</span><span class="sxs-lookup"><span data-stu-id="e1885-107">A [ServerSettings Class](serversettings-class.md) object that represents a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="e1885-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="e1885-108">Parameters</span></span>  
  
|<span data-ttu-id="e1885-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="e1885-109">Parameter</span></span>|<span data-ttu-id="e1885-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e1885-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e1885-111">*Overschreiteall*</span><span class="sxs-lookup"><span data-stu-id="e1885-111">*OverwriteAll*</span></span>|<span data-ttu-id="e1885-112">Ein boleescher Wert, der angibt, ob vorhandene Werte in der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] überschreiben werden sollen: `true` zum Überschreiben bestehender Daten oder `false`, wenn vorhandene Daten nicht überschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e1885-112">A Boolean value that specifies whether to overwrite existing values on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: `true` to overwrite existing data, or `false` if existing data is not to be overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e1885-113">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e1885-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="e1885-114">Ein u`int32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="e1885-114">A u`int32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1885-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e1885-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1885-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e1885-116">See Also</span></span>  
 <span data-ttu-id="e1885-117">[Konfigurieren von Servernetzwerkprotokollen und Netzwerkbibliotheken](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="e1885-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
