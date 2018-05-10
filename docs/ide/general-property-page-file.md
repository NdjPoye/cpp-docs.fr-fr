---
title: Page de propriétés Général (fichier) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCFileConfiguration.ExcludedFromBuild
- VC.Project.VCFileConfiguration.Tool
dev_langs:
- C++
ms.assetid: 26e3711e-9e7d-4e8d-bc4c-2474538efdad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 523ac16a647116f4d18da7e516adb4f0e6bb7fc4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="general-property-page-file"></a>Général, page de propriétés (Fichier)

Quand un fichier est sélectionné dans **l’Explorateur de solutions**, le **général** page de propriétés sous la **propriétés de Configuration** nœud contient les propriétés suivantes :

**Exclure de la Build**  
Spécifie si le fichier doit être dans la génération de la configuration actuelle.

Pour accéder par programmation à cette propriété, consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCFileConfiguration.ExcludedFromBuild%2A>.

**Outil**  
L’outil qui permet de générer ce fichier. Consultez [spécifiant des outils de génération personnalisée](../ide/specifying-custom-build-tools.md) pour plus d’informations.

Pour accéder par programmation à cette propriété, consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCFileConfiguration.Tool%2A>.

Pour plus d’informations sur l’accès à la **général** page de propriétés sous la **propriétés de Configuration** nœud, consultez [utilisation des propriétés de projet](../ide/working-with-project-properties.md).

Pour les projets non Windows, consultez [référence de Page de propriété Linux C++](../linux/prop-pages-linux.md)<!-- or [C++ Cross Platform Property Page Reference](../linux/prop-pages-linux.md)-->.

## <a name="see-also"></a>Voir aussi

[Pages de propriétés](../ide/property-pages-visual-cpp.md)  