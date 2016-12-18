---
title: "/analyze (analyse de code) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.EnablePREfast"
  - "/analyze"
  - "VC.Project.VCCLCompilerTool.PREfastAdditionalOptions"
  - "VC.Project.VCCLCompilerTool.PREfastAdditionalPlugins"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/analyze (option du compilateur C++)"
  - "analyze (option du compilateur C++)"
  - "-analyze (option du compilateur C++)"
ms.assetid: 81da536a-e030-4bd4-be18-383927597d08
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /analyze (analyse de code)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Active l'analyse du code et les options de contrôle.  
  
## Syntaxe  
  
```  
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only]  
```  
  
## Arguments  
 \/analyze  
 Active l'analyse en mode par défaut.  La sortie de l'analyse aboutit à la fenêtre **Sortie** comme d'autres messages d'erreur.  Utilisez **\/analyze\-** pour désactiver explicitement l'analyse.  
  
 \/analyze:WX\-  
 La spécification de **\/analyze:WX\-** signifie que les avertissements relatifs à l'analyse du code ne sont pas traités comme des erreurs lorsque vous compilez à l'aide de **\/WX**.  Pour plus d'informations, consultez [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won \(Niveau d'avertissement\)](../../build/reference/compiler-option-warning-level.md).  
  
 \/analyze:log `filename`  
 Les résultats détaillés de l'analyseur sont écrits au format XML dans le fichier spécifié par `filename`.  
  
 \/analyze:quiet  
 Désactive la sortie de l'analyseur dans la fenêtre **Sortie**.  
  
 \/analyze:stacksize `number`  
 Le paramètre `number` utilisé avec cette option spécifie la taille, en octets, du frame de pile pour lequel l'avertissement [C6262](../Topic/C6262.md) est généré.  Si ce paramètre n'est pas spécifié, la taille du frame de pile est de 16 Ko par défaut.  
  
 \/analyze:max\_paths `number`  
 Le paramètre `number` utilisé avec cette option spécifie le nombre maximal de chemins de code à analyser.  Si ce paramètre n'est pas spécifié, ce nombre est égal à 256 par défaut.  Des valeurs supérieures permettent d'effectuer une vérification plus approfondie, mais l'analyse risque de prendre plus de temps.  
  
 \/analyze:only  
 En règle générale, le compilateur génère du code et effectue plutôt une vérification de la syntaxe après avoir exécuté l'analyseur.  L'option **\/analyze:only** désactive cette étape de génération du code, ce qui permet de rendre l'analyse plus rapide. Toutefois, les erreurs et les avertissements de compilation qui peuvent avoir été détectées lors de l'étape de génération du code du compilateur ne sont pas émises.  Si le programme n'est pas exempt d'erreurs au moment de la génération du code, les résultats de l'analyse risquent de ne pas être fiables. Par conséquent, nous vous recommandons d'utiliser cette option uniquement si le code réussit l'étape de vérification de la syntaxe de génération du code sans erreurs.  
  
## Notes  
 Pour plus d'informations, consultez [Vue d'ensemble de l'analyse du code C\/C\+\+](../Topic/Code%20Analysis%20for%20C-C++%20Overview.md) et [Analyse de code pour les avertissements C\/C\+\+](../Topic/Code%20Analysis%20for%20C-C++%20Warnings.md).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Développez le nœud **Propriétés de configuration**.  
  
3.  Développez le nœud **Analyse du code**.  
  
4.  Sélectionnez la page de propriétés **Général**.  
  
5.  Modifiez une ou plusieurs des propriétés dans **Analyse du code**.  
  
### Pour définir cette option du compilateur par programmation  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)