---
title: "/Wp64 (D&#233;tecter les probl&#232;mes de portabilit&#233; 64&#160;bits) | Microsoft Docs"
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
  - "VC.Project.VCCLWCECompilerTool.Detect64BitPortabilityProblems"
  - "VC.Project.VCCLCompilerTool.Detect64BitPortabilityProblems"
  - "/wp64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Wp64 (option du compilateur C++)"
  - "compilateur 64 bits (C++), détecter les problèmes de portabilité"
  - "Wp64 (option du compilateur C++)"
  - "-Wp64 (option du compilateur C++)"
ms.assetid: 331ae5aa-e627-4d03-8f63-dd2c2d76dadd
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Wp64 (D&#233;tecter les probl&#232;mes de portabilit&#233; 64&#160;bits)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'option du compilateur est obsolète. Dans les versions de Visual studio antérieures à Visual Studio 2013, cette option détecte les problèmes de portabilité 64 bits sur les types qui sont également marqués avec le mot clé [\_\_w64](../../cpp/w64.md).  
  
## Syntaxe  
  
```  
/Wp64  
```  
  
## Notes  
 Par défaut, dans les versions de Visual Studio antérieures à Visual Studio 2013, l'option de compilateur **\/Wp64** est désactivée dans le compilateur Visual C\+\+ 32 bits et elle est activée dans le compilateur Visual C\+\+ 64 bits.  
  
> [!IMPORTANT]
>  L'option de compilateur [\/Wp64](../../build/reference/wp64-detect-64-bit-portability-issues.md) et le mot clé [\_\_w64](../../cpp/w64.md) sont déconseillés dans Visual Studio 2010 et Visual Studio 2012 et non pris en charge depuis Visual Studio 2013. Si vous convertissez un projet qui utilise ce commutateur, le commutateur ne sera pas migré lors de la conversion. Pour utiliser cette option dans Visual Studio 2010 ou Visual Studio 2012, vous devez taper le commutateur du compilateur sous **Options supplémentaires** dans la section **Ligne de commande** des propriétés du projet. Si vous utilisez l’option de compilateur **\/Wp64** sur la ligne de commande, le compilateur émet l’avertissement de ligne de commande D9002. Au lieu d’utiliser cette option et un mot clé pour détecter les problèmes de portabilité 64 bits, utilisez un compilateur Visual C\+\+ qui cible une plateforme 64 bits et spécifiez l’option [\/W4](../../build/reference/compiler-option-warning-level.md). Pour plus d’informations, consultez [Configuration des programmes pour les processeurs 64 bits](../../build/configuring-programs-for-64-bit-visual-cpp.md).  
  
 Les variables des types suivants sont testées sur un système d’exploitation 32 bits comme si elles étaient utilisées sur un système d’exploitation 64 bits :  
  
-   int  
  
-   long  
  
-   pointer  
  
 Si vous compilez régulièrement votre application avec un compilateur 64 bits, vous pouvez désactiver **\/Wp64** dans vos compilations 32 bits, car le compilateur 64 bits détectera tous les problèmes. Pour plus d’informations sur la façon de cibler un système d’exploitation Windows 64 bits, consultez [Configuration des programmes pour les processeurs 64 bits](../../build/configuring-programs-for-64-bit-visual-cpp.md).  
  
### Pour définir cette option du compilateur dans l’environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriétés** du projet.  
  
     Pour plus d’informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Changez la zone **Options supplémentaires** pour y inclure **\/Wp64**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Detect64BitPortabilityProblems%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [Configuration des programmes pour les processeurs 64 bits](../../build/configuring-programs-for-64-bit-visual-cpp.md)