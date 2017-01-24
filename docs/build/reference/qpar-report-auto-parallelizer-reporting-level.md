---
title: "/Qpar-report (Niveau de rapport du parall&#233;liseur automatique) | Microsoft Docs"
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
ms.assetid: 562673b9-02da-4bf8-bb64-70bc25ef4651
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Qpar-report (Niveau de rapport du parall&#233;liseur automatique)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Active la fonctionnalité de création de rapports du [Paralléliseur automatique](../../parallel/auto-parallelization-and-auto-vectorization.md) du compilateur et spécifie le niveau des messages d'information pour la sortie pendant la compilation.  
  
## Syntaxe  
  
```  
/Qpar-report:{1}{2}  
```  
  
## Notes  
 **\/Qpar\-report:1**  
 Génère un message d'information pour les boucles parallélisées.  
  
 **\/Qpar\-report:2**  
 Génère un message d'information pour les boucles parallélisées et non parallélisées, ainsi qu'un code motif.  
  
 Les messages sont signalés à stdout.  Si aucun message d'information n'est signalé, cela signifie que le code ne contient pas de boucle ou que le niveau de rapport n'a pas été défini pour signaler les boucles non parallélisées.  Pour plus d'informations sur les codes motifs et les messages, consultez [Messages du vectoriseur et du paralléliseur](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
### Pour définir l'option de compilateur \/Qpar\-report dans Visual Studio  
  
1.  Dans l'**Explorateur de solutions**, ouvrez le menu contextuel du projet et choisissez **Propriétés**.  
  
2.  Dans la boîte de dialogue **Pages de propriétés**, sous **C\/C\+\+**, sélectionnez **Ligne de commande**.  
  
3.  Dans la zone **Options supplémentaires**, entrez `/Qpar-report: 1` ou `/Qpar-report: 2`.  
  
### Pour définir l'option de compilateur \/Qpar\-report par programmation  
  
-   Utilisez l'exemple de code fourni dans <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [\/Q \(Opérations de bas niveau\), options](../../build/reference/q-options-low-level-operations.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [Programmation parallèle en code natif](http://go.microsoft.com/fwlink/?LinkId=263662)