---
title: "/GZ (Activer les v&#233;rifications des erreurs au moment de l&#39;ex&#233;cution pour le frame de pile) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/gz"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GZ (option du compilateur C++)"
  - "versions debug, interception des erreurs de version Release"
  - "GZ (option du compilateur C++)"
  - "-GZ (option du compilateur C++)"
  - "erreurs de version Release"
ms.assetid: b3efeeff-d5e3-4057-91c9-f6fc73d0270c
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /GZ (Activer les v&#233;rifications des erreurs au moment de l&#39;ex&#233;cution pour le frame de pile)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Exécute les mêmes opérations que l'option [\/RTC \(Vérifications des erreurs au moment de l'exécution\)](../../build/reference/rtc-run-time-error-checks.md).  Déconseillé.  
  
## Syntaxe  
  
```  
/GZ  
```  
  
## Notes  
 **\/GZ** est uniquement destiné à une utilisation dans une génération de \([\/Od \(Désactiver \(Débogage\)\)](../../build/reference/od-disable-debug.md)\) non optimisée.  
  
 **\/GZ** est déconseillé ; utilisation de [\/RTC \(Vérifications des erreurs au moment de l'exécution\)](../../build/reference/rtc-run-time-error-checks.md) à la place.  Pour plus d'informations, consultez [Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/fr-fr/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Spécifiez l'option du compilateur dans la zone **Options supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)