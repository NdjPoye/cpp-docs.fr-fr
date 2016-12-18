---
title: "D&#233;pannage des exceptions&#160;: System.Data.OleDb.OleDbException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "OLEDB"
  - "OleDbException (classe)"
  - "exceptions, OLEDB"
ms.assetid: f50077cf-e411-41f0-b73e-19eef83036c1
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# D&#233;pannage des exceptions&#160;: System.Data.OleDb.OleDbException
Une exception <xref:System.Data.OleDb.OleDbException> est générée lorsqu'une source de données OLE DB retourne un avertissement ou une erreur.  
  
## Conseils associés  
 **Vérifiez que vous vous connectez à l'aide d'informations d'identification valides.**  
 Assurez\-vous que les informations d'identification que vous fournissez sont valides. Pour plus d'informations, consultez <xref:System.Data.OleDb.OleDbErrorCollection>.  
  
 **Vérifiez que le nom de serveur est correct et que le serveur s'exécute.**  
 Assurez\-vous d’utiliser le nom de serveur correct et vérifiez que le serveur peut être atteint. Pour plus d'informations, consultez <xref:System.Data.OleDb.OleDbErrorCollection>.  
  
### Notes  
 Cette exception est levée toutes les fois que le fournisseur de données .NET Framework pour OLE DB rencontre une erreur générée par le serveur.  
  
 Si la gravité de l'erreur est trop élevée, le serveur peut fermer <xref:System.Data.OleDb.OleDbConnection>. L'utilisateur peut toutefois rouvrir la connexion et continuer.  
  
## Voir aussi  
 <xref:System.Data.OleDb.OleDbException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)