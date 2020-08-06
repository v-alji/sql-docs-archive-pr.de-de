---
title: Beispiel für einen benutzerdefinierten Workflow (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: dfd1616c-a75c-4f32-bdb1-7569e367bf41
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ee9d6e18bf4e54ae5eb6af6a56494fff0db28684
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695766"
---
# <a name="custom-workflow-example-master-data-services"></a>Beispiel für einen benutzerdefinierten Workflow (Master Data Services)
  [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)]Wenn Sie in eine benutzerdefinierte Workflow Klassenbibliothek erstellen, erstellen Sie eine Klasse, die die [Microsoft. masterdataservices. workflowtypeextender. iworkflowtypeextender](/previous-versions/sql/sql-server-2016/hh758785(v=sql.130)) -Schnittstelle implementiert. Diese Schnittstelle enthält eine Methode, [Microsoft. masterdataservices. workflowtypeextender. iworkflowtypeextender. StartWorkflow *](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)), die beim Start eines Workflows von SQL Server MDS Workflow Integration Service aufgerufen wird. Die [Microsoft. masterdataservices. workflowtypeextender. iworkflowtypeextender. StartWorkflow *](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)) -Methode enthält zwei Parameter: Workflow Type enthält den Text, den Sie in in das Textfeld *Workflowtyp* eingegeben **Workflow type** [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] haben, und *dataelement* enthält Metadaten und Elementdaten für das Element, das die Workflow Geschäftsregel ausgelöst hat.  
  
## <a name="custom-workflow-example"></a>Beispiel für einen benutzerdefinierten Workflow  
 Im folgenden Codebeispiel wird gezeigt, wie Sie die [Microsoft. masterdataservices. workflowtypeextender. iworkflowtypeextender. StartWorkflow *](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)) -Methode implementieren, um die Attribute Name, Code und lastchgusername aus den XML-Daten für das Element zu extrahieren, das die Workflow Geschäftsregel ausgelöst hat Ein Beispiel für die Elementdaten-XML und eine Erläuterung der enthaltenen Tags finden Sie unter [Benutzerdefinierte Workflow-XML-Beschreibung &#40;Master Data Services&#41;](create-a-custom-workflow-xml-description.md).  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.IO;  
using System.Data.SqlClient;  
using System.Xml;  
  
using Microsoft.MasterDataServices.Core.Workflow;  
  
namespace MDSWorkflowTestLib  
{  
    public class WorkflowTester : IWorkflowTypeExtender  
    {  
        #region IWorkflowTypeExtender Members  
  
        public void StartWorkflow(string workflowType, System.Xml.XmlElement dataElement)  
        {  
            // Extract the attributes we want out of the element data.  
            XmlNode NameNode = dataElement.SelectSingleNode("//ExternalAction/MemberData/Name");  
            XmlNode CodeNode = dataElement.SelectSingleNode("//ExternalAction/MemberData/Code");  
            XmlNode EnteringUserNode = dataElement.SelectSingleNode("//ExternalAction/MemberData/LastChgUserName");  
  
            // Open a connection on the workflow database.  
            SqlConnection workflowConn = new SqlConnection(@"Data Source=<Server instance>; Initial Catalog=WorkflowTest; Integrated Security=True");  
  
            // Create a command to call the stored procedure that adds a new user to the workflow database.  
            SqlCommand addCustomerCommand = new SqlCommand("AddNewCustomer", workflowConn);  
            addCustomerCommand.CommandType = System.Data.CommandType.StoredProcedure;  
            addCustomerCommand.Parameters.Add(new SqlParameter("@Name", NameNode.InnerText));  
            addCustomerCommand.Parameters.Add(new SqlParameter("@Code", CodeNode.InnerText));  
            addCustomerCommand.Parameters.Add(new SqlParameter("@EnteringUser", EnteringUserNode.InnerText));  
  
            // Execute the command.  
            workflowConn.Open();  
            addCustomerCommand.ExecuteNonQuery();  
            workflowConn.Close();  
        }  
  
        #endregion  
    }  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen  
 [Erstellen eines benutzerdefinierten Workflows &#40;Master Data Services&#41;](create-a-custom-workflow-master-data-services.md)  
  
  
