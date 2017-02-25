---
title: "CDynamicStringAccessor::SetString | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicStringAccessor::SetString"
  - "CDynamicStringAccessor.SetString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetString (méthode)"
ms.assetid: 94846d8b-4c1b-47fe-acdc-1752981cee25
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# CDynamicStringAccessor::SetString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit les données de la colonne spécifiée sous forme de chaîne.  
  
## Syntaxe  
  
```  
HRESULT SetString(  
   DBORDINAL nColumn,  
   BaseType* data  
) throw( );  
HRESULT SetString(  
   const CHAR* pColumnName,  
   BaseType* data  
) throw( );  
HRESULT SetString(  
   const WCHAR* pColumnName,  
   BaseType* data  
) throw( );  
```  
  
#### Paramètres  
 `nColumn`  
 \[in\] Le numéro de colonne.  Les numéros de colonne commencent à 1.  La valeur spéciale de 0 fait référence à la colonne du signet le cas échéant.  
  
 `pColumnName`  
 \[in\] Un pointeur vers une chaîne de caractères contenant le nom de la colonne.  
  
 `data`  
 \[in\] Un pointeur vers les données de chaîne à écrire dans la colonne spécifiée.  
  
## Valeur de retour  
 Pointeur vers la valeur de chaîne à laquelle il faut définir la colonne spécifiée.  La valeur est de type `BaseType`, qui sera `CHAR` ou selon que `_UNICODE` de `WCHAR` est activée ou non.  
  
## Notes  
 Le second format de priorité prend le nom de colonne comme une chaîne ANSI et la troisième forme de priorité prend le nom de colonne comme chaîne Unicode.  
  
 Si `_SECURE_ATL` est défini de manière à posséder une valeur différente de zéro, un échec d'assertion d'exécution est généré si la chaîne de `data` d'entrée est supérieure à la longueur maximale autorisée de la colonne de données référencée.  Sinon, la chaîne d'entrée sera tronquée si elle est supérieure à la longueur maximale autorisée.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDynamicStringAccessor, classe](../../data/oledb/cdynamicstringaccessor-class.md)