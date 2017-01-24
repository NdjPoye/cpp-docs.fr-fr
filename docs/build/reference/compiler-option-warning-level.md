---
title: "/w, /Wn, /WX, /Wall, /wln, /wdn, /wen, /won (Niveau d&#39;avertissement) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.DisableSpecificWarnings"
  - "VC.Project.VCCLCompilerTool.WarningLevel"
  - "VC.Project.VCCLWCECompilerTool.DisableSpecificWarnings"
  - "VC.Project.VCCLCompilerTool.WarnAsError"
  - "VC.Project.VCCLWCECompilerTool.WarnAsError"
  - "/wx"
  - "VC.Project.VCCLWCECompilerTool.WarningLevel"
  - "/wall"
  - "VC.Project.VCCLCompilerTool.TreatSpecificWarningsAsErrors"
  - "/Wv"
  - "/w0"
  - "/w1"
  - "/w2"
  - "/w3"
  - "/w4"
  - "/wd"
  - "/we"
  - "/wo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/w (option du compilateur)"
  - "/W0 (option du compilateur C++)"
  - "/W1 (option du compilateur C++)"
  - "/W2 (option du compilateur C++)"
  - "/W3 (option du compilateur C++)"
  - "/W4 (option du compilateur C++)"
  - "/Wall (option du compilateur C++)"
  - "/wd (option du compilateur C++)"
  - "/we (option du compilateur C++)"
  - "/wo (option du compilateur C++)"
  - "/WX (option du compilateur C++)"
  - "w (option du compilateur C++)"
  - "-w (option du compilateur C++)"
  - "W0 (option du compilateur C++)"
  - "-W0 (option du compilateur C++)"
  - "W1 (option du compilateur C++)"
  - "-W1 (option du compilateur C++)"
  - "W2 (option du compilateur C++)"
  - "-W2 (option du compilateur C++)"
  - "W3 (option du compilateur C++)"
  - "-W3 (option du compilateur C++)"
  - "W4 (option du compilateur C++)"
  - "-W4 (option du compilateur C++)"
  - "Wall (option du compilateur C++)"
  - "-Wall (option du compilateur C++)"
  - "niveau d'avertissement (option du compilateur)"
  - "avertissements, en tant qu'erreurs (option du compilateur C++)"
  - "wd (option du compilateur C++)"
  - "-wd (option du compilateur C++)"
  - "we (option du compilateur C++)"
  - "-we (option du compilateur C++)"
  - "wo (option du compilateur C++)"
  - "-wo (option du compilateur C++)"
  - "WX (option du compilateur C++)"
  - "-WX (option du compilateur C++)"
ms.assetid: d6bc7bf5-c754-4879-909c-8e3a67e2629f
caps.latest.revision: 21
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /w, /Wn, /WX, /Wall, /wln, /wdn, /wen, /won (Niveau d&#39;avertissement)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie comment le compilateur génère les avertissements pour une compilation donnée.  
  
## Syntaxe  
  
```  
/w  
/Wn  
/WX  
/Wall  
/wln  
/wdn  
/wen  
/won  
```  
  
## Notes  
 Ces options et les arguments qui leur sont associés sont décrits dans le tableau suivant.  
  
|Option|Description|  
|------------|-----------------|  
|**\/w**|Désactive tous les avertissements du compilateur.|  
|**\/W** `n`|Spécifie le niveau d'avertissement devant être généré par le compilateur.  Les niveaux d'avertissement valides pour `n` sont compris entre 0 et 4 :<br /><br /> -   Le niveau 0 désactive tous les avertissements.<br />-   Le niveau 1 affiche les avertissements graves.  Le paramètre par défaut est le niveau 1.<br />-   Le niveau 2 affiche tous les avertissements de niveau 1 et de gravité inférieure au niveau 1.<br />-   Le niveau 3 affiche tous les avertissements de niveau 2 ainsi que tous les autres avertissements recommandés à des fins de production.<br />-   Le niveau 4 affiche tous les avertissements de niveau 3 ainsi que les avertissements d'information.  Nous vous recommandons d'utiliser cette option pour ne fournir que des avertissements pelucheux.  Toutefois, pour un nouveau projet, il est préférable d'utiliser `/W4` dans toutes les compilations ; ceci garantira le minimum possible d'erreurs difficiles à trouver dans le code.|  
|**\/Wall**|Affiche tous les avertissements de \/W4 et tous les autres avertissements qui ne sont pas inclus dans \/W4 \(par exemple, les avertissements qui sont désactivés par défaut\).  Consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).|  
|**\/WX**|Considère tous les avertissements du compilateur comme des erreurs.  Pour un nouveau projet, il est préférable d'utiliser **\/WX** dans toutes les compilations ; la résolution de tous les avertissements garantira le minimum possible d'erreurs difficiles à trouver dans le code.<br /><br /> L'éditeur de liens a également une option **\/WX**.  Pour plus d'informations, consultez [\/WX \(Traiter les avertissements de l'Éditeur de liens comme des erreurs\)](../../build/reference/wx-treat-linker-warnings-as-errors.md).|  
|**\/w** `ln`|Spécifie le niveau d'un avertissement particulier.  Le premier paramètre définit le niveau d'avertissement \(identique à **\/W**`n`\) et le deuxième paramètre désigne le numéro effectif de l'avertissement.<br /><br /> Par exemple, `/w14326` fait apparaître C4326 comme un avertissement de niveau 1.|  
|**\/wd** `n`|Désactive l'avertissement du compilateur spécifié dans `n`.<br /><br /> Par exemple, `/wd4326` désactive l'avertissement du compilateur C4326.|  
|**\/we** `n`|Traite l'avertissement du compilateur spécifié dans `n` comme une erreur.<br /><br /> Par exemple, `/we4326` fait apparaître l'avertissement C4326 en tant qu'erreur.|  
|**\/wo** `n`|Ne signale qu'une seule fois l'erreur pour l'avertissement du compilateur spécifié dans `n`.<br /><br /> Par exemple, `/wo4326` provoque un seul signalement de l'avertissement C4326.|  
  
 Si vous créez un en\-tête précompilé \([\/Yc \(Créer un fichier d'en\-tête précompilé\)](../../build/reference/yc-create-precompiled-header-file.md)\) à l'aide d'une des options **\/w**, toute utilisation de l'en\-tête précompilé \([\/Yu \(Utiliser un fichier d'en\-tête précompilé\)](../../build/reference/yu-use-precompiled-header-file.md)\) provoque la remise en vigueur de ces mêmes options **\/w** .  Passez outre le paramètre **\/w** dans l'en\-tête précompilé à l'aide d'une autre option **\/w** dans la ligne de commande.  
  
 Les directives pragma contenues dans le code source ne sont pas affectées par l'option **\/w**  
  
 Utilisez également [warning](../../preprocessor/warning.md) pour contrôler le niveau de l'avertissement signalé au moment de la compilation.  
  
 La [documentation d'erreurs de construction](../../error-messages/compiler-errors-1/c-cpp-build-errors.md) décrit les avertissements et les niveaux d'avertissement, et montre pourquoi certaines instructions peuvent ne pas être compilées comme vous le souhaitez.  
  
### Pour définir l'option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Sélectionnez **C\/C\+\+**.  
  
3.  Sur la page de propriétés **Général** modifiez les propriétés du **Niveau d'avertissement** ou du **Traitement des avertissements comme des erreurs** .  
  
4.  Sur la page de propriétés **Avancé** modifiez la propriété **Désactivation des avertissements spécifiques** .  
  
5.  Pour les options restantes, sur la page de propriétés **Ligne de commande** spécifiez l'option du compilateur dans la zone **Options supplémentaires** .  
  
### Pour définir l'option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarningLevel%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarnAsError%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableSpecificWarnings%2A> et <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)