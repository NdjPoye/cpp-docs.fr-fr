---
title: "SafeNotEquals | Microsoft Docs"
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
  - "SafeNotEquals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeNotEquals (fonction)"
ms.assetid: 032e45a8-4159-4b55-b7cc-ecd27f4e4788
caps.latest.revision: 6
caps.handback.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# SafeNotEquals
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Détermine si deux nombres ne sont pas égaux.  
  
## Syntaxe  
  
```  
template<typename T, typename U>  
inline bool SafeNotEquals (  
   const T t,  
   const U u  
) throw ();  
```  
  
#### Paramètres  
 \[in\] `t`  
 Premier nombre à comparer.  Ce doit être de type T.  
  
 \[in\] `u`  
 Deuxième nombre à comparer.  Ce doit être de type U.  
  
## Valeur de retour  
 `true` si `t` et `u` ne sont pas égaux ; sinon `false`.  
  
## Notes  
 La méthode améliore `!=` car `SafeNotEquals` vous permet de comparer deux types différents de nombres.  
  
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
 [SafeEquals](../windows/safeequals.md)