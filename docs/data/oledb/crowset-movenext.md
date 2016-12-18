---
title: "CRowset::MoveNext | Microsoft Docs"
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
  - "ATL.CRowset<TAccessor>.MoveNext"
  - "ATL.CRowset.MoveNext"
  - "ATL::CRowset<TAccessor>::MoveNext"
  - "CRowset<TAccessor>.MoveNext"
  - "CRowset.MoveNext"
  - "CRowset<TAccessor>::MoveNext"
  - "CRowset::MoveNext"
  - "ATL::CRowset::MoveNext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveNext (méthode)"
ms.assetid: 0df3288c-2bce-494f-99c0-6344b54a4adf
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::MoveNext
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Déplace le curseur sur l'enregistrement suivant.  
  
## Syntaxe  
  
```  
  
      HRESULT MoveNext( ) throw( );   
HRESULT MoveNext(   
   LONG lSkip,   
   bool bForward = true    
) throw( );  
```  
  
#### Paramètres  
 `lSkip`  
 \[in\] nombre de lignes à ignorer avant d'extraire.  
  
 `bForward`  
 \[in\] passez **true** pour avancer jusqu'à l'enregistrement suivant, **false** pour déplacer vers l'arrière.  
  
## Valeur de retour  
 Un `HRESULT` standard.  Lorsque la fin de l'ensemble de lignes a été atteinte, retourne **DB\_S\_ENDOFROWSET**.  
  
## Notes  
 Extrait la ligne séquentielle suivante de l'objet `CRowset`, en se souvenant de la position précédente.  Éventuellement, vous pouvez choisir d'avancer en sautant des lignes `lSkip` ou de vous déplacer vers l'arrière.  
  
 Cette méthode requiert que vous définissez les propriétés suivantes avant d'appeler **Ouvrir** sur la table ou la commande contenant l'ensemble de lignes :  
  
-   **DBPROP\_CANSCROLLBACKWARDS** doit être `VARIANT_TRUE` si `lSkip` \< 0  
  
-   **DBPROP\_CANFETCHBACKWARDS** doit être `VARIANT_TRUE` si `bForward` \= false  
  
 Sinon \(si `lSkip` \>\= 0 et `bForward` \= true\), vous n'avez pas besoin de définir des propriétés supplémentaires.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CRowset, classe](../../data/oledb/crowset-class.md)   
 [CRowset::MoveFirst](../../data/oledb/crowset-movefirst.md)   
 [CRowset::MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)