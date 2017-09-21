---
title: "SafeLessThanEquals | Microsoft Docs"
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
  - "SafeLessThanEquals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeLessThanEquals (fonction)"
ms.assetid: cbd70526-faf2-4fbc-96a0-b61e8cf5f04a
caps.latest.revision: 6
caps.handback.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# SafeLessThanEquals
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Compare deux nombres.  
  
## Syntaxe  
  
```  
template <typename T, typename U>  
inline bool SafeLessThanEquals (  
   const T t,  
   const U u  
) throw ();  
```  
  
#### Paramètres  
 \[in\] `t`  
 Premier nombre à comparer.  Ceci doit être de type T.  
  
 \[in\] `u`  
 Deuxième nombre à comparer.  Ceci doit être de type U.  
  
## Valeur de retour  
 `true` si `t` est inférieur ou égal à `u` ; sinon, `false`.  
  
## Notes  
 `SafeLessThanEquals` étend l'opérateur de comparaison standard en vous permettant de comparer deux types de nombres différents .  
  
 Cette méthode fait partie de [Bibliothèque SafeInt](../windows/safeint-library.md) et est conçue pour une opération de comparaison simple sans création d'une instance [SafeInt, classe](../windows/safeint-class.md).  
  
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
 [SafeGreaterThan](../windows/safegreaterthan.md)   
 [SafeLessThan](../windows/safelessthan.md)   
 [SafeGreaterThanEquals](../windows/safegreaterthanequals.md)