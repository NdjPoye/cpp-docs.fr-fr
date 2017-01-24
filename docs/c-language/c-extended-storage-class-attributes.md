---
title: "Attributs &#233;tendus de classe de stockage C | Microsoft Docs"
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
  - "__declspec (mot clé) (C)"
  - "attributs étendus"
  - "attributs de classe de stockage étendue"
  - "spécificateurs de classe de stockage, classes de stockage C"
ms.assetid: 2580735c-f5bf-46ab-9468-0696893d82be
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Attributs &#233;tendus de classe de stockage C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Des informations plus récentes à ce sujet sont disponibles dans [\_\_declspec \(Référence C\+\+\)](../cpp/declspec.md).  
  
 La syntaxe à attributs étendus simplifie et normalise les extensions spécifiques à Microsoft pour le langage C.  Les attributs de classe de stockage qui utilisent la syntaxe à attributs étendus incluent thread, naked, dllimport et dllexport.  
  
 La syntaxe à attributs étendus utilisée pour la spécification des informations de classe de stockage utilise le mot clé \_\_declspec, qui indique qu'une instance d'un type donné doit être stockée avec un attribut de classe de stockage spécifique à Microsoft \(thread, naked, dllimport ou dllexport\).  Parmi les exemples d'autres modificateurs de classe de stockage figurent les mots clés static et extern.  Toutefois, ces mots clés font partie de la norme ANSI C et, en tant que tels, ne sont pas couverts par la syntaxe à attributs étendus.  
  
## Syntaxe  
 *storage\-class\-specifier*:  
 `__declspec` \( *extended\-decl\-modifier\-seq* \) \/\* Spécifique à Microsoft \*\/  
  
 *extended\-decl\-modifier\-seq*:  
 *extended\-decl\-modifier*  opt  
  
 *extended\-decl\-modifier\-seq extended\-decl\-modifier*  
  
 *extended\-decl\-modifier*:  
 **thread**  
  
 **naked**  
  
 **dllimport**  
  
 `dllexport`  
  
 Un espace blanc sépare les modificateurs de déclaration.  Notez que *extended\-decl\-modifier\-seq* peut être vide, auquel cas \_\_declspec n'a aucun effet.  
  
 Les attributs de classe de stockage thread, naked, dllimport et dllexport sont une propriété uniquement de la déclaration des données ou de la fonction à laquelle ils sont appliqués. Ils ne redéfinissent pas les attributs de type de la fonction elle\-même.  L'attribut thread affecte uniquement les données.  L'attribut naked affecte uniquement les fonctions.  Les attributs dllimport et dllexport affectent les fonctions et les données.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Déclarations et types](../c-language/declarations-and-types.md)