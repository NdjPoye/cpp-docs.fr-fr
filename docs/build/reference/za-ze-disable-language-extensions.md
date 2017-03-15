---
title: "/Za, /Ze (D&#233;sactiver les extensions de langage) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.DisableLanguageExtensions"
  - "/za"
  - "/ze"
  - "VC.Project.VCCLCompilerTool.DisableLanguageExtensions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Za (option du compilateur C++)"
  - "/Ze (option du compilateur C++)"
  - "Désactivation des extensions de langage (option du compilateur)"
  - "activer les extensions de langage"
  - "extensions de langage"
  - "extensions de langage, désactiver dans le compilateur"
  - "Za (option du compilateur C++)"
  - "-Za (option du compilateur C++)"
  - "Ze (option du compilateur C++)"
  - "-Ze (option du compilateur C++)"
ms.assetid: 65e49258-7161-4289-a176-7c5c0656b1a2
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# /Za, /Ze (D&#233;sactiver les extensions de langage)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'option du compilateur **\/Za** émet une erreur pour les constructions de langage qui ne sont pas compatibles avec ANSI C ou ANSI C\+\+.  L'option du compilateur **\/Ze**, qui est la valeur par défaut, active des extensions Microsoft.  
  
## Syntaxe  
  
```  
/Za  
/Ze  
```  
  
## Notes  
  
> [!NOTE]
>  L'option **\/Ze** est déconseillée.  Pour plus d'informations, consultez [Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/fr-fr/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce).  
  
 Le compilateur [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] offre un certain nombre de fonctionnalités en plus de celles qui sont spécifiées dans les normes C ANSI ou C\+\+ ANSI.  Ces fonctionnalités sont désignées collectivement sous le nom d'extensions Microsoft pour C et C\+\+.  Ces extensions sont disponibles lorsque l'option **\/Ze** est spécifiée ; en revanche, elles ne le sont pas lorsque l'option **\/Za** est spécifiée.  Pour plus d'informations, consultez [Extensions Microsoft pour C et C\+\+](../../build/reference/microsoft-extensions-to-c-and-cpp.md).  
  
 Désactivez les extensions de langage si vous envisagez de porter votre programme vers d'autres environnements.  Le compilateur considère alors les mots clés étendus comme de simples identificateurs, désactive les autres extensions Microsoft et définit automatiquement la macro prédéfinie `__STDC__` pour les programmes C.  
  
 D'autres options du compilateur utilisées avec l'option **\/Za** peuvent influer sur la manière dont le compilateur garantit la compatibilité ANSI.  Par exemple, **\/Za** et [\/fp \(Spécifier le comportement de virgule flottante\)](../../build/reference/fp-specify-floating-point-behavior.md) peuvent entraîner un comportement inattendu.  
  
 Consultez l'option du compilateur [\/Zc](../../build/reference/zc-conformance.md) pour savoir comment obtenir un comportement standard avec **\/Za**.  
  
 Pour plus d'informations sur les problèmes de conformité avec [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)], consultez [Compatibilité et problèmes de conformité en Visual C\+\+](../../misc/compatibility-and-compliance-issues-in-visual-cpp.md).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Langue**.  
  
4.  Modifiez la propriété **Désactivation des extensions de langage**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableLanguageExtensions%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)