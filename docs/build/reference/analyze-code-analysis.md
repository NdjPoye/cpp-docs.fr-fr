---
title: -analyser (analyse du Code) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.EnablePREfast
- /analyze
- VC.Project.VCCLCompilerTool.PREfastAdditionalOptions
- VC.Project.VCCLCompilerTool.PREfastAdditionalPlugins
dev_langs:
- C++
helpviewer_keywords:
- /analyze compiler option [C++]
- -analyze compiler option [C++]
- analyze compiler option [C++]
ms.assetid: 81da536a-e030-4bd4-be18-383927597d08
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ba76ddd10866e414d9817f628c7a1aec019964de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="analyze-code-analysis"></a>/analyze (analyse de code)
Active l'analyse du code et les options de contrôle.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only]  
```  
  
## <a name="arguments"></a>Arguments  
 /analyze  
 Active l'analyse en mode par défaut. Sortie de l’analyse passe à la **sortie** fenêtre comme d’autres messages d’erreur. Utilisez **/ analyze-** pour désactiver explicitement l’analyse.  
  
 /analyze:WX-  
 Spécification de **/ analyze : WX -** signifie que les avertissements d’analyse du code n’est pas traités comme des erreurs lorsque vous compilez à l’aide de **/WX**. Pour plus d’informations, consultez [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX (Niveau d’avertissement)](../../build/reference/compiler-option-warning-level.md).  
  
 /analyze:log `filename`  
 Les résultats détaillés de l'analyseur sont écrits au format XML dans le fichier spécifié par `filename`.  
  
 /analyze:quiet  
 Désactive la sortie de l’analyseur pour le **sortie** fenêtre.  
  
 /analyze:stacksize `number`  
 Le `number` paramètre qui est utilisé avec cette option spécifie la taille, en octets, du frame de pile pour lequel l’avertissement [C6262](/visualstudio/code-quality/c6262) est généré. Si ce paramètre n'est pas spécifié, la taille du frame de pile est de 16 Ko par défaut.  
  
 /analyze:max_paths `number`  
 Le paramètre `number` utilisé avec cette option spécifie le nombre maximal de chemins de code à analyser. Si ce paramètre n'est pas spécifié, ce nombre est égal à 256 par défaut. Des valeurs supérieures permettent d'effectuer une vérification plus approfondie, mais l'analyse risque de prendre plus de temps.  
  
 /analyze:only  
 En règle générale, le compilateur génère du code et effectue plutôt une vérification de la syntaxe après avoir exécuté l'analyseur. Le **/ analyze : uniquement** option désactive cette étape de génération de code ; cela rend l’analyse plus rapide, mais les erreurs de compilation et les avertissements qui peuvent avoir été détectées par le test de génération de code du compilateur ne sont pas émis. Si le programme n'est pas exempt d'erreurs au moment de la génération du code, les résultats de l'analyse risquent de ne pas être fiables. Par conséquent, nous vous recommandons d'utiliser cette option uniquement si le code réussit l'étape de vérification de la syntaxe de génération du code sans erreurs.  
  
## <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [analyse du Code pour C/C++ Overview](/visualstudio/code-quality/code-analysis-for-c-cpp-overview) et [l’analyse du Code pour les avertissements C/C++](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Développez le **propriétés de Configuration** nœud.  
  
3.  Développez le **l’analyse du Code** nœud.  
  
4.  Sélectionnez la page de propriétés **Général** .  
  
5.  Modifier une ou plusieurs de la **l’analyse du Code** propriétés.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Pour définir cette option du compilateur par programmation  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)