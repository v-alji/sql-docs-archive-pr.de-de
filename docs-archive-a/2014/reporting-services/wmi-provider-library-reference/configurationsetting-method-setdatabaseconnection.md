---
title: 'SetDatabaseConnection-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetDatabaseConnection (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDatabaseConnection method
ms.assetid: c040aa78-92b8-41e4-9ae2-eff9fcdddc5b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b5c62777edd1fab2b0cb3babc13ab09f7bcf32a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722389"
---
# <a name="setdatabaseconnection-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="6ef62-102">SetDatabaseConnection-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="6ef62-102">SetDatabaseConnection Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="6ef62-103">Legt die Berichtsserver-Datenbankverbindung auf eine bestimmte Berichtsserver-Datenbank fest</span><span class="sxs-lookup"><span data-stu-id="6ef62-103">Sets the report server database connection to a particular report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ef62-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6ef62-104">Syntax</span></span>  
  
```vb  
Public Sub SetDatabaseConnection(Server as String, _  
    DatabaseName as string, CredentialsType as Integer, _  
    Username as String, Password as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void BackupEncryptionKey(string Server,   
    string DatabaseName, Int32 CredentialsType,   
    string UserName, string Password, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ef62-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6ef62-105">Parameters</span></span>  
 <span data-ttu-id="6ef62-106">*Server*</span><span class="sxs-lookup"><span data-stu-id="6ef62-106">*Server*</span></span>  
 <span data-ttu-id="6ef62-107">Der Name der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz, die zum Hosten der Berichtsserver-Datenbank verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6ef62-107">The name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is used to host the report server database.</span></span>  
  
 <span data-ttu-id="6ef62-108">*DatabaseName*</span><span class="sxs-lookup"><span data-stu-id="6ef62-108">*DatabaseName*</span></span>  
 <span data-ttu-id="6ef62-109">Der Name der Berichtsserver-Datenbank</span><span class="sxs-lookup"><span data-stu-id="6ef62-109">The name of the report server database.</span></span>  
  
 <span data-ttu-id="6ef62-110">*CredentialsType*</span><span class="sxs-lookup"><span data-stu-id="6ef62-110">*CredentialsType*</span></span>  
 <span data-ttu-id="6ef62-111">Der Typ der zu verwendenden Anmeldeinformationen für die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="6ef62-111">The type of credentials to use for the connection.</span></span> <span data-ttu-id="6ef62-112">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="6ef62-112">Values can be:</span></span>  
  
-   <span data-ttu-id="6ef62-113">0 – Windows</span><span class="sxs-lookup"><span data-stu-id="6ef62-113">0 - Windows</span></span>  
  
-   <span data-ttu-id="6ef62-114">1 – [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ef62-114">1 - [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="6ef62-115">2 – Windows-Dienst</span><span class="sxs-lookup"><span data-stu-id="6ef62-115">2 - Windows Service</span></span>  
  
 <span data-ttu-id="6ef62-116">*UserName*</span><span class="sxs-lookup"><span data-stu-id="6ef62-116">*UserName*</span></span>  
 <span data-ttu-id="6ef62-117">Der Kontoname, der zum Herstellen der Verbindung mit der Berichtsserver-Datenbank verwendet wird</span><span class="sxs-lookup"><span data-stu-id="6ef62-117">The account name used to connect to the report server database.</span></span>  
  
 <span data-ttu-id="6ef62-118">*Kennwort*</span><span class="sxs-lookup"><span data-stu-id="6ef62-118">*Password*</span></span>  
 <span data-ttu-id="6ef62-119">Das Kennwort, das zum Herstellen der Verbindung mit der Berichtsserver-Datenbank verwendet wird</span><span class="sxs-lookup"><span data-stu-id="6ef62-119">The password used to connect to the report server database.</span></span>  
  
 <span data-ttu-id="6ef62-120">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="6ef62-120">*HRESULT*</span></span>  
 <span data-ttu-id="6ef62-121">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="6ef62-121">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ef62-122">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6ef62-122">Return Value</span></span>  
 <span data-ttu-id="6ef62-123">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6ef62-123">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="6ef62-124">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="6ef62-124">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="6ef62-125">Ein Wert ungleich 0 (null) gibt an, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="6ef62-125">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ef62-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6ef62-126">Remarks</span></span>  
 <span data-ttu-id="6ef62-127">Wenn der *CredentialsType* -Parameter auf 0 (Windows) festgelegt ist, müssen die Parameter *UserName* und *Password* festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="6ef62-127">When the *CredentialsType* parameter is set to 0 (Windows), the *UserName* and *Password* parameters must be set.</span></span> <span data-ttu-id="6ef62-128">Der *UserName* -Parameter muss die Form „domain\username“ haben, und der Wert muss einen gültigen Windows-Anmeldenamen darstellen.</span><span class="sxs-lookup"><span data-stu-id="6ef62-128">The *UserName* parameter must be in the form "domain\username", and the value must represent a valid Windows logon.</span></span>  
  
 <span data-ttu-id="6ef62-129">Wenn der *CredentialsType* -Parameter auf 1 ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]) festgelegt ist, muss der im *UserName* -Parameter übergebene Wert den Anforderungen an einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldenamen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="6ef62-129">When the *CredentialsType* parameter is set to 1 ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]), the value passed in the *UserName* parameter must conform to the requirements of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login name.</span></span>  
  
 <span data-ttu-id="6ef62-130">Wenn der *CredentialsType* -Parameter auf 2 (Windows-Dienst) festgelegt ist, verwendet der Berichtsserver die integrierte Sicherheit, um eine Verbindung mit der Berichtsserver-Datenbank herzustellen, und die Parameter *UserName* und *Password* werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="6ef62-130">When the *CredentialsType* parameter is set to 2 (Windows Service), the report server uses integrated security to connect to the report server database and the *UserName* and *Password* parameters are ignored.</span></span> <span data-ttu-id="6ef62-131">Der Report Server-Webdienst verwendet entweder das [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)]-Konto oder das Konto eines Anwendungspools und das Windows-Dienstkonto, um auf die Berichtsserver-Datenbank zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="6ef62-131">The Reporting Server Web service will use either the [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] account or an application pool's account and the Windows service account to access the report server database.</span></span>  
  
 <span data-ttu-id="6ef62-132">Die „SetDatabaseConnection“-Methode verschlüsselt und speichert beim Aufruf die Anmelde- und Datenbankinformationen in der Konfigurationsdatei für den angegebenen Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="6ef62-132">When called, the SetDatabaseConnection method encrypts and stores the credentials and database information in the configuration file for the specified report server.</span></span>  
  
 <span data-ttu-id="6ef62-133">Die „SetDatabaseConnection“-Methode überprüft nicht, ob der Berichtsserver mithilfe der angegebenen Daten eine Verbindung mit der Berichtsserver-Datenbank herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="6ef62-133">The SetDatabaseConnection method does not check that the report server can connect to the report server database using the data specified.</span></span>  
  
 <span data-ttu-id="6ef62-134">Wenn die „ConnectionPoolSize“-Eigenschaft zum ersten Mal festgelegt wird, werden folgende Prozessoren zugrunde gelegt: ConnectionPoolSize = Anzahl der Prozessoren x 75.</span><span class="sxs-lookup"><span data-stu-id="6ef62-134">When set for the first time, the ConnectionPoolSize property is set based on the following processors: ConnectionPoolSize = #Processors \* 75.</span></span>  
  
 <span data-ttu-id="6ef62-135">Die „SetDatabaseConnection“-Methode erteilt den angegebenen Konten keine Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="6ef62-135">The SetDatabaseConnection method does not grant permissions to the specified account(s).</span></span> <span data-ttu-id="6ef62-136">Sie müssen die [GenerateDatabaseRightsScript](configurationsetting-method-generatedatabaserightsscript.md) -Methode für jedes Konto aufrufen, das Zugriff auf die Berichtsserver-Datenbank erfordert, und dann das resultierende Skript ausführen.</span><span class="sxs-lookup"><span data-stu-id="6ef62-136">You must call the [GenerateDatabaseRightsScript](configurationsetting-method-generatedatabaserightsscript.md) method for each account that requires access to the report server database and run the resulting script.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ef62-137">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6ef62-137">Requirements</span></span>  
 <span data-ttu-id="6ef62-138">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ef62-138">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ef62-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6ef62-139">See Also</span></span>  
 [<span data-ttu-id="6ef62-140">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="6ef62-140">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
