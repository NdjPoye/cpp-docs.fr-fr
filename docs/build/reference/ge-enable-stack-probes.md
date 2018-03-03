---
title: -Ge (activer les tests de pile) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /ge
dev_langs:
- C++
helpviewer_keywords:
- -Ge compiler option [C++]
- enable stack probes
- /Ge compiler option [C++]
- stack, stack probes
- stack probes
- stack checking calls
- Ge compiler option [C++]
ms.assetid: 4b54deae-4e3c-4bfa-95f3-ba23590f7258
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8fef08e817c35858b4fab096e669f62c0ae404c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ge-enable-stack-probes"></a>/Ge (Activer les tests de pile)
Active les tests de pile pour chaque appel de fonction qui requiert un stockage pour les variables locales.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/Ge  
```  
  
## <a name="remarks"></a>Notes  
 Ce mécanisme est utile si vous réécrivez la fonctionnalité de la sonde de pile. Il est recommandé d’utiliser [/Gh (Enable _penter Hook Function)](../../build/reference/gh-enable-penter-hook-function.md) au lieu de la réécriture du test de pile.  
  
 [/GS (control Stack Checking Calls)](../../build/reference/gs-control-stack-checking-calls.md) a le même effet.  
  
 **/GE** est déconseillé ; à compter de Visual Studio 2005, le compilateur génère automatiquement la vérification de la pile. Pour obtenir la liste des options du compilateur déconseillées, consultez **déconseillées et supprimées des Options du compilateur** dans [Options du compilateur classées par catégorie](../../build/reference/compiler-options-listed-by-category.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **C/C++** .  
  
3.  Cliquez sur la page de propriétés **Ligne de commande** .  
  
4.  Tapez l'option de compilateur dans la zone **Options supplémentaires** .  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)