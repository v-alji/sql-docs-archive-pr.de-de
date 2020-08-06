---
title: Konfigurieren einer Firewall für FILESTREAM-Zugriff | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- Windows Firewall [Database Engine], FILESTREAM
- FILESTREAM [SQL Server], Windows Firewall
ms.assetid: fc52007f-c26f-4f8e-b9d8-55a7978f4d56
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8b787403fefdd336dd82bf7ccb93cdf21fe5a90d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621024"
---
# <a name="configure-a-firewall-for-filestream-access"></a><span data-ttu-id="b130f-102">Konfigurieren einer Firewall für FILESTREAM-Zugriff</span><span class="sxs-lookup"><span data-stu-id="b130f-102">Configure a Firewall for FILESTREAM Access</span></span>
  <span data-ttu-id="b130f-103">Um FILESTREAM in einer firewallgeschützten Umgebung verwenden zu können, müssen Client und Server in der Lage sein, DNS-Namen zu dem Server aufzulösen, der die FILESTREAM-Dateien enthält.</span><span class="sxs-lookup"><span data-stu-id="b130f-103">To use FILESTREAM in a firewall-protected environment, both the client and server must be able to resolve DNS names to the server that contains the FILESTREAM files.</span></span> <span data-ttu-id="b130f-104">Es ist für FILESTREAM erforderlich, dass unter Windows die Ports 139 und 445 für Dateifreigabe geöffnet sind.</span><span class="sxs-lookup"><span data-stu-id="b130f-104">FILESTREAM requires the Windows file-sharing ports 139 and 445 to be open.</span></span>  
  
### <a name="to-open-the-windows-file-sharing-ports-on-a-computer-that-is-running-windows-7"></a><span data-ttu-id="b130f-105">So öffnen Sie die Ports für die Datenfreigabe auf einem Computer unter Windows 7</span><span class="sxs-lookup"><span data-stu-id="b130f-105">To open the Windows file-sharing ports on a computer that is running Windows 7</span></span>  
  
1.  <span data-ttu-id="b130f-106">Öffnen Sie in der Systemsteuerung **Windows-Firewall**.</span><span class="sxs-lookup"><span data-stu-id="b130f-106">In Control Panel, open **Windows Firewall**.</span></span>  
  
2.  <span data-ttu-id="b130f-107">Klicken Sie im linken Bereich auf **Erweiterte Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="b130f-107">In the left pane, click **Advanced settings**.</span></span> <span data-ttu-id="b130f-108">Wenn Sie zur Eingabe eines Administratorkennworts oder einer Bestätigung aufgefordert werden, geben Sie das Kennwort oder eine entsprechende Bestätigung ein.</span><span class="sxs-lookup"><span data-stu-id="b130f-108">If you're prompted for an administrator password or confirmation, type the password or provide confirmation.</span></span>  
  
3.  <span data-ttu-id="b130f-109">Klicken Sie im Dialogfeld **Windows-Firewall mit erweiterter Sicherheit** im linken Bereich auf **Eingehende Regeln**, und klicken Sie dann im rechten Bereich auf **Neue Regel**.</span><span class="sxs-lookup"><span data-stu-id="b130f-109">In the **Windows Firewall with Advanced Security** dialog box, in the left pane, click **Inbound Rules**, and then, in the right pane, click **New Rule**.</span></span>  
  
4.  <span data-ttu-id="b130f-110">Folgen Sie den Anweisungen im Assistenten für neue eingehende Regel, um TCP-Port 139 hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b130f-110">Follow the instructions in the New Inbound Rule wizard to add TCP port 139.</span></span>  
  
5.  <span data-ttu-id="b130f-111">Wiederholen Sie den vorherigen Schritt, um TCP-Port 445 hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b130f-111">Repeat the previous step to add TCP port 445.</span></span>  
  
6.  <span data-ttu-id="b130f-112">Schließen Sie das Dialogfeld **Windows-Firewall mit erweiterter Sicherheit** .</span><span class="sxs-lookup"><span data-stu-id="b130f-112">Close the **Windows Firewall with Advanced Security** dialog box.</span></span>  
  
  
