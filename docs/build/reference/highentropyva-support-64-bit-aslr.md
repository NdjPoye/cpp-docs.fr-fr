---
title: "/HIGHENTROPYVA (Prendre en charge l&#39;ASLR 64&#160;bits) | Microsoft Docs"
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
ms.assetid: fe35f9f7-d28e-4694-9aeb-a79db06168e0
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# /HIGHENTROPYVA (Prendre en charge l&#39;ASLR 64&#160;bits)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie que l'image exécutable prend en charge la fonctionnalité de randomisation du format d'espace d'adresse \(ASLR\) 64 bits de forte entropie.  
  
## Syntaxe  
  
```  
/HIGHENTROPYVA[:NO]  
```  
  
## Notes  
 Par défaut, \/HIGHENTROPYVA est activé pour les images exécutables 64 bits.  Il n'est pas applicable aux images exécutables 32 bits.  Pour activer cette option, \/DYNAMICBASE doit aussi être activé.  
  
 \/HIGHENTROPYVA modifie l'en\-tête d'un fichier .dll ou .exe pour indiquer si ASLR est pris en charge avec des adresses 64 bits.  Quand cette option est définie au niveau d'un fichier exécutable et de tous les modules dont il dépend, un système d'exploitation qui prend en charge l'ASLR 64 bits peut redéfinir les segments de l'image exécutable au moment du chargement en utilisant des adresses aléatoires tirées d'un espace d'adressage virtuel de 64 bits.  Devant ce grand espace d'adressage, il est plus difficile pour une personne malveillante de deviner l'emplacement d'une région de mémoire particulière.  
  
### Pour définir cette option d'éditeur de liens dans Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriétés** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Développez le nœud **Propriétés de configuration**.  
  
3.  Développez le nœud **Éditeur de liens**.  
  
4.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
5.  Dans **Options supplémentaires**, entrez `/HIGHENTROPYVA` ou `/HIGHENTROPYVA:NO`.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)