---
title: "/Qfast_transcendentals (Force Fast Transcendentals) | Microsoft Docs"
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
  - "/Qfast_transcendentals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Qfast_transcendentals"
  - "Force Fast Transcendentals"
ms.assetid: 4de24bd1-38e6-49d4-9a05-04c9937d24ac
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Qfast_transcendentals (Force Fast Transcendentals)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Génère le code incorporé pour les fonctions transcendantes.  
  
## Syntaxe  
  
```  
/Qfast_transcendentals  
```  
  
## Notes  
 Cette option du compilateur force des fonctions transcendantes à être converties en code incorporé pour améliorer la vitesse d'exécution.  Cette option a un effet uniquement lorsqu'elle est couplée avec **\/fp:except** ou **\/fp:precise**.  La génération du code incorporé pour les fonctions transcendantes est déjà le comportement par défaut sous **\/fp:fast**.  
  
 Cette option est incompatible avec **\/fp:strict**.  Consultez [\/fp \(Spécifier le comportement de virgule flottante\)](../../build/reference/fp-specify-floating-point-behavior.md) pour plus d'informations sur les options du compilateur de virgule flottante.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Spécifiez l'option du compilateur dans la zone **Options supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [\/Q \(Opérations de bas niveau\), options](../../build/reference/q-options-low-level-operations.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)