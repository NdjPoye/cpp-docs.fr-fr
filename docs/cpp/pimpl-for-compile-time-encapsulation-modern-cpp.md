---
title: "Pimpl pour l&#39;encapsulation au moment de la compilation (Modern C++) | Microsoft Docs"
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
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Pimpl pour l&#39;encapsulation au moment de la compilation (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'*idiome pimpl* est une technique moderne de C\+\+ pour masquer l'implémentation, réduire le couplage, et pour séparer les interfaces.  Pimpl est l'abréviation de « pointeur vers implémentation. » Vous connaissez peut\-être déjà le concept mais le connaissez sous d'autres noms tels que Cheshire Cat ou idiome de pare\-feu du compilateur.  
  
## Pourquoi utiliser pimpl ?  
 Voici comment l'idiome pimpl peut améliorer le cycle de vie de développement logiciel :  
  
-   Minimisation des dépendances de compilation.  
  
-   Séparation d'interface et d'implémentation.  
  
-   Portabilité  
  
## En\-tête de Pimpl  
  
```cpp  
  
// my_class.h  
class my_class {  
   //  ... all public and protected stuff goes here ...  
private:  
   class impl; unique_ptr<impl> pimpl; // opaque type here  
};  
  
```  
  
 L'idiome pimpl évite des cascades de reconstruction et les mises en page fragiles de l'objet.  Il convient bien pour les types \(transitivement\) très utilisés.  
  
## Implémentation de pimple  
 Définissez la classe `impl` dans le fichier.cpp.  
  
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
  
## Méthodes conseillées  
 Demandez\-vous s'il faut ajouter la prise en charge de la spécialisation non\-throwing swap.  
  
## Voir aussi  
 [Bienvenue dans C\+\+](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [Référence du langage C\+\+](../cpp/cpp-language-reference.md)   
 [Bibliothèque standard C\+\+](../standard-library/cpp-standard-library-reference.md)