---
title: "/Qvec-report (Niveau de rapport du vectoriseur automatique) | Microsoft Docs"
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
ms.assetid: 4778c9a3-0692-4085-9b05-1bfeadf4c74a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Qvec-report (Niveau de rapport du vectoriseur automatique)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Active la fonctionnalité de rapport du compilateur [AUTO\-Vectorizer](../../parallel/auto-parallelization-and-auto-vectorization.md) et spécifie le niveau des messages d'information pour la sortie pendant la compilation.  
  
## Syntaxe  
  
```  
/Qvec-report:{1}{2}  
```  
  
## Notes  
 **\/Qvec\-report:1**  
 Génère un message d'information pour les boucles for qui sont vectorisées.  
  
 **\/Qvec\-report:2**  
 Génère un message d'information pour les boucles for qui sont vectorisées et les boucles for qui ne sont pas vectorisées, avec un code de la raison.  
  
 Pour des informations sur les codes supplémentaires et les messages, consultez [Messages du vectoriseur et du paralléliseur](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
### Pour définir l'option \/Qvec\-report du compilateur dans Visual Studio  
  
1.  Dans l'**Explorateur de solutions**, ouvrez le menu contextuel du projet et choisissez **Propriétés**.  
  
2.  Dans la boîte de dialogue **Pages de propriétés**, sous **C\/C\+\+**, sélectionnez **Ligne de commande**.  
  
3.  Dans la zone **Options supplémentaires**, entrez `/Qvec-report:1` ou `/Qvec-report:2`.  
  
### Pour définir l'option \/Qvec\-report du compilateur par programmation  
  
-   Utilisez l'exemple de code dans <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [\/Q \(Opérations de bas niveau\), options](../../build/reference/q-options-low-level-operations.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [Programmation parallèle dans le Code Natif](http://go.microsoft.com/fwlink/?LinkId=263662)