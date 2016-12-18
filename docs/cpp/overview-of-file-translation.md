---
title: "Vue d&#39;ensemble de la traduction de fichier | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "translation de fichier (C++), à propos de la translation de fichier"
  - "fichiers (C++), translation"
  - "prétraitement de la phase de translation"
  - "programmes (C++), conventions lexicales de"
  - "conversion (C++)"
  - "phases de translation"
ms.assetid: 5036c7b7-ccff-4e2c-b052-a9ea6c71af87
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Vue d&#39;ensemble de la traduction de fichier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les programmes C\+\+, comme les programmes C, se composent d'un ou plusieurs fichiers.  Chacun de ces fichiers est traduit dans l'ordre conceptuel suivant \(l'ordre réel suit la règle « comme si » : la traduction doit avoir lieu comme si les étapes ci\-dessous avaient été suivies\) :  
  
1.  Génération de jetons lexicaux.  Le mappage de caractère et le traitement de trigraphe, la ligne épissant et la génération de jetons sont exécutés dans cette phase de traduction.  
  
2.  Prétraitement.  Cette phase de traduction apporte les fichiers sources auxiliaires référencés par les directives `#include`, traite les directives de transformation de chaîne et de charizing et effectue le collage de jetons et l'expansion des macros \(pour plus d'informations, consultez [Directives de préprocesseur](../preprocessor/preprocessor-directives.md) dans la rubrique *Référence du préprocesseur*\).  Le résultat de la phase de prétraitement est une séquence de jetons qui, une fois combinés, définissent une unité de traduction.  
  
     Les directives de préprocesseur commencent toujours par le signe dièse \(**\#**\) \(autrement dit, le premier caractère autre que blanc sur la ligne doit être un signe dièse\).  Une seule directive de préprocesseur peut apparaître sur une ligne donnée.  Par exemple :  
  
    ```  
    #include <iostream>  // Include text of iostream in   
                         //  translation unit.  
    #define NDEBUG       // Define NDEBUG (NDEBUG contains empty   
                         //  text string).  
    ```  
  
3.  Génération de code.  Cette phase de traduction utilise les jetons générés dans la phase de prétraitement pour générer le code objet.  
  
     Pendant cette phase, l'activation syntaxique et sémantique du code source est exécutée.  
  
 Pour plus d'informations, consultez [Phases de traduction](../preprocessor/phases-of-translation.md) dans la rubrique *Référence du préprocesseur*.  
  
 Le préprocesseur C\+\+ est un sur\-ensemble strict du préprocesseur ANSI C, mais le préprocesseur C\+\+ diffère dans certaines instances.  La liste suivante décrit plusieurs différences entre le préprocesseur ANSI C et le préprocesseurs C\+\+ :  
  
-   Les commentaires sur une seule ligne sont pris en charge.  Pour plus d'informations, consultez [Commentaires](../cpp/comments-cpp.md).  
  
-   La macro prédéfinie **\_\_cplusplus**, est définie uniquement pour C\+\+.  Pour plus d'informations, consultez [Macros prédéfinies](../preprocessor/predefined-macros.md) dans la rubrique *Référence du préprocesseur*.  
  
-   Le préprocesseur C ne reconnaît pas les opérateurs C\+\+ : **.\***, **–\>\*** et `::`.  Pour plus d'informations sur les opérateurs, consultez [Opérateurs](../cpp/cpp-built-in-operators-precedence-and-associativity.md) et [Expressions](../cpp/expressions-cpp.md).  
  
## Voir aussi  
 [Conventions lexicales](../cpp/lexical-conventions.md)