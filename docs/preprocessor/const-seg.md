---
title: "const_seg | Microsoft Docs"
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
  - "vc-pragma.const_seg"
  - "const_seg_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "const_seg (pragma)"
  - "pragmas, const_seg"
ms.assetid: 1eb58ee2-fb0e-4a39-9621-699c8f5ef957
caps.latest.revision: 12
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# const_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie le segment où les variables [const](../cpp/const-cpp.md) sont stockées dans le fichier .obj.  
  
## Syntaxe  
  
```  
#pragma const_seg ( [ [ { push | pop}, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## Notes  
 Les termes *segment* et *section* sont interchangeables dans cette rubrique.  
  
 Les fichiers OBJ peuvent être affichés à l'aide de l'application [dumpbin](../build/reference/dumpbin-command-line.md).  Dans le fichier .obj, le segment par défaut pour les variables `const` est .rdata.  Certaines variables `const`, telles que les scalaires, sont automatiquement incluses en ligne dans le flux de code.  Le code inline n'apparaîtra pas dans .rdata.  
  
 La définition d'un objet qui requiert une initialisation dynamique dans un `const_seg` entraîne un comportement non défini.  
  
 `#pragma const_seg` sans paramètre réinitialise le segment sur .rdata.  
  
 `push`\(facultatif\)  
 Place un enregistrement sur la pile interne du compilateur.  Un `push` peut avoir un `identifier` et un `segment-name`.  
  
 `pop`\(facultatif\)  
 Supprime un enregistrement du haut de la pile interne du compilateur.  
  
 `identifier`\(facultatif\)  
 En cas d'utilisation avec `push`, assigne un nom à l'enregistrement sur la pile interne du compilateur.  En cas d'utilisation avec `pop`, dépile les enregistrements de la pile interne jusqu'à ce que `identifier` soit supprimé ; si `identifier` est introuvable sur la pile interne, rien n'est dépilé.  
  
 Utiliser `identifier` permet à plusieurs enregistrements d'être dépilés à l'aide d'une seule commande `pop`.  
  
 "`segment-name`" \(facultatif\)  
 Nom d'un segment.  Lorsqu'il est utilisé avec `pop`, la pile est dépilée et `segment-name` devient le nom du segment actif.  
  
 "`segment-class`" \(facultatif\)  
 Incluse pour la compatibilité avec les versions de C\+\+ antérieures à la version 2.0.  Elle est ignorée.  
  
## Exemple  
  
```  
// pragma_directive_const_seg.cpp  
// compile with: /EHsc  
#include <iostream>  
  
const int i = 7;               // inlined, not stored in .rdata  
const char sz1[]= "test1";     // stored in .rdata  
  
#pragma const_seg(".my_data1")  
const char sz2[]= "test2";     // stored in .my_data1  
  
#pragma const_seg(push, stack1, ".my_data2")  
const char sz3[]= "test3";     // stored in .my_data2  
  
#pragma const_seg(pop, stack1) // pop stack1 from stack  
const char sz4[]= "test4";     // stored in .my_data1  
  
int main() {  
    using namespace std;  
   // const data must be referenced to be put in .obj  
   cout << sz1 << endl;  
   cout << sz2 << endl;  
   cout << sz3 << endl;  
   cout << sz4 << endl;  
}  
```  
  
  **test1**  
**test2**  
**test3**  
**test4**   
## Commentaires  
 Consultez [\/SECTION](../build/reference/section-specify-section-attributes.md) pour obtenir la liste des noms à ne pas utiliser lorsque vous créez une section.  
  
 Vous pouvez également spécifier des sections pour les données initialisées \([data\_seg](../preprocessor/data-seg.md)\), les données non initialisées \([bss\_seg](../preprocessor/bss-seg.md)\) et les fonctions \([code\_seg](../preprocessor/code-seg.md)\).  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)