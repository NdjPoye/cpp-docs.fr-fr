---
title: "implementation_only | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "implementation_only"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "implementation_only (attribut)"
ms.assetid: d8cabc86-4425-45a0-9587-d57536980088
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# implementation_only
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Supprime la génération du fichier d'en\-tête .tlh \(fichier d'en\-tête principal\).  
  
## Syntaxe  
  
```  
implementation_only  
```  
  
## Notes  
 Ce fichier contient toutes les déclarations utilisées pour exposer le contenu de la bibliothèque de types.  Le fichier d'en\-tête .tli, avec les implémentations des fonctions membres de wrapper, sera généré et inclus dans la compilation.  
  
 Lorsque cet attribut est spécifié, le contenu de l'en\-tête .tli se trouve dans le même espace de noms que celui utilisé normalement dans l'en\-tête .tlh.  En outre, les fonctions membres ne sont pas déclarées comme inline.  
  
 L'attribut `implementation_only` est conçu pour être utilisé conjointement avec l'attribut [no\_implementation](../preprocessor/no-implementation.md) afin de conserver les implémentations hors du fichier d'en\-tête précompilé \(PCH\).  Une instruction `#import` avec l'attribut `no_implementation` est placée dans la région source utilisée pour créer le PCH.  Le PCH résultant est utilisé par plusieurs fichiers sources.  Une instruction `#import` avec l'attribut `implementation_only` est ensuite utilisée hors de la zone PCH.  Vous ne devez utiliser cette instruction qu'une seule fois dans l'un des fichiers sources.  Cela permet de générer toutes les fonctions membres de wrapper requises sans recompilation supplémentaire pour chaque fichier source.  
  
> [!NOTE]
>  L'attribut `implementation_only` dans une instruction `#import` doit être utilisé conjointement avec une autre instruction `#import`, de la même bibliothèque de types, avec l'attribut `no_implementation`.  Sinon, des erreurs du compilateur sont générées.  Cela est dû au fait que les définitions de classe wrapper générées par l'instruction `#import` avec l'attribut `no_implementation` sont requises pour compiler les implémentations générées par l'attribut `implementation_only`.  
  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)