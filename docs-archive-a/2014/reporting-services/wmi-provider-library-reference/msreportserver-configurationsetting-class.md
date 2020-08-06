---
title: MSReportServer_ConfigurationSetting-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- MSReportServer_ConfigurationSetting Class
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- WMI provider [Reporting Services], MSReportServer_ConfigurationSetting class
- MSReportServer_ConfigurationSetting class
ms.assetid: 874be718-54b9-49e8-a3d6-b83a0ba13dc3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d7f1481dc037e1b15f6fc5d2da3e65dcf7cdf40d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722289"
---
# <a name="msreportserver_configurationsetting-class"></a><span data-ttu-id="52b91-102">MSReportServer_ConfigurationSetting-Klasse</span><span class="sxs-lookup"><span data-stu-id="52b91-102">MSReportServer_ConfigurationSetting Class</span></span>
  <span data-ttu-id="52b91-103">Stellt die Installationsparameter und die Laufzeitparameter einer Berichtsserverinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="52b91-103">Represents the installation and runtime parameters of a report server instance.</span></span> <span data-ttu-id="52b91-104">Diese Parameter werden in der Konfigurationsdatei für den Berichtsserver gespeichert.</span><span class="sxs-lookup"><span data-stu-id="52b91-104">These parameters are stored in the configuration file for the report server.</span></span>  
  
 <span data-ttu-id="52b91-105">Eine Liste aller Member dieses Typs finden Sie unter [MSReportServer_ConfigurationSetting Members](msreportserver-configurationsetting-members.md).</span><span class="sxs-lookup"><span data-stu-id="52b91-105">For a list of all members of this type, see [MSReportServer_ConfigurationSetting Members](msreportserver-configurationsetting-members.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52b91-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="52b91-106">Syntax</span></span>  
  
```vb  
Public Class MSReportServer_ConfigurationSetting  
```  
  
```csharp  
public class MSReportServer_ConfigurationSetting  
```  
  
## <a name="thread-safety"></a><span data-ttu-id="52b91-107">Threadsicherheit</span><span class="sxs-lookup"><span data-stu-id="52b91-107">Thread Safety</span></span>  
 <span data-ttu-id="52b91-108">Alle öffentlichen statischen Member dieses Typs (**Shared** in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]) sind für Vorgänge mit mehreren Threads sicher.</span><span class="sxs-lookup"><span data-stu-id="52b91-108">Any public static (**Shared** in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]) members of this type are safe for multithreaded operations.</span></span> <span data-ttu-id="52b91-109">Für Instanzmember kann nicht gewährleistet werden, dass sie für Threads sicher sind.</span><span class="sxs-lookup"><span data-stu-id="52b91-109">Any instance members are not guaranteed to be thread-safe.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52b91-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="52b91-110">Example</span></span>  
 <span data-ttu-id="52b91-111">Um den folgenden Code auszuführen, fügen Sie den Servernamen anstelle der einzelnen hinzu \<*servername*> .</span><span class="sxs-lookup"><span data-stu-id="52b91-111">To run the following code, add your server name in place of each \<*servername*>.</span></span> <span data-ttu-id="52b91-112">Aktualisieren Sie ggf. den Pfad, sodass dieser auf den Installationspfad verweist.</span><span class="sxs-lookup"><span data-stu-id="52b91-112">Update the path to point to your installation location, if it is not the default.</span></span> <span data-ttu-id="52b91-113">Im folgenden Codebeispiel wird jede Eigenschaft in der [MSReportServer_ConfigurationSetting](msreportserver-configurationsetting-class.md) -Klasse durchlaufen, wobei der Name jeder Eigenschaft und deren Wert in die Konsole geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="52b91-113">The following code example iterates through each property in the [MSReportServer_ConfigurationSetting](msreportserver-configurationsetting-class.md) class, printing the name of each property and its value to the console.</span></span>  
  
```vb  
Imports System  
Imports System.Management  
Imports System.IO  
  
Module Module1  
  
    Sub Main()  
        Const machineWmiNamespace As String = "\\<servername>\root\Microsoft\SqlServer\ReportServer\<InstanceName>\v10"  
        Const wmiNamespace As String = "\\<servername>\root\Microsoft\SqlServer\ReportServer\<InstanceName>\v10:MSReportServer_ConfigurationSetting"  
  
        Dim connOptions As New ConnectionOptions()  
        connOptions.Authentication = AuthenticationLevel.Default  
  
        Dim getOptions As New ObjectGetOptions()  
        getOptions.Timeout = New System.TimeSpan(0, 0, 30)  
  
        Dim machineScope As New ManagementScope(machineWmiNamespace, connOptions)  
        machineScope.Connect()  
  
        Dim scope As ManagementScope = Nothing  
  
        scope = New ManagementScope(wmiNamespace, connOptions)  
        scope.Connect()  
  
        Dim path As New ManagementPath("MSReportServer_Instance")  
        Dim serverClass As New ManagementClass(scope, path, getOptions)  
  
        serverClass.Get()  
  
        Dim instances As ManagementObjectCollection = serverClass.GetInstances()  
  
        For Each instance As ManagementObject In instances  
  
            Console.WriteLine("\n-----\nSERVER STATUS:\n")  
  
            Dim serverStatusObject As ManagementBaseObject = instance.InvokeMethod("GetServerStatus", Nothing, Nothing)  
  
            Dim t As Integer = serverStatusObject("Length")  
  
            Dim namesArray As Array = serverStatusObject("Names")  
            Dim descArray As Array = serverStatusObject("Descriptions")  
            Dim statusArray As Array = serverStatusObject("Statuses")  
            Dim severityArray As Array = serverStatusObject("Severities")  
  
            Dim i As Integer  
  
            For i = 0 To t - 1  
                Console.WriteLine("{0} - {1}", namesArray.GetValue(i), descArray.GetValue(i))  
                Console.WriteLine("Value: {0}, Severity: {1}", statusArray.GetValue(i), severityArray.GetValue(i))  
            Next i  
  
        Next instance  
  
    End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using System.Management;  
using System.IO;  
[assembly: CLSCompliant(true)]  
  
class Class1  
{  
   [STAThread]  
   static void Main(string[] args)  
   {  
      const string machineWmiNamespace = @"\\<servername>\root\Microsoft\SqlServer\ReportServer\<InstanceName>\v10";  
        const string wmiNamespace = @"\\<servername>\root\Microsoft\SqlServer\ReportServer\<InstanceName>\v10:MSReportServer_ConfigurationSetting";  
  
      ConnectionOptions connOptions = new ConnectionOptions();  
      connOptions.Authentication = AuthenticationLevel.Default;  
  
      ObjectGetOptions getOptions = new ObjectGetOptions();  
      getOptions.Timeout = new System.TimeSpan(0,0,30);  
  
      ManagementScope machineScope = new ManagementScope(machineWmiNamespace, connOptions);  
      machineScope.Connect();  
  
      ManagementScope scope = null;  
  
      scope = new ManagementScope(wmiNamespace, connOptions);  
      scope.Connect();  
  
      ManagementPath path = new ManagementPath("MSReportServer_Instance");  
      ManagementClass serverClass = new ManagementClass(scope, path, getOptions);  
  
      serverClass.Get();  
  
      ManagementObjectCollection instances = serverClass.GetInstances();  
  
      foreach (ManagementObject instance in instances)  
      {  
  
         Console.WriteLine("\n-----\nSERVER STATUS:\n");  
  
         ManagementBaseObject serverStatusObject = instance.InvokeMethod("GetServerStatus", null, null);  
  
         int t = (int)serverStatusObject["Length"];  
  
         Array namesArray = (Array)serverStatusObject["Names"];  
         Array descArray = (Array)serverStatusObject["Descriptions"];  
         Array statusArray = (Array)serverStatusObject["Statuses"];  
         Array severityArray = (Array)serverStatusObject["Severities"];  
  
         for (int i = 0; i < t; i++)  
         {  
            Console.WriteLine("{0} - {1}",  
               (string)namesArray.GetValue(i),(string)descArray.GetValue(i));  
            Console.WriteLine("Value: {0}, Severity: {1}",  
               (string)statusArray.GetValue(i), (int)severityArray.GetValue(i));  
         }  
  
         Console.ReadKey();  
      }  
   }  
}  
```  
  
## <a name="requirements"></a><span data-ttu-id="52b91-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="52b91-114">Requirements</span></span>  
 <span data-ttu-id="52b91-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52b91-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
 <span data-ttu-id="52b91-116">**Plattform:** [!INCLUDE[ssRSWMIPlatform](../../includes/ssrswmiplatform-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52b91-116">**Platform:** [!INCLUDE[ssRSWMIPlatform](../../includes/ssrswmiplatform-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52b91-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52b91-117">See Also</span></span>  
 [<span data-ttu-id="52b91-118">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="52b91-118">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
