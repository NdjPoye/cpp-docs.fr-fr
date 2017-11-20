---
title: "-Yl (injecter une référence PCH pour une bibliothèque de débogage) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /yi
dev_langs: C++
helpviewer_keywords:
- -Yl compiler option [C++]
- Yl compiler option [C++]
- /Yl compiler option [C++]
ms.assetid: 8e4a396a-6790-4a9f-8387-df015a3220e7
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 271681849d78eb8a6a4032bcbafbcc81b96c9f9b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="yl-inject-pch-reference-for-debug-library"></a>/Yl (Injecter une référence PCH pour une bibliothèque de débogage)
Utilisé si la création d’une bibliothèque de débogage qui utilise des en-têtes précompilés et que la build échoue.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/Ylsymbol  
```  
  
```  
/Yl-  
```  
  
## <a name="arguments"></a>Arguments  
 `symbol`  
 Un symbole arbitraire à stocker dans le module objet.  
  
 \-  
 Un signe moins (-) qui désactive explicitement la **/Yl** option du compilateur.  
  
## <a name="remarks"></a>Remarques  
 Par défaut, le compilateur utilise le **/Yl** option (sans spécifier un *symbole*). Le **/Yl** option active le débogueur obtenir des informations complètes sur les types. **/YL-** désactive le comportement par défaut.  
  
 Lorsque vous compilez un module avec **/Yc** et **/Yl**`symbol`, le compilateur crée un symbole __ @@_PchSym\_@00@... @`symbol`, où les points de suspension (...) représente une chaîne de caractères générée par l’éditeur de liens et le stocke dans le module objet. N’importe quel fichier source que vous compilez avec cet en-tête précompilé fait référence au symbole spécifié, ce qui entraîne l’éditeur de liens à inclure le module objet et ses informations de débogage à partir de la bibliothèque.  
  
 À l’aide de cette option, vous pouvez générer LNK1211. Lorsque vous spécifiez la [/Yc (créer un en-tête précompilé)](../../build/reference/yc-create-precompiled-header-file.md) et [/Z7, / Zi, /ZI (Format des informations de débogage)](../../build/reference/z7-zi-zi-debug-information-format.md) options, le compilateur crée un fichier d’en-tête précompilé qui contient des informations de débogage. Une erreur peut se produire quand vous stockez l’en-tête précompilé dans une bibliothèque, utilisez la bibliothèque pour générer un module objet et le code source ne fait pas référence à une des fonctions que le fichier d’en-tête précompilé définit.  
  
 Pour résoudre le problème, spécifiez **/Yl**`symbol`, où `symbol` est le nom d’un symbole arbitraire dans la bibliothèque, lorsque vous créez un fichier d’en-tête précompilé qui ne contient-elle pas toutes les définitions de fonction. Cette option indique au compilateur de stocker les informations de débogage dans le fichier d’en-tête précompilé.  
  
 Pour plus d’informations sur les en-têtes précompilés, consultez :  
  
-   [/Y (en-têtes précompilés)](../../build/reference/y-precompiled-headers.md)  
  
-   [Création de fichiers d’en-tête précompilé](../../build/reference/creating-precompiled-header-files.md)  
  
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