---
title: Installieren von Microsoft Connector für 1,1 SAP BW | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3bfb9023-9597-4f59-9085-4b9057e7702e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ef96f38054f04e71de72bda0bbb12f8f003ef20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617184"
---
# <a name="installing-the-microsoft-connector-for-11-sap-bw"></a><span data-ttu-id="2aff9-102">Installieren von Microsoft Connector 1.1 für SAP BW</span><span class="sxs-lookup"><span data-stu-id="2aff9-102">Installing the Microsoft Connector for 1.1 SAP BW</span></span>
  <span data-ttu-id="2aff9-103">Um den [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1,1 für SAP BW und seine Dokumentation zu installieren, laden Sie das Windows Installer-Paket von der SQL Server Feature Pack-Webseite herunter, und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="2aff9-103">To install the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW and its documentation, download and run the Windows installer package from the SQL Server Feature Pack Web page.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2aff9-104">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="2aff9-104">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="2aff9-105">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="2aff9-105">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2aff9-106">Das Extrahieren von Daten aus SAP NetWeaver BW erfordert zusätzliche SAP-Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="2aff9-106">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="2aff9-107">Stimmen Sie diese Anforderungen mit SAP ab.</span><span class="sxs-lookup"><span data-stu-id="2aff9-107">Check with SAP to verify these requirements.</span></span>  
  
## <a name="required-sap-files"></a><span data-ttu-id="2aff9-108">Erforderliche SAP-Dateien</span><span class="sxs-lookup"><span data-stu-id="2aff9-108">Required SAP Files</span></span>  
 <span data-ttu-id="2aff9-109">[!INCLUDE[msCoName](../includes/msconame-md.md)]Wenn Sie den Connector 1,1 für SAP BW verwenden möchten, müssen Sie die SAP-Front-End-Software (SAP GUI) nicht auf dem lokalen Computer installieren.</span><span class="sxs-lookup"><span data-stu-id="2aff9-109">To use the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW, you do not have to install the SAP Front End software (SAP GUI) on the local computer.</span></span>  
  
 <span data-ttu-id="2aff9-110">Sie müssen jedoch die SAP .NET-Connector-Datei librfc32.dll im Ordner Windows in den Unterordner system kopieren.</span><span class="sxs-lookup"><span data-stu-id="2aff9-110">However you must copy the SAP .NET connector file, librfc32.dll, into the system subfolder in the Windows folder.</span></span> <span data-ttu-id="2aff9-111">(In der Regel ist der Speicherort dieses Ordners **C:\Windows\system32**.)</span><span class="sxs-lookup"><span data-stu-id="2aff9-111">(Typically, this folder location is **C:\Windows\system32**.)</span></span>  
  
## <a name="considerations-for-64-bit-computers"></a><span data-ttu-id="2aff9-112">Überlegungen für 64-Bit-Computer</span><span class="sxs-lookup"><span data-stu-id="2aff9-112">Considerations for 64-bit Computers</span></span>  
 <span data-ttu-id="2aff9-113">Der [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1,1 für SAP BW unterstützt die 64-Bit-Version von Windows vollständig [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2aff9-113">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW fully supports the 64-bit version of [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span></span> <span data-ttu-id="2aff9-114">Auf einem 64-Bit-Computer [!INCLUDE[msCoName](../includes/msconame-md.md)] weist der Connector 1,1 für SAP BW die folgenden zusätzlichen Anforderungen auf:</span><span class="sxs-lookup"><span data-stu-id="2aff9-114">On a 64-bit computer, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW has the following additional requirements:</span></span>  
  
-   <span data-ttu-id="2aff9-115">Wenn Sie Pakete im 64-Bit-Modus auf einem 64-Bit-Windows-Betriebssystem ausführen möchten, kopieren Sie die 64-Bit-Version der SAP GUI-Datei „librfc32.dll“ in den Unterordner **system32** des Windows-Ordners.</span><span class="sxs-lookup"><span data-stu-id="2aff9-115">To run packages in 64-bit mode on any 64-bit Windows operating system, copy the 64-bit version of the SAP GUI file, librfc32.dll, into the **system32** folder of the Windows folder.</span></span> <span data-ttu-id="2aff9-116">(In der Regel ist der Speicherort dieser Datei **C:\Windows\system32**.)</span><span class="sxs-lookup"><span data-stu-id="2aff9-116">(Typically, this file location is **C:\Windows\system32**.)</span></span>  
  
-   <span data-ttu-id="2aff9-117">Wenn Sie Pakete im 32-Bit-Modus auf einem 64-Bit-Windows-Betriebssystem ausführen möchten, kopieren Sie die SAP GUI-Datei „librfc32.dll“ in den Unterordner **SysWow64** des Windows-Ordners.</span><span class="sxs-lookup"><span data-stu-id="2aff9-117">To run packages in 32-bit mode on any 64-bit Windows operating system, copy the SAP GUI file, librfc32.dll, into the **SysWow64** folder of the Windows folder.</span></span> <span data-ttu-id="2aff9-118">(In der Regel ist der Speicherort dieses Ordners **C:\Windows\SysWow64**.)</span><span class="sxs-lookup"><span data-stu-id="2aff9-118">(Typically, this folder location is **C:\Windows\SysWow64**.)</span></span>  
  
  
