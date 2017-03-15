---
title: "code_seg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "code_seg_CPP"
  - "vc-pragma.code_seg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "code_seg (pragma)"
  - "pragmas, code_seg"
ms.assetid: bf4faac1-a511-46a6-8d9e-456851d97d56
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# code_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie le segment de texte dans lequel les fonctions sont stockées dans un fichier .obj.  
  
## Syntaxe  
  
```  
#pragma code_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## Notes  
 La directive de pragma `code_seg` ne contrôle pas l'emplacement de code objet généré pour les modèles instanciés, ni le code généré de manière implicite par le compilateur \(par exemple, les fonctions membres spéciales\).  Il est recommandé d'utiliser l'attribut [\_\_declspec\(code\_seg\(...\)\)](../cpp/code-seg-declspec.md), car il permet de contrôler l'emplacement de tout le code objet.  Cela comprend le code généré par le compilateur.  
  
 Un *segment* d'un fichier .obj est un bloc nommé de données chargées en mémoire comme un ensemble.  Un *segment de texte* est un segment qui contient du code exécutable.  Dans cet article, les termes *segment* et *section* sont utilisés indifféremment.  
  
 La directive de pragma `code_seg` indique au compilateur de déplacer tout prochain code objet de l'unité de traduction vers un segment de texte nommé `segment-name`.  Par défaut, le segment de texte utilisé pour les fonctions d'un fichier .obj est nommé ".text".  
  
 Une directive de pragma `code_seg` sans paramètres réinitialise le nom du segment de texte en ".text" pour le prochain code objet.  
  
 **Push** \(facultatif\)  
 Place un enregistrement sur la pile interne du compilateur.  Un **push** peut avoir un `identifier` et un `segment-name`.  
  
 **pop** \(facultatif\)  
 Supprime un enregistrement du haut de la pile interne du compilateur.  
  
 `identifier` \(facultatif\)  
 En cas d'utilisation avec **push**, assigne un nom à l'enregistrement sur la pile interne du compilateur.  En cas d'utilisation avec **pop**, dépile les enregistrements de la pile interne jusqu'à ce que `identifier` soit supprimé ; si `identifier` est introuvable sur la pile interne, rien n'est dépilé.  
  
 `identifier` permet à plusieurs enregistrements d'être dépilés à l'aide d'une seule commande **pop**.  
  
 "`segment-name`" \(facultatif\)  
 Nom d'un segment.  Lorsqu'il est utilisé avec **pop**, la pile est dépilée et `segment-name` devient le nom du segment de texte actif.  
  
 "`segment-class`" \(facultatif\)  
 Ignoré, mais inclus pour des raisons de compatibilité avec les versions de C\+\+ antérieures à la version 2.0.  
  
 Vous pouvez utiliser l'application [DUMPBIN.EXE](../build/reference/dumpbin-command-line.md) pour afficher les fichiers .obj.  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] comprend une version de DUMPBIN pour chaque architecture cible prise en charge.  
  
## Exemple  
 Cet exemple montre comment utiliser la directive de pragma `code_seg` afin de contrôler l'emplacement du code objet :  
  
```  
// pragma_directive_code_seg.cpp  
void func1() {                  // stored in .text  
}  
  
#pragma code_seg(".my_data1")  
void func2() {                  // stored in my_data1  
}  
  
#pragma code_seg(push, r1, ".my_data2")  
void func3() {                  // stored in my_data2  
}  
  
#pragma code_seg(pop, r1)      // stored in my_data1  
void func4() {  
}  
  
int main() {  
}  
```  
  
 Pour obtenir la liste des noms à ne pas utiliser lorsque vous créez une section, consultez [\/SECTION](../build/reference/section-specify-section-attributes.md).  
  
 Vous pouvez également spécifier des sections pour les données initialisées \([data\_seg](../preprocessor/data-seg.md)\), les données non initialisées \([bss\_seg](../preprocessor/bss-seg.md)\) et les variables const \([const\_seg](../preprocessor/const-seg.md)\).  
  
## Voir aussi  
 [code\_seg \(\_\_declspec\)](../cpp/code-seg-declspec.md)   
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)