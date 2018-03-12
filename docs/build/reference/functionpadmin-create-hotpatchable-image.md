---
title: "/FUNCTIONPADMIN (création d’Image corrigeable en mémoire) | Documents Microsoft"
ms.custom: 
ms.date: 03/09/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /functionpadmin
dev_langs:
- C++
helpviewer_keywords:
- -FUNCTIONPADMIN linker option
- /FUNCTIONPADMIN linker option
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c941ec7f0e94ba03979c914ddd26b8bd21237369
ms.sourcegitcommit: eb246547c7c9adc7d7ac4083ef09bf6e54dec914
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2018
---
# <a name="functionpadmin-create-hotpatchable-image"></a>/FUNCTIONPADMIN (Création d'une image corrigeable en mémoire)

Prépare une image corrigeable en mémoire.

## <a name="syntax"></a>Syntaxe

> **/FUNCTIONPADMIN**[**:**_espace_]  

### <a name="arguments"></a>Arguments

*space*<br/>
La quantité de remplissage à ajouter au début de chaque fonction en octets. Sur x86 par défaut est 5 octets de remplissage et de x64 par défaut est 6 octets. Une valeur doit être fournie sur d’autres cibles.

## <a name="remarks"></a>Notes

Pour l’éditeur de liens produire une image corrigeable en mémoire, les fichiers .obj doivent avoir été compilés avec [/hotpatch (créer une Image corrigeable en mémoire)](../../build/reference/hotpatch-create-hotpatchable-image.md).

Lorsque vous compilez et liez une image avec un appel unique de cl.exe, **/hotpatch** implique **/functionpadmin**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio

1. Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [définition des propriétés de projet Visual C++](../../ide/working-with-project-properties.md).

1. Sélectionnez le **propriétés de Configuration** > **l’éditeur de liens** > **ligne de commande** page de propriétés.

1. Entrez le **/FUNCTIONPADMIN** option **des Options supplémentaires**. Choisissez **OK** pour enregistrer vos modifications.

### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation

- Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Voir aussi

[Définition des options de l’Éditeur de liens](../../build/reference/setting-linker-options.md)<br/>
[Options de l’éditeur de liens](../../build/reference/linker-options.md)
