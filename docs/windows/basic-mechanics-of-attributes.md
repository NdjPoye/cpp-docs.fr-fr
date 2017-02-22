---
title: "Basic Mechanics of Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attributes [C++], inserting in code"
  - "attributes [C++], about attributes"
ms.assetid: dc2069c3-b9f3-4a72-965c-4e5208ce8e34
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Basic Mechanics of Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il existe trois façons d'insérer des attributs dans votre projet.  Tout d'abord, vous pouvez les insérer manuellement dans votre code source.  Ensuite, vous pouvez les insérer à l'aide de la grille des propriétés d'un objet dans votre projet.  Enfin, vous pouvez les insérer à l'aide de les différents assistants.  Pour plus d'informations sur l'utilisation de la fenêtre Propriétés et les différents assistants, consultez [Création et gestion des projets Visual C\+\+](../ide/creating-and-managing-visual-cpp-projects.md).  
  
 Depuis Visual C\+\+ .NET, le compilateur identifie la présence d'attributs dans un fichier source et peut dynamiquement les analyser et vérifier pendant la compilation.  
  
 Comme avant, lorsque le projet est généré, le compilateur analyse chaque fichier source C\+\+, pour produire un fichier objet.  Toutefois, lorsque le compilateur rencontre un attribut, il est interprète et syntaxiquement vérifié.  Le compilateur appelle ensuite dynamiquement un fournisseur d'attribut pour insérer le code ou pour apporter d'autres modifications au moment de la compilation.  l'implémentation du fournisseur diffère selon le type d'attribut.  Par exemple, les attributs ATL\-mis en relation sont implémentés par Atlprov.dll.  
  
 l'illustration suivante montre la relation entre le compilateur et le fournisseur d'attribut.  
  
 ![Communication des attributs de composants](../windows/media/vccompattrcomm.png "vcCompAttrComm")  
  
> [!NOTE]
>  l'utilisation d'attribut ne modifie pas le contenu du fichier source.  La seule fois le code généré d'attribut est visible pendant les sessions de débogage.  En outre, pour chaque fichier source dans le projet, vous pouvez générer un fichier texte et affiche les résultats de la substitution d'attribut.  Pour plus d'informations sur cette procédure, consultez [\/Fx \(Code injecté par fusion\)](../build/reference/fx-merge-injected-code.md) et le [Le code injecté par débogage](../Topic/How%20to:%20Debug%20Injected%20Code.md).  
  
 Comme la plupart des éléments C\+\+, les attributs ont un ensemble de fonctionnalités qui définit leur utilisation appropriée.  Cela est indiqué comme le contexte de l'attribut et est traité dans le tableau de contexte d'attribut pour chaque rubrique de référence d'attribut.  Par exemple, l'attribut de [coclasse](../windows/coclass.md) peut s'appliquer qu'à une classe ou une structure existante, par opposition à l'attribut de [cpp\_quote](../windows/cpp-quote.md) , qui peut être inséré n'importe où dans le fichier source C\+\+.  
  
## Voir aussi  
 [Concepts](../windows/attributed-programming-concepts.md)