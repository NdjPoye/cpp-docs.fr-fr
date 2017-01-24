---
title: "CDynamicAccessor::GetValue | Microsoft Docs"
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
  - "GetValue"
  - "CDynamicAccessor::GetValue<ctype>"
  - "ATL.CDynamicAccessor.GetValue<ctype>"
  - "CDynamicAccessor.GetValue"
  - "CDynamicAccessor::GetValue"
  - "ATL.CDynamicAccessor.GetValue"
  - "ATL::CDynamicAccessor::GetValue"
  - "ATL::CDynamicAccessor::GetValue<ctype>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetValue (méthode)"
ms.assetid: 553f44af-68bc-4cb6-8774-e0940003fa90
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::GetValue
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère les données pour une colonne spécifiée.  
  
## Syntaxe  
  
```  
  
      void* GetValue(   
   DBORDINAL nColumn    
) const throw( );  
void* GetValue(  
   const CHAR* pColumnName   
) const throw( );  
void* GetValue(  
   const WCHAR* pColumnName   
) const throw( );  
template < class ctype >  
bool GetValue(  
   DBORDINAL nColumn,  
   ctype* pData   
) const throw( );  
template < class ctype >  
bool GetValue(  
   const CHAR* pColumnName,  
   ctype* pData   
) const throw( );  
template < class ctype >  
bool GetValue(  
   const WCHAR* pColumnName,  
   ctype* pData   
) const throw( );  
```  
  
#### Paramètres  
 `ctype`  
 \[in\] Un paramètre de modèle type qui gère tout type de données à l'exception des chaînes de caractères \(**CHAR\***, **WCHAR\***\), qui nécessitent une gestion spéciale.  `GetValue` utilise le type de données approprié selon ce que vous spécifiez ici.  
  
 `nColumn`  
 \[in\] Le numéro de colonne.  Les numéros de colonne commencent à 1.  La valeur 0 fait référence à la colonne du signet, le cas échéant.  
  
 `pColumnName`  
 \[in\] Le nom de colonne.  
  
 `pData`  
 \[out\] Le pointeur au contenu de la colonne spécifiée.  
  
## Valeur de retour  
 Si vous souhaitez définir des données de chaîne, utilisez les versions basées sur des modèles de `GetValue`.  Les versions non typées de cette méthode renvoie **void\***, qui indique la partie de la mémoire tampon qui contient les données de la colonne spécifiée.  Retourne la valeur **NULL** si la colonne est introuvable.  
  
 Pour tous les autres types de données, il est plus facile à utiliser les versions basées sur des modèles de `GetValue`.  Les versions basées sur des modèles renvoient **true** en cas de réussite ou **false** en cas d'échec.  
  
## Notes  
 Utilisez les versions non typées pour renvoyer les colonnes qui contiennent des chaînes et des versions basées sur des modèles pour les colonnes qui contiennent des autres types de données.  
  
 En mode débogage, vous obtiendrez une assertion si la taille de `pData` est différente de la taille de la colonne qu'elle pointe.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)