---
title: /ALIGN (alignement des sections) | Documents Microsoft
ms.custom: 
ms.date: 12/29/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.Alignment
- /align
dev_langs:
- C++
helpviewer_keywords:
- sections, specifying alignment
- ALIGN linker option
- /ALIGN linker option
- -ALIGN linker option
- section alignment
- sections
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4ca4572e84c7ad32be2d03a312f7bb7d8a3f3f29
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/03/2018
---
# <a name="align-section-alignment"></a>/ALIGN (Alignement des sections)

## <a name="syntax"></a>Syntaxe

> **/ALIGN**[**:**_nombre_]

### <a name="arguments"></a>Arguments

*nombre*  
La valeur d’alignement en octets.

## <a name="remarks"></a>Notes

Le **/ALIGN** option spécifie l’alignement de chaque section dans l’espace d’adressage linéaire du programme. Le *nombre* argument est exprimée en octets et doit être une puissance de deux. La valeur par défaut est de 4 Ko (4096). L’éditeur de liens émet un avertissement si l’alignement génère une image non valide.

Sauf si vous écrivez une application telle qu’un pilote de périphérique, vous ne devez pas modifier l’alignement.

Il est possible de modifier l’alignement d’une section donnée avec le paramètre d’alignement de la [/SECTION](../../build/reference/section-specify-section-attributes.md) option.

La valeur d’alignement que vous spécifiez ne peut pas être inférieure à l’alignement de section plus grand.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio

1. Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [définition des propriétés de projet Visual C++](../../ide/working-with-project-properties.md).

1. Choisissez le **propriétés de Configuration** > **l’éditeur de liens** > **ligne de commande** page de propriétés.

1. Entrez l’option dans le **des Options supplémentaires** boîte. Choisissez **OK** ou **appliquer** pour appliquer la modification.

### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation

- Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Voir aussi

[Définition des options de l’Éditeur de liens](../../build/reference/setting-linker-options.md)  
[Options de l’éditeur de liens](../../build/reference/linker-options.md)  
