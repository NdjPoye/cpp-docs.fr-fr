---
title: "SafeInt::SafeInt | Microsoft Docs"
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
  - "SafeInt::SafeInt"
  - "SafeInt"
  - "SafeInt.SafeInt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeInt (classe), constructeur"
ms.assetid: 39e6f632-a396-40e6-9ece-cc3d4c5a78ef
caps.latest.revision: 7
caps.handback.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# SafeInt::SafeInt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Construit un objet `SafeInt`.  
  
## Syntaxe  
  
```  
SafeInt() throw  
  
SafeInt (  
   const T& i  
) throw ()  
  
SafeInt (  
   bool b  
) throw ()  
  
template <typename U>  
SafeInt (  
   const SafeInt <U, E>& u  
)  
  
I template <typename U>  
SafeInt (  
   const U& i  
)  
```  
  
#### Paramètres  
 \[in\] `i`  
 Valeur du nouvel objet `SafeInt`.  Il doit s'agir d'un paramètre de type T ou U, selon le constructeur.  
  
 \[in\] `b`  
 Valeur booléenne initiale du nouvel objet `SafeInt`.  
  
 \[in\] `u`  
 Un `SafeInt` de type U.  Le nouvel objet `SafeInt` a la même valeur que `u`, mais est de type T.  
  
 U  
 Type de données stockées dans le `SafeInt`.  Cela peut être une valeur booléenne, un caractère, ou un type entier.  S'il s'agit d'un type entier, il peut être signé ou non signé et être compris entre 8 et 64 bits.  
  
## Notes  
 Pour plus d'informations sur les types de modèle `T` et `E`, consultez [SafeInt, classe](../windows/safeint-class.md).  
  
 Le paramètre d'entrée pour le constructeur, `i` ou `u`, doit être un booléen, un caractère, ou un type entier.  S'il s'agit d'un autre type de paramètre, la classe `SafeInt` appelle [static\_assert](../cpp/static-assert.md) pour indiquer un paramètre d'entrée non valide.  
  
 Les constructeurs qui utilisent le type de modèle `U` convertissent automatiquement le paramètre d'entrée en le type spécifié par `T`.  La classe `SafeInt` convertit les données sans perte de données.  Il rapporte dans le gestionnaire d'erreurs `E` s'il ne peut pas convertir les données dans le type `T` sans perte de données.  
  
 Si vous créez un `SafeInt` à partir d'un paramètre booléen, vous devez initialiser la valeur immédiatement.  Vous ne pouvez pas créer un `SafeInt` à l'aide du code `SafeInt<bool> sb;`.  Ceci génère une erreur de compilation.  
  
## Configuration requise  
 **En\-tête :** safeint.h  
  
 **Espace de noms :** msl::utilities  
  
## Voir aussi  
 [Bibliothèque SafeInt](../windows/safeint-library.md)   
 [SafeInt, classe](../windows/safeint-class.md)   
 [SafeIntException, classe](../windows/safeintexception-class.md)