---
title: Übersicht über benutzerdefinierte Attribute der CLR-Integration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- custom attributes [CLR integration]
- attributes [CLR integration]
- common language runtime [SQL Server], attributes
- database objects [CLR integration], custom attributes
- building database objects [CLR integration], custom attributes
ms.assetid: ecf5c097-0972-48e2-a9c0-b695b7dd2820
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: aa0bf94ee27fd89a6aa690e0ff2f8e3295648946
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608831"
---
# <a name="overview-of-clr-integration-custom-attributes"></a><span data-ttu-id="645e9-102">Übersicht über benutzerdefinierte Attribute der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="645e9-102">Overview of CLR Integration Custom Attributes</span></span>
  <span data-ttu-id="645e9-103">Die CLR-Komponente (Common Language Runtime) von [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] ermöglicht den Einsatz beschreibender Schlüsselwörter, so genannter Attribute.</span><span class="sxs-lookup"><span data-stu-id="645e9-103">The common language runtime (CLR) of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] allows the use of descriptive keywords, called attributes.</span></span> <span data-ttu-id="645e9-104">Diese Attribute stellen weitere Informationen für viele Elemente bereit, z. B. Methoden und Klassen.</span><span class="sxs-lookup"><span data-stu-id="645e9-104">These attributes provide additional information for many elements, such as methods and classes.</span></span> <span data-ttu-id="645e9-105">Die Attribute werden mit den Metadaten des Objekts in der Assembly gespeichert. Mit Attributen kann Code für andere Entwicklungstools beschrieben oder das Laufzeitverhalten in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] beeinflusst werden.</span><span class="sxs-lookup"><span data-stu-id="645e9-105">The attributes are saved in the assembly with the metadata of the object, and can be used to describe your code to other development tools or to affect runtime behavior inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="645e9-106">Wenn Sie eine CLR-Routine bei [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registrieren, leitet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] einen Satz von Eigenschaften zu der Routine ab.</span><span class="sxs-lookup"><span data-stu-id="645e9-106">When you register a CLR routine with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] derives a set of properties about the routine.</span></span> <span data-ttu-id="645e9-107">Diese Routineneigenschaften bestimmen die Fähigkeiten der Routine, darunter auch, ob die Routine indiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="645e9-107">These routine properties determine the capabilities of the routine, including whether the routine can be indexed.</span></span> <span data-ttu-id="645e9-108">Durch Festlegen von `DataAccess` für die `DataAccessKind.Read`-Eigenschaft können Sie beispielsweise innerhalb einer CLR-Funktion auf Daten aus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Benutzertabellen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="645e9-108">For example, setting the `DataAccess` property to `DataAccessKind.Read` lets you access data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user tables inside a CLR function.</span></span> <span data-ttu-id="645e9-109">Das folgende Beispiel zeigt einen einfachen Fall, in dem die- `DataAccess` Eigenschaft festgelegt ist, um den Datenzugriff aus einer Benutzertabelle **Table1**zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="645e9-109">The following example shows a simple case in which the `DataAccess` property is set to facilitate data access from a user table **table1**.</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.Sql;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
  
public partial class UserDefinedFunctions  
{  
    [SqlFunction(DataAccess = DataAccessKind.Read)]  
    public static string func1()  
    {  
        // Open a connection and create a command  
        SqlConnection conn = new SqlConnection("context connection = true");  
        conn.Open();  
        SqlCommand cmd = conn.CreateCommand();  
        cmd.CommandText = "SELECT str_val FROM table1 WHERE int_val = 10";  
        // where table1 is a user table  
        // Execute this command   
        SqlDataReader rd = cmd.ExecuteReader();  
        // Set string ret_val to str_val returned from the query  
        string ret_val = rd.GetValue(0).ToString();  
        rd.Close();  
        return ret_val;  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
Public partial Class UserDefinedFunctions  
    <SqlFunction(DataAccess = DataAccessKind.Read)> _   
    Public Shared Function func1() As String  
        ' Open a connection and create a command  
        Dim conn As SqlConnection = New SqlConnection("context connection = true")   
        conn.Open()  
        Dim cmd As SqlCommand =  conn.CreateCommand()   
        cmd.CommandText = "SELECT str_val FROM table1 WHERE int_val = 10"  
        ' where table1 is a user table  
        ' Execute this command   
        Dim rd As SqlDataReader =  cmd.ExecuteReader()   
        ' Set string ret_val to str_val returned from the query  
        Dim ret_val As String =  rd.GetValue(0).ToString()   
        rd.Close()  
        Return ret_val  
    End Function  
End Class  
```  
  
 <span data-ttu-id="645e9-110">Für [!INCLUDE[tsql](../../includes/tsql-md.md)]-Routinen leitet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Routineneigenschaften direkt aus der Routinendefinition ab.</span><span class="sxs-lookup"><span data-stu-id="645e9-110">For [!INCLUDE[tsql](../../includes/tsql-md.md)] routines, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] derives routine properties directly from the routine definition.</span></span> <span data-ttu-id="645e9-111">Für CLR-Routinen analysiert der Server den Routinentext nicht, um diese Eigenschaften abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="645e9-111">For CLR routines, the server does not analyze the body of the routine to derive these properties.</span></span> <span data-ttu-id="645e9-112">Stattdessen können Sie benutzerdefinierte Attribute für Klassen und Klassenmember verwenden, die in einer [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Sprache implementiert wurden.</span><span class="sxs-lookup"><span data-stu-id="645e9-112">Instead, you can use custom attributes for classes and class members implemented in a [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] language.</span></span>  
  
 <span data-ttu-id="645e9-113">Die für CLR-Routinen benötigten benutzerdefinierten Attribute, benutzerdefinierte Typen und Aggregate werden im `Microsoft.SqlServer.Server`-Namespace definiert.</span><span class="sxs-lookup"><span data-stu-id="645e9-113">The custom attributes needed for CLR routines, user-defined types, and aggregates are defined in the `Microsoft.SqlServer.Server` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="645e9-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="645e9-114">See Also</span></span>  
 [<span data-ttu-id="645e9-115">Benutzerdefinierte Attribute für CLR-Routinen</span><span class="sxs-lookup"><span data-stu-id="645e9-115">Custom Attributes for CLR Routines</span></span>](../../relational-databases/clr-integration/database-objects/clr-integration-custom-attributes-for-clr-routines.md)  
  
  
