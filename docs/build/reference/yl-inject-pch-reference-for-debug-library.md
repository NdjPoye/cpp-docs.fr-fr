---
title: "-Yl (injecter une référence PCH pour une bibliothèque de débogage) | Documents Microsoft"
ms.custom: 
ms.date: 12/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /yl
dev_langs: C++
helpviewer_keywords:
- -Yl compiler option [C++]
- Yl compiler option [C++]
- /Yl compiler option [C++]
ms.assetid: 8e4a396a-6790-4a9f-8387-df015a3220e7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6e777977f6d869d2bbc28d980f6445851e54396b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="yl-inject-pch-reference-for-debug-library"></a>/Yl (Injecter une référence PCH pour une bibliothèque de débogage)

Le **/Yl** option crée un symbole standard pour un fichier d’en-tête précompilé et injecte des références à ce symbole dans tous les fichiers qui utilisent l’en-tête précompilé. Les informations de type complète pour les symboles d’en-têtes précompilés sont ainsi disponibles pour le débogueur dans tous les fichiers qui utilisent l’en-tête précompilé. Cette option est activée par défaut. Utilisation de cette option peut éviter les erreurs de l’éditeur de liens due à l’absence d’informations de débogage dans les bibliothèques de liens qui utilisent des en-têtes précompilés.

## <a name="syntax"></a>Syntaxe

>**/YL**  
>**/YL**_nom_  
>**/YL-**  

### <a name="arguments"></a>Arguments

*name*  
Nom facultatif utilisé pour définir un symbole pour être stockée et référencé dans l’objet des fichiers qui définissent ou utilisent l’en-tête précompilé.

*\-*  
Un tiret (-) désactive explicitement la **/Yl** option du compilateur.

## <a name="remarks"></a>Notes

Le **/Yl** option active le débogueur obtenir des informations complètes sur les types dans un en-tête précompilé dans chaque fichier qui inclut l’en-tête précompilé. Cette option crée un nom de symbole interne, injecte la définition du symbole dans le fichier de l’objet utilisé pour créer l’en-tête précompilé par le [/Yc](../../build/reference/yc-create-precompiled-header-file.md) option et injecte une référence au symbole dans tous les fichiers qui incluent le précompilés en-tête à l’aide de la [/Yu](../../build/reference/yu-use-precompiled-header-file.md) option du compilateur. Étant donné que tous les fichiers sources qui utilisent l’en-tête précompilé font référence au symbole nommé, l’éditeur de liens lie toujours le fichier de l’objet qui définit le symbole et l’en-tête précompilé associé, les informations de débogage. Cette option est activée par défaut.

Le **/Yl**_nom_ option permet de créer explicitement le symbole d’identification pour le fichier d’en-tête précompilé. Le compilateur utilise le *nom* pour créer un symbole comme argument \_ \_ @@ \_PchSym\_@00@... @*nom* , où la chaîne de caractères de points de suspension (...) représente un éditeur de liens généré. Si l’argument est omis, le compilateur génère automatiquement un nom de symbole.

**/YL-** désactive le comportement par défaut et n’impose pas une référence d’identification symbole dans les fichiers d’objets qui incluent l’en-tête précompilé. Cette option peut être nécessaire pour les fichiers compilés sans le présent fichier d’en-tête précompilé.

Si vous utilisez **/Yl-**, **/Yc** et [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md) options pour générer une bibliothèque, le compilateur crée un fichier d’en-tête précompilé qui contient des informations de débogage qui sont stockées dans un fichier objet plutôt qu’un fichier .pdb. [LNK1211](../../error-messages/tool-errors/linker-tools-error-lnk1211.md) erreurs ou [LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md) avertissements peuvent se produire dans les builds qui utilisent cette bibliothèque et de l’en-tête précompilé, si le fichier source utilisé pour créer l’en-tête précompilé ne définit pas de symboles. L’éditeur de liens peut exclure ce fichier d’objet de bibliothèque à partir du lien, ainsi que les informations de débogage d’en-tête précompilé associé, lorsque rien dans le fichier objet est référencé dans le client de bibliothèque. Pour résoudre le problème, spécifiez **/Yl** lorsque vous utilisez **/Yc** pour créer un fichier d’en-tête précompilé et **/Yu** à le faire. Cela garantit que le fichier de l’objet qui contient les informations de débogage est inclus dans votre build.

Pour plus d’informations sur les en-têtes précompilés, consultez :

- [/Y (En-têtes précompilés)](../../build/reference/y-precompiled-headers.md)

- [Création de fichiers d’en-tête précompilé](../../build/reference/creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio

1. Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).

1. Choisissez le **ligne de commande** page de propriétés dans le **C/C++** dossier.

1. Ajouter le **/Yl**_nom_ option du compilateur dans le **des Options supplémentaires** boîte. Choisissez **OK** pour enregistrer vos modifications.

### <a name="to-set-this-compiler-option-programmatically"></a>Pour définir cette option du compilateur par programmation

- Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Voir aussi

[Options du compilateur](../../build/reference/compiler-options.md)  
[Définition des options du compilateur](../../build/reference/setting-compiler-options.md)  
