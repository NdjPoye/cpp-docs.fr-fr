---
title: "CDataSource::GetInitializationString | Microsoft Docs"
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
  - "ATL::CDataSource::GetInitializationString"
  - "CDataSource.GetInitializationString"
  - "GetInitializationString"
  - "CDataSource::GetInitializationString"
  - "ATL.CDataSource.GetInitializationString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetInitializationString (méthode)"
ms.assetid: 97134723-6e99-4004-a56d-ec57543dbf3b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataSource::GetInitializationString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère la chaîne d'initialisation d'une source de données qui est actuellement ouverte.  
  
## Syntaxe  
  
```  
  
      HRESULT GetInitializationString(   
   BSTR* pInitializationString,   
   bool bIncludePassword = false    
) throw( );  
```  
  
#### Paramètres  
 *pInitialisationCaractere*  
 \[out\] pointeur à la chaîne d'initialisation.  
  
 *bInclureMotdepasse*  
 \[in\] **vrai** si la chaîne contient un mot de passe ; sinon **faux**.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 La chaîne d'initialisation résultante peut être utilisée pour réouvrir plus loin cette connexion à la source de données.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDataSource, classe](../../data/oledb/cdatasource-class.md)