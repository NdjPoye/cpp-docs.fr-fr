---
title: "CDynamicStringAccessor::GetString | Microsoft Docs"
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
  - "CDynamicStringAccessor.GetString"
  - "CDynamicStringAccessor::GetString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetString (méthode)"
ms.assetid: 4af27f27-7589-49f5-93d8-6ef05c023c8a
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicStringAccessor::GetString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère les données de la colonne spécifiée sous forme de chaîne.  
  
## Syntaxe  
  
```  
  
      BaseType* GetString(  
   DBORDINAL nColumn  
) const throw( );  
BaseType* GetString(  
   const CHAR* pColumnName  
) const throw( );  
BaseType* GetString(  
   const WCHAR* pColumnName  
) const throw( );  
```  
  
#### Paramètres  
 `nColumn`  
 \[in\] Le numéro de colonne.  Les numéros de colonne commencent à 1.  La valeur 0 fait référence à la colonne du signet, le cas échéant.  
  
 `pColumnName`  
 \[in\] Un pointeur vers une chaîne de caractères contenant le nom de la colonne.  
  
## Valeur de retour  
 Pointeur vers la valeur de chaîne extraite de la colonne spécifiée.  La valeur de est de type ***BaseType***, qui sera **CHAR** ou **WCHAR** selon que \_UNICODE est activé ou non.  Retourne NULL si la colonne spécifiée n'est pas trouvée.  
  
## Notes  
 Le second format de substitution prend le nom de colonne comme chaîne ANSI.  Le troisième format de substitution prend le nom de colonne comme chaîne Unicode.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDynamicStringAccessor, classe](../../data/oledb/cdynamicstringaccessor-class.md)