---
title: "SafeCast | Microsoft Docs"
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
  - "SafeCast"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeCast (fonction)"
ms.assetid: 55316729-8456-403a-9f96-59d4038f67af
caps.latest.revision: 7
caps.handback.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# SafeCast
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ajoute un type de nombre à un autre type.  
  
## Syntaxe  
  
```  
template<typename T, typename U>  
inline bool SafeCast (  
   const T From,  
   U& To  
);  
```  
  
#### Paramètres  
 \[in\] `From`  
 Flux source à convertir.  Ceci doit être de type T.  
  
 \[out\] `To`  
 Une référence au nouveau type de nombre.  Ceci doit être de type U.  
  
## Valeur de retour  
 `true` si aucune erreur ne se produit; `false` si une erreur se produit.  
  
## Notes  
 Cette méthode fait partie de [Bibliothèque SafeInt](../windows/safeint-library.md) et est conçue pour une unique addition sans créer une instance de [SafeInt, classe](../windows/safeint-class.md).  
  
> [!NOTE]
>  Cette méthode doit être utilisée uniquement lorsqu'une seule opération doit être protégée.  S'il existe plusieurs opérations, vous devez utiliser la classe `SafeInt` au lieu d'appeler des fonctions autonomes.  
  
 Pour plus d'informations sur les types de modèle T et U, consultez [SafeInt, fonctions](../windows/safeint-functions.md).  
  
## Configuration requise  
 **En\-tête :** safeint.h  
  
 **Espace de noms :** Microsoft::Utilities  
  
## Voir aussi  
 [SafeInt, fonctions](../windows/safeint-functions.md)   
 [Bibliothèque SafeInt](../windows/safeint-library.md)   
 [SafeInt, classe](../windows/safeint-class.md)