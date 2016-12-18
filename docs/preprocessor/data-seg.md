---
title: "data_seg | Microsoft Docs"
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
  - "data_seg_CPP"
  - "vc-pragma.data_seg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "data_seg (pragma)"
  - "pragmas, data_seg"
ms.assetid: 65c66466-4c98-494f-93af-106beb4caf78
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# data_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie le segment de données où les variables initialisées sont stockées dans le fichier .obj.  
  
## Syntaxe  
  
```  
  
#pragma data_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## Notes  
 Les termes *segment* et *section* sont interchangeables dans cette rubrique.  
  
 Les fichiers OBJ peuvent être affichés à l'aide de l'application [dumpbin](../build/reference/dumpbin-command-line.md).  Le segment par défaut dans le fichier .obj pour les variables initialisées est .data.  Les variables qui ne sont pas initialisées doivent être initialisées sur zéro et sont stockées dans .bss.  
  
 **data\_seg** sans paramètre réinitialise le segment sur .data.  
  
 **push** \(facultatif\)  
 Place un enregistrement sur la pile interne du compilateur.  Une instruction **push** peut avoir *identifier* et *segment\-name*.  
  
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
// pragma_directive_data_seg.cpp  
int h = 1;                     // stored in .data  
int i = 0;                     // stored in .bss  
#pragma data_seg(".my_data1")  
int j = 1;                     // stored in "my_data1"  
  
#pragma data_seg(push, stack1, ".my_data2")     
int l = 2;                     // stored in "my_data2"  
  
#pragma data_seg(pop, stack1)   // pop stack1 off the stack  
int m = 3;                     // stored in "stack_data1"  
  
int main() {  
}  
```  
  
 Les données allouées à l'aide de **data\_seg** ne conservent aucune information concernant leur emplacement.  
  
 Consultez [\/SECTION](../build/reference/section-specify-section-attributes.md) pour obtenir la liste des noms à ne pas utiliser lorsque vous créez une section.  
  
 Vous pouvez également spécifier des sections pour les variables const \([const\_seg](../preprocessor/const-seg.md)\), les données non initialisées \([bss\_seg](../preprocessor/bss-seg.md)\) et les fonctions \([code\_seg](../preprocessor/code-seg.md)\).  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)