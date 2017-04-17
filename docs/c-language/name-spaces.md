---
title: "Espaces de noms | Microsoft Docs"
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
  - "balises d'énumération"
  - "espaces de noms (C++)"
  - "noms (C++), éléments déclarés"
  - "balises de structure"
  - "balises, balises de structure"
  - "union (mot clé) (C)"
  - "union (mot clé) (C), balises"
ms.assetid: b4bda1d1-cb5e-4f60-ac2b-29af93d8a9a2
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Espaces de noms
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le compilateur configure les « espaces de noms » pour établir une distinctions entre les identificateurs utilisés pour différents genres d'éléments.  Les noms dans chaque espace de noms doivent être uniques pour éviter tout conflit, mais un nom identique peut apparaître dans plusieurs espaces de noms.  Cela signifie que vous pouvez utiliser le même identificateur pour deux ou plusieurs éléments différents, à condition que ces éléments se trouvent dans différents espaces de noms.  Le compilateur peut résoudre les références selon le contexte syntaxique de l'identificateur dans le programme.  
  
> [!NOTE]
>  Ne confondez pas la notion C limitée d'un espace de noms avec la fonction « espace de noms » de C\+\+.  Pour plus d'informations, consultez [Espaces de noms](../cpp/namespaces-cpp.md) dans le Guide de référence du langage C*\+\+*.  
  
 Cette liste décrit les espaces de noms utilisés dans C.  
  
 Étiquettes d'instruction  
 Les étiquettes d'instructions nommées font partie des instructions.  Les définitions des étiquettes d'instructions sont toujours suivies par deux\-points mais ne font pas partie des étiquettes **case**.  Les utilisations des étiquettes d'instructions suivent toujours immédiatement le mot clé `goto`.  Les étiquettes d'instructions ne doivent pas nécessairement être séparées des autres noms ou des noms d'étiquette dans les autres fonctions.  
  
 Balises de structure, d'union et d'énumération  
 Ces balises font partie des spécificateurs de type de structure, d'union et d'énumération et, si elles sont présentes, suivent toujours immédiatement les mots réservés `struct`, **union** ou `enum`.  Les noms de balises doivent être séparés de toutes les autres balises de structure, d'énumération ou d'union avec la même visibilité.  
  
 Membres de structures ou d'unions  
 Les noms de membre sont alloués dans les espaces de noms associés à chaque type de structure et d'union.  Autrement dit, le même identificateur peut être un nom de composant dans plusieurs structures ou unions simultanément.  Les définitions de noms composants apparaissent toujours dans les spécificateurs de type de structure ou d'union.  Les utilisations des noms de composant suivent toujours immédiatement les opérateurs de sélection de membres \(**–\>** et **.**\).  Le nom d'un membre doit être unique dans la structure ou l'union, mais pas nécessairement distinct d'autres noms du programme, notamment les noms des membres des différentes structures et unions, ou du nom de la structure elle\-même.  
  
 Identificateurs ordinaires  
 Tous les autres noms se trouvent dans un espace de noms qui inclut les variables, les fonctions \(y compris les paramètres formels et les variables locales\) et les constantes d'énumération.  Les noms d'identificateurs ont une visibilité imbriquée, vous pouvez donc les redéfinir dans des blocs.  
  
 Noms de typedef  
 Les noms de typedef ne peuvent pas être utilisés en tant qu'identificateurs dans la même portée.  
  
 Par exemple, étant donné que les balises de structure, les membres de structure et les noms de variable se trouvent dans trois espaces de noms différents, les trois éléments nommés `student` dans cet exemple ne sont pas en conflit.  Le contexte de chaque élément permet une interprétation correcte de chaque occurrence de `student` dans le programme. \(Pour plus d'informations sur les structures, consultez [Déclarations de structure](../c-language/structure-declarations.md).\)  
  
```  
struct student {  
   char student[20];  
   int class;  
   int id;  
   } student;  
```  
  
 Lorsque `student` apparaît après le mot clé `struct`, le compilateur l'identifie comme une balise de structure.  Lorsque `student` apparaît après un opérateur de sélection de membres \(**–\>** ou **.**\), le nom fait référence au membre de structure.  Dans d'autres contextes, `student` désigne la variable de structure.  Toutefois, surcharger l'espace de noms de balise n'est pas recommandé car cela masque la signification.  
  
## Voir aussi  
 [Structure du programme](../c-language/program-structure.md)