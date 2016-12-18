---
title: "bss_seg | Microsoft Docs"
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
  - "vc-pragma.bss_seg"
  - "bss_seg_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "bss_seg (pragma)"
  - "pragmas, bss_seg"
ms.assetid: 755f0154-de51-4778-97d3-c9b24e445079
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# bss_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie le segment où les variables non initialisées sont stockées dans le fichier .obj.  
  
## Syntaxe  
  
```  
  
#pragma bss_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## Notes  
 Les fichiers .obj peuvent être affichés avec l'application [dumpbin](../build/reference/dumpbin-command-line.md).  Le segment par défaut dans le fichier .obj pour les données non initialisées est .bss.  Dans certains cas, l'utilisation de **bss\_seg** peut accélérer les temps de chargement en regroupant les données non initialisées en une seule section.  
  
 **bss\_seg** sans paramètre réinitialise le segment à .bss.  
  
 **push** \(facultatif\)  
 Place un enregistrement sur la pile interne du compilateur.  Une instruction **push** peut avoir un *identifier* et un *segment\-name*.  
  
 **pop** \(facultatif\)  
 Supprime un enregistrement du haut de la pile interne du compilateur.  
  
 *identifier* \(facultatif\)  
 Lorsqu'il est utilisé avec **push**, il assigne un nom à l'enregistrement sur la pile interne du compilateur.  Lorsqu'il est utilisé avec **pop**, il dépile les enregistrements de la pile interne jusqu'à ce que *identifier* soit supprimé. Si *identifier* est introuvable sur la pile interne, rien n'est dépilé.  
  
 *identifier* active plusieurs enregistrements à dépiler avec une seule commande **pop**.  
  
 *"segment\-name"* \(facultatif\)  
 Nom d'un segment*.* Lorsqu'il est utilisé avec **pop**, la pile est dépilée et *segment\-name* devient le nom de segment actif.  
  
 *"segment\-class"* \(facultatif\)  
 Incluse pour la compatibilité avec les versions de C\+\+ antérieures à la version 2.0.  Elle est ignorée.  
  
## Exemple  
  
```  
// pragma_directive_bss_seg.cpp  
int i;                     // stored in .bss  
#pragma bss_seg(".my_data1")  
int j;                     // stored in "my_data1"  
  
#pragma bss_seg(push, stack1, ".my_data2")     
int l;                     // stored in "my_data2"  
  
#pragma bss_seg(pop, stack1)   // pop stack1 from stack  
int m;                     // stored in "stack_data1"  
  
int main() {  
}  
```  
  
 Vous pouvez également spécifier des sections pour les variables initialisées \([data\_seg](../preprocessor/data-seg.md)\), les fonctions \([code\_seg](../preprocessor/code-seg.md)\) et les variables const \([const\_seg](../preprocessor/const-seg.md)\).  
  
 Les données allouée à l'aide du pragma **bss\_seg** ne conservent aucune information concernant leur emplacement.  
  
 Consultez [\/SECTION](../build/reference/section-specify-section-attributes.md) pour obtenir la liste des noms à ne pas utiliser lorsque vous créez une section.  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)