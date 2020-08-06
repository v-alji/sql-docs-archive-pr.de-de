---
title: Testen der Berechtigungen eines Benutzers (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 83a03b85-ea7f-4b4a-b19b-f7eca534ffae
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8c109eebb4bf06bf7605ca3b7b5930ce18951e41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618747"
---
# <a name="test-a-user39s-permissions-master-data-services"></a><span data-ttu-id="5085f-102">Testen der Berechtigungen eines Benutzers (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5085f-102">Test a User&#39;s Permissions (Master Data Services)</span></span>
  <span data-ttu-id="5085f-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]können Sie einen Testbenutzer erstellen und sich bei der Webanwendung anmelden, um Berechtigungen zu testen. Wenn ein Benutzer versucht, auf die [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -URL zuzugreifen, werden die Anmeldeinformationen des Benutzers authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="5085f-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can create a test user and log into the web application to test permissions.When a user attempts to access the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] URL, the user's credentials are authenticated.</span></span> <span data-ttu-id="5085f-104">In Internet Explorer wird über Sicherheitseinstellungen gesteuert, ob dies automatisch stattfindet oder ob der Benutzer einen Benutzernamen und ein Kennwort eingeben muss.</span><span class="sxs-lookup"><span data-stu-id="5085f-104">In Internet Explorer, security settings control whether this occurs automatically or if the user must enter a user name and password.</span></span> <span data-ttu-id="5085f-105">Um diese Einstellungen zu ändern, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="5085f-105">To change these settings, complete the following steps:</span></span>  
  
### <a name="to-test-a-users-security"></a><span data-ttu-id="5085f-106">So testen Sie die Sicherheitseinstellungen für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="5085f-106">To test a user's security</span></span>  
  
1.  <span data-ttu-id="5085f-107">Klicken Sie in Internet Explorer 7 und höher auf **Extras**, **Internetoptionen**und dann auf die Registerkarte **Sicherheit** .</span><span class="sxs-lookup"><span data-stu-id="5085f-107">In Internet Explorer 7 and later, click **Tools**, **Internet Options**, and then click the **Security** tab.</span></span>  
  
2.  <span data-ttu-id="5085f-108">Klicken Sie auf **Lokales Intranet** und dann auf die Schaltfläche **Stufe anpassen** .</span><span class="sxs-lookup"><span data-stu-id="5085f-108">Click **Local Intranet** and then the **Custom Level** button.</span></span>  
  
3.  <span data-ttu-id="5085f-109">Wählen Sie im Abschnitt **Benutzerauthentifizierung** die Option **Nach Benutzername und Kennwort fragen**aus.</span><span class="sxs-lookup"><span data-stu-id="5085f-109">In the **User Authentication** section, choose **Prompt for user name and password**.</span></span>  
  
4.  <span data-ttu-id="5085f-110">Das nächste Mal, wenn Sie das Browserfenster öffnen, werden Sie zur Eingabe eines Benutzernamens und Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="5085f-110">The next time you open the browser window, you will be prompted for a user name and password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5085f-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5085f-111">See Also</span></span>  
 [<span data-ttu-id="5085f-112">Sicherheit &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5085f-112">Security &#40;Master Data Services&#41;</span></span>](security-master-data-services.md)  
  
  
