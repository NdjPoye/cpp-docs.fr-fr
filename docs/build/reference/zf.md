---
title: "/ZF (génération plus rapide PDB) | Documents Microsoft"
ms.date: 02/22/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /Zf
dev_langs:
- C++
helpviewer_keywords:
- /Zf
- -Zf
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e8817b72e5e6eb7ba808455113104e8fb5000505
ms.sourcegitcommit: d24de38f9da844f824acb9d200a3f263077145fc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2018
---
# <a name="zf-faster-pdb-generation"></a>/ZF (génération PDB plus rapide)

Activer la génération PDB plus rapide dans les builds parallèles en réduisant les appels RPC à mspdbsrv.exe.

## <a name="syntax"></a>Syntaxe

> **/Zf**

## <a name="remarks"></a>Notes

Le **/Zf** option active la prise en charge du compilateur pour la génération plus rapide des fichiers PDB lorsque vous utilisez la [/MP (générer avec plusieurs processus)](mp-build-with-multiple-processes.md) option, ou lorsque le système de génération (par exemple, [MSBuild ](/visualstudio/msbuild/msbuild-reference) ou [CMake](../../ide/cmake-tools-for-visual-cpp.md)) peuvent s’exécuter cl.exe plusieurs processus du compilateur en même temps. Cette option entraîne le compilateur frontal différer la génération de l’index de type pour chaque enregistrement de type dans le fichier PDB jusqu'à la fin de la compilation, puis les demande tous dans un seul appel RPC mspdbsrv.exe, au lieu d’effectuer une demande RPC pour chaque enregistrement. Cela peut considérablement améliorer le débit de la build en réduisant la charge RPC sur le processus de mspdbsrv.exe dans un environnement où plusieurs processus du compilateur cl.exe s’exécutent simultanément.

Étant donné que la **/Zf** option s’applique uniquement à la génération du fichier PDF, il requiert le [/Zi](z7-zi-zi-debug-information-format.md) ou [/Zi](z7-zi-zi-debug-information-format.md) option.

Le **/Zf** option est disponible à compter de Visual Studio 2017 version 15,1 et est désactivée par défaut.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio

1. Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).

1. Sélectionnez le **propriétés de Configuration** > **C/C++** > **ligne de commande** page de propriétés.

1. Modifier la **des Options supplémentaires** propriété à inclure **/Zf** , puis **OK**.

## <a name="see-also"></a>Voir aussi

[Options du compilateur classées par ordre alphabétique](compiler-options-listed-alphabetically.md)  
[/MP (Générer avec plusieurs processus)](mp-build-with-multiple-processes.md)  
