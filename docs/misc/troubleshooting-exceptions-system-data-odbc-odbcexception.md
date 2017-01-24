---
title: "D&#233;pannage des exceptions&#160;: System.Data.Odbc.OdbcException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EHOdbc"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "exceptions, ODBC"
  - "ODBC, exceptions"
  - "OdbcException (classe)"
ms.assetid: 5f2c2167-cf7b-4634-af86-44dc71eff02d
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# D&#233;pannage des exceptions&#160;: System.Data.Odbc.OdbcException
Une exception <xref:System.Data.Odbc.OdbcException> est générée lorsqu'une source de données ODBC retourne un avertissement ou une erreur.  
  
## Conseils associés  
 **Vérifiez que vous vous connectez à l'aide d'informations d'identification valides.**  
 Vérifiez la validité de vos informations d'identification.  
  
 **Vérifiez que le nom de serveur est correct et que le serveur s'exécute.**  
 Assurez\-vous d’utiliser le nom de serveur correct et vérifiez que le serveur peut être atteint.  
  
## Notes  
 Cette exception est levée toutes les fois que <xref:System.Data.Odbc.OdbcDataAdapter> rencontre une erreur générée par le serveur.  
  
 Si la gravité de l'erreur est trop élevée, le serveur peut fermer <xref:System.Data.Odbc.OdbcConnection>. L'utilisateur peut toutefois rouvrir la connexion et continuer.  
  
## Voir aussi  
 <xref:System.Data.Odbc.OdbcException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)