---
title: "-FC (chemin d’accès complet du fichier de Code Source dans les Diagnostics) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.UseFullPaths
- /FC
dev_langs:
- C++
helpviewer_keywords:
- /FC compiler option [C++]
- -FC compiler option [C++]
ms.assetid: 1f11414e-cb42-421b-be68-9d369aab036b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b055b5431d41bc09fbdd2750c01d3efca8f21287
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fc-full-path-of-source-code-file-in-diagnostics"></a>/FC (Chemin d’accès complet du fichier de code source dans les diagnostics)

Indique au compilateur afficher le chemin d’accès complet des fichiers de code source passé au compilateur dans le diagnostic.

## <a name="syntax"></a>Syntaxe

> /FC

## <a name="remarks"></a>Notes

Prenons l’exemple de code suivant :

```cpp
// compiler_option_FC.cpp
int main( ) {
   int i   // C2143
}
```

Sans **/FC**, le texte de diagnostic devrait être semblable à ce texte de diagnostic :

- compiler_option_FC.cpp (5) : erreur C2143 : erreur de syntaxe : manquant ';' avant '}'

Avec **/FC**, le texte de diagnostic devrait être semblable à ce texte de diagnostic :

- c:\test\compiler_option_FC.cpp(5) : erreur C2143 : erreur de syntaxe : manquant ';' avant '}'

**/FC** est également nécessaire si vous souhaitez afficher le chemin d’accès complet d’un nom de fichier lorsque vous utilisez le &#95; &#95; FICHIER &#95; &#95; (macro).  Consultez [Macros prédéfinies](../../preprocessor/predefined-macros.md) pour plus d’informations sur les &#95; &#95; FICHIERS &#95; &#95;.

Le **/FC** option est implicite **/Zi**. Pour plus d’informations sur **/Zi**, consultez [/Z7, / Zi, /ZI (Format des informations de débogage)](../../build/reference/z7-zi-zi-debug-information-format.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio

1. Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).

1. Développez le **propriétés de Configuration** nœud.

1. Développez le **C/C++** nœud.

1. Sélectionnez le **avancé** page de propriétés.

1. Modifier la **utilisez les chemins d’accès complet** propriété.

### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation

- Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UseFullPaths%2A>.

## <a name="see-also"></a>Voir aussi

[Options du compilateur](../../build/reference/compiler-options.md)   
[Définition des options du compilateur](../../build/reference/setting-compiler-options.md)