---
title: "CDataSource::OpenFromInitializationString | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDataSource.OpenFromInitializationString"
  - "OpenFromInitializationString"
  - "CDataSource::OpenFromInitializationString"
  - "ATL::CDataSource::OpenFromInitializationString"
  - "ATL.CDataSource.OpenFromInitializationString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OpenFromInitializationString (méthode)"
ms.assetid: 5ef1f1fd-92a9-4e1c-ad80-d3601b094b8c
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataSource::OpenFromInitializationString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ouvre une source de données spécifiée par la chaîne d'initialisation fournie par l'utilisateur.  
  
## Syntaxe  
  
```  
  
      HRESULT OpenFromInitializationString(   
   LPCOLESTR szInitializationString,   
   bool fPromptForInfo = false    
) throw( );  
```  
  
#### Paramètres  
 *szInitializationString*  
 \[in\] La chaîne d'initialisation.  
  
 *fPromptForInfo*  
 \[in\] si cet argument a la valeur **true**, puis `OpenFromInitializationString` définit la propriété de **DBPROP\_INIT\_PROMPT** à **DBPROMPT\_COMPLETEREQUIRED**, qui indique que l'utilisateur est invité si plus d'informations.  Cette option est utile pour les cas où la chaîne d'initialisation spécifie une base de données qui requiert un mot de passe, mais la chaîne ne contient pas le mot de passe.  L'utilisateur est invité à entrer un mot de passe \(ou toutes les autres informations manquantes\) lorsque vous tentez de vous connecter à la base de données.  
  
 La valeur par défaut est **false**, qui indique que l'utilisateur n'est soit jamais invité \(ensembles **DBPROP\_INIT\_PROMPT** à **DBPROMPT\_NOPROMPT**\).  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 Cette méthode ouvre un objet source de données à l'aide des composants de service dans oledb32.dll ; cette DLL contient l'implémentation des fonctionnalités de composants de service telles que le regroupement de ressources, inscription automatique des transactions, et ainsi de suite.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDataSource, classe](../../data/oledb/cdatasource-class.md)