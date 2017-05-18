---
title: Fonctions inline | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- fast code
- inline functions, __inline keyword
- functions [C++], inline functions
ms.assetid: 00f4b2ff-8ad0-4165-9f4c-2ef157d03f31
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: cdcf109b76725855aeb6daae1628bbc6a57e6e32
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="inline-functions"></a>Fonctions inline
**Section spécifique à Microsoft**  
  
 Le mot clé `__inline` indique au compilateur de substituer le code dans la définition de fonction pour chaque instance d'un appel de fonction. Toutefois, la substitution se produit uniquement à la discrétion du compilateur. Par exemple, le compilateur n'incorpore pas une fonction si son adresse est prise ou si elle trop volumineuse pour être incorporée.  
  
 Pour qu'une fonction soit considérée comme candidat pour l'incorporation, elle doit utiliser la définition de fonction de style nouveau.  
  
 Utilisez la forme suivante pour spécifier une fonction inline :  
  
 `__inline` *type*opt*function-definition*`;`  
  
 Les fonctions inline permettent de générer un code plus rapide et parfois plus petit que l'appel de fonction équivalent, pour les raisons suivantes :  
  
-   Elles permettent d'économiser le temps requis pour exécuter les appels de fonction.  
  
-   Les petites fonctions inline, de trois lignes ou moins, créent moins de code que l'appel de fonction équivalent, car le compilateur ne génère pas de code pour gérer les arguments et une valeur de retour.  
  
-   Les fonctions générées inline font l'objet d'optimisations de code non disponibles aux fonctions normales, car le compilateur n'exécute pas les optimisations interprocédurales.  
  
 Les fonctions utilisant `__inline` ne doivent pas être confondues avec du code assembleur inline. Consultez [Assembleur inline](../c-language/inline-assembler-c.md) pour plus d’informations.  
  
 **Fin de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [inline, __inline, \__forceinline](../cpp/inline-functions-cpp.md)


