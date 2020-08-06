---
title: Reporting Services-Anmeldung (Dialogfeld) (SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.reportservicelogin.f1
ms.assetid: 2037d797-0b61-44c7-931f-6c689c3fc733
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 232ee51614a668b07263c3e3a4182f23652135bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721040"
---
# <a name="reporting-services-login-dialog-box-ssrs"></a><span data-ttu-id="46ce0-102">Reporting Services-Anmeldung (Dialogfeld) (SSRS)</span><span class="sxs-lookup"><span data-stu-id="46ce0-102">Reporting Services Login Dialog Box (SSRS)</span></span>
  <span data-ttu-id="46ce0-103">Verwenden Sie das Dialogfeld **Reporting Services-Anmeldung** , um die Anmeldeinformationen zum Veröffentlichen von Berichten auf dem Berichtsserver bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="46ce0-103">Use the **Reporting Services Login** dialog box to provide credentials to publish reports to the report server.</span></span>  
  
-   <span data-ttu-id="46ce0-104">**Hinweis** Wenn Sie zum ersten Mal einen Bericht auf einem Berichts Server veröffentlicht haben, nachdem Sie die Bereitstellungs Eigenschaft **TargetServerURL** für ein Projekt festgelegt haben, überprüfen Sie, ob der angegebene Servername dem Wert entspricht `http://localhost/reportserver` und nicht `http://localhost/reports` .</span><span class="sxs-lookup"><span data-stu-id="46ce0-104">**Note** If this is the first time you have published a report to a report server since set you set the deployment property **TargetServerURL** for a project, verify that the server name you specified is similar to `http://localhost/reportserver`, and not `http://localhost/reports`.</span></span> <span data-ttu-id="46ce0-105">Durch Angeben des `reports` -Verzeichnisses auf dem lokalen Server anstelle des `reportserver` -Verzeichnisses wird indirekt bewirkt, dass dieses Dialogfeld geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="46ce0-105">Specifying the `reports` directory on the local server instead of the `reportserver` directory indirectly causes this dialog box to open.</span></span> <span data-ttu-id="46ce0-106">Weitere Informationen zum Festlegen von **TargetServerURL** finden Sie unter [Festlegen von Bereitstellungseigenschaften (Reporting Services)](set-deployment-properties-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="46ce0-106">For more information about setting **TargetServerURL**, see [Set Deployment Properties &#40;Reporting Services&#41;](set-deployment-properties-reporting-services.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="46ce0-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="46ce0-107">Options</span></span>  
 <span data-ttu-id="46ce0-108">**Server**</span><span class="sxs-lookup"><span data-stu-id="46ce0-108">**Server**</span></span>  
 <span data-ttu-id="46ce0-109">Zeigt den Namen des Berichtsservers an.</span><span class="sxs-lookup"><span data-stu-id="46ce0-109">Displays the name of the report server.</span></span> <span data-ttu-id="46ce0-110">Beispiel: `http://localhost/reportserver`.</span><span class="sxs-lookup"><span data-stu-id="46ce0-110">For example, `http://localhost/reportserver`.</span></span> <span data-ttu-id="46ce0-111">Für Berichtsserver, die einen anderen Port verwenden als Standardport 80, schließen Sie die Portnummer ein.</span><span class="sxs-lookup"><span data-stu-id="46ce0-111">For report servers that use a different port than default port 80, include the port number.</span></span> <span data-ttu-id="46ce0-112">Beispiel: `http://localhost:81/reportserver`.</span><span class="sxs-lookup"><span data-stu-id="46ce0-112">For example, `http://localhost:81/reportserver`.</span></span>  
  
 <span data-ttu-id="46ce0-113">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="46ce0-113">**User name**</span></span>  
 <span data-ttu-id="46ce0-114">Geben Sie den Benutzernamen ein, der beim Anmelden am Webdienst verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="46ce0-114">Type the user name to log in to the Web service.</span></span>  
  
 <span data-ttu-id="46ce0-115">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="46ce0-115">**Password**</span></span>  
 <span data-ttu-id="46ce0-116">Geben Sie das Kennwort ein, das beim Anmelden am Webdienst verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="46ce0-116">Type the password to log in to the Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46ce0-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46ce0-117">See Also</span></span>  
 <span data-ttu-id="46ce0-118">[Datenverbindungen, Datenquellen und Verbindungs Zeichenfolgen in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="46ce0-118">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="46ce0-119">[Angeben von Anmelde Informationen und Verbindungsinformationen für Berichtsdaten Quellen](../report-data/specify-credential-and-connection-information-for-report-data-sources.md) [Berichts-Designer F1-Hilfe](report-designer-f1-help.md)</span><span class="sxs-lookup"><span data-stu-id="46ce0-119">[Specify Credential and Connection Information for Report Data Sources](../report-data/specify-credential-and-connection-information-for-report-data-sources.md) [Report Designer F1 Help](report-designer-f1-help.md)</span></span>  
  
  
