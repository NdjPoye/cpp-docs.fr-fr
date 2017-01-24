---
title: "SafeMultiply | Microsoft Docs"
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
  - "SafeMultiply"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeMultiply (fonction)"
ms.assetid: 81d988a5-fac7-4930-8c37-c24fa8e2c853
caps.latest.revision: 5
caps.handback.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# SafeMultiply
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Multiplie deux nombres ensemble d'une manière qui protège contre un dépassement de capacité.  
  
## Syntaxe  
  
```  
template<typename T, typename U>  
inline bool SafeMultiply (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### Paramètres  
 \[in\] `t`  
 Premier nombre à multiplier.  Ceci doit être de type T.  
  
 \[in\] `u`  
 Second nombre à multiplier.  Ceci doit être de type U.  
  
 \[out\] `result`  
 Le paramètre où `SafeMultiply` stocke le résultat.  
  
## Valeur de retour  
 `true` si aucune erreur ne se produit; `false` si une erreur se produit.  
  
## Notes  
 Cette méthode fait partie de [Bibliothèque SafeInt](../windows/safeint-library.md) et est conçue pour une opération de multiplication sans création d'une instance de [SafeInt, classe](../windows/safeint-class.md).  
  
> [!NOTE]
>  Cette méthode doit être utilisée uniquement lorsqu'une seule opération mathématique doit être protégée.  S'il existe plusieurs opérations, vous devez utiliser la classe `SafeInt` au lieu d'appeler des fonctions autonomes.  
  
 Pour plus d'informations sur les types de modèle T et U, consultez [SafeInt, fonctions](../windows/safeint-functions.md).  
  
## Configuration requise  
 **En\-tête :** safeint.h  
  
 **Espace de nommage :** Microsoft::Utilities  
  
## Voir aussi  
 [SafeInt, fonctions](../windows/safeint-functions.md)   
 [Bibliothèque SafeInt](../windows/safeint-library.md)   
 [SafeInt, classe](../windows/safeint-class.md)   
 [SafeDivide](../windows/safedivide.md)