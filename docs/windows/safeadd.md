---
title: "SafeAdd | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeAdd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeAdd (fonction)"
ms.assetid: 3f82b91d-59fe-4ee1-873b-d056182fa8be
caps.latest.revision: 5
caps.handback.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# SafeAdd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Additionne deux nombres d'une manière qui protège contre un dépassement de capacité \(overflow\).  
  
## Syntaxe  
  
```  
template<typename T, typename U>  
inline bool SafeAdd (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### Paramètres  
 \[in\] `t`  
 Le premier nombre à ajouter.  Ceci doit être de type T.  
  
 \[in\] `u`  
 Le deuxième nombre à ajouter.  Ceci doit être de type U.  
  
 \[out\] `result`  
 Le paramètre où `SafeAdd` stocke le résultat.  
  
## Valeur de retour  
 `true` si aucune erreur ne se produit; `false` si une erreur se produit.  
  
## Notes  
 Cette méthode fait partie de [Bibliothèque SafeInt](../windows/safeint-library.md) et est conçue pour une unique addition sans créer une instance de [SafeInt, classe](../windows/safeint-class.md).  
  
> [!NOTE]
>  Cette méthode doit être utilisée uniquement lorsqu'une seule opération mathématique doit être protégée.  S'il existe plusieurs opérations, vous devez utiliser la classe `SafeInt` au lieu d'appeler des fonctions autonomes.  
  
 Pour plus d'informations sur les types de modèle T et U, consultez [SafeInt, fonctions](../windows/safeint-functions.md).  
  
## Configuration requise  
 **En\-tête :** safeint.h  
  
 **Espace de noms :** Microsoft::Utilities  
  
## Voir aussi  
 [SafeInt, fonctions](../windows/safeint-functions.md)   
 [Bibliothèque SafeInt](../windows/safeint-library.md)   
 [SafeInt, classe](../windows/safeint-class.md)   
 [SafeSubtract](../windows/safesubtract.md)