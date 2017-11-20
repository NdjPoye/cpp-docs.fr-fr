---
title: "Pimpl pour l’Encapsulation au moment de la compilation (Modern C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2cfb333052b0f54ac241607ba7324dca920b8051
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>Pimpl pour l’encapsulation au moment de la compilation (Modern C++)
Le *pimpl idiome* est une technique C++ moderne pour masquer l’implémentation, afin de minimiser le couplage, and pour séparer les interfaces. Pimpl est l’abréviation de « pointeur vers l’implémentation. » Vous pouvez déjà être familiarisé avec le concept, mais il connaître d’autres noms comme l’idiome malicieusement ou du compilateur pare-feu.  
  
## <a name="why-use-pimpl"></a>Pourquoi utiliser pimpl ?  
 Voici comment l’idiome pimpl peut améliorer le cycle de vie de développement logiciel :  
  
-   Minimisation des dépendances de compilation.  
  
-   Séparation de l’interface et l’implémentation.  
  
-   Portabilité.  
  
## <a name="pimpl-header"></a>Pimpl en-tête  
  
```cpp  
// my_class.h  
class my_class {  
   //  ... all public and protected stuff goes here ...  
private:  
   class impl; unique_ptr<impl> pimpl; // opaque type here  
};  
  
```  
  
 L’idiome pimpl évite les cascades de reconstruction et de mises en page de l’objet fragile. Il est particulièrement adaptée pour les types courants (de manière transitive).  
  
## <a name="pimpl-implementation"></a>Implémentation de Pimpl  
 Définir la `impl` classe dans le fichier .cpp.  
  
```cpp  
// my_class.cpp  
class my_class::impl {  // defined privately here  
  // ... all private data and functions: all of these  
  //     can now change without recompiling callers ...  
};  
my_class::my_class(): pimpl( new impl )  
{  
  // ... set impl values ...   
}  
```  
  
## <a name="best-practices"></a>Recommandations  
 Pensez à ajouter la prise en charge pour la spécialisation de permutation non lanceurs.  
  
## <a name="see-also"></a>Voir aussi  
 [Bienvenue dans C++](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [Référence du langage C++](../cpp/cpp-language-reference.md)   
 [Bibliothèque C++ standard](../standard-library/cpp-standard-library-reference.md)