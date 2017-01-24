---
title: "/Tc, /Tp, /TC, /TP (Sp&#233;cifier le type de fichier source) | Microsoft Docs"
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
  - "VC.Project.VCCLWCECompilerTool.CompileAs"
  - "VC.Project.VCCLCompilerTool.CompileAs"
  - "/Tp"
  - "/tc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Tc (option du compilateur C++)"
  - "/Tp (option du compilateur C++)"
  - "fichiers sources, spécifier au compilateur"
  - "Tc (option du compilateur C++)"
  - "-Tc (option du compilateur C++)"
  - "Tp (option du compilateur C++)"
  - "-Tp (option du compilateur C++)"
ms.assetid: 7d9d0a65-338b-427c-8b48-fff30e2f9d2b
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Tc, /Tp, /TC, /TP (Sp&#233;cifier le type de fichier source)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'option **\/Tc** spécifie que `filename` est un fichier source C, même s'il ne possède pas d'extension .c.  L'option **\/Tp** spécifie que `filename` est un fichier source C\+\+, même si celui\-ci ne possède pas l'extension .cpp ou .cxx.  L'espace compris entre l'option et `filename` est facultatif.  Chaque option spécifie un seul fichier ; pour spécifier des fichiers supplémentaires, répétez l'option.  
  
 **\/TC** et **\/TP** sont des variantes globales de **\/Tc** et **\/Tp**.  Ils indiquent au compilateur de considérer tous les fichiers spécifiés sur la ligne de commande en tant que fichiers sources C \(**\/TC**\) ou fichiers source C\+\+ \(**\/TP**\), sans tenir compte de leur emplacement sur la ligne de commande par rapport à l'option.  Ces options globales peuvent être substituées sur un fichier unique au moyen de **\/Tc** ou **\/Tp**.  
  
## Syntaxe  
  
```  
/Tcfilename  
/Tpfilename  
/TC  
/TP  
```  
  
## Arguments  
 `filename`  
 Fichier source C ou C\+\+.  
  
## Notes  
 Par défaut, CL présume que les fichiers dotés de l'extension .c sont des fichiers source C et que les fichiers portant l'extension .cpp ou .cxx sont des fichiers sources C\+\+.  
  
 Lorsque **TC** ou l'option **Tc** est spécifiée, toute spécification de l'option [\/Zc:wchar\_t \(wchar\_t est un type natif\)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) est ignorée.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Avancé**.  
  
4.  Modifiez la propriété **Compilation sous**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs%2A>.  
  
## Exemples  
 La ligne de commande CL suivante spécifie que MAIN.c, TEST.prg et COLLATE.prg sont tous des fichiers source C.  CL ne reconnaîtra pas PRINT.prg.  
  
```  
CL MAIN.C /TcTEST.PRG /TcCOLLATE.PRG PRINT.PRG  
```  
  
 La ligne de commande CL suivante spécifie que TEST1.c, TEST2.cxx, TEST3.huh et TEST4.o sont compilés en tant que fichiers C\+\+, et que TEST5.z est compilé en tant que fichier C.  
  
```  
CL TEST1.C TEST2.CXX TEST3.HUH TEST4.O /Tc TEST5.Z /TP  
```  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)