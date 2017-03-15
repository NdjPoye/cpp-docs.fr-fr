---
title: "SafeLessThan | Microsoft Docs"
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
  - "SafeLessThan"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeLessThan (fonction)"
ms.assetid: 9d85bc0d-8d94-4d59-9b72-ef3c63a120a0
caps.latest.revision: 6
caps.handback.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# SafeLessThan
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Déterminer si une valeur est inférieure à une autre  
  
## Syntaxe  
  
```  
template<typename T, typename U>  
inline bool SafeLessThan (  
   const T t,  
   const U u  
) throw ();  
```  
  
#### Paramètres  
 \[in\] `t`  
 Le premier nombre.  Ce doit être de type T.  
  
 \[in\] `u`  
 Le deuxième numer.  Ce doit être de type U.  
  
## Valeur de retour  
 `true` si `t` est inférieur à `u` ; sinon, `false`.  
  
## Notes  
 Cette méthode améliore l'opérateur de comparaison standard car `SafeLessThan` vous permet de comparer deux types différents de nombre.  
  
 Cette méthode fait partie de [Bibliothèque SafeInt](../windows/safeint-library.md) et est conçue pour une opération de comparaison sans création d'une instance de [SafeInt, classe](../windows/safeint-class.md).  
  
> [!NOTE]
>  Cette méthode doit être utilisée lorsqu'une seule opération mathématique doit être protégée.  S'il existe plusieurs opérations, vous devez utiliser la classe `SafeInt` au lieu d'appeler des fonctions autonomes.  
  
 Pour plus d'informations sur les types de modèle T et U, consultez [SafeInt, fonctions](../windows/safeint-functions.md).  
  
## Configuration requise  
 **En\-tête :** safeint.h  
  
 **Espace de noms :** Microsoft::Utilities  
  
## Voir aussi  
 [SafeInt, fonctions](../windows/safeint-functions.md)   
 [Bibliothèque SafeInt](../windows/safeint-library.md)   
 [SafeInt, classe](../windows/safeint-class.md)   
 [SafeLessThanEquals](../windows/safelessthanequals.md)   
 [SafeGreaterThan](../windows/safegreaterthan.md)   
 [SafeGreaterThanEquals](../windows/safegreaterthanequals.md)