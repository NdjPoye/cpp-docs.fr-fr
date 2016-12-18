---
title: "Fonctions inline | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "code rapide"
  - "fonctions (C++), fonctions inline"
  - "fonctions inline, __inline (mot clé)"
ms.assetid: 00f4b2ff-8ad0-4165-9f4c-2ef157d03f31
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fonctions inline
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Le mot clé `__inline` indique au compilateur de substituer le code dans la définition de fonction pour chaque instance d'un appel de fonction.  Toutefois, la substitution se produit uniquement à la discrétion du compilateur.  Par exemple, le compilateur n'incorpore pas une fonction si son adresse est prise ou si elle trop volumineuse pour être incorporée.  
  
 Pour qu'une fonction soit considérée comme candidat pour l'incorporation, elle doit utiliser la définition de fonction de style nouveau.  
  
 Utilisez la forme suivante pour spécifier une fonction inline :  
  
 `__inline` *type*option *function\-definition*`;`  
  
 Les fonctions inline permettent de générer un code plus rapide et parfois plus petit que l'appel de fonction équivalent, pour les raisons suivantes :  
  
-   Elles permettent d'économiser le temps requis pour exécuter les appels de fonction.  
  
-   Les petites fonctions inline, de trois lignes ou moins, créent moins de code que l'appel de fonction équivalent, car le compilateur ne génère pas de code pour gérer les arguments et une valeur de retour.  
  
-   Les fonctions générées inline font l'objet d'optimisations de code non disponibles aux fonctions normales, car le compilateur n'exécute pas les optimisations interprocédurales.  
  
 Les fonctions utilisant `__inline` ne doivent pas être confondues avec du code assembleur inline.  Reportez\-vous à la rubrique [Assembleur inline](../c-language/inline-assembler-c.md) pour plus d'informations.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [inline, \_\_inline, \_\_forceinline](../misc/inline-inline-forceinline.md)