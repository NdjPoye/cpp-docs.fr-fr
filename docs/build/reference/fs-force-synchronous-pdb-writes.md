---
title: "/FS (forcer les &#233;critures PDB synchrones) | Microsoft Docs"
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
  - "/FS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "-FS (option du compilateur C++)"
  - "/FS (option du compilateur C++)"
ms.assetid: b2caaffe-f6e1-4963-b068-648f06b105e0
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FS (forcer les &#233;critures PDB synchrones)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Force la sérialisation des écritures dans le fichier de base de données de programme \(PDB\) via MSPDBSRV.EXE des fichiers créées par [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) ou [\/ZI](../../build/reference/z7-zi-zi-debug-information-format.md).  
  
## Syntaxe  
  
```  
/FS  
```  
  
## Notes  
 Par défaut, lorsque **\/Zi** ou **\/ZI** est spécifié, le compilateur verrouille les fichiers PDB pour écrire des informations de type et les informations de débogage symboliques.  Cela peut réduire considérablement la durée d'exécution prend le compilateur de générer des informations de type lorsque le nombre de types est important.  Si un autre processus verrouille temporairement PDB fichier\- par exemple, les programme\- écrit dans un antivirus par le compilateur peuvent échouer et une erreur irrécupérable peut se produire.  Ce problème peut également se produire lorsque plusieurs copies de cl.exe accèdent le même fichier PDB\- par exemple, si votre solution a des projets indépendants qui utilisent les mêmes répertoires intermédiaires ou répertoires de sortie et builds parallèles sont activés.  L'option du compilateur **\/FS** empêche le compilateur de verrouiller le fichier PDB et d'écriture de force pour parcourir MSPDBSRV.EXE, qui sérialise l'accès.  Cela peut provoquer des builds beaucoup plus longues, et n'empêche pas toutes les erreurs qui peuvent survenir lorsque plusieurs instances de cl.exe accèdent au fichier PDB simultanément.  Nous vous recommandons de modifier votre solution afin que l'écriture indépendante de projets se fasse sur des emplacements intermédiaires de sortie, ou que vous rendiez un des projets dépendants de l'autre pour forcer la génération du projet sérialisé.  
  
 L'option [\/MP](../../build/reference/mp-build-with-multiple-processes.md) active **\/FS** par défaut.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le dossier **C\/C\+\+**.  
  
3.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
4.  Modifiez la propriété **Options supplémentaires** pour inclure `/FS` puis cliquez sur **OK**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)