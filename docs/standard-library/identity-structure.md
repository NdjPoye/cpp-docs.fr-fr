---
title: "identity, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::identity"
  - "utility/std::identity"
  - "identity"
  - "std.identity"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "identity (classe)"
  - "identity (structure)"
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# identity, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une structure qui fournit une définition de type en guise de paramètre de modèle.  
  
## Syntaxe  
  
```  
template<class Type>  
   struct identity {  
      typedef Type type;  
      Type operator()(const Type& _Left) const;  
   };  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`_Left`|La valeur à l'identifier.|  
  
## Notes  
 La classe contient la définition du type `type`publique, qui est identique au type de modèle.  Elle est utilisée conjointement avec la fonction [forward](../Topic/forward.md) de modèle pour garantir qu'un paramètre de fonction de le type souhaité.  
  
 Pour assurer la compatibilité avec les versions antérieures, la classe définit également la fonction d'identité `operator()` qui retourne son argument `_Left`.  
  
## Configuration requise  
 **En\-tête :**utilitaire \<de \>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<utility\>](../standard-library/utility.md)