---
title: SQLXML ist nicht in SQL Server installiert | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: 3dbb4f65-41de-48b8-ad62-47c9d7932de3
author: rothja
ms.author: jroth
ms.openlocfilehash: ffa4cfd8b18dbfd9b4ba05599e2a973ac5f6e888
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619703"
---
# <a name="sqlxml-is-not-installed-in-sql-server"></a><span data-ttu-id="bbe4f-102">SQLXML ist in SQL Server nicht installiert</span><span class="sxs-lookup"><span data-stu-id="bbe4f-102">SQLXML Is Not Installed in SQL Server</span></span>
  <span data-ttu-id="bbe4f-103">Vor der Veröffentlichung von [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]wurde SQLXML 4.0 mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] veröffentlicht und war Bestandteil der Standardinstallation aller [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Versionen außer [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bbe4f-103">Before [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], SQLXML 4.0 was released with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and was part of the default installation of all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versions except for [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="bbe4f-104">Ab [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]ist die neueste Version von SQLXML (SQLXML 4.0 SP1) nicht mehr in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]enthalten.</span><span class="sxs-lookup"><span data-stu-id="bbe4f-104">Starting with [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the latest version of SQLXML (SQLXML 4.0 SP1) is no longer included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bbe4f-105">Um SQLXML 4,0 SP1 zu installieren, wenn es verfügbar ist, laden Sie es vom [Installationsort für SQLXML SP1](https://www.microsoft.com/download/details.aspx?id=44272)herunter.</span><span class="sxs-lookup"><span data-stu-id="bbe4f-105">To install SQLXML 4.0 SP1 when it is available, download it from [Install Location for SQLXML SP1](https://www.microsoft.com/download/details.aspx?id=44272).</span></span>  
  
 <span data-ttu-id="bbe4f-106">Wenn eine Anwendung in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgeführt wird und SQLXML 4.0 erfordert und auf dem Computer [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] nicht installiert ist, müssen Sie SQLXML 4.0 SP1 herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="bbe4f-106">If an application runs on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and requires SQLXML 4.0, and if the computer does not have [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], you must download and install SQLXML 4.0 SP1.</span></span>  
  
## <a name="sqlxml-40-sp1-behavior-with-new-data-types-using-sqloledb-and-sql-server-native-client-ole-db-provider"></a><span data-ttu-id="bbe4f-107">Verhalten von SQLXML 4.0 SP1 mit neuen Datentypen, die SQLOLEDB und SQL Server Native Client-OLE DB-Anbieter verwenden</span><span class="sxs-lookup"><span data-stu-id="bbe4f-107">SQLXML 4.0 SP1 Behavior with New Data Types Using SQLOLEDB and SQL Server Native Client OLE DB Provider</span></span>  
 <span data-ttu-id="bbe4f-108">Mit [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] werden die folgenden Datentypen eingeführt, die von SQLXML-Entwicklern verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="bbe4f-108">[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] introduces the following data types, which developers using SQLXML might want to use:</span></span>  
  
-   `Date`  
  
-   `Time`  
  
-   `DateTime2`  
  
-   `DateTimeOffset`  
  
 <span data-ttu-id="bbe4f-109">Bei Verwendung von SQLXML 4.0 SP1 mit SQLOLEDB (in Windows Data Access Components, früher Microsoft Data Access Components) oder [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-OLE DB in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] werden diese neuen Typen Entwicklern als Zeichenfolgen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bbe4f-109">When using SQLXML 4.0 SP1 with either SQLOLEDB (from Windows Data Access Components, formerly Microsoft Data Access Components) or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], these new types will appear as strings to a developer.</span></span> <span data-ttu-id="bbe4f-110">SQLXML 4.0 SP1 aktiviert diese vier neuen Datentypen als integrierte skalare Typen, wenn diese mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-OLE DB-Anbieter 11.0 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bbe4f-110">SQLXML 4.0 SP1 will enable these four new data types as built-in scalar types when used with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider 11.0.</span></span> <span data-ttu-id="bbe4f-111">Wenn Sie SQLXML 4.0 SP1 noch nicht heruntergeladen haben, kann die Zuordnung dieser Typen zu anderen als Zeichenfolgentypen zum Abschneiden einiger Daten führen.</span><span class="sxs-lookup"><span data-stu-id="bbe4f-111">Until you download SQLXML 4.0 SP1, mapping these types to non-string types might cause truncation of some data.</span></span> <span data-ttu-id="bbe4f-112">Beispielsweise führt die Zuordnung zu dazu, dass `DateTime2` `xsd:date` die Daten auf die [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] `DateTime` Genauigkeit von 3,33 Millisekunden gekürzt werden.</span><span class="sxs-lookup"><span data-stu-id="bbe4f-112">For example, mapping `DateTime2` to `xsd:date` will cause data to be truncated to the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] `DateTime` precision of 3.33 milliseconds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe4f-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bbe4f-113">See Also</span></span>  
 [<span data-ttu-id="bbe4f-114">SQLXML 4.0-Programmierkonzepte</span><span class="sxs-lookup"><span data-stu-id="bbe4f-114">SQLXML 4.0 Programming Concepts</span></span>](sqlxml-4-0-programming-concepts.md)  
  
  
